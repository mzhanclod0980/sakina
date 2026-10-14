# Quran source — text, translation and tafsir

Never quote an ayah's Arabic text or translation from memory. Take it from one of these sources, in this order.

## 1. Bundled files (first choice — work offline, including in the regular Claude app)

The skill ships verified, unmodified texts from QuranEnc.com for 147 ayahs — every ayah named in `themes.md`, `family-dawah.md`, `safety.md` and `opening-up.md`, plus widely used ayahs of comfort.

- `references/ayahs/<lang>.md` — Arabic text + translation of the meanings. Languages: `ru` Russian, `kk` Kazakh, `en` English, `tr` Turkish, `uz` Uzbek, `ky` Kyrgyz, `tg` Tajik, `az` Azerbaijani, `id` Indonesian, `fr` French, `de` German, `ur` Urdu, `bn` Bengali, `fa` Persian.
- `references/tafsir/<lang>.md` — Al-Mukhtasar short tafsir: `ru`, `en`, `tr`, `uz`, `ky`, `az`, `id`, `fr`, `bn`, `fa`, `ar` (Arabic, with the Arabic text — use for Arabic speakers). For a language without its own tafsir file, read the tafsir in `ru` or `en` and explain it in the person's language.

The files are large: **search, don't read them whole.** Each ayah starts with a line `## <sura>:<aya>`, e.g. `grep -A3 "^## 94:5$" references/ayahs/kk.md` (tafsir: `grep -A2 "^## 94:5$" references/tafsir/ru.md`). Copy the text exactly as it is.

Prefer an ayah from the bundled set — then the text is guaranteed. If the right ayah isn't in it, use the API below.

## 2. API (QuranEnc, King Fahd Complex translations — free, no key)

In the regular Claude app, network access is often switched off; if the call fails, go to step 3.

```
https://quranenc.com/api/v1/translation/aya/<key>/<sura>/<aya>
```

The response contains `result.arabic_text` (Uthmani Arabic) and `result.translation`. One call gives you both. An empty response (`""`) means the key does not exist — try the fallback.

How to call it, depending on the environment:
- With a shell: `curl -s https://quranenc.com/api/v1/translation/aya/russian_rwwad/94/5`
- From a script (Python etc.): the server returns **403 for default library User-Agents** — send a browser-like header, e.g. `User-Agent: Mozilla/5.0`. curl works as is.
- With a web-fetch tool: fetch the same URL.


Note: the official list endpoint (`/translations/list`) is incomplete — the keys below work even if they are missing from it.

## Translation key by language

| Language | Translation key | Tafsir key (Al-Mukhtasar, short tafsir) |
|---|---|---|
| Russian | `russian_rwwad` (alt: `russian_aboadel`; Kuliev — see below) | `russian_mokhtasar` |
| Kazakh | `kazakh_altai` (Khalifa Altay) | — use `russian_mokhtasar` |
| English | `english_saheeh` (alt: `english_rwwad`) | `english_mokhtasar` |
| Turkish | `turkish_rwwad` (alt: `turkish_shahin`) | `turkish_mokhtasar` |
| Uzbek | `uzbek_mansour` (alt: `uzbek_sadiq`) | `uzbek_mokhtasar` |
| Kyrgyz | `kyrgyz_hakimov` | `kyrgyz_mokhtasar` |
| Tajik | `tajik_arifi` | — use `russian_mokhtasar` |
| Azerbaijani | `azeri_musayev` | `azeri_mokhtasar` |
| Ukrainian | `ukrainian_yakubovych` | — use `russian_mokhtasar` |
| Uyghur | `uyghur_saleh` | `uyghur_mokhtasar` |
| Persian | `persian_ih` | `persian_mokhtasar` |
| Urdu | `urdu_junagarhi` | — use `english_mokhtasar` |
| Indonesian | `indonesian_affairs` | `indonesian_mokhtasar` |
| Malay | `malay_basumayyah` | — use `indonesian_mokhtasar` |
| French | `french_montada` (alt: `french_hameedullah`) | `french_mokhtasar` |
| German | `german_bubenheim` | — use `english_mokhtasar` |
| Spanish | `spanish_garcia` | `spanish_mokhtasar` |
| Bengali | `bengali_zakaria` | `bengali_mokhtasar` |
| Arabic speakers | no translation needed | `arabic_mokhtasar` |

Other languages: the key pattern is `<language>_<translator>`; the full list of working keys is visible on `https://quranenc.com/en/home` (links of the form `browse/<key>`). If nothing exists for the language, use `english_saheeh` and translate its meaning yourself, marked «my translation of the meaning».

**Kuliev (Russian).** Many Russian speakers know the Kuliev translation best. It is not on QuranEnc; get it from `https://api.alquran.cloud/v1/ayah/<sura>:<aya>/ru.kuliev` (`data.text`). Use it if the person prefers Kuliev.

**Two translations.** If the person is bilingual or asks (e.g. Kazakh + Russian), give both translations under the Arabic.


## 3. No bundled text and no network

Give the meaning as your own paraphrase, clearly marked as such, without Arabic text, and point to `https://quranenc.com/en/browse/<key>/<sura>` so the person can check. Don't present recalled Arabic as verified. Better still: pick a bundled ayah that fits.

## Using the tafsir

Take the Al-Mukhtasar tafsir of the same ayah from `references/tafsir/<lang>.md` (or, outside the bundled set, from the API key `<language>_mokhtasar`, field `translation`). It is a short explanation of the meaning. Build your 2–4 sentences «why this ayah for you» on it, plus the context of revelation only when you are sure of it. Do not paste the tafsir verbatim; connect it to the person's situation.

## Presenting the ayah

```
<Arabic text from arabic_text>

«<translation of the meaning>» — <Sura name> <sura>:<aya>
(<translator name>)

<2–4 sentences: what it means and why it speaks to you>
```

Prefer short ayahs or a short part of an ayah that is complete in meaning — the person should be able to learn it this week. If the key part is a fragment of a long ayah, give just that fragment and say it is part of the ayah.

Before choosing, check the journal (if any) so you don't repeat an ayah already given — unless there is a reason to return to it.
