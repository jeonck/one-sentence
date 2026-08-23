# CLAUDE.md — Scheduled Post Guidelines

이 파일은 매 세션마다 자동으로 읽힙니다. 스케줄 포스트 작성 시 반드시 아래 지침을 따르세요.

---

## 문장 선택 기준

### ✅ 써야 할 문장 유형 (실용 네이티브 영어)

일상·직장·여행에서 실제로 쓰이는 살아있는 영어를 선택합니다.

| 유형 | 예시 |
|---|---|
| 자주 쓰는 이디엄 | "I'll take a rain check on that." |
| 구동사(phrasal verb) 활용 | "We ran out of time before we could wrap it up." |
| 뉴스/스피치 표현 | "It's not a matter of if, but when." |
| 비즈니스/일상 구어체 | "Let's circle back on this after lunch." |
| 강한 연어(collocation) | "The decision completely slipped my mind." |

**좋은 출처:**
- BBC 6 Minute English 대화문
- TED / TED-Ed 강연 인상적인 한 문장
- 유명 영어 유튜버 스크립트 (English with Lucy, EngVid, Rachel's English 등)
- 실제 드라마·영화 대사 (Friends, The Office, Modern Family 등)
- 유명인 인터뷰·연설 (Steve Jobs, Obama, Oprah 등)

### ❌ 쓰지 말아야 할 문장 유형

- 19세기 이전 고전 문학 (Austen, Dickens, Fitzgerald 등 문어체)
- 현대 영어에서 잘 쓰이지 않는 고어체 표현
- 비유가 과도해 실용성이 낮은 시적 문장

---

## 중복 방지 (필수)

포스트 생성 **전에** 반드시 아래 명령으로 기존 문장을 확인하세요.

```bash
grep -r "^> \"" content/posts/ | grep -i "확인할_키워드"
```

또는 전체 기존 문장 목록 조회:

```bash
grep -h "^> \"" content/posts/2026-*.md | grep -v "/" | sort -u
```

**기존 문장 또는 같은 주제어가 이미 있으면 반드시 다른 문장으로 교체합니다.**

---

## 태그 기준

| 태그 자리 | 내용 |
|---|---|
| 1번째 | 출처 키워드 (예: `"BBC"`, `"TED"`, `"Friends"`, `"Jobs"`) |
| 2번째 | 장르 (예: `"idiom"`, `"speech"`, `"conversation"`, `"drama"`) |
| 3번째 | 난이도 (`"beginner"` / `"intermediate"` / `"advanced"`) |

---

## 포스트 형식 (변경 없음)

`WRITING_GUIDE.md` 의 볼드·날짜·파일명 규칙을 그대로 따릅니다.
