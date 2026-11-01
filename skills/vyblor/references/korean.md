# Korean typography and interfaces

Most design advice assumes the Latin alphabet. Hangul is set in square blocks of even weight, has no capitals and no true italics, and its fonts are enormous files. Pages that ignore this look translated, even when the words are native.

## Line breaking

Set this first, on the whole document:

```css
:lang(ko), html[lang="ko"] {
  word-break: keep-all;
  overflow-wrap: anywhere;
}
```

Browsers break Hangul between any two syllables by default, which cuts words in half. `keep-all` breaks between words. `overflow-wrap: anywhere` catches long URLs and emails that would otherwise push the page sideways.

On headings, add `text-wrap: balance`, then read the result. A particle left alone on a last line, or a line ending before a short word, looks careless, so choose breaks by meaning. Use `<br>` for a large phrase only when it is safe at every width, or better, wrap the phrase in an inline-block span so it stays whole.

## Line height and length

- Body text 1.6 to 1.8. Hangul fills its whole square, so settings tuned for Latin at 1.4 feel cramped.
- Headings 1.25 to 1.4. The 1.0 to 1.1 that works for tight Latin display makes Hangul lines collide.
- Line length about 30 to 45 syllables. The Latin 75-character habit reads long and tiring in Korean.

## Letter spacing

- Large Hangul headings often want slight tightening, around -0.01em to -0.03em. Body text wants 0 or very little.
- Positive tracking separates syllables and damages reading. Never use it as a style.
- Small capitals with wide tracking have no Korean equivalent. For a small label, use a slightly heavier weight at normal spacing.

## What Hangul does not have

- **Italics.** No true italic exists. `font-style: italic` gives a machine slant that looks like an error. Emphasise with weight, colour, or a tone of background. Set `font-synthesis: none` so the browser cannot fake it.
- **Capitals.** `text-transform: uppercase` does nothing, so any design that relies on capitals for hierarchy disappears in Korean.
- **Fake bold.** If the font has no 700 file loaded, the browser smears the 400. Load the weights you use.

## Choosing Korean fonts

Pretendard is an excellent text face and also the Korean Inter: used alone it says nothing. Use it for text if you like, and find a voice elsewhere.

| Voice | Candidates |
|---|---|
| Neutral text | Pretendard, SUIT, Wanted Sans, IBM Plex Sans KR, Noto Sans KR |
| Warm, printed, literary | Noto Serif KR, Gowun Batang, Hahmlet, Nanum Myeongjo, Song Myung |
| Soft, hand-held | Gowun Dodum, Jua |
| Heavy, poster, signage | Black Han Sans, Do Hyeon, Gugi |
| Friendly brand-like sans | Gmarket Sans, Paperlogy |

Check each font's current licence before use. Most on this list are under the SIL Open Font License, but do not assume it, especially for a logo or for embedding.

Serif Hangul (명조, 바탕) does what serif Latin does and is underused on Korean web pages, so it is one of the quickest ways to escape the default look. Very thin weights fall apart below about 16 px, so raise the weight or the size.

## Mixing Hangul and Latin

Latin letters inside many Korean fonts are an afterthought: small, wide or oddly shaped. Put a Latin font first in the stack if the page has much English or many numbers, and let Hangul fall through to the next font:

```css
font-family: "Your Latin Face", "Your Korean Face", sans-serif;
```

Compare the sizes, because the Latin may need `size-adjust` in its `@font-face`. Digits in a price or date should come from one font throughout, with `tabular-nums` where they align.

## Performance

A complete Korean font file is several megabytes, because it holds more than 11,000 syllables. Never load one whole.

- Use a dynamic subset (split by `unicode-range`) or, for a display face used on one headline, a subset of just those glyphs.
- Load woff2 with `font-display: swap`, preload only the first subset, and keep it to one or two weights.
- A variable font can replace several weights, but check its size first.

## Copy

- Choose one register and keep it. 해요체 suits most consumer products and feels spoken. 합쇼체 suits banks, law and public services. Mixed within a screen, it reads as machine output.
- Do not write 당신. Koreans rarely address the reader that way. Drop the subject: 지금 시작해 보세요 needs no pronoun.
- Avoid translated marketing phrasing: 새로운 차원의, 혁신적인, 한 단계 더, ~을 경험해 보세요, 여정, 솔루션, 극대화. Say what the thing does.
- Buttons are short and name the action: 저장하기, 예약하기, 구독 시작하기. A vague 확인 is fine only when there is truly nothing else to say.
- Errors say what to do, without apologising: 이메일 주소를 다시 확인해 주세요, rather than 오류가 발생했습니다.

## Local conventions

- Money: `12,000원`, or `₩12,000` in tight spaces. Round large figures the Korean way when writing prose: 1만 2천 명, 3억 원.
- Dates: `2026년 11월 2일` or `2026.11.02`. Days: 월, 화, 수.
- Names: one field for the full name, family name first. Never split into first and last.
- Phones: `010-1234-5678`, with `inputmode="tel"`. Addresses: search by road name through a postal code service rather than free text. Do not ask for 주민등록번호.
- Sign-in and sharing often live inside KakaoTalk. Pages open in its in-app browser, on a phone, so test narrow screens first.
- Do not design cold email, SMS or DM capture into a Korean product without consent. 정보통신망법 article 50 requires prior opt-in for advertising messages.
