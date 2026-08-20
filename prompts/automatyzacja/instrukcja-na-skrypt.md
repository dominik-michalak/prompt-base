# Zamiana instrukcji słownej/dokumentu na gotowy skrypt automatyzujący

**Kategoria:** Automatyzacja
**Cel:** Odpowiedź na pytanie "jak można zautomatyzować proces instrukcji" — czyli przejście od opisanej krok-po-kroku procedury do działającego skryptu, zamiast ręcznego powtarzania instrukcji za każdym razem.
**Kiedy używać:** Masz spisaną instrukcję/procedurę (np. w Wordzie, Notion, mailu) wykonywaną cyklicznie przez człowieka.

## Prompt

```
Poniżej instrukcja wykonywana ręcznie przez człowieka. Zamień ją na skrypt automatyzujący.

Instrukcja:
{instrukcja}

Środowisko docelowe: {np. "Python na Windows", "Google Apps Script dla arkusza Google", "Bash na Linuksie"}
Dostępne dane wejściowe: {np. "plik CSV eksportowany co tydzień z systemu X"}

Wykonaj:
1. Przepisz instrukcję jako listę jednoznacznych kroków algorytmicznych — wypisz też ukryte założenia, które człowiek wykonuje "automatycznie" a które trzeba jawnie zakodować (np. "pomiń puste wiersze", "traktuj duże/małe litery jako te same").
2. Napisz działający kod realizujący te kroki.
3. Dodaj obsługę błędów dla najbardziej prawdopodobnych przypadków brzegowych (brakujące dane, zły format, plik nie istnieje).
4. Wskaż, którego kroku NIE da się w pełni zautomatyzować bez ryzyka, i zaproponuj gdzie zostawić potwierdzenie człowieka.
5. Krótka instrukcja uruchomienia skryptu (jak dla osoby nietechnicznej, która przejmie ten proces).
```

## Zmienne do dostosowania
- `{instrukcja}`, `{środowisko docelowe}`, `{dostępne dane wejściowe}`

## Przykład użycia
Input: instrukcja "co tydzień pobierz raport, usuń duplikaty po e-mailu, wyślij podsumowanie mailem do zespołu".
Output: skrypt Python (pandas + smtplib) realizujący te kroki, z obsługą braku pliku i pustego raportu, plus uwaga że decyzję "kogo uznać za duplikat przy różnicach w wielkości liter w domenie" warto zostawić do potwierdzenia.

## Wskazówki
- Krok 1 (ukryte założenia) jest tym, co najczęściej wywala automatyzacje w praktyce — ludzie robią mnóstwo mikro-decyzji "z automatu", których nie zapisują w instrukcji.
- To jest praktyczna odpowiedź na pytanie z oferty pracy "jak zautomatyzować proces instrukcji" — sam ten prompt jest demonstracją podejścia.

## Powiązane prompty
[[analiza-procesu-do-automatyzacji.md]]
