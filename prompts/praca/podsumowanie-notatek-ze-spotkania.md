# Podsumowanie notatek ze spotkania → action items

**Kategoria:** Praca
**Cel:** Zamienić chaotyczne notatki (albo transkrypcję) w czytelne podsumowanie z jasnym podziałem decyzji, zadań i otwartych kwestii.
**Kiedy używać:** Po każdym spotkaniu roboczym, standupie, rozmowie z klientem.

## Prompt

```
Poniżej surowe notatki / transkrypcja ze spotkania. Przekształć je w podsumowanie o strukturze:

1. **Kontekst** (1-2 zdania: temat spotkania, uczestnicy jeśli podani)
2. **Decyzje podjęte** (lista, tylko to, co faktycznie ustalono, nie propozycje)
3. **Zadania (action items)** — format: [Kto] - [Co] - [Termin jeśli podany, inaczej "brak terminu"]
4. **Otwarte kwestie / do wyjaśnienia** — pytania, które padły, ale nie mają odpowiedzi
5. **Ryzyka wspomniane w rozmowie** (jeśli były)

Zasady:
- Nie wymyślaj terminów ani osób odpowiedzialnych, jeśli nie padły wprost — napisz "nieprzypisane".
- Pomijaj dygresje niezwiązane z tematem.
- Maksymalna zwięzłość — to ma się dać przeczytać w 30 sekund.

Notatki:
{notatki}
```

## Zmienne do dostosowania
- `{notatki}` — surowy tekst, mogą być nawet nieuporządkowane fragmenty

## Przykład użycia
Input: 40 linijek luźnych notatek ze standupu.
Output: 4 decyzje, 6 action items z osobami, 2 otwarte pytania — gotowe do wklejenia w kanał zespołu.

## Wskazówki
- Zasada "nie wymyślaj" jest kluczowa — bez niej model dopisuje terminy "na wyczucie", co jest niebezpieczne w realnej pracy.
- Dobrze działa jako pierwszy krok automatyzacji: transkrypcja (np. z nagrania) → ten prompt → wysyłka do Slacka.

## Powiązane prompty
[[../automatyzacja/analiza-procesu-do-automatyzacji.md]]
