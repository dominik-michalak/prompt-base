# Redagowanie e-maili trudnych/formalnych z kontrolą tonu

**Kategoria:** Praca
**Cel:** Uniknąć dwóch skrajności AI w pisaniu maili: nadmiernej sztywności biurokratycznej i sztucznej poufałości. Dać model narzędzie do pisania w konkretnym, kontrolowanym rejestrze.
**Kiedy używać:** Maile do przełożonych, klientów, sytuacje wymagające dyplomacji (odmowa, eskalacja problemu, przeprosiny).

## Prompt

```
Napisz e-mail w języku {jezyk} o następujących parametrach:

Cel maila: {cel — np. "poinformować o opóźnieniu projektu bez obwiniania zespołu"}
Odbiorca: {kim jest — przełożony / klient / współpracownik}
Rejestr: średni — nie kancelaryjny, nie potocznie-luźny. Bez zwrotów typu "Szanowni Państwo" jeśli to nie jest oficjalne pismo,
ale też bez emotikon i nadmiernej swobody.
Długość: maksymalnie {liczba} zdań w treści właściwej (bez powitania/pożegnania).
Fakty do zawarcia: {lista faktów/punktów}
Czego unikać: {np. "nie składaj obietnic co do nowego terminu", "nie używaj słowa 'niestety' więcej niż raz"}

Podaj 2 warianty: (A) bardziej stonowany/defensywny, (B) bardziej bezpośredni/asertywny.
Po każdym wariancie jedno zdanie: w jakiej sytuacji ten wariant jest lepszym wyborem.
```

## Zmienne do dostosowania
- `{jezyk}`, `{cel}`, `{odbiorca}`, `{liczba}`, `{lista faktów}`, `{czego unikać}`

## Przykład użycia
Input: cel "poinformować klienta o poślizgu terminu o tydzień", odbiorca "klient B2B".
Output: wariant A (stonowany, z podkreśleniem działań naprawczych) i wariant B (krótki, rzeczowy, z nowym terminem na pierwszym miejscu).

## Wskazówki
- Dwa warianty zamiast jednego to najważniejszy trik — pozwala wybrać ton zamiast negocjować go w kolejnych turach.
- Jawne wskazanie rejestru ("średni, nie kancelaryjny") eliminuje najczęstszy problem: domyślną sztywność AI po polsku.

## Powiązane prompty
—
