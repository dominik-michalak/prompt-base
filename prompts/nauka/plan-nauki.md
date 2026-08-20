# Plan nauki nowej technologii pod konkretny cel i deadline

**Kategoria:** Nauka
**Cel:** Zamienić ogólne "muszę się nauczyć X" w konkretny, sprawdzalny plan z priorytetami — zamiast uczenia się wszystkiego po kolei z dokumentacji.
**Kiedy używać:** Nowa technologia w projekcie/pracy, przygotowanie do certyfikacji, nauka pod konkretną rozmowę kwalifikacyjną.

## Prompt

```
Stwórz plan nauki technologii: {technologia}

Mój cel: {cel — np. "umieć zbudować prosty projekt end-to-end", "zdać rozmowę techniczną na poziomie X", "zdać certyfikat Y"}
Mój obecny poziom: {poziom}
Dostępny czas: {liczba godzin/tygodni}
Mam już doświadczenie w: {powiązane technologie}

Zaprojektuj plan:
1. Podziel materiał na 20% rzeczy, które dają 80% praktycznej wartości pod mój cel (zasada Pareto) — wypisz je jako priorytet 1.
2. Resztę materiału podziel na "przydatne, ale nie krytyczne" i "pomiń, chyba że zostanie czas".
3. Rozpisz plan na etapy z jednym konkretnym, sprawdzalnym rezultatem na każdy etap (np. "zbudowany mini-projekt X", nie "przeczytany rozdział Y").
4. Wskaż 2-3 najczęstsze błędy/pułapki początkujących w tej technologii, żebym mógł ich świadomie unikać.
5. Zaproponuj sposób sprawdzenia, czy faktycznie jestem gotowy pod mój cel (nie "poczucie", tylko konkretne kryterium).
```

## Zmienne do dostosowania
- `{technologia}`, `{cel}`, `{poziom}`, `{liczba godzin/tygodni}`, `{powiązane technologie}`

## Przykład użycia
Input: technologia "Docker", cel "rozmowa kwalifikacyjna na stanowisko z DevOps w tle", czas "10 godzin".
Output: priorytet 1 = obrazy/kontenery/Dockerfile/docker-compose; priorytet 2 = multi-stage builds, sieci; pominięte = Docker Swarm; plan na 4 etapy z mini-projektem na końcu; lista typowych błędów (np. mylenie CMD z ENTRYPOINT).

## Wskazówki
- Krok 1 (Pareto) jest tym, co odróżnia ten prompt od standardowego "zrób mi plan nauki" — bez niego AI zwykle daje spis treści podręcznika, a nie priorytety.
- Krok 5 wymusza konkretne kryterium sukcesu, co jest szczególnie ważne przy nauce pod deadline (np. rozmowę kwalifikacyjną).

## Powiązane prompty
[[wyjasnienie-koncepcji.md]]
