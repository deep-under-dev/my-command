# /frontend - 프론트엔드 개발 가이드

## Usage
```
/frontend [task_type] "설명"
```

### Task Types
- `component` - 컴포넌트 생성
- `page` - 페이지 생성  
- `hook` - 커스텀 훅 생성
- `style` - 스타일링 작업
- `test` - 테스트 작성
- `refactor` - 리팩토링

## Framework Detection
프로젝트 구조를 분석하여 자동 감지:
- `next.config.*` → Next.js
- `vite.config.*` → Vite (React/Vue)
- `angular.json` → Angular
- `nuxt.config.*` → Nuxt.js

## Component 생성 규칙

### React/Next.js
```typescript
// 컴포넌트 구조
components/
├── ui/           # 재사용 UI (Button, Input, Modal)
├── features/     # 기능별 컴포넌트
├── layouts/      # 레이아웃 컴포넌트
└── pages/        # 페이지 컴포넌트

// 컴포넌트 템플릿
interface Props {
  // props 정의
}

export function ComponentName({ ...props }: Props) {
  // hooks
  // handlers
  // render
}
```

### 네이밍 컨벤션
- 컴포넌트: `PascalCase` (Button.tsx)
- 훅: `camelCase` with `use` prefix (useAuth.ts)
- 유틸: `camelCase` (formatDate.ts)
- 상수: `UPPER_SNAKE_CASE`
- CSS/스타일: `kebab-case` or `camelCase` (CSS Modules)

## State Management 패턴

### 로컬 상태
```typescript
// 단순 상태
const [value, setValue] = useState<Type>(initial);

// 복잡한 상태
const [state, dispatch] = useReducer(reducer, initialState);
```

### 전역 상태
- Zustand (권장 - 심플)
- Jotai (atomic 패턴)
- Redux Toolkit (복잡한 앱)

## 스타일링 가이드

### 우선순위
1. Tailwind CSS (유틸리티 퍼스트)
2. CSS Modules (스코프드)
3. Styled Components (CSS-in-JS)

### Tailwind 패턴
```tsx
// 조건부 클래스
className={cn(
  "base-classes",
  condition && "conditional-classes",
  variant === "primary" && "primary-classes"
)}
```

## 성능 최적화

### 체크리스트
- [ ] React.memo() 적절히 사용
- [ ] useMemo/useCallback 과도한 사용 지양
- [ ] 이미지 최적화 (next/image, lazy loading)
- [ ] 코드 스플리팅 (dynamic import)
- [ ] 번들 사이즈 확인

### 렌더링 최적화
```typescript
// 비싼 계산
const memoizedValue = useMemo(() => expensiveCalc(deps), [deps]);

// 콜백 안정화 (자식 컴포넌트 최적화 시에만)
const memoizedCallback = useCallback(() => {}, [deps]);
```

## 테스트 가이드

### 테스트 구조
```
__tests__/
├── components/
├── hooks/
└── utils/
```

### 테스트 패턴
```typescript
describe('ComponentName', () => {
  it('renders correctly', () => {});
  it('handles user interaction', () => {});
  it('shows error state', () => {});
});
```

## Output Format

```markdown
## Frontend Task: [task_type]

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
[테스트 코드 또는 수동 테스트 방법]
```

## Rules
- 기존 프로젝트 패턴 따르기
- TypeScript 타입 명시
- 접근성(a11y) 고려
- 반응형 디자인 기본
- 에러 바운더리 적용
