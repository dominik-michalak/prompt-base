# Podsumowanie artykułu naukowego / dokumentacji technicznej pod kątem praktycznego zastosowania

**Kategoria:** Nauka
**Cel:** Wyciągnąć z długiego źródła (paper, dokumentacja biblioteki, długi artykuł) to, co faktycznie da się zastosować, zamiast streszczenia akademickiego, które i tak trzeba by przetłumaczyć na "co to dla mnie znaczy".
**Kiedy używać:** Research przed wyborem technologii, czytanie dokumentacji nowej biblioteki, przegląd literatury pod projekt.

## Prompt

```
Podsumuj poniższy materiał pod kątem praktycznego zastosowania, nie akademickiego streszczenia.

Materiał / link / fragment:
{material}

Mój kontekst: {po co mi to — np. "oceniam czy użyć tej biblioteki w projekcie X", "przygotowuję się do prezentacji na zajęciach"}

Struktura:
1. **Jednym zdaniem**: co to jest / co robi / czego dotyczy.
2. **Kluczowe wnioski** (max 5) — tylko te, które mają znaczenie dla mojego kontekstu, nie pełna lista ustaleń.
3. **Kiedy to zastosować, a kiedy NIE** — konkretne warunki brzegowe, nie ogólnik "zależy od przypadku".
4. **Czego materiał NIE odpowiada / jakie ma ograniczenia** (ważne, żeby nie brać wyników za pewnik poza kontekstem, w którym powstały).
5. **Jedno pytanie**, które warto zadać dalej / sprawdzić samodzielnie, zanim podejmę decyzję na podstawie tego materiału.

Nie cytuj długich fragmentów dosłownie — parafrazuj.
```

## Zmienne do dostosowania
- `{material}`, `{moj_kontekst}`

## Przykład użycia
Input: dokumentacja nowej biblioteki ORM + kontekst "oceniam czy użyć w projekcie z dużą liczbą relacji many-to-many".
Output: jednozdaniowe streszczenie, 4 wnioski praktyczne, jasne "nie używaj przy bardzo dużych zbiorach bez indeksów X", ograniczenie "dokumentacja nie testowała pod obciążeniem", pytanie kontrolne o wsparcie dla konkretnej relacji.

## Wskazówki
- Punkt 4 (czego materiał nie odpowiada) chroni przed częstym błędem: traktowaniem wyników z jednego kontekstu jako uniwersalnej prawdy.
- Warto zawsze podawać własny kontekst (`{moj_kontekst}`) — bez niego streszczenie jest ogólne i trzeba i tak samemu filtrować, co istotne.

## Powiązane prompty
[[wyjasnienie-koncepcji.md]], [[plan-nauki.md]]
