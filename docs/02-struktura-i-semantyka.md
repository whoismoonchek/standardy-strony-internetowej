# 2. Struktura Strony Internetowej i Architektura Informacji

Dobrze zaplanowana struktura strony pełni podwójną rolę: prowadzi użytkownika przez proces decyzyjny (*Journey-Led Architecture*) oraz pozwala robotom wyszukiwarek i czytnikom ekranu bezbłędnie zrozumieć hierarchię treści.

---

## 2.1. Architektura Informacji w skali całego serwisu (Mapa Strony)

Typowa, zoptymalizowana struktura serwisu ma kształt piramidy:
* **Poziom 0:** Strona główna (*Homepage*)
* **Poziom 1:** Główne kategorie / Usługi / O nas / Kontakt / Blog
* **Poziom 2:** Podkategorie / Konkretne oferty / Wpisy blogowe / Case studies
* **Strony pomocnicze i systemowe:**
  * Strona błędu `404` (z informacją, co się stało, wyszukiwarką i linkiem powrotnym do strony głównej).
  * Strona podziękowania (*Thank You Page*) lub jasny komunikat po wysłaniu formularza.
  * Strony prawne: Polityka prywatności, Polityka cookies, Regulamin, Deklaracja dostępności.

---

## 2.2. Anatomia Pojedynczej Strony (Sekcja po sekcji)

Nowoczesna strona (szczególnie strona główna lub ofertowa) powinna odpowiadać na kolejne pytania pojawiające się w głowie użytkownika:

1. **Nagłówek (`<header>` + `<nav>`):**
   * Logo (link do strony głównej).
   * Główne menu nawigacyjne (5–7 pozycji maksymalnie).
   * Przełącznik języka / motywu (jeśli dotyczy).
   * Wyróżniony przycisk głównej akcji (CTA, np. *"Umów konsultację"*, *"Kup teraz"*).
2. **Sekcja Hero (Pierwszy ekran):**
   * Główny nagłówek `H1` odpowiadający na pytanie: *Co to jest i jaką daje mi korzyść?*
   * Podtytuł rozwijający myśl w 1–2 zdaniach.
   * Główne CTA (oraz opcjonalnie drugorzędne CTA o niższym progu wejścia, np. *"Zobacz realizacje"*).
   * Element wizualny pokazujący produkt/usługę w akcji.
3. **Dowód społeczny (Social Proof / Trust Bar):**
   * Logotypy klientów, certyfikaty, liczby, oceny z zewnętrznych portali.
4. **Problem i Rozwiązanie / Oferta / Funkcjonalności:**
   * Podział na czytelne karty lub sekcje z ikonami/ilustracjami pokazujące, jak strona/produkt rozwiązuje problem użytkownika.
5. **Studia przypadków (Case Studies) / Opinie (Testimonials):**
   * Konkretne rezultaty i autentyczne recenzje budujące wiarygodność.
6. **Sekcja FAQ (Najczęściej zadawane pytania):**
   * Rozwiewanie ostatnich wątpliwości przed podjęciem decyzji (doskonałe również pod SEO i wyszukiwanie głosowe/AI).
7. **Końcowa sekcja CTA (Final Call to Action):**
   * Wyraźne zamknięcie strony zachęcające do kontaktu lub zakupu.
8. **Stopka (`<footer>`):**
   * Pełna mapa linków (nawigacja dolna), dane kontaktowe i rejestrowe firmy (NIP, adres), linki do social mediów, linki do dokumentów prawnych, informacja o prawach autorskich.

---

## 2.3. Struktura Kodu – Semantyczny HTML5

Przeglądarki, wyszukiwarki i technologie asystujące opierają się na znacznikach semantycznych zamiast anonimowych bloków `<div>`:

```html
<body>
  <a href="#main-content" class="skip-link">Przejdź do głównej treści</a>
  
  <header>
    <nav aria-label="Główna nawigacja">
      <!-- Elementy menu -->
    </nav>
  </header>

  <main id="main-content">
    <section aria-labelledby="hero-heading">
      <h1 id="hero-heading">Główny tytuł strony</h1>
      <!-- Treść sekcji Hero -->
    </section>

    <section aria-labelledby="services-heading">
      <h2 id="services-heading">Nasze usługi</h2>
      <article>
        <h3>Usługa 1</h3>
        <p>Opis usługi...</p>
      </article>
    </section>

    <aside>
      <!-- Treści poboczne, np. powiązane wpisy lub filtry -->
    </aside>
  </main>

  <footer>
    <nav aria-label="Nawigacja w stopce">
      <!-- Linki w stopce -->
    </nav>
  </footer>
</body>
```

### Kluczowe zasady semantyki:
* **Ścisła hierarchia nagłówków (`H1`–`H6`):**
  * Dokładnie **jeden** znacznik `<h1>` na każdej podstronie.
  * Zakaz pomijania poziomów nagłówków (np. przejścia z `<h2>` bezpośrednio do `<h4>` tylko ze względu na rozmiar czcionki – do wyglądu służy CSS).
* **Właściwy dobór elementów interaktywnych:**
  * `<a>` (link) służy do **nawigacji** (zmiany adresu URL lub przewinięcia do kotwicy).
  * `<button>` (przycisk) służy do **wykonywania akcji** na stronie (wysłanie formularza, otwarcie okna modalnego, rozwinięcie menu).
  * Nigdy nie używaj `<div onclick="...">` jako zamiennika przycisku.
