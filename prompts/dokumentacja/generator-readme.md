# Generator README.md dla repozytorium GitHub

**Kategoria:** Dokumentacja
**Cel:** Ustandaryzować proces tworzenia README tak, żeby za każdym razem zawierało to, co faktycznie jest potrzebne odbiorcy (rekruterowi, innemu developerowi), a nie przypadkowy zestaw sekcji.
**Kiedy używać:** Nowe repozytorium portfolio, projekt zaliczeniowy do wystawienia na GitHub.

## Prompt

```
Napisz README.md dla repozytorium GitHub na podstawie poniższego opisu projektu.

Opis projektu / stack technologiczny / kod:
{opis}

Cel repozytorium: {np. "projekt portfolio do pokazania na rozmowie kwalifikacyjnej", "projekt zaliczeniowy", "narzędzie do użytku wewnętrznego"}
Grupa docelowa czytelników: {rekruter techniczny / inny developer / wykładowca}

Struktura README:
1. Nagłówek + jedno zdanie "elevator pitch" — co to robi i dla kogo, zanim ktokolwiek przewinie dalej
2. Krótki spis technologii (badge'e lub lista) — z jednym słowem uzasadnienia wyboru kluczowej technologii, jeśli nieoczywisty
3. Instrukcja instalacji/uruchomienia — musi faktycznie działać, zero pominiętych kroków (zmienne środowiskowe, wersje, zależności)
4. Krótki opis architektury / struktury folderów
5. Najważniejsza funkcjonalność pokazana na przykładzie (fragment kodu / komenda / zrzut ekranu jako placeholder)
6. Sekcja "czego się nauczyłem / jakie wyzwania rozwiązałem" — TO jest sekcja, która sprzedaje projekt rekruterowi
7. Status projektu i plany rozwoju (jeśli dotyczy)

Zasady: żadnych pustych fraz marketingowych, konkretne komendy zamiast opisowych zdań tam gdzie to możliwe,
markdown gotowy do wklejenia (nagłówki, bloki kodu, listy).
```

## Zmienne do dostosowania
- `{opis}`, `{cel repozytorium}`, `{grupa docelowa}`

## Przykład użycia
Input: opis projektu Node.js/React platformy studenckiej, cel "portfolio na rozmowę".
Output: README z sekcją "czego się nauczyłem" opisującą konkretny problem architektoniczny (np. synchronizacja stanu real-time) i jak go rozwiązano — dokładnie materiał do rozmowy kwalifikacyjnej.

## Wskazówki
- Sekcja 6 to sekcja, którą większość ludzi pomija, a rekruterzy czytają najuważniej — pokazuje myślenie, nie tylko efekt końcowy.
- Ten sam prompt (z innym `{opis}`) użyłem do zbudowania README tego repozytorium — patrz sekcja "Meta" w głównym README.

## Powiązane prompty
[[dokumentacja-techniczna.md]]
