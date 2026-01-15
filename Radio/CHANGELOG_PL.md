Zmiany wprowadzone (podsumowanie po polsku)

Data: 2026-01-13

1. Naprawa wyświetlania bitrate:
   - Dodano mechanizm fallback — jeśli przy powrocie do trybu WEB nie ma otrzymanego zdarzenia bitrate, wyświetlacz spróbuje pobrać bieżącą wartość z silnika audio.

2. Zachowanie przy przełączaniu źródeł:
   - Przy przejściu z trybu RADIO (PM_WEB) na inne źródło player jest natychmiast zatrzymywany (żeby nie leciał w tle).
   - Po powrocie do trybu RADIO odtwarzanie nie jest automatycznie uruchamiane — pokazujemy placeholder "yoRadio".

3. Interfejs użytkownika (UX):
   - Gdy wracasz do radia i player jest zatrzymany, pasek stacji pokazuje "yoRadio", a pola artysty i utworu są czyszczone.
   - Po naciśnięciu enkodera (start) odtwarzanie rozpoczyna się i wyświetlane są nazwa stacji i metadane.
   - Dodano wymuszone odświeżenie stacji i tytułu po pomyślnym starcie odtwarzania.

4. Inne zmiany kompilacyjne/porządkujące:
   - Zmieniono wywołanie zatrzymania playera na użycie publicznego API (`sendCommand({PR_STOP,0})`) aby uniknąć wywołań prywatnych metod klasy.

Instrukcja testów:
 - Przełącz źródło: radio -> BT/AUX -> radio. Na ekranie powinno być "yoRadio".
 - Naciśnij enkoder, aby uruchomić radio: po chwili powinna się pojawić nazwa stacji i meta.

Jeśli chcesz, mogę dodać tę informację także do `README.md` lub utworzyć tag/release na GitHubie z tym opisem.