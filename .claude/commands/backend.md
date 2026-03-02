# /backend - 백엔드 개발 가이드

## Usage
```
/backend [task_type] "설명"
```

### Task Types
- `api` - API 엔드포인트 생성
- `service` - 서비스/비즈니스 로직
- `model` - 데이터 모델/스키마
- `middleware` - 미들웨어 작성
- `test` - 테스트 작성
- `migration` - DB 마이그레이션

## Framework Detection
프로젝트 구조를 분석하여 자동 감지:
- `package.json` + express/fastify/nest → Node.js
- `requirements.txt` / `pyproject.toml` → Python (FastAPI/Django/Flask)
- `go.mod` → Go (Gin/Echo/Fiber)
- `pom.xml` / `build.gradle` → Java (Spring)

## API 설계 원칙

### RESTful 컨벤션
```
GET    /resources          # 목록 조회
GET    /resources/:id      # 단일 조회
POST   /resources          # 생성
PUT    /resources/:id      # 전체 수정
PATCH  /resources/:id      # 부분 수정
DELETE /resources/:id      # 삭제
```

### 응답 형식
```json
// 성공
{
  "success": true,
  "data": { ... },
  "meta": { "page": 1, "total": 100 }
}

// 에러
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid input",
    "details": [...]
  }
}
```

### HTTP 상태 코드
- `200` OK - 성공
- `201` Created - 생성 성공
- `204` No Content - 삭제 성공
- `400` Bad Request - 잘못된 요청
- `401` Unauthorized - 인증 필요
- `403` Forbidden - 권한 없음
- `404` Not Found - 리소스 없음
- `422` Unprocessable Entity - 유효성 검사 실패
- `500` Internal Server Error - 서버 에러

## 아키텍처 패턴

### 레이어드 아키텍처
```
src/
├── controllers/    # HTTP 요청/응답 처리
├── services/       # 비즈니스 로직
├── repositories/   # 데이터 접근
├── models/         # 데이터 모델
├── middlewares/    # 미들웨어
├── utils/          # 유틸리티
└── config/         # 설정
```

### 의존성 방향
```
Controller → Service → Repository → Database
     ↓          ↓           ↓
   DTO        Domain      Entity
```

## 데이터 검증

### 입력 검증 (Node.js - Zod)
```typescript
const CreateUserSchema = z.object({
  email: z.string().email(),
  password: z.string().min(8),
  name: z.string().min(2).max(50),
});
```

### 입력 검증 (Python - Pydantic)
```python
class CreateUser(BaseModel):
    email: EmailStr
    password: str = Field(min_length=8)
    name: str = Field(min_length=2, max_length=50)
```

## 에러 처리

### 커스텀 에러 클래스
```typescript
class AppError extends Error {
  constructor(
    public code: string,
    public message: string,
    public statusCode: number = 400
  ) {
    super(message);
  }
}

// 사용
throw new AppError('USER_NOT_FOUND', 'User not found', 404);
```

### 글로벌 에러 핸들러
```typescript
app.use((err, req, res, next) => {
  const statusCode = err.statusCode || 500;
  res.status(statusCode).json({
    success: false,
    error: {
      code: err.code || 'INTERNAL_ERROR',
      message: err.message,
    }
  });
});
```

## 보안 체크리스트

- [ ] 입력값 검증 및 새니타이징
- [ ] SQL Injection 방지 (파라미터화된 쿼리)
- [ ] XSS 방지 (출력 이스케이프)
- [ ] CSRF 토큰 적용
- [ ] Rate Limiting 설정
- [ ] 인증/인가 미들웨어
- [ ] 민감 정보 로깅 금지
- [ ] CORS 설정

## 데이터베이스 패턴

### 트랜잭션
```typescript
await db.transaction(async (tx) => {
  await tx.insert(users).values(userData);
  await tx.insert(profiles).values(profileData);
});
```

### N+1 문제 방지
```typescript
// Bad: N+1
const users = await db.query.users.findMany();
for (const user of users) {
  user.posts = await db.query.posts.findMany({ where: { userId: user.id } });
}

// Good: Eager loading
const users = await db.query.users.findMany({
  with: { posts: true }
});
```

## 테스트 가이드

### 테스트 구조
```
tests/
├── unit/           # 단위 테스트
├── integration/    # 통합 테스트
└── e2e/            # E2E 테스트
```

### API 테스트 패턴
```typescript
describe('POST /users', () => {
  it('creates a user with valid data', async () => {
    const res = await request(app)
      .post('/users')
      .send({ email: 'test@example.com', password: 'password123' });
    
    expect(res.status).toBe(201);
    expect(res.body.data).toHaveProperty('id');
  });

  it('returns 422 with invalid email', async () => {
    const res = await request(app)
      .post('/users')
      .send({ email: 'invalid', password: 'password123' });
    
    expect(res.status).toBe(422);
  });
});
```

## Output Format

```markdown
## Backend Task: [task_type]

### 분석
- Framework: [detected]
- 관련 파일: [files]
- 기존 패턴: [patterns]

### 구현 계획
1. [ ] Step 1
2. [ ] Step 2

### 코드
[구현 코드]

### 테스트
[테스트 코드]

### API 문서
[OpenAPI/Swagger 스펙 또는 설명]
```

## Rules
- 기존 프로젝트 패턴 따르기
- 입력값 항상 검증
- 에러 처리 명시적으로
- 비즈니스 로직은 서비스 레이어에
- 테스트 작성 필수
