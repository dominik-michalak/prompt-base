# Code review pod konkretny cel (nie ogólne "sprawdź kod")

**Kategoria:** Praca
**Cel:** Wymusić na AI recenzję kodu skupioną na jednym wymiarze naraz (bezpieczeństwo / czytelność / wydajność), zamiast ogólnikowej listy "można by tu i tam".
**Kiedy używać:** Przed PR-em, code review, albo gdy przejmujesz cudzy kod i chcesz szybko ocenić ryzyko.

## Prompt

```
Zrób code review poniższego kodu wyłącznie pod kątem: {wymiar_recenzji}.
Nie komentuj innych aspektów, chyba że stanowią realne ryzyko krytyczne.

Język/technologia: {jezyk}
Kontekst: {np. "endpoint API obsługujący płatności", "skrypt jednorazowy do migracji danych"}

Kod:
{kod}

Dla każdego znalezionego problemu podaj:
- Linia/fragment
- Dlaczego to problem (1-2 zdania, konkretnie, nie ogólnikowo)
- Poziom ryzyka: krytyczne / średnie / kosmetyczne
- Poprawiony fragment kodu

Na końcu: jedno zdanie werdyktu — czy mergowałbyś to bez zmian, z poprawkami, czy wymaga przepisania.
```

## Zmienne do dostosowania
- `{wymiar_recenzji}` — np. "bezpieczeństwo (SQL injection, walidacja wejścia, sekrety w kodzie)", "wydajność przy dużych danych", "zgodność z SOLID"
- `{jezyk}`, `{kontekst}`, `{kod}`

## Przykład użycia
Input: fragment endpointu Express.js + "bezpieczeństwo".
Output: wykryty brak walidacji `req.body`, ryzyko krytyczne, poprawka z użyciem `zod`/`joi`; werdykt "wymaga poprawek przed mergem".

## Wskazówki
- Jeden wymiar na raz daje dużo trafniejsze wyniki niż "zrób pełny code review" — AI nie rozprasza się na styl, gdy pytasz o bezpieczeństwo.
- Warto uruchomić ten prompt 2-3 razy z różnymi wymiarami zamiast raz z prośbą o "wszystko".

## Powiązane prompty
[[../dokumentacja/dokumentacja-techniczna.md]]
