# My Commands

사장님의 Claude Code 커맨드 & 스킬 모음

## 구조

```
my-command/
├── commands/          # 슬래시 커맨드
│   ├── build.md       # /build - 기능 만들기
│   ├── overview.md    # /overview - 프로젝트 파악
│   ├── deep-review.md # /deep-review - 심층 코드 리뷰
│   ├── plan.md        # /plan - 계획 세우기
│   ├── step.md        # /step - 단계별 실행
│   └── review.md      # /review - 간단 리뷰
├── skills/            # 스킬 (지식/워크플로우)
│   ├── token-optimization/  # 토큰 절약
│   ├── verification/        # 검증 루프
│   └── exploration/         # 탐색 우선
├── rules/             # 규칙
│   └── workflow.md    # 워크플로우 규칙
├── agents/            # 서브에이전트 (예정)
└── .claude/           # Claude 설정
```

## 사용법

### 기본 워크플로우
```
/overview           # 프로젝트 파악
/build "기능 설명"   # 계획 세우기
/clear              # 컨텍스트 정리
/step 1             # 1단계 실행
/clear              # 컨텍스트 정리
/step 2             # 2단계 실행
...
```

### 코드 리뷰
```
/review src/file.ts           # 간단 리뷰
/deep-review src/             # 심층 리뷰
/deep-review --security       # 보안 집중
```

## 설치

Claude Code 프로젝트에서:
```bash
# 커맨드 복사
cp -r commands/* ~/.claude/commands/

# 스킬 복사  
cp -r skills/* ~/.claude/skills/

# 규칙 복사
cp -r rules/* ~/.claude/rules/
```

## 업데이트

도넛맨이 매일 10시에 새로운 커맨드/스킬 확인해서 알려드려요!
