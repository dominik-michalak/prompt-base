# Analiza danych z Excela przez AI

**Kategoria:** Praca
**Cel:** Szybkie wyciąganie wniosków biznesowych z arkusza danych bez ręcznego budowania tabel przestawnych i wykresów za każdym razem.
**Kiedy używać:** Masz eksport danych (sprzedaż, ankiety, logi, budżet) i potrzebujesz zrozumieć "co się w nich dzieje", zanim zaczniesz budować dashboard albo raport.

## Prompt

```
Jesteś analitykiem danych. Otrzymujesz zestaw danych w formacie tabelarycznym (wklejony niżej jako CSV/tekst
lub opisany strukturalnie: nazwy kolumn + typy + liczba wierszy).

Dane / opis danych:
{dane_lub_opis_kolumn}

Kontekst biznesowy: {kontekst - np. "dane sprzedażowe sieci sklepów za Q1-Q3 2026"}
Pytanie / cel analizy: {konkretne_pytanie}

Wykonaj kolejno:
1. Zdiagnozuj jakość danych: braki, duplikaty, podejrzane wartości odstające, niespójne formaty.
2. Zaproponuj 3-5 sposobów pocięcia danych (grupowania, filtry, okresy), które odpowiedzą na pytanie.
3. Dla najważniejszego cięcia opisz krok po kroku formułę Excela LUB kod (Python/pandas) potrzebny do jego wykonania.
4. Podaj 3 konkretne wnioski biznesowe, które mogę wyciągnąć z takiej analizy, i jedno ryzyko błędnej interpretacji.
5. Zaproponuj typ wykresu najlepiej pokazujący wynik i wyjaśnij dlaczego (nie inny).

Format odpowiedzi: nagłówki numerowane 1-5, bez lania wody, konkretne liczby/nazwy kolumn jeśli je podałem.
```

## Zmienne do dostosowania
- `{dane_lub_opis_kolumn}` — wklej próbkę danych (10-20 wierszy) albo listę kolumn z typami
- `{kontekst}` — branża, źródło danych, okres
- `{konkretne_pytanie}` — np. "który region traci klientów", "gdzie mamy sezonowość"

## Przykład użycia
Input: 15 wierszy sprzedaży (produkt, region, miesiąc, przychód) + pytanie "gdzie spada sprzedaż".
Output: lista braków danych w kolumnie region, propozycja pivotu miesiąc×region, formuła `SUMIFS`, wniosek że spadek dotyczy jednego regionu w Q3, ostrzeżenie że to może być efekt sezonowy a nie trend.

## Wskazówki
- Nie wklejaj całego arkusza — model gubi się przy >100 wierszach, lepiej dać próbkę + pełny opis kolumn.
- Punkt 1 (jakość danych) jest najczęściej pomijany przez ludzi, a to on wyłapuje błędy zanim trafią do raportu.
- Dla dużych zbiorów zamień krok 3 na prośbę o gotowy skrypt pandas zamiast formuł.

## Powiązane prompty
[[../automatyzacja/instrukcja-na-skrypt.md]], [[../dokumentacja/dokumentacja-techniczna.md]]
