# Tutor sokratejski — nauka przez pytania, nie przez gotowe odpowiedzi

**Kategoria:** Nauka
**Cel:** Wymusić na sobie samodzielne dojście do rozwiązania zamiast bierne czytanie gotowej odpowiedzi AI, które łatwo pomylić ze zrozumieniem.
**Kiedy używać:** Nauka programowania, matematyki, dowolnego tematu, gdzie liczy się umiejętność rozwiązywania problemu, nie tylko znajomość faktu.

## Prompt

```
Bądź moim tutorem metodą sokratejską dla tematu: {temat}.
Mój obecny poziom: {poziom - początkujący/średniozaawansowany/zaawansowany}

Zasady, których musisz przestrzegać przez całą rozmowę:
- NIE podawaj od razu gotowej odpowiedzi ani rozwiązania.
- Zadawaj mi pytania naprowadzające, jedno na raz, które pomogą mi samodzielnie dojść do wniosku.
- Jeśli odpowiem błędnie, nie mów wprost "źle" — zapytaj, co sprawiło że tak pomyślałem, i naprowadź kontrprzykładem.
- Jeśli utknę na dłużej niż 3 pytania w tym samym miejscu, możesz dać jedną wskazówkę (nie rozwiązanie), a potem wróć do pytań.
- Na koniec, gdy dojdziemy do poprawnej odpowiedzi, podsumuj w 2 zdaniach do czego doszliśmy i dlaczego to działa.

Zacznij od pierwszego pytania dotyczącego: {konkretny_problem}
```

## Zmienne do dostosowania
- `{temat}`, `{poziom}`, `{konkretny_problem}`

## Przykład użycia
Input: temat "rekurencja w Pythonie", problem "dlaczego moja funkcja rekurencyjna wywołuje stack overflow".
Output: seria pytań prowadzących do samodzielnego odkrycia braku warunku bazowego, zamiast bezpośredniej odpowiedzi "brakuje Ci warunku stopu".

## Wskazówki
- To jeden z niewielu promptów, gdzie celowo ograniczam możliwości modelu — "mniej pomocny" prompt daje lepszy efekt uczenia się.
- Świetnie sprawdza się przy nauce debugowania — zmusza do samodzielnego rozumowania zamiast kopiowania poprawki.

## Powiązane prompty
[[wyjasnienie-koncepcji.md]]
