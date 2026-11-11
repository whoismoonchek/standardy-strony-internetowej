# 3. Adaptacja pod Różne Urządzenia (Responsywność / RWD)

Współczesny internet jest przeglądany na setkach różnych rozdzielczości i proporcji ekranu: od małych smartfonów (`320px` szerokości), przez składane telefony (*foldables*), tablety (w orientacji pionowej i poziomej), laptopy, aż po monitory panoramiczne 4K i telewizory Smart TV.

---

## 3.1. Filozofia Mobile-First

* **Projektowanie od najmniejszego ekranu w górę:** Ponad 60–70% ruchu w sieci pochodzi z urządzeń mobilnych, a Google stosuje *Mobile-First Indexing* (ocenia i pozycjonuje stronę na podstawie jej wersji mobilnej).
* **Równorzędność treści (Content Parity):** Wersja mobilna nie może być „okrojoną" wersją strony, z której ukryto istotne informacje za pomocą `display: none`. Może mieć inny układ (np. akordeony lub karty układane jedna pod drugą), ale musi dostarczać pełną wartość merytoryczną.
* **Strefa kciuka (Thumb Zone):** Na smartfonach kluczowe elementy interaktywne (główne CTA, przycisk otwierania menu lub dolny pasek nawigacyjny) powinny znajdować się w łatwym zasięgu kciuka trzymającego telefon jedną ręką.

---

## 3.2. Punkty Przerwania (Breakpoints) i Elastyczne Układy

Zamiast projektować sztywne widoki pod konkretne modele telefonów, stosuje się płynne siatki (*Fluid Grids*) oraz orientacyjne punkty przerwania (`@media`):

| Kategoria urządzenia | Zakres szerokości | Typowy układ |
| :--- | :--- | :--- |
| **Małe smartfony** | `320px – 479px` | 1 kolumna, pełna szerokość przycisków, zoptymalizowane odstępy (`16px` marginesu bocznego). |
| **Duże smartfony / Małe tablety** | `480px – 767px` | 1–2 kolumny dla mniejszych kart, większe zdjęcia. |
| **Tablety / Składane ekrany** | `768px – 1023px` | 2–3 kolumny, przejście z menu mobilnego (hamburger) do pełnego menu lub układu hybrydowego. |
| **Laptopy i standardowe desktopy** | `1024px – 1439px` | Układ wielokolumnowy (np. siatka 12-kolumnowa), pełna nawigacja, efekty `hover`. |
| **Duże monitory / Ultrawide / 4K** | `1440px+` | Ograniczenie maksymalnej szerokości kontenera z treścią (`max-width: 1280px` lub `1440px`) i wyśrodkowanie go, aby wiersze tekstu nie rozciągały się na całą szerokość ekranu. |

---

## 3.3. Nowoczesne Techniki Techniczne RWD

### 1. Meta Viewport
Obowiązkowy znacznik w sekcji `<head>`, bez którego urządzenia mobilne skalują stronę jak widok desktopowy:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
*(Uwaga: Nigdy nie blokuj możliwości przybliżania strony przez użytkownika za pomocą `user-scalable=no` lub `maximum-scale=1.0` – narusza to zasady dostępności WCAG!)*

### 2. CSS Grid, Flexbox i Container Queries
* **Flexbox:** Idealny do układów jednowymiarowych (paski nawigacji, wyrównanie elementów w wierszu lub kolumnie).
* **CSS Grid (`minmax`, `auto-fit`, `auto-fill`):** Pozwala na tworzenie automatycznie łamiących się siatek bez użycia ani jednego zapytania `@media`:
  ```css
  .grid-cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(100%, 280px), 1fr));
    gap: 1.5rem;
  }
  ```
* **Container Queries (`@container`):** Nowoczesny standard pozwalający komponentowi (np. karcie produktu) dostosować swój wygląd do szerokości **kontenera, w którym się znajduje**, a nie tylko całego okna przeglądarki.

### 3. Płynna Typografia i Odstępy (`clamp()`)
Zamiast skokowej zmiany rozmiaru czcionki na punktach przerwania, funkcja `clamp(minimum, wartość-preferowana, maksimum)` płynnie skaluje tekst wraz z szerokością ekranu:
```css
h1 {
  font-size: clamp(1.75rem, 3vw + 1rem, 3.25rem);
}
```

### 4. Adaptacja pod rodzaj wejścia (Dotyk vs. Myszka)
Nie każde duże urządzenie ma myszkę (np. duże iPady) i nie każde małe urządzenie jest wyłącznie dotykowe:
* Wykrywanie możliwości urządzenia w CSS za pomocą `@media (hover: hover) and (pointer: fine)` – efekty najechania myszką (`:hover`) nie powinny blokować dostępu do treści na ekranach dotykowych.
* **Rozmiar obszarów dotykowych (Touch Targets):** Przyciski, ikony i linki na urządzeniach dotykowych muszą mieć odpowiedni rozmiar (minimum `44×44 px` wg iOS/WCAG 2.1 AAA lub `48×48 dp` wg Material Design, a wg WCAG 2.2 AA minimum `24×24 px` wraz z odpowiednim odstępem).

### 5. Responsywne Obrazy i Media
Wysyłanie obrazu o szerokości `2500px` na ekran telefonu to marnowanie transferu i spowolnienie strony:
* Używanie atrybutów `srcset` oraz `sizes` lub znacznika `<picture>`, aby przeglądarka pobrała plik dopasowany do rozdzielczości i gęstości pikseli ekranu (Retina `2x`, `3x`).
* Stosowanie `max-width: 100%; height: auto;` oraz właściwości `aspect-ratio`, aby obrazy i wideo nie rozpychały układu na wąskich ekranach.
* Tabele danych na mobile: umieszczanie szerokich tabel w przewijanym poziomo kontenerze (`overflow-x: auto`) lub przekształcanie wierszy w pionowe karty.
