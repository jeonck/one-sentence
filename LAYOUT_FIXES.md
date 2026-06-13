# 레이아웃 수정 기록

## 1. 홈 화면 깃헙 아이콘과 첫 포스트 사이 빈 여백 문제

### 증상
홈 화면에서 소셜 아이콘(깃헙 아이콘) 아래와 첫 번째 포스트 카드 사이에 불필요한 빈 공간이 넓게 표시됨.

### 원인
PaperMod 테마의 `post-entry.css`에 두 가지 CSS 규칙이 겹쳐 여백을 만들고 있었음.

```css
/* themes/PaperMod/assets/css/common/post-entry.css */
.first-entry {
    min-height: 320px;                        /* ← 콘텐츠와 무관하게 최소 320px 강제 */
    margin: var(--gap) 0 calc(var(--gap) * 2) 0;  /* ← 하단 마진이 gap의 2배 */
}
```

1. **`min-height: 320px`** — 홈 인포 섹션(제목 + 설명 + 소셜 아이콘)의 실제 높이가 320px보다 짧아도 강제로 320px 공간을 차지하게 만듦
2. **`margin-bottom: calc(var(--gap) * 2)`** — 섹션 아래에 gap의 2배 여백 추가

### 해결
`assets/css/extended/custom.css` 파일을 생성해 두 속성을 덮어씀.

```css
/* assets/css/extended/custom.css */
.first-entry {
    min-height: unset;   /* 강제 최소 높이 제거 → 콘텐츠 높이만큼만 차지 */
    margin-bottom: 0;    /* 하단 마진 제거 */
}
```

### 참고
- PaperMod 테마 파일은 직접 수정하지 않고 `assets/css/extended/` 디렉토리에 커스텀 CSS를 추가하면 자동으로 덮어쓰기됨
- 추후 여백이 너무 없다면 `margin-bottom: 8px` 등 소폭 조정 가능
