# 1. Wygląd i Funkcjonowanie Strony Internetowej (UX / UI)

Nowoczesna strona internetowa musi łączyć estetykę z użytecznością. Jej głównym celem jest szybkie dostarczenie użytkownikowi odpowiedzi na jego potrzeby przy minimalnym wysiłku poznawczym (*cognitive load*).

---

## 1.1. Zasady Wyglądu (User Interface – UI)

### Hierarchia wizualna i układ
* **Zasada pierwszeństwa (Above the Fold):** Najważniejsza propozycja wartości (*Value Proposition*) oraz główne wezwanie do działania (*Call to Action – CTA*) muszą być widoczne od razu po załadowaniu strony, bez konieczności przewijania.
* **Wzorce skanowania wzrokiem:** Użytkownicy nie czytają stron słowo po słowie – skanują je wzrokiem według wzorca **F** (dla stron z dużą ilością tekstu) lub **Z** (dla stron typu landing page).
* **Biała przestrzeń (Whitespace / Negative Space):** Odpowiednie odstępy między sekcjami, akapitami i elementami interaktywnymi poprawiają czytelność o ponad 20% i nadają stronie profesjonalny, uporządkowany wygląd (*Calm Interface*).
* **System siatki (Grid System):** Stosowanie spójnej siatki (np. 12-kolumnowej na desktopie, 4-kolumnowej na mobile) oraz stałych jednostek odstępów (np. wielokrotności `4px` lub `8px`).

### Typografia
* **Ograniczona liczba krojów pisma:** Maksymalnie 2 kroje pisma (np. jeden wyrazisty dla nagłówków, drugi wysoce czytelny bezszeryfowy dla tekstu głównego).
* **Czytelność tekstu głównego:**
  * Rozmiar bazowy: minimum `16px` (`1rem`) na urządzeniach mobilnych i `16px–18px` na desktopie.
  * Długość linii tekstu: optymalnie **50–75 znaków** w wierszu (zbyt długie wiersze męczą wzrok).
  * Interlinia (*line-height*): około `1.5` dla tekstu głównego i `1.15–1.3` dla nagłówków.

### Kolorystyka
* **Zasada 60-30-10:**
  * **60%** – kolor dominujący / tło (zazwyczaj neutralny: biel, bardzo jasny szary lub ciemny grafit w trybie Dark Mode).
  * **30%** – kolor wtórny (identyfikacja marki, karty, sekcje wyróżnione).
  * **10%** – kolor akcentowy (przyciski CTA, kluczowe interakcje, powiadomienia).
* **Spójność semantyczna kolorów:** Czerwony zawsze oznacza błąd/usuwanie, zielony – sukces/potwierdzenie, żółty/pomarańczowy – ostrzeżenie, niebieski – informację.
* **Obsługa Dark Mode (`prefers-color-scheme`):** Coraz częściej wymagana adaptacja kolorystyki do preferencji systemowych użytkownika.

---

## 1.2. Zasady Funkcjonowania (User Experience – UX)

### Intuicyjna nawigacja
* **Przewidywalność (Prawo Jakoba):** Użytkownicy spędzają większość czasu na innych stronach, dlatego oczekują, że Twoja strona będzie działać podobnie (logo w lewym górnym rogu prowadzące do strony głównej, główne menu na górze, koszyk/konto w prawym górnym rogu).
* **Zasada 3 kliknięć / niska głębokość nawigacji:** Użytkownik powinien dotrzeć do dowolnej kluczowej informacji w maksymalnie 3 krokach.
* **Wyszukiwarka wewnętrzna:** Niezbędna w serwisach rozbudowanych, blogach i sklepach e-commerce (z obsługą autouzupełniania i tolerancją na literówki).

### Interaktywność i informacja zwrotna (Feedback)
Każdy element interaktywny musi komunikować swój stan:
1. **Default** (stan domyślny)
2. **Hover** (najazd kursorem – na urządzeniach ze wskaźnikiem)
3. **Focus** (wybranie klawiaturą – wyraźny obrys)
4. **Active / Pressed** (moment kliknięcia/dotknięcia)
5. **Disabled** (element nieaktywny – wyszarzony, brak reakcji na klik)
6. **Loading** (stan ładowania – np. spinner na przycisku po wysłaniu formularza, aby zapobiec podwójnemu kliknięciu).

### Projektowanie formularzy
* **Minimalizacja pól:** Pytaj tylko o dane absolutnie niezbędne na danym etapie.
* **Widoczne etykiety (`<label>`):** Nigdy nie zastępuj etykiety samym tekstem pomocniczym (`placeholder`), ponieważ znika on w momencie wpisywania tekstu.
* **Walidacja w czasie rzeczywistym (Inline Validation):** Informuj o błędach od razu po opuszczeniu pola (`onBlur`), wskazując dokładnie, co należy poprawić (np. *"Wpisz adres e-mail zawierający znak @"* zamiast ogólnego *"Błąd w formularzu"*).
* **Odpowiednie typy pól:** Używanie `type="email"`, `type="tel"`, `inputmode="numeric"` oraz atrybutów `autocomplete`, aby przeglądarka i klawiatura ekranowa podpowiadały właściwy układ znaków.

### Wydajność postrzegana i mikrointerakcje
* **Skeleton Screens:** Zamiast pustego ekranu lub kręcącego się kółka na środku strony, stosuj szkieletowe zamienniki treści podczas ładowania danych.
* **Płynne, nienachalne animacje:** Animacje powinny trwać od `150ms` do `300ms` i służyć wyjaśnieniu zmian na ekranie (np. rozwinięcie menu), a nie spowalnianiu użytkownika.
