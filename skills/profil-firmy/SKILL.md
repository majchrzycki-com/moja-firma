---
name: profil-firmy
description: Zbiera profil polskiej małej lub średniej firmy (branża, waluta, programy, biuro rachunkowe, osoby zatwierdzające, granice pracy agenta) i zapisuje go jako plik moja-firma.md, z którego korzystają pozostałe procedury. Użyj na początku pracy z firmą, gdy ktoś pisze „skonfiguruj”, „zacznijmy”, „opisz moją firmę” albo gdy brakuje kontekstu firmy do innego zadania.
license: MIT
metadata:
  autor: Krzysztof Majchrzycki
  zrodlo: https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty
  wersja: 0.1.0
---

# Profil firmy

Celem jest jeden krótki plik `moja-firma.md`, który opisuje firmę i granice pracy agenta. Każda kolejna procedura zaczyna od jego przeczytania, więc rozmowa nie startuje od zera.

## Jak pracujesz

1. Sprawdź, czy w rozmowie, projekcie albo katalogu roboczym jest już `moja-firma.md`. Jeśli tak, pokaż jego treść i zapytaj tylko o to, co się zmieniło.
2. Zadawaj pytania partiami, najwyżej pięć naraz. Nie pytaj o to, co użytkownik już podał.
3. Zbierz:
   - nazwę skróconą firmy, branżę, liczbę osób i formę współpracy z księgowością (własny dział, biuro rachunkowe, samodzielnie),
   - walutę rozliczeń i to, czy kwoty raportujemy netto czy brutto,
   - programy: faktury i księgowość, magazyn lub ERP, CRM, poczta i kalendarz, arkusze,
   - skąd agent dostaje dane: eksport CSV lub XLSX, konektor, wklejony tekst,
   - definicje trzech pojęć, które w każdej firmie znaczą co innego: „sprzedaż” (zamówienia, faktury czy wpłaty), „należność po terminie” (od którego dnia), „klient aktywny”,
   - kto zatwierdza: płatności, wysyłkę wiadomości do klientów, rabaty i zmiany warunków,
   - czego agentowi nie wolno: domyślnie wysyłać wiadomości, tworzyć i zmieniać dokumentów, zmieniać rekordów w systemach, zlecać przelewów,
   - jedno zadanie na pierwszy tydzień, które dziś ktoś robi ręcznie.
4. Zapisz plik według wzoru poniżej. Gdy nie możesz zapisywać plików, pokaż treść w bloku kodu i poproś, żeby użytkownik zachował ją i dołączał do kolejnych rozmów albo wkleił do instrukcji projektu.
5. Zaproponuj pierwszą procedurę: zwykle `kontrola-danych`, a po niej `naleznosci` albo `odprawa-wlasciciela`.

## Wzór pliku moja-firma.md

```markdown
# Moja firma — profil dla agenta
Aktualizacja: RRRR-MM-DD

## Firma
- Nazwa skrócona:
- Branża i model sprzedaży:
- Liczba osób:
- Księgowość:
- Waluta i sposób raportowania kwot:

## Systemy i źródła danych
| Obszar | Program | Jak agent dostaje dane |
|---|---|---|

## Definicje
- Sprzedaż oznacza:
- Należność po terminie oznacza:
- Klient aktywny oznacza:

## Kto zatwierdza
| Decyzja | Osoba lub rola |
|---|---|

## Granice pracy agenta
- Agent nie wysyła wiadomości, nie tworzy i nie zmienia dokumentów, nie zmienia rekordów, nie zleca płatności.
- Agent pokazuje źródło każdej liczby i nazywa brak danych wprost.

## Pierwsze zadanie
```

## Zasady

- Nie proś o hasła, klucze API, tokeny ani numery rachunków. Jeśli użytkownik je wklei, nie powtarzaj ich i poradź, żeby je unieważnił.
- Nie zapisuj w profilu danych osobowych klientów ani pracowników poza rolą osoby zatwierdzającej.
- Nazwa programu w profilu to kontekst procesu. Nie zakładaj, że istnieje do niego gotowy konektor.
- Pisz po polsku, krótko, bez żargonu.
