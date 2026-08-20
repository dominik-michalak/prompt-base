# Generowanie fiszek (spaced repetition) z materiału źródłowego

**Kategoria:** Nauka
**Cel:** Automatyczne wyciągnięcie z notatek/rozdziału materiału gotowego do wrzucenia do Anki, bez ręcznego formułowania każdego pytania.
**Kiedy używać:** Przygotowanie do egzaminu, nauka nowej technologii, powtórki przed rozmową kwalifikacyjną.

## Prompt

```
Na podstawie poniższego materiału stwórz fiszki do nauki metodą spaced repetition (styl Anki).

Materiał:
{material}

Zasady tworzenia fiszek:
- Jedna fiszka = jeden fakt/koncepcja (zasada atomowości — nie łącz kilku pytań w jedno).
- Pytania testują zrozumienie i zastosowanie, nie tylko przypominanie definicji (min. 30% fiszek typu "co by się stało gdyby...", "kiedy użyć X zamiast Y").
- Unikaj pytań, na które można odpowiedzieć "tak/nie" bez wiedzy.
- Format wyjścia: tabela z kolumnami "Przód" | "Tył" | "Tag" (tag = podkategoria tematu), gotowa do importu CSV.

Wygeneruj {liczba} fiszek.
```

## Zmienne do dostosowania
- `{material}`, `{liczba}`

## Przykład użycia
Input: rozdział o indeksach w bazach danych.
Output: tabela 15 fiszek, część definicyjna ("Co to jest indeks B-tree"), część aplikacyjna ("Kiedy indeks spowolni zapis zamiast przyspieszyć odczyt").

## Wskazówki
- Wymuszenie min. 30% pytań aplikacyjnych to najważniejsza linijka — bez niej model generuje same definicje, które łatwo "wykuć" bez realnego zrozumienia.
- Format CSV/tabela pozwala jednym kliknięciem przenieść wynik do Anki lub Quizletu.

## Powiązane prompty
[[wyjasnienie-koncepcji.md]]
