# Metodologia — jak projektuję prompty w tej bazie

Ten dokument opisuje **powtarzalny sposób myślenia**, którego używam przy tworzeniu każdego promptu
w tym repozytorium. To nie jest zbiór przypadkowych "sztuczek", tylko świadoma metoda — i to właśnie
metoda, a nie pojedyncze prompty, jest tu najważniejszym elementem do pokazania.

## 1. Standardowa struktura każdego promptu

Każdy plik w `prompts/` ma identyczny szkielet:

| Sekcja | Po co istnieje |
|---|---|
| Kategoria / Cel / Kiedy używać | Wyszukiwalność — po przeczytaniu nagłówka wiadomo, czy to jest właściwy prompt do sytuacji, bez czytania całości |
| Prompt | Gotowy do skopiowania szablon z jawnie oznaczonymi zmiennymi `{tak}` |
| Zmienne do dostosowania | Rozbicie promptu na parametry — traktowanie promptu jak funkcji, nie jak jednorazowego zdania |
| Przykład użycia | Dowód, że prompt faktycznie działa, nie tylko wygląda dobrze na papierze |
| Wskazówki | Wiedza "dlaczego" — najważniejsza sekcja do obrony merytorycznej |
| Powiązane prompty | Linkowanie między dokumentami — baza wiedzy ma być grafem, nie listą |

Ten format jest świadomą decyzją inżynierską: **traktuję prompt jak komponent oprogramowania** —
ma interfejs (zmienne wejściowe), udokumentowane zachowanie (przykład) i wiadomo, kiedy go użyć
(kategoria + kiedy używać), zamiast być jednorazowym zdaniem wpisanym do czatu i zapomnianym.

## 2. Zasady, których pilnuję przy każdym prompcie

**a) Rola + kontekst przed instrukcją.**
Każdy prompt najpierw ustawia rolę/kontekst modelu ("Jesteś analitykiem danych...", "Zrób code
review wyłącznie pod kątem...."), zanim poda instrukcję. To redukuje przypadkowość odpowiedzi —
model "wie", z jakiej perspektywy ma odpowiadać, zanim dostanie zadanie.

**b) Jeden wymiar / jeden cel na prompt.**
Widać to np. w `code-review.md` — zamiast "sprawdź kod" proszę o recenzję pod JEDNYM wymiarem na raz
(bezpieczeństwo *albo* wydajność, nie oba naraz). Modele językowe rozmywają uwagę, gdy dostają zbyt
szeroki cel — węższy prompt daje głębszą, trafniejszą odpowiedź niż jeden uniwersalny "sprawdź wszystko".

**c) Ustrukturyzowany format wyjścia.**
Prawie każdy prompt narzuca konkretny format odpowiedzi (numerowane sekcje, tabela, JSON). Dzięki temu
wynik jest przewidywalny i — co ważne przy automatyzacji — **parsowalny przez kod**, a nie tylko czytelny
dla człowieka. To bezpośrednio widać w `pipeline-promptow-chain.md`, gdzie każdy etap pipeline'u ma
jeden jasno zdefiniowany format wyjścia.

**d) Jawne ograniczenia i "czego nie rób".**
Np. w `podsumowanie-notatek-ze-spotkania.md` jest zasada "nie wymyślaj terminów, jeśli nie padły wprost".
To świadome przeciwdziałanie halucynacjom — model językowy domyślnie "chce" wypełnić luki w danych,
więc trzeba mu to wprost zabronić tam, gdzie zmyślenie faktu jest kosztowne.

**e) Przykład jako część dokumentacji, nie dodatek.**
Każdy prompt ma sekcję "Przykład użycia" pokazującą realny input → output. To nie jest ozdobnik —
to sposób na wychwycenie, czy prompt faktycznie robi to, co miał robić, zanim ktoś użyje go "na żywo".

**f) Świadome ograniczanie możliwości modelu, gdy to służy celowi.**
`tutor-sokratejski.md` jest tu najlepszym przykładem — prompt celowo **zabrania** modelowi podawania
gotowej odpowiedzi. To pokazuje zrozumienie, że "więcej możliwości AI" nie zawsze oznacza "lepszy
efekt dla użytkownika" — czasem celem jest samodzielne myślenie człowieka, nie szybkość odpowiedzi.

## 3. Dlaczego katalogowanie ma sens biznesowy (nie tylko osobisty)

Pojedynczy dobry prompt jest wart niewiele, jeśli za tydzień o nim zapomnę albo ktoś inny w zespole
musi wymyślać go od nowa. Wartość powstaje dopiero, gdy:

- prompty są **skategoryzowane** pod realne sytuacje (praca / nauka / dokumentacja / automatyzacja),
  a nie pod technologię czy model, który się zmienia
- każdy prompt jest **sparametryzowany**, więc można go użyć wielokrotnie w różnych kontekstach bez
  przepisywania od zera
- baza jest **linkowana** (`Powiązane prompty`) — bo w praktyce rzadko używa się jednego promptu
  w oderwaniu; częściej to fragment większego przepływu pracy (np. `analiza-procesu-do-automatyzacji.md`
  → `instrukcja-na-skrypt.md`)
- baza jest **wersjonowana w Git** — widać historię zmian, można się cofnąć, można ją forkować i
  dostosować pod inny zespół

To dokładnie odpowiada na potrzebę z oferty pracy: "porządkowanie treści, promptów i use case'ów" —
nie chodzi o posiadanie dużo promptów, tylko o system, który sprawia, że są one odnajdywalne,
wielokrotnego użytku i zrozumiałe dla kogoś innego niż autor.
