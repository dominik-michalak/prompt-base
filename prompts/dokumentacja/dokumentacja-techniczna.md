# Pisanie czytelnej dokumentacji technicznej z gotowego kodu/projektu

**Kategoria:** Dokumentacja
**Cel:** Uzyskać dokumentację, którą faktycznie ktoś przeczyta — ustrukturyzowaną pod odbiorcę, a nie automatyczny "opis co robi każda linijka".
**Kiedy używać:** Dokumentowanie modułu, API, architektury projektu na studia/pracę/portfolio.

## Prompt

```
Napisz dokumentację techniczną dla poniższego {projektu/modułu/funkcji}.

Kod / opis architektury:
{kod_lub_opis}

Odbiorca dokumentacji: {kto to będzie czytał — np. "nowy developer dołączający do zespołu", "recenzent projektu zaliczeniowego", "użytkownik API"}
Poziom szczegółowości: {ogólny przegląd / szczegółowy opis implementacji}

Struktura dokumentacji:
1. Cel i kontekst — po co ten komponent istnieje, jaki problem rozwiązuje (nie "co robi", tylko "po co")
2. Jak to uruchomić / użyć — minimalny działający przykład
3. Architektura / kluczowe decyzje projektowe — i DLACZEGO takie, a nie inne (to najważniejsza sekcja dla oceny merytorycznej)
4. Ograniczenia i znane problemy — szczerze, nie ukrywaj kompromisów
5. Możliwe rozszerzenia na przyszłość

Zasada: pisz tak, żeby osoba nieznająca projektu po przeczytaniu rozumiała nie tylko "co", ale "dlaczego tak to zrobiono".
Unikaj pustych fraz typu "nowoczesne rozwiązanie", "łatwe w użyciu" bez uzasadnienia.
```

## Zmienne do dostosowania
- `{projektu/modułu/funkcji}`, `{kod_lub_opis}`, `{odbiorca}`, `{poziom szczegółowości}`

## Przykład użycia
Input: opis architektury REST API do zarządzania zadaniami + odbiorca "recenzent projektu zaliczeniowego".
Output: dokument z sekcją "dlaczego wybrano JWT zamiast sesji" zamiast samego "używamy JWT" — dokładnie to, czego szuka osoba oceniająca projekt.

## Wskazówki
- Sekcja 3 (decyzje projektowe + dlaczego) jest tym, co odróżnia dobrą dokumentację od wygenerowanego opisu kodu — i tym, o co najczęściej pytają na obronach/rozmowach.
- Sekcja 4 (ograniczenia) brzmi ryzykownie, ale w praktyce buduje wiarygodność — recenzenci ufają dokumentacji, która przyznaje się do kompromisów.

## Powiązane prompty
[[generator-readme.md]], [[dokumentacja-api.md]]
