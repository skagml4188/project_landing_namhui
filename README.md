# PROJECT_LANDING_NAMHUI
# HODU 고양이 랜딩 페이지

## 1. 프로젝트 개요

본 프로젝트는 **모바일 퍼스트(Mobile First)** 전략을 기반으로 제작한 고양이 랜딩 페이지 과제입니다.

HTML과 CSS의 기본 원칙을 충실히 적용하여, **시맨틱 마크업·레이아웃 구조·유지보수성**을 고려한 페이지 구현을 목표로 하였습니다.

---

## 2. 사용 기술

* **HTML5**

  * 시맨틱 태그(`header`, `main`, `section`, `article`, `footer`) 적극 활용
  * 접근성을 고려한 `aria-label`, `visually-hidden` 패턴 적용

* **CSS3**

  * Flexbox 기반 레이아웃
  * Mobile First 기준 고정 폭 설계
  * 컴포넌트 단위 스타일링

---

## 3. 전체 레이아웃 구조 설명

```text
body
 └─ page-wrapper (개선 제안)
    ├─ header
    ├─ main
    │   ├─ hero section
    │   ├─ content section (cards)
    │   ├─ subscribe section
    │   └─ top button
    └─ footer
```

### 구조 설계 의도

* `body`는 문서 흐름만 담당
* 실제 폭 제어와 정렬은 **wrapper 단위에서 관리**하는 것이 유지보수에 유리
* 모든 주요 콘텐츠는 `main` 내부에 위치

---

## 4. Header 영역 설계 포인트 (dialog 제외)

### 주요 특징

* 로고 + 메뉴 버튼 구조
* `position: fixed`로 상단 고정
* 시각적 요소보다 **네비게이션의 역할**에 집중

### 개선 포인트

* `href="#"` 사용 시 의도치 않은 스크롤 이동 발생 → 실제 목적 URL 명시 필요
* 고정 헤더 사용 시 `top: 0`, `z-index` 명확화 필요

---

## 5. Hero 섹션 설명

### 구성 요소

* 핵심 메시지 제목 (`h2`)
* 설명 텍스트 (`p`)
* CTA 버튼 (`download`)
* 메인 비주얼 이미지

### 설계 의도

* 콘텐츠 중심 정렬
* 이미지와 텍스트를 분리하여 반응형 확장 가능성 확보


## 6. Content Section (Card 구조)

### 카드 설계 방식

* `article.card`를 공통 컴포넌트로 사용
* 카드 내부에 `title / description / image` 패턴 반복

### 장점

* 동일한 구조를 재사용 가능
* 향후 리스트 데이터 기반 렌더링에도 유리

---

## 7. Subscribe 섹션

### 구성

* 제목 및 설명 텍스트
* 이메일 입력 폼

### 접근성 고려

* `label`을 `visually-hidden`로 제공
* `type="email"`, `required` 사용

### 개선 포인트

* 버튼 정렬을 중앙 기준으로 통일하여 모바일 UX 안정화

---

## 8. Top 버튼 (Hover Icon)

### 역할

* 페이지 하단에서 상단 이동을 유도하는 보조 UI

### 구현 범위

* CSS로는 **위치와 형태만 제어 가능**
* 실제 스크롤 이동은 JavaScript 영역

```css
.hover-icon {
  position: fixed;
  right: 16px;
  bottom: 16px;
}
```

---

## 9. CSS 설계 기준 요약

* 콘텐츠 흐름 기반 레이아웃
* 공통 컴포넌트 → 변형 구조
* 전역 선택자 최소화
* 클래스 의미 중심 네이밍

---

## 10. 과제 수행 결과 및 느낀 점

본 과제를 통해 HTML 구조 설계 단계에서 시맨틱 태그의 중요성과, CSS 레이아웃을 콘텐츠 중심으로 구성하는 방식의 필요성을 이해할 수 있었습니다.

특히 `height`와 `max-height`에 의존하지 않고 Flexbox와 자연스러운 문서 흐름을 활용하는 것이 유지보수성과 확장성 측면에서 효과적이라는 점을 학습하였습니다.

본 프로젝트는 이러한 학습 내용을 바탕으로, 기본기에 충실한 구조 설계를 목표로 수행되었습니다.
