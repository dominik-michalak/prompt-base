# Dokumentacja API (endpointy) w formacie gotowym do Postman/Swagger-opisu

**Kategoria:** Dokumentacja
**Cel:** Szybko udokumentować endpointy API w spójnym formacie, który da się wkleić do repo albo przenieść do Swaggera/Postmana, zamiast pisać każdy endpoint innym stylem.
**Kiedy używać:** Dokumentowanie własnego backendu, przygotowanie API do udostępnienia zespołowi/portfolio.

## Prompt

```
Udokumentuj poniższe endpointy API w spójnym formacie.

Kod / lista endpointów:
{kod_lub_lista}

Dla każdego endpointu podaj:
- **Metoda i ścieżka**: np. `POST /api/users`
- **Opis**: jedno zdanie, co robi i po co (nie "tworzy użytkownika", tylko np. "rejestruje nowego użytkownika i wysyła e-mail aktywacyjny")
- **Parametry / body**: tabela nazwa | typ | wymagany | opis
- **Przykładowe żądanie**: gotowy JSON
- **Przykładowa odpowiedź (sukces)**: gotowy JSON + kod statusu
- **Możliwe błędy**: lista kodów statusu + kiedy występują (np. 409 gdy e-mail już istnieje)
- **Wymagana autoryzacja**: tak/nie + jaki poziom uprawnień

Na końcu dodaj jedną tabelę zbiorczą ze wszystkimi endpointami (metoda, ścieżka, opis w 3-5 słowach) jako szybki spis treści.
```

## Zmienne do dostosowania
- `{kod_lub_lista}`

## Przykład użycia
Input: 5 endpointów Express.js do zarządzania wydarzeniami.
Output: pełna dokumentacja z tabelami parametrów, przykładowymi JSON-ami i tabelą zbiorczą — gotowa do wklejenia w `docs/API.md`.

## Wskazówki
- Wymuszenie "kiedy występują" przy błędach (a nie tylko listy kodów) to szczegół, który realnie odróżnia dobrą dokumentację API od automatycznie wygenerowanej.
- Tabela zbiorcza na końcu jest tania do wygenerowania, a drastycznie poprawia użyteczność dłuższej dokumentacji.

## Powiązane prompty
[[dokumentacja-techniczna.md]]
