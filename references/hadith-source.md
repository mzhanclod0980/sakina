# Hadith source — verified texts only

Never quote a hadith's wording, grade or reference from memory. Take it from the bundled files; if the hadith you want isn't there, convey only its general meaning and say plainly that you are paraphrasing, without a collection number.

## Bundled files

`references/hadith/<lang>.md` — 32 hadiths, each with the reference (sunnah.com numbering), the grade and attribution, the text, and (for HadeethEnc entries) a short explanation. Languages: `ar`, `ru`, `en`, `tr`, `uz`, `ky`, `tg`, `az`, `id`, `fr`, `de`, `ur`, `bn`, `fa`.

- Search, don't read whole files: `sed -n '/^## H:hanzala$/,/^## /p' references/hadith/ru.md`.
- An entry that says «No … translation in this language» → take the `en` (or `ru`) entry and give your own translation of the meaning, marked «my translation of the meaning».
- Kazakh has no verified hadith translation: use `ru`, translate the meaning into Kazakh yourself, marked as such.
- Quote the hadith short: the one sentence of the Prophet ﷺ that matters, not the whole chain or story. Use the `Explanation` line the way you use tafsir for an ayah — to understand it, not to paste it.
- Name the grade only when it isn't sahih (e.g. «hasan — good»). Never present a hasan or weaker hadith as if it were in al-Bukhari or Muslim.

## Keys and when they fit

| Key | Reference | Fits when |
|---|---|---|
| `intention` | al-Bukhari 1; Muslim 1907 | the niyyah line; «does my small step even count?» |
| `no-harm` | Ibn Majah 2341 (hasan) | abuse, harm, «I must endure everything» |
| `never-struck` | Muslim 2328 | domestic violence |
| `tears-ibrahim` | al-Bukhari 1303 | grief; «is crying weak iman?» |
| `thorn` | al-Bukhari 5641–5642 | illness, exhaustion, long pain — «is my suffering for nothing?» |
| `believer-affair` | Muslim 2999 | gratitude and patience; seeing good in a hard time |
| `birds` | at-Tirmidhi 2344 | rizq, work, money anxiety |
| `after-death` | Muslim 1631 | grief with guilt; «I can't do anything for them now» |
| `charity-mother` | al-Bukhari 1388 | charity on behalf of someone who died |
| `sinners-repent` | at-Tirmidhi 2499 (hasan) | guilt; «I keep falling into the same sin» |
| `son-of-adam` | at-Tirmidhi 3540 (hasan) | «Allah won't forgive me» |
| `mercy-100` | al-Bukhari 6000; Muslim 2752 | fear of Allah without hope; harsh image of Allah |
| `mercy-before-anger` | al-Bukhari 3194; Muslim 2751 | «Allah is punishing me» |
| `kissed-confession` | al-Bukhari 526; Muslim 2763 | **shame that blocks opening up**: a man came to the Prophet ﷺ with his sin, and the answer was an ayah of hope (11:114), not exposure |
| `grave-thoughts` | Muslim 132 | intrusive, terrible thoughts about Allah or religion |
| `thoughts-forgiven` | al-Bukhari 2528; Muslim 127 | ashamed of thoughts or feelings; «I'm bad for even thinking this» |
| `covering` | Muslim 2590 | privacy; «will this be held against me?» |
| `nasiha` | Muslim 55 | why honest advice (including «your part») is an act of care |
| `hearts` | Muslim 2564 | self-worth tied to looks, money, grades, status |
| `strong-anger` | al-Bukhari 6114 | anger, shouting |
| `dont-anger` | al-Bukhari 6116 | anger |
| `strong-believer` | Muslim 2664 | «if only I had…», regret, helplessness |
| `capable-regular` | al-Bukhari 6465; Muslim 782 | all-or-nothing in worship; burnout; small steady steps |
| `forgot-prayer` | al-Bukhari 597; Muslim 684 | missed or overslept prayer |
| `slept-journey` | al-Bukhari 344; Muslim 682 | the Prophet ﷺ and companions slept through Fajr — «I'm a hypocrite» |
| `fajr-khaybar` | Muslim 680 | same, the Khaybar journey |
| `hanzala` | Muslim 2750 | «I'm a hypocrite», faith that rises and falls |
| `musa-patience` | al-Bukhari 3150 | hurt by people's words or unfair criticism |
| `worry-dua` | al-Bukhari 6369 | anxiety; a dua to learn |
| `cure` | al-Bukhari 5678 | seeking treatment — doctor or psychologist is Sunnah |
| `asma-mother` | al-Bukhari 2620 | non-Muslim parent; new Muslims |
| `hind-complaint` | al-Bukhari 5364 | «talking about my husband / parent is gheebah»: Hind described her husband's stinginess to the Prophet ﷺ to get help, and he answered her need — speaking in order to get help is not backbiting |

## Outside the bundled set

If the situation truly needs a hadith that isn't here, and you have network access:
- HadeethEnc API (same publisher family as QuranEnc, free, no key): `https://hadeethenc.com/api/v1/hadeeths/one/?language=<lang>&id=<id>`; to find an id, list a category: `https://hadeethenc.com/api/v1/hadeeths/list/?language=en&category_id=<id>&page=1&per_page=100` (categories: `/api/v1/categories/list/?language=en`). Send `User-Agent: Mozilla/5.0` from scripts.
- Sahih al-Bukhari / Sahih Muslim by number: `https://cdn.jsdelivr.net/gh/fawazahmed0/hadith-api@1/editions/eng-bukhari/<n>.json` (Muslim's file numbering differs from the sunnah.com numbering — match on the `arabicnumber` field of `eng-muslim.min.json`).

If you can't verify it, don't cite it — paraphrase and say so.
