# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

**invoice-web** — 인보이스 관리 웹 애플리케이션 (초기 단계)

## 기술 스택

- **Next.js 16.1.6** (App Router, React Server Components)
- **React 19.2.3**
- **TypeScript 5** (strict mode)
- **Tailwind CSS v4** (PostCSS 기반, `@tailwindcss/postcss`)
- **shadcn/ui** (New York 스타일, Lucide 아이콘, Radix UI 기반)
- **ESLint 9** (next/core-web-vitals + typescript)

## 개발 명령어

```bash
npm run dev       # 개발 서버 실행
npm run build     # 프로덕션 빌드
npm run start     # 프로덕션 서버 실행
npm run lint      # ESLint 린트
```

## shadcn/ui 컴포넌트 추가

```bash
npx shadcn@latest add <component-name>
```

## 경로 별칭

| 별칭 | 경로 |
|------|------|
| `@/*` | 프로젝트 루트 (`./`) |
| `@/components/ui` | shadcn/ui 컴포넌트 |
| `@/components` | 커스텀 컴포넌트 |
| `@/lib` | 유틸리티 및 헬퍼 |
| `@/hooks` | 커스텀 훅 |

## 아키텍처 규칙

- **App Router 사용**: 모든 페이지는 `app/` 디렉토리 내에 구성
- **React Server Components 기본**: 클라이언트 컴포넌트는 `"use client"` 명시
- **Tailwind CSS v4 문법**: `globals.css`에서 `@import "tailwindcss"` 사용 (v3의 `@tailwind` 디렉티브 아님)
- **CSS 변수 기반 테마**: OKLch 색상 시스템, Light/Dark 모드 지원 (`globals.css`에 정의)
- **cn() 유틸리티**: `lib/utils.ts`의 `cn()` 함수로 클래스 병합 (`clsx` + `tailwind-merge`)

## 스타일링 규칙

- 반응형 디자인: 모바일 → 태블릿 → 데스크톱 (모바일 퍼스트)
- Tailwind 브레이크포인트: `sm`, `md`, `lg`
- 색상은 CSS 변수 사용 (예: `bg-background`, `text-foreground`, `bg-primary`)
- 애니메이션: 간단한 건 Framer Motion, 복잡한 스크롤 섹션은 GSAP + Lenis

## 코드 컨벤션

- 응답 언어: 한국어
- 코드 주석: 한국어
- 변수명/함수명: 영어
- 컴포넌트 분리 및 재사용 원칙 준수
