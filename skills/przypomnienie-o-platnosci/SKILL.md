---
name: przypomnienie-o-platnosci
description: Szkicuje po polsku uprzejme przypomnienie o płatności dla wskazanej faktury, wyłącznie na potwierdzonych danych, w dwóch wariantach tonu, z listą rzeczy do sprawdzenia przed wysłaniem. Nigdy nie wysyła. Użyj, gdy ktoś prosi o maila do klienta w sprawie zaległej faktury, monit, przypomnienie albo upomnienie płatnicze.
license: CC-BY-4.0
metadata:
  autor: Krzysztof Majchrzycki
  zrodlo: https://majchrzycki.com/blog/claude-small-business-polska-firma-inicjacja-prompty
  wersja: 0.1.0
---

# Przypomnienie o płatności

Szkic ma oszczędzić właścicielowi pisania, ale nie może złożyć w jego imieniu obietnicy ani groźby. Wysyła zawsze człowiek.

## Jak pracujesz

1. Ustal potwierdzone dane: numer faktury, kwota pozostała do zapłaty, waluta, termin płatności, nazwa klienta, osoba kontaktowa po naszej stronie. Źródłem jest raport z procedury `naleznosci`, eksport albo dane podane przez użytkownika. Brakującą daną zostaw w szkicu jako `[nadawca uzupełnia]` i wpisz na listę kontrolną.
2. Jeśli nie znasz historii, zapytaj: czy to pierwsze przypomnienie, czy klient zgłaszał reklamację, czy jest uzgodniony harmonogram spłaty.
3. Przygotuj dwa warianty:
   - **uprzejmy** — pierwsze przypomnienie, zakłada przeoczenie,
   - **stanowczy** — kolejne przypomnienie, prosi o termin wpłaty albo kontakt.
4. Każdy wariant to temat wiadomości, treść do 120 słów i podpis z rolą nadawcy.
5. Przed szkicami pokaż listę kontrolną: adresat, numer i kwota zgodne z dokumentem, faktura nie jest sporna, wpłata nie wpłynęła po dacie eksportu, czy dołączyć kopię faktury.

## Zasady

- Nie wspominaj o odsetkach, rekompensatach, windykacji, sądzie ani rejestrach dłużników, chyba że użytkownik poda to jako ustaloną decyzję firmy. Nawet wtedy nie podawaj stawek ani przepisów z pamięci.
- Nie obiecuj rabatu, rat ani przesunięcia terminu.
- Nie wysyłaj wiadomości. Gdy narzędzie pozwala zapisać szkic, zapisz szkic i powiedz, gdzie jest.
- Jeśli faktura jest sporna, nie pisz przypomnienia. Zaproponuj wiadomość z prośbą o wyjaśnienie dla osoby, która prowadzi sprawę.
- Ton grzeczny i rzeczowy, bez wykrzykników i bez języka urzędowego.
