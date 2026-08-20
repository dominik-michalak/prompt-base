# Projektowanie łańcucha promptów (prompt chaining) dla złożonego zadania

**Kategoria:** Automatyzacja
**Cel:** Rozbić zadanie zbyt złożone na jeden prompt (np. "przeanalizuj i napisz raport") na sekwencję mniejszych, weryfikowalnych kroków — bo pojedynczy długi prompt częściej halucynuje i trudniej go debugować.
**Kiedy używać:** Budowa automatyzacji/aplikacji korzystającej z LLM, gdzie zadanie ma kilka logicznie różnych etapów (ekstrakcja → analiza → generowanie → weryfikacja).

## Prompt

```
Zaprojektuj łańcuch promptów (pipeline) dla następującego złożonego zadania:

Zadanie końcowe: {opis_zadania}
Dane wejściowe: {opis_wejscia}
Ograniczenia: {np. "musi działać bez nadzoru człowieka", "koszt/liczba wywołań API ma znaczenie", "wynik musi być w formacie JSON do dalszego przetwarzania"}

Zaprojektuj:
1. Podziel zadanie na 3-6 etapów, gdzie KAŻDY etap ma jeden jasny cel i JEDEN typ wyjścia (nie mieszaj ekstrakcji z generowaniem w jednym kroku).
2. Dla każdego etapu podaj: cel, format wejścia, format wyjścia (najlepiej ustrukturyzowany, np. JSON), oraz jeden przykładowy prompt.
3. Wskaż, między którymi etapami warto dodać automatyczną walidację (np. sprawdzenie schematu JSON) zanim dane pójdą dalej — i co zrobić gdy walidacja się nie powiedzie.
4. Oceń, który etap jest najbardziej podatny na błędy/halucynacje modelu i zaproponuj zabezpieczenie (np. drugi model weryfikujący, reguła twarda w kodzie zamiast promptu).
5. Porównaj krótko: dlaczego ten podział na etapy jest lepszy niż jeden duży prompt robiący wszystko naraz (w kontekście TEGO konkretnego zadania).
```

## Zmienne do dostosowania
- `{opis_zadania}`, `{opis_wejscia}`, `{ograniczenia}`

## Przykład użycia
Input: zadanie "z opinii klientów o produktach wygeneruj tygodniowy raport trendów", ograniczenie "wynik jako JSON do dashboardu".
Output: pipeline: (1) ekstrakcja sentymentu i kategorii z pojedynczej opinii → JSON, (2) agregacja per kategoria, (3) generowanie narracyjnego podsumowania z agregatu, (4) walidacja schematu przed zapisem do bazy; wskazany etap ryzykowny = ekstrakcja sentymentu przy ironii/sarkazmie.

## Wskazówki
- Zasada "jeden etap = jeden typ wyjścia" jest kluczowa — to ona odróżnia projektowanie pipeline'u od zwykłego "dużego promptu".
- Ten sam sposób myślenia (rozbicie na etapy z jednym typem wyjścia) zastosowałem projektując przepływ danych w moim projekcie GenAI do analizy recenzji produktowych — ekstrakcja cech produktu i sentymentu jako osobne etapy przed agregacją.

## Powiązane prompty
[[analiza-procesu-do-automatyzacji.md]], [[instrukcja-na-skrypt.md]]
