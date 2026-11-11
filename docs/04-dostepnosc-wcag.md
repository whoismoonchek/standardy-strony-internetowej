# 4. Dostępność Cyfrowa: WCAG 2.0 (oraz rozszerzenia 2.1 i 2.2)

**WCAG (Web Content Accessibility Guidelines)** to międzynarodowy standard opracowany przez W3C (WAI), który określa, jak tworzyć strony internetowe dostępne dla wszystkich ludzi – w tym osób z niepełnosprawnościami wzroku, słuchu, ruchu oraz z trudnościami poznawczymi i neurologicznymi.

---

## 4.1. Ewolucja Standardu: WCAG 2.0 → 2.1 → 2.2

* **WCAG 2.0 (fundament):** Wprowadził 4 główne zasady (**POUR**), 12 wytycznych i 3 poziomy zgodności (A, AA, AAA). Wszystkie wymogi WCAG 2.0 są w pełni aktualne i obowiązują w nowszych wersjach.
* **WCAG 2.1 (rozszerzenie o mobile i słabowidzących):** Zachowuje całość WCAG 2.0 i dodaje kryteria dotyczące ekranów dotykowych, orientacji ekranu (pion/poziom), kontrastu elementów nietekstowych (ikon, obramowań pól) oraz odstępów w tekście.
* **WCAG 2.2 (najnowszy standard obowiązujący m.in. w ramach Europejskiego Aktu o Dostępności – EAA):** Dodaje kryteria dotyczące widoczności fokusu (brak zasłaniania elementu z fokusem przez przyklejone menu), minimalnego rozmiaru celów dotykowych (`24×24 px`), alternatyw dla gestów przeciągania (*drag-and-drop*) oraz dostępnego uwierzytelniania (logowania bez testów obciążających pamięć i bez blokowania menedżerów haseł).

### Poziomy zgodności:
1. **Poziom A:** Absolutne minimum – jego brak uniemożliwia wielu osobom jakiekolwiek skorzystanie ze strony.
2. **Poziom AA:** **Standard docelowy i wymóg prawny** (w Polsce i UE dla instytucji publicznych oraz wielu sektorów prywatnych, takich jak e-commerce, bankowość i usługi).
3. **Poziom AAA:** Najwyższy poziom dostępności, stosowany w wyspecjalizowanych serwisach (nie zawsze możliwy do wdrożenia dla każdego rodzaju treści).

---

## 4.2. Cztery Filary Dostępności (Zasady POUR)

### 1. Postrzegalność (Perceivable)
Informacje oraz komponenty interfejsu muszą być przedstawione użytkownikowi w sposób, który potrafi on dostrzec swoimi zmysłami.

* **Teksty alternatywne (Kryterium 1.1.1):**
  * Każdy obraz niosący informację musi mieć opisowy atrybut `alt="..."`.
  * Obrazy czysto dekoracyjne muszą mieć pusty atrybut `alt=""` (lub `role="presentation"`), aby czytnik ekranu je pominął i nie czytał nazwy pliku.
* **Multimedia (Kryteria 1.2.x):**
  * Nagrania wideo ze ścieżką dźwiękową wymagają napisów rozszerzonych (*captions*) dla osób niesłyszących oraz audiodeskrypcji (lub transkrypcji tekstowej) dla osób niewidomych.
* **Możliwość adaptacji i struktura (Kryteria 1.3.x):**
  * Treść musi zachować logiczną kolejność czytania nawet po wyłączeniu arkuszy stylów CSS.
  * Instrukcje nie mogą opierać się wyłącznie na cechach zmysłowych, takich jak kształt, rozmiar czy położenie (np. unikaj sformułowań typu *"Kliknij okrągły zielony przycisk po prawej stronie"*).
  * Strona nie może być zablokowana tylko do jednej orientacji ekranu (pionowej lub poziomej).
* **Możliwość rozróżnienia i Kontrast (Kryteria 1.4.x):**
  * **Nie samym kolorem:** Kolor nie może być jedynym sposobem przekazania informacji (np. błędne pole formularza musi mieć nie tylko czerwoną ramkę, ale też ikonę i tekstowy opis błędu; linki w tekście powinny być podkreślone, a nie tylko różnić się kolorem).
  * **Kontrast tekstu (Poziom AA):**
    * Minimum **4.5:1** dla zwykłego tekstu.
    * Minimum **3:1** dla dużego tekstu (od `18pt`/`24px` lub pogrubionego od `14pt`/`18.5px`).
  * **Kontrast elementów graficznych i UI (WCAG 2.1 AA):** Minimum **3:1** dla ikon, wykresów oraz obramowań pól formularzy i przycisków.
  * **Powiększanie i przelewanie tekstu (Reflow):** Strona musi pozostać czytelna i funkcjonalna przy powiększeniu tekstu do **200%** oraz przy szerokości ekranu `320px` (odpowiednik powiększenia 400% na ekranie `1280px`) bez konieczności przewijania w dwóch wymiarach jednocześnie.

---

### 2. Funkcjonalność (Operable)
Wszystkie komponenty interfejsu i nawigacja muszą być możliwe do obsłużenia przez każdego użytkownika.

* **Dostępność z klawiatury (Kryteria 2.1.x):**
  * **100% funkcji strony** (menu, formularze, karuzele, okna modalne, odtwarzacze) musi dać się obsłużyć wyłącznie za pomocą klawiatury (`Tab`, `Shift + Tab`, `Enter`, `Spacja`, `Strzałki`, `Esc`).
  * **Zakaz pułapek klawiaturowych (No Keyboard Trap):** Użytkownik, który wszedł do elementu za pomocą klawisza `Tab`, musi móc z niego wyjść. W otwartym oknie modalnym fokus powinien krążyć wewnątrz modala, a klawisz `Esc` powinien zamykać okno i przywracać fokus na przycisk, który je otworzył.
* **Wystarczający czas (Kryteria 2.2.x):**
  * Jeśli na stronie są limity czasowe (np. wygasanie sesji), użytkownik musi mieć możliwość ich wyłączenia lub przedłużenia.
  * Automatycznie przesuwające się karuzele czy animacje trwające dłużej niż 5 sekund muszą posiadać przycisk **Pauza / Stop**.
* **Ataki padaczki i reakcje fizyczne (Kryteria 2.3.x):**
  * Żaden element na stronie nie może błyskać częściej niż **3 razy na sekundę**.
  * Obsługa ustawienia systemowego `prefers-reduced-motion: reduce` (wyłączenie gwałtownych animacji i efektu paralaksy dla osób z zaburzeniami błędnika).
* **Nawigacja (Kryteria 2.4.x):**
  * **Skip Link:** Ukryty wizualnie (widoczny po pierwszym naciśnięciu `Tab`) link *"Przejdź do głównej treści"* na samym początku strony.
  * **Unikalne i opisowe tytuły stron (`<title>`):** Np. `<title>Cennik usług projektowych – NazwaFirmy</title>` zamiast samego `<title>Strona główna</title>`.
  * **Widoczny Fokus (Focus Visible):** Nigdy nie używaj `outline: none` bez zapewnienia wyraźnego, kontrastowego zastępstwa dla stanu `:focus-visible`.
  * **Zrozumiały cel linku:** Unikaj linków o treści *"Kliknij tutaj"* lub *"Więcej"*. Tekst linku powinien jednoznacznie opisywać, dokąd prowadzi (np. *"Pobierz raport roczny 2026 (PDF, 2 MB)"*).

---

### 3. Zrozumiałość (Understandable)
Treść oraz sposób działania interfejsu muszą być zrozumiałe dla odbiorcy.

* **Czytelność i język (Kryteria 3.1.x):**
  * Zadeklarowany główny język dokumentu w znaczniku HTML: `<html lang="pl">`, aby syntezator mowy używał polskiej wymowy.
  * Fragmenty w innym języku oznaczone atrybutem `lang` (np. `<span lang="en">Design Thinking</span>`).
  * Prosty, zrozumiały język i wyjaśnianie specjalistycznych skrótów.
* **Przewidywalność (Kryteria 3.2.x):**
  * Samo otrzymanie fokusu przez element (`onFocus`) lub zmiana wartości pola (`onChange`) nie może powodować nieoczekiwanej zmiany kontekstu (np. automatycznego przeładowania strony lub otwarcia nowego okna bez kliknięcia przycisku zatwierdzającego).
  * Nawigacja i elementy powtarzalne występują zawsze w tej samej kolejności na wszystkich podstronach.
* **Pomoc przy wprowadzaniu danych (Kryteria 3.3.x):**
  * Każde pole formularza ma trwale powiązaną etykietę (`<label for="id_pola">`).
  * W przypadku błędu walidacji błąd jest opisany tekstem, powiązany z polem (np. przez `aria-describedby` i `aria-invalid="true"`) i podpowiada sposób naprawy.
  * W przypadku ważnych operacji (finansowych, prawnych, usuwania danych) użytkownik może cofnąć operację, zweryfikować dane przed wysłaniem lub potwierdzić swój wybór.

---

### 4. Solidność / Kompatybilność (Robust)
Treść musi być stworzona na tyle solidnie, aby mogła być niezawodnie interpretowana przez różne przeglądarki oraz technologie asystujące (czytniki ekranu takie jak NVDA, JAWS, VoiceOver, TalkBack).

* **Poprawność kodu HTML:** Brak niezamkniętych znaczników, duplikatów atrybutów `id` czy nieprawidłowego zagnieżdżania (np. `<button>` wewnątrz `<a>`).
* **Nazwa, Rola, Wartość (Kryterium 4.1.2):**
  * Wszystkie niestandardowe komponenty (akordeony, zakładki, rozwijane listy) muszą informować czytnik ekranu o swojej roli i stanie za pomocą atrybutów **WAI-ARIA** (np. `aria-expanded="true/false"`, `aria-controls`, `aria-selected`).
* **Komunikaty o stanie (Kryterium 4.1.3 – WCAG 2.1):**
  * Dynamiczne komunikaty pojawiające się bez przeładowania strony (np. *"Produkt dodano do koszyka"*, *"Znaleziono 5 wyników"*, komunikaty błędów) muszą być ogłaszane przez czytniki ekranu za pomocą regionów `aria-live="polite"` lub `role="status"` / `role="alert"`.
