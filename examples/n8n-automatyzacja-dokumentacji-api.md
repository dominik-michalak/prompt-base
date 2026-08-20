# Case study: automatyzacja dokumentacji API z commitów (n8n)

Praktyczne wdrożenie promptu [`dokumentacja-api.md`](../prompts/dokumentacja/dokumentacja-api.md) —
zamiast ręcznego wklejania kodu do AI za każdym razem, gdy zmieni się endpoint, workflow robi to
automatycznie po każdym pushu i proponuje gotowy PR z aktualną dokumentacją.

Gotowy do importu plik: [`n8n-automatyzacja-dokumentacji-api.json`](n8n-automatyzacja-dokumentacji-api.json)
(w n8n: **Import from File**).

## Jak to działa (7 węzłów)

```
GitHub Trigger (push)
        │
        ▼
Filtruj: tylko pliki tras/kontrolerów   ← odsiewa nieistotne commity (CSS, README, itp.)
        │
        ▼
Pobierz zawartość pliku (GitHub)        ← aktualny stan pliku po zmianie
        │
        ▼
Wygeneruj dokumentację (AI)             ← dokładnie prompt z prompts/dokumentacja/dokumentacja-api.md
        │
        ▼
Waliduj i sformatuj wynik               ← zabezpieczenie przed zapisaniem halucynacji
        │
        ▼
Zapisz docs/API.md (commit na branch)   ← NIE prosto na main
        │
        ▼
Powiadom zespół (Slack)                 ← human-in-the-loop zamiast cichej automatyzacji
```

## Kluczowe decyzje projektowe (to, o co zapytają na rozmowie)

**1. Filtr plików przed wywołaniem AI, nie po.**
Bez filtra workflow wywoływałby AI przy KAŻDYM pushu — łącznie ze zmianami w plikach niezwiązanych
z API (style, README, testy). To marnowanie wywołań API i ryzyko, że model "udokumentuje" coś, co
nie jest endpointem. Filtr działa na etapie odczytu commitów, zanim jakikolwiek kod trafi do AI —
taniej jest odrzucić nieistotny commit w kodzie niż płacić za analizę przez model.

**2. Węzeł walidacji między AI a zapisem do repozytorium.**
To bezpośrednie zastosowanie zasady z [`docs/METODOLOGIA.md`](../docs/METODOLOGIA.md) — "jawne
ograniczenia i zabezpieczenia tam, gdzie błąd jest kosztowny". Zapisanie halucynacji AI wprost do
dokumentacji repozytorium bez żadnej kontroli byłoby gorsze niż brak automatyzacji. Walidacja tutaj
jest celowo prosta (długość + obecność nagłówków markdown) — w wersji produkcyjnej rozbudowałbym ją
o sprawdzenie, czy w treści są rzeczywiście wymienione metody HTTP z kodu źródłowego.

**3. Commit na osobną gałąź (`docs/auto-api-update`), nie na `main`.**
To świadome ograniczenie automatyzacji — dokładnie to podejście, które opisuję w prompcie
[`analiza-procesu-do-automatyzacji.md`](../prompts/automatyzacja/analiza-procesu-do-automatyzacji.md)
jako "human-in-the-loop zamiast pełnej automatyzacji" dla kroków wymagających oceny człowieka.
Automatyzacja przygotowuje gotowy materiał, ale finalne zatwierdzenie (merge) zostaje przy człowieku.

**4. Powiadomienie w Slacku zamiast cichego commita.**
Automatyzacja, o której nikt nie wie, że działa, jest ryzykowna — ten krok zamyka pętlę informacyjną
i sprawia, że ktoś faktycznie zajrzy i zmerguje zmianę, zamiast żeby leżała niezauważona tygodniami.

## Ograniczenia tego rozwiązania (świadomie, nie przypadkiem)

- Filtr plików bazuje na wzorcu ścieżki (`routes/`, `controllers/`, `api/`) — w projekcie o innej
  konwencji nazewnictwa trzeba by go dostosować; nie jest to rozwiązanie w 100% uniwersalne.
- Workflow dokumentuje **stan pliku po zmianie**, nie sam diff — jeśli commit usuwa endpoint,
  dokumentacja tego expressis verbis nie zaznaczy jako "usunięty", tylko po prostu go nie będzie.
  W wersji rozszerzonej dodałbym porównanie z poprzednią wersją `docs/API.md`.
- Węzeł AI zakłada dostęp do modelu przez API (koszt per wywołanie) — dla bardzo aktywnego
  repozytorium warto by dodać debounce/kolejkowanie, żeby nie wywoływać AI przy każdym z serii
  szybkich commitów.

## Dlaczego to wzmacnia resztę projektu

Baza promptów (`prompts/`) pokazuje, że umiem **zaprojektować** dobry prompt. Ten workflow pokazuje,
że umiem **osadzić go w realnym procesie** z zabezpieczeniami, walidacją i nadzorem człowieka —
czyli różnicę między "prompt engineering jako ciekawostka" a "prompt engineering jako część
działającego systemu".
