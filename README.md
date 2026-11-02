# moja-firma

**Otwarte procedury AI dla polskiej małej i średniej firmy.** Jeden zestaw instrukcji w formacie [Agent Skills](https://agentskills.io/specification) (`SKILL.md`), który działa w Claude, ChatGPT i Codex, Microsoft 365 Copilot, Gemini oraz OpenClaw.

Każda procedura **przygotowuje decyzję, a nie ją podejmuje**: nie wysyła wiadomości, nie zmienia rekordów, nie zleca płatności, pokazuje źródło każdej liczby i nazywa brak danych wprost. Procedury są pisane pod polski obieg dokumentów: PLN, biuro rachunkowe, eksport z polskiego programu do faktur zamiast gotowego konektora.

> Wersja 0.1, wczesna. Procedury opierają się na poradnikach z [majchrzycki.com](https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty?utm_source=github&utm_medium=referral&utm_campaign=moja-firma), ale wymagają sprawdzenia na Waszych danych.

## Procedury

| Procedura | Co robi | Poradnik |
|---|---|---|
| [`profil-firmy`](skills/profil-firmy/SKILL.md) | Zbiera profil firmy i granice pracy agenta do pliku `moja-firma.md`, z którego korzystają pozostałe procedury. | [Start w polskiej firmie](https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=profil-firmy) |
| [`kontrola-danych`](skills/kontrola-danych/SKILL.md) | Sprawdza eksport CSV lub XLSX przed analizą i spisuje kontrakt danych. | [Krok 2: kontrakt danych](https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=kontrola-danych) |
| [`naleznosci`](skills/naleznosci/SKILL.md) | Raport należności po terminie na wskazany dzień, z sumą kontrolną i rekordami do sprawdzenia. | [Raport należności](https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=naleznosci) |
| [`przypomnienie-o-platnosci`](skills/przypomnienie-o-platnosci/SKILL.md) | Dwa szkice przypomnienia o płatności na potwierdzonych danych. Nigdy nie wysyła. | [Krok 4: komunikacja](https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=przypomnienie-o-platnosci) |
| [`odprawa-wlasciciela`](skills/odprawa-wlasciciela/SKILL.md) | Jednostronicowa odprawa tygodnia: sprzedaż, wpływy, należności, szanse i trzy decyzje. | [Krok 3: odprawa](https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=odprawa-wlasciciela) |
| [`pakiet-dla-biura-rachunkowego`](skills/pakiet-dla-biura-rachunkowego/SKILL.md) | Spis dokumentów miesiąca, braki, rozbieżności i pytania do księgowej. Bez wyliczania podatków. | [Czego nie lokalizować tłumaczeniem](https://majchrzycki.com/blog/claude-small-business-plugin-skille-dla-polskiego-msp?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=pakiet-dla-biura-rachunkowego) |
| [`plan-integracji`](skills/plan-integracji/SKILL.md) | Plan podłączenia polskiego programu (np. inFakt, wFirma, Fakturownia) na podstawie oficjalnej dokumentacji, do oceny przez informatyka. | [Krok 5: polski program](https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=plan-integracji) |

Zacznij od `profil-firmy`, potem `kontrola-danych` na jednym eksporcie, potem jedna procedura z wynikiem, który da się sprawdzić z programem źródłowym.

## Instalacja

Nazwy menu zmieniają się często. Jeśli wyglądają inaczej, sprawdź aktualną dokumentację narzędzia.

### Claude Code

```text
/plugin marketplace add majchrzycki-com/moja-firma
/plugin install moja-firma@moja-firma
```

Procedury wywołasz jako `/moja-firma:naleznosci` albo zwykłym zdaniem, np. „przygotuj raport należności na koniec miesiąca”.

### Claude w przeglądarce i aplikacji (Cowork)

Spakuj katalog wybranej procedury, np. `skills/naleznosci/`, do pliku ZIP i dodaj go jako umiejętność w ustawieniach Claude. Więcej o pluginach i skillach Claude: [Claude dla firm](https://majchrzycki.com/blog/co-to-jest-claude-poradnik-dla-firm?utm_source=github&utm_medium=referral&utm_campaign=moja-firma).

### ChatGPT i Codex

W Codex skopiuj katalogi z `skills/` do katalogu skilli Codex. W ChatGPT wklej plik z `dist/instrukcje/` do instrukcji projektu albo GPT. Porównanie pluginów Claude, ChatGPT, Codex i Copilot: [pluginy agentów AI](https://majchrzycki.com/blog/pluginy-agentow-claude-chatgpt-codex-copilot?utm_source=github&utm_medium=referral&utm_campaign=moja-firma).

### Microsoft 365 Copilot

W Copilot Cowork: **Dostosuj → Umiejętności → Dodaj** i zaimportuj `SKILL.md`. Opis krok po kroku: [umiejętności SKILL.md w Copilot Cowork](https://majchrzycki.com/blog/microsoft-copilot-cowork-umiejetnosci-skill-md?utm_source=github&utm_medium=referral&utm_campaign=moja-firma). Dla agenta w Agent Builderze wklej plik z `dist/instrukcje/` do pola instrukcji.

### Gemini

Utwórz Gem i wklej plik z `dist/instrukcje/` do instrukcji. Eksporty dodaj jako pliki albo z Dysku. Więcej: [Gemini dla firm](https://majchrzycki.com/blog/co-to-jest-google-gemini-poradnik-dla-firm?utm_source=github&utm_medium=referral&utm_campaign=moja-firma).

### OpenClaw

Skopiuj katalogi z `skills/` do katalogu skilli OpenClaw. Kiedy OpenClaw ma sens w firmie: [OpenClaw w praktyce](https://majchrzycki.com/blog/ai-sdlc-agent-openclaw?utm_source=github&utm_medium=referral&utm_campaign=moja-firma).

## Budowanie paczek

```bash
node scripts/build.mjs
```

Skrypt sprawdza każdy `SKILL.md` (nazwa, opis, zgodność z katalogiem) i tworzy `dist/`:

- `dist/skills/` — procedury bez zmian, dla Claude, Codex, OpenClaw i Copilot Cowork,
- `dist/instrukcje/` — procedura jako jeden tekst do wklejenia w agencie Microsoft 365 Copilot, Gemie lub ChatGPT.

Gotowe paczki są też dołączane do każdego wydania w zakładce Releases.

## Pakiety branżowe

Rdzeń jest wspólny. Procedury dla konkretnej branży trafiają do osobnych repozytoriów, każde z danymi ćwiczeniowymi i wynikiem kontrolnym:

| Repozytorium | Procedura | Poradnik branżowy |
|---|---|---|
| `moja-firma-dystrybucja` | agent zamówień B2B | [Dystrybucja i hurt B2B](https://majchrzycki.com/transformacja-agenci-ai/dystrybucja-hurt-b2b?utm_source=github&utm_medium=referral&utm_campaign=moja-firma#pobierz) |
| `moja-firma-produkcja` | agent zamówień sieci handlowych | [Produkcja seryjna](https://majchrzycki.com/transformacja-agenci-ai/produkcja-seryjna?utm_source=github&utm_medium=referral&utm_campaign=moja-firma#pobierz) |
| `moja-firma-produkcja-uslugowa` | agent zapytań ofertowych | [Firma produkcyjno-usługowa](https://majchrzycki.com/transformacja-agenci-ai/firma-produkcyjno-uslugowa?utm_source=github&utm_medium=referral&utm_campaign=moja-firma#pobierz) |
| `moja-firma-handel` | agent rozliczenia kampanii | [Handel wielokanałowy](https://majchrzycki.com/transformacja-agenci-ai/handel-wielokanalowy?utm_source=github&utm_medium=referral&utm_campaign=moja-firma#pobierz) |
| `moja-firma-logistyka` | agent zleceń transportowych | [Usługi logistyczne](https://majchrzycki.com/transformacja-agenci-ai/uslugi-logistyczne?utm_source=github&utm_medium=referral&utm_campaign=moja-firma#pobierz) |
| `moja-firma-serwis` | agent zgłoszeń serwisowych | [Usługi techniczne i serwisowe](https://majchrzycki.com/transformacja-agenci-ai/uslugi-techniczne-i-serwisowe?utm_source=github&utm_medium=referral&utm_campaign=moja-firma#pobierz) |

Pakiety są w przygotowaniu.

## Bezpieczeństwo

Procedura to instrukcja, którą agent wykona. Zanim ją zainstalujesz, przeczytaj `SKILL.md`. Wersja 0.1 nie zawiera skryptów ani serwerów MCP, tylko tekst. Nie wklejaj do rozmowy haseł, kluczy API ani pełnych danych klientów. Zgłoszenia dotyczące bezpieczeństwa: [SECURITY.md](SECURITY.md).

Procedury nie są poradą podatkową, prawną ani kadrową. Wynik sprawdza osoba, która za niego odpowiada.

## Licencja

Kod (skrypty, manifesty) na licencji [MIT](LICENSE). Treść procedur w katalogu `skills/` na licencji [CC BY 4.0](LICENSE-CONTENT.md): możesz je kopiować i przerabiać, także komercyjnie, z podaniem źródła.

Autor: [Krzysztof Majchrzycki](https://majchrzycki.com/o-mnie?utm_source=github&utm_medium=referral&utm_campaign=moja-firma), wdrożenia AI w polskich firmach.

---

## English

**moja-firma** ("my company") is an open set of AI procedures for Polish small and medium businesses, written in the [Agent Skills](https://agentskills.io/specification) `SKILL.md` format so the same files work in Claude, ChatGPT/Codex, Microsoft 365 Copilot, Gemini and OpenClaw. Procedures are in Polish and follow Polish practice: PLN, external accounting offices, exports from local invoicing software. Every procedure prepares a decision and never sends messages, changes records or makes payments. Code is MIT, procedure texts are CC BY 4.0.
