# 🗂️ Baza wiedzy z promptami — Prompt Knowledge Base

Uporządkowany, wersjonowany katalog przemyślanych promptów do pracy i nauki. Każdy prompt ma
jasno określony cel, gotowy do skopiowania szablon, sparametryzowane zmienne wejściowe, sprawdzony
przykład działania i wyjaśnienie decyzji projektowych stojących za jego konstrukcją.

To repozytorium powstało jako odpowiedź na prostą obserwację: dobre prompty, które piszę ad hoc
w rozmowach z AI, znikają w historii czatu i za tydzień wymyślam je od nowa. Zamiast tego —
katalogowanie, parametryzacja i wielokrotne użycie.

## Dlaczego to repozytorium istnieje

Nie chodziło mi o zebranie jak największej liczby "ciekawych promptów". Chodziło o zbudowanie
**systemu**, w którym:

- każdy prompt da się użyć wielokrotnie, w różnych sytuacjach, bez przepisywania od zera,
- ktoś inny niż ja (nowy członek zespołu, przyszły ja za pół roku) rozumie prompt bez dopytywania o kontekst,
- widać nie tylko *co* prompt robi, ale *dlaczego* jest skonstruowany akurat tak, a nie inaczej.

Pełne wyjaśnienie zasad projektowania znajduje się w [`docs/METODOLOGIA.md`](docs/METODOLOGIA.md).

## Struktura repozytorium

```
prompt-knowledge-base/
├── README.md                          — ten plik
├── prompts/
│   ├── praca/                         — 4 prompty do codziennej pracy
│   ├── nauka/                         — 5 promptów do nauki i researchu
│   ├── dokumentacja/                  — 3 prompty do pisania dokumentacji
│   └── automatyzacja/                 — 3 prompty do analizy i budowy automatyzacji
├── docs/
│   ├── METODOLOGIA.md                 — zasady projektowania promptów (meta-poziom)
│   └── PRZYGOTOWANIE_DO_ROZMOWY.md    — notatki własne, nieczęść "produktu"
└── examples/                          — miejsce na dodatkowe materiały (zrzuty ekranu, dłuższe case studies)
```

## Katalog promptów

### 💼 Praca
| Prompt | Do czego służy |
|---|---|
| [Analiza danych z Excela przez AI](prompts/praca/analiza-danych-excel.md) | Wyciąganie wniosków biznesowych z arkusza danych — diagnoza jakości danych, propozycje cięć, formuły, wykresy |
| [Code review pod konkretny cel](prompts/praca/code-review.md) | Recenzja kodu skupiona na jednym wymiarze (bezpieczeństwo / wydajność / czytelność) zamiast ogólnikowej |
| [Podsumowanie notatek ze spotkania](prompts/praca/podsumowanie-notatek-ze-spotkania.md) | Chaotyczne notatki → decyzje, action items, otwarte kwestie, bez zmyślania faktów |
| [Redagowanie e-maili z kontrolą tonu](prompts/praca/redagowanie-emaili.md) | Trudne/formalne maile w kontrolowanym, średnim rejestrze — z dwoma wariantami do wyboru |

### 📚 Nauka
| Prompt | Do czego służy |
|---|---|
| [Wyjaśnienie koncepcji na 3 poziomach](prompts/nauka/wyjasnienie-koncepcji.md) | Nowe pojęcie wyjaśnione od analogii po poziom ekspercki, z pytaniem kontrolnym |
| [Generowanie fiszek (spaced repetition)](prompts/nauka/tworzenie-fiszek.md) | Materiał źródłowy → fiszki gotowe do Anki, z naciskiem na pytania aplikacyjne, nie tylko definicje |
| [Tutor sokratejski](prompts/nauka/tutor-sokratejski.md) | Nauka przez pytania naprowadzające — model celowo nie podaje gotowej odpowiedzi |
| [Plan nauki pod cel i deadline](prompts/nauka/plan-nauki.md) | Priorytetyzacja materiału metodą Pareto zamiast uczenia się wszystkiego po kolei |
| [Podsumowanie artykułu/dokumentacji](prompts/nauka/podsumowanie-artykulu.md) | Streszczenie pod kątem praktycznego zastosowania, z jawnymi ograniczeniami źródła |

### 📄 Dokumentacja
| Prompt | Do czego służy |
|---|---|
| [Dokumentacja techniczna projektu](prompts/dokumentacja/dokumentacja-techniczna.md) | Dokumentacja skupiona na "dlaczego tak", nie tylko "co robi kod" |
| [Generator README.md](prompts/dokumentacja/generator-readme.md) | Ustandaryzowany proces tworzenia README pod portfolio/projekt zaliczeniowy |
| [Dokumentacja API](prompts/dokumentacja/dokumentacja-api.md) | Spójna dokumentacja endpointów gotowa do Postman/Swaggera |

### ⚙️ Automatyzacja
| Prompt | Do czego służy |
|---|---|
| [Analiza procesu pod automatyzację](prompts/automatyzacja/analiza-procesu-do-automatyzacji.md) | Systematyczna ocena, którą część powtarzalnego procesu opłaca się zautomatyzować najpierw |
| [Instrukcja → gotowy skrypt](prompts/automatyzacja/instrukcja-na-skrypt.md) | Zamiana spisanej procedury ręcznej na działający skrypt, z ukrytymi założeniami wyciągniętymi na wierzch |
| [Projektowanie łańcucha promptów](prompts/automatyzacja/pipeline-promptow-chain.md) | Rozbicie złożonego zadania LLM na etapy z jednym typem wyjścia na etap, zamiast jednego dużego promptu |

## Jak korzystać z tej bazy

1. Znajdź prompt pasujący do sytuacji w tabeli powyżej.
2. Skopiuj treść z sekcji **Prompt** danego pliku.
3. Podstaw wartości pod zmienne oznaczone `{tak}` — każdy plik wymienia je w sekcji **Zmienne do dostosowania**.
4. Sprawdź sekcję **Wskazówki** — zawiera uwagi, które realnie wpływają na jakość odpowiedzi.

Każdy prompt jest samodzielnym plikiem markdown — można go łatwo przenieść do dowolnego narzędzia
(Notion, wewnętrzna wiki, inny model AI) bez zależności od reszty repozytorium.

## Zasady, którymi się kierowałem (skrót)

- **Jeden cel na prompt** — zamiast uniwersalnego "zrób wszystko", każdy prompt ma wąsko zdefiniowane zadanie.
- **Sparametryzowane wejście** — zmienne zamiast promptu "na sztywno", żeby dało się go użyć wielokrotnie.
- **Jawne ograniczenia tam, gdzie halucynacja jest kosztowna** (np. zakaz zmyślania terminów w podsumowaniu spotkania).
- **Sprawdzony przykład przy każdym prompcie** — żaden prompt nie trafił tu bez realnego testu.
- **Linkowanie między promptami** — baza jest grafem powiązanych narzędzi, nie płaską listą.

Pełne, szczegółowe wyjaśnienie każdej z tych zasad wraz z uzasadnieniem: [`docs/METODOLOGIA.md`](docs/METODOLOGIA.md).

## Automatyzacja w praktyce (n8n)

Jeden z promptów — [`dokumentacja-api.md`](prompts/dokumentacja/dokumentacja-api.md) — nie został
tylko opisany, ale realnie wdrożony jako automatyzacja: workflow n8n generujący dokumentację API
automatycznie po każdym pushu do repozytorium, z walidacją wyniku i zatwierdzeniem przez człowieka
przed mergem. Pełny opis decyzji projektowych i gotowy do importu plik workflow:
[`examples/n8n-automatyzacja-dokumentacji-api.md`](examples/n8n-automatyzacja-dokumentacji-api.md).

## Wersja dla Obsidiana

Repozytorium jest jednocześnie gotowym vaultem Obsidiana — linki `[[tak]]` w sekcjach "Powiązane
prompty" tworzą wizualny graf połączeń między promptami. Punkt startowy po otwarciu folderu jako
vault: [`Indeks - Baza Promptów.md`](Indeks%20-%20Baza%20Promptów.md).

## Status i dalszy rozwój

Baza jest żywym dokumentem — nowy prompt trafia tutaj, gdy zauważam, że po raz trzeci formułuję
to samo zapytanie do AI od nowa. Planowane rozszerzenia: dodanie realnych zrzutów ekranu z działania
wybranych promptów w `examples/`, oraz prompty specyficzne dla narzędzi używanych w konkretnym
środowisku pracy.

---
*Repozytorium prowadzone jako osobista baza wiedzy — swobodnie fork'uj i dostosuj pod własne potrzeby.*
