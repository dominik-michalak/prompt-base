# Wyjaśnienie trudnej koncepcji na 3 poziomach trudności

**Kategoria:** Nauka
**Cel:** Zrozumieć nowe pojęcie technicznie poprawnie, ale bez przeskakiwania od razu w żargon — i mieć punkt odniesienia, żeby sprawdzić, czy naprawdę rozumiem, czy tylko "rozpoznaję słowa".
**Kiedy używać:** Nowy temat na studiach/w pracy, przygotowanie do rozmowy kwalifikacyjnej, nadrabianie zaległości.

## Prompt

```
Wyjaśnij pojęcie: {pojecie}
w kontekście: {dziedzina - np. "programowanie równoległe", "sieci neuronowe", "bazy danych"}

Podaj trzy wyjaśnienia rosnącej trudności:
1. **W 3 zdaniach, jak dla kogoś spoza branży** — analogia z życia codziennego, zero żargonu.
2. **Wyjaśnienie techniczne** — poprawna terminologia, mechanizm działania, dlaczego to działa tak a nie inaczej.
3. **Poziom ekspercki** — ograniczenia, edge case'y, z czym to się myli/porównuje, typowe błędne przekonania (misconceptions).

Na końcu dodaj: "Pytanie kontrolne" — jedno pytanie, które sprawdzi, czy faktycznie rozumiem koncepcję,
a nie tylko potrafię ją powtórzyć (najlepiej pytanie o zastosowanie w nowej sytuacji, nie o definicję).
```

## Zmienne do dostosowania
- `{pojecie}`, `{dziedzina}`

## Przykład użycia
Input: pojęcie "deadlock", dziedzina "programowanie równoległe".
Output: analogia z dwoma osobami blokującymi sobie przejście w wąskim korytarzu → techniczne wyjaśnienie (wzajemne czekanie na zasoby, 4 warunki Coffmana) → poziom ekspercki (różnica względem livelock, strategie detekcji) → pytanie kontrolne każące zaprojektować scenariusz deadlocku w konkretnym systemie.

## Wskazówki
- Poziom 1 wymusza na modelu unikanie żargonu — bez tego AI często "wyjaśnia trudne słowo innym trudnym słowem".
- Pytanie kontrolne jest kluczowe — bez niego łatwo o złudzenie zrozumienia po przeczytaniu ładnego wyjaśnienia.

## Powiązane prompty
[[tutor-sokratejski.md]]
