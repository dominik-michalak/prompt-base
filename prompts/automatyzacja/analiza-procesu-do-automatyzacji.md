# Analiza procesu pod kątem: co da się zautomatyzować

**Kategoria:** Automatyzacja
**Cel:** Systematycznie ocenić powtarzalny proces (ręczny/administracyjny) i wskazać konkretnie, którą jego część opłaca się zautomatyzować najpierw — zamiast ogólnego "zautomatyzuj to AI".
**Kiedy używać:** Masz powtarzalną czynność (raportowanie, obsługa zgłoszeń, wprowadzanie danych) i zastanawiasz się, czy/jak ją zautomatyzować.

## Prompt

```
Przeanalizuj poniższy proces pod kątem automatyzacji.

Opis procesu (kroki, jak wygląda dziś, kto/co go wykonuje):
{opis_procesu}

Częstotliwość wykonywania: {np. "codziennie", "raz w tygodniu"}
Czas trwania obecnie: {np. "30 minut dziennie"}

Wykonaj:
1. Rozbij proces na dyskretne kroki i oznacz każdy jako: (A) w pełni regułowy/przewidywalny, (B) wymaga oceny/decyzji człowieka, (C) wymaga kreatywności/kontekstu, którego AI nie ma.
2. Dla kroków (A) — zaproponuj konkretne narzędzie/podejście do automatyzacji (skrypt, reguła, integracja, no-code).
3. Dla kroków (B) — oceń, czy AI może przygotować "propozycję decyzji" do zatwierdzenia przez człowieka (human-in-the-loop), zamiast pełnej automatyzacji.
4. Policz przybliżony ROI: ile czasu automatyzacja zaoszczędzi w skali miesiąca vs. szacowany czas wdrożenia.
5. Wskaż JEDNO miejsce w procesie, gdzie automatyzacja może się "wysypać" bez nadzoru człowieka (największe ryzyko) i zaproponuj zabezpieczenie.

Bądź konkretny — nie pisz "można to zautomatyzować za pomocą AI", tylko wskaż DOKŁADNIE jaki mechanizm/narzędzie i na jakim kroku.
```

## Zmienne do dostosowania
- `{opis_procesu}`, `{częstotliwość}`, `{czas trwania}`

## Przykład użycia
Input: proces ręcznego przepisywania danych z formularza PDF do arkusza kalkulacyjnego, codziennie 20 minut.
Output: krok ekstrakcji danych oznaczony jako (A) → propozycja OCR + skrypt walidujący; krok "sprawdzenia podejrzanych wartości" jako (B) → propozycja flagowania przez AI do ręcznej akceptacji; ROI ok. 8h/miesiąc; ryzyko: błędne odczyty OCR bez alertu.

## Wskazówki
- Podział A/B/C jest sercem tego prompta — zapobiega typowemu błędowi "zautomatyzujmy wszystko naraz", w tym części wymagające ludzkiego osądu.
- Krok 5 (gdzie się wysypie) wymusza myślenie o ryzyku, co jest tym, o co pyta się na rozmowach o wdrożeniach AI/automatyzacji.

## Powiązane prompty
[[instrukcja-na-skrypt.md]], [[pipeline-promptow-chain.md]]
