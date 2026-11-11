# 5. Inne Bardzo Ważne Składowe Strony Internetowej

Poza wyglądem (UI/UX), strukturą, responsywnością i dostępnością (WCAG), o sukcesie, bezpieczeństwie i widoczności strony w internecie decyduje pięć kluczowych obszarów techniczno-prawnych.

---

## 5.1. Wydajność, Szybkość i Core Web Vitals

Szybkość działania strony wpływa bezpośrednio na współczynnik odrzuceń (*bounce rate*), konwersję oraz pozycję w wynikach wyszukiwania Google.

### Wskaźniki Core Web Vitals (CWV):
1. **LCP (Largest Contentful Paint) ≤ 2.5 sekundy:** Czas wyrenderowania największego widocznego elementu w pierwszym oknie ekranu (np. głównego zdjęcia lub nagłówka w sekcji Hero).
2. **INP (Interaction to Next Paint) ≤ 200 milisekund:** Czas reakcji strony na interakcję użytkownika (kliknięcie, dotknięcie ekranu, naciśnięcie klawisza) aż do odświeżenia widoku.
3. **CLS (Cumulative Layout Shift) < 0.1:** Stabilność wizualna układu – brak „skakania" tekstu i przycisków podczas doczytywania grafik, reklam czy czcionek.

### Kluczowe techniki optymalizacji:
* **Nowoczesne formaty obrazów:** Konwersja grafik do formatu **WebP** lub **AVIF** oraz wektorowego **SVG** dla ikon i logotypów.
* **Leniwe ładowanie (Lazy Loading):** Dodanie `loading="lazy"` dla obrazów i ramek `<iframe>` znajdujących się poniżej pierwszego ekranu, ale użycie `fetchpriority="high"` (bez lazy loadingu!) dla głównego obrazu w sekcji Hero.
* **Jawne wymiary mediów:** Zawsze podawaj atrybuty `width` i `height` w znaczniku `<img>` lub `aspect-ratio` w CSS, aby przeglądarka zarezerwowała miejsce przed pobraniem pliku (eliminacja CLS).
* **Optymalizacja fontów:** Lokalny hosting czcionek (lub preconnect do serwera fontów), format `WOFF2`, podzbiory znaków (np. `latin-ext` dla polskich znaków) oraz właściwość `font-display: swap`.
* **Minifikacja i kompresja:** Kompresja tekstu na serwerze (**Brotli** lub **Gzip**), minifikacja CSS/JS, usuwanie nieużywanego kodu oraz ładowanie skryptów z atrybutami `defer` lub `async`.
* **Caching i CDN:** Wykorzystanie sieci Content Delivery Network (np. Cloudflare) oraz nagłówków pamięci podręcznej (`Cache-Control`).

---

## 5.2. Techniczne SEO i Widoczność (Search & AI Readiness)

Nawet najlepsza strona nie spełni swojej roli, jeśli użytkownicy nie będą mogli jej znaleźć w wyszukiwarkach i systemach AI.

* **Meta tagi na każdej podstronie:**
  * Unikalny `<title>` (optymalnie 50–60 znaków).
  * Unikalny `<meta name="description">` (optymalnie 120–155 znaków, zachęcający do kliknięcia).
* **Open Graph i Social Media Cards (`og:title`, `og:description`, `og:image`):** Odpowiadają za atrakcyjny wygląd linku po wklejeniu go na Facebooka, LinkedIna, Slacka, Discorda czy w wiadomości SMS/WhatsApp.
* **Przyjazne adresy URL (Clean URLs):** Krótkie, opisowe adresy pisane małymi literami ze słowami oddzielonymi myślnikiem (np. `/uslugi/projektowanie-stron` zamiast `/index.php?id=48&cat=2`).
* **Pliki dla robotów i indeksowania:**
  * `sitemap.xml` – automatycznie aktualizowana mapa strony zgłoszona w Google Search Console.
  * `robots.txt` – instrukcje dla robotów wyszukiwarek (upewnienie się, że strona produkcyjna nie ma blokady `noindex` po zakończeniu prac deweloperskich!).
  * **Tagi kanoniczne (`rel="canonical"`):** Zapobieganie duplikacji treści.
  * Poprawne przekierowania `301` (np. ujednolicenie wersji z `www` i bez `www` oraz wymuszenie `https://`).
* **Dane strukturalne (Schema.org / JSON-LD):** Znaczniki pomagające Google i asystentom AI zrozumieć typ treści (np. `Organization`, `LocalBusiness`, `Product`, `FAQPage`, `Article`, `BreadcrumbList`).

---

## 5.3. Bezpieczeństwo (Web Security)

* **Certyfikat SSL / HTTPS:** Szyfrowanie połączenia to absolutny standard (brak HTTPS skutkuje ostrzeżeniem *"Strona niezabezpieczona"* w przeglądarce i blokadą wielu nowoczesnych API przeglądarkowych).
* **Nagłówki bezpieczeństwa HTTP (Security Headers):**
  * `Strict-Transport-Security` (HSTS) – wymuszenie połączenia wyłącznie przez HTTPS.
  * `Content-Security-Policy` (CSP) – ochrona przed atakami XSS (Cross-Site Scripting) poprzez określenie dozwolonych źródeł skryptów.
  * `X-Content-Type-Options: nosniff` oraz `X-Frame-Options: SAMEORIGIN` (ochrona przed *clickjackingiem*).
  * `Referrer-Policy` oraz `Permissions-Policy`.
* **Zabezpieczenie formularzy:**
  * Ochrona przed spamem i botami – najlepiej niewidoczna dla użytkownika i zgodna z WCAG (np. Cloudflare Turnstile, pole typu *Honeypot*, ograniczanie liczby zapytań – *Rate Limiting*) zamiast trudnych do odczytania obrazkowych CAPTCHA.
  * Walidacja i sanityzacja danych **po stronie serwera** (ochrona przed SQL Injection i XSS), używanie tokenów CSRF.
* **Aktualizacje i kopie zapasowe (Backups):** Regularne automatyczne kopie zapasowe bazy danych i plików przechowywane w zewnętrznej lokalizacji oraz aktualizacja zależności/wtyczek CMS.

---

## 5.4. Wymogi Prawne, Prywatność i RODO (GDPR)

Każda strona zbierająca jakiekolwiek dane użytkowników (nawet adresy IP w logach, pliki cookies analityczne czy dane w formularzu kontaktowym) musi spełniać wymogi prawne:

* **Baner Cookies i Zarządzanie Zgodami (Consent Management / Google Consent Mode v2):**
  * Skrypty śledzące, analityczne i marketingowe (np. Google Analytics, Meta Pixel) **nie mogą** uruchamiać się przed wyrażeniem dobrowolnej zgody przez użytkownika.
  * Przycisk *"Odrzuć wszystkie"* (lub *"Tylko niezbędne"*) musi być równie widoczny i łatwy do kliknięcia jak przycisk *"Zaakceptuj wszystkie"* (zakaz stosowania tzw. *Dark Patterns*).
  * Użytkownik musi mieć możliwość zmiany lub wycofania zgody w dowolnym momencie (np. poprzez stały link w stopce).
* **Polityka Prywatności i Plików Cookies:** Jasny dokument informujący, kto jest administratorem danych (pełne dane firmy), w jakim celu i jak długo dane są przetwarzane, komu są powierzane oraz jakie prawa przysługują użytkownikowi.
* **Klauzule informacyjne przy formularzach:** Informacja o przetwarzaniu danych osobowych w celu obsługi zapytania (oraz osobne, **niezaznaczone domyślnie** checkboxy na ewentualne zgody marketingowe/newsletter).
* **Regulamin świadczenia usług drogą elektroniczną:** Wymagany szczególnie przy sklepach internetowych, zakładaniu kont użytkowników, systemach rezerwacji czy zapisie na newsletter.
* **Dyrektywa Omnibus (dla e-commerce i promocji):** Obowiązek informowania o najniższej cenie produktu/usługi z ostatnich 30 dni przed wprowadzeniem obniżki.

---

## 5.5. Analityka, Testowanie i Utrzymanie

* **Analityka webowa:** Wdrożenie narzędzi pozwalających mierzyć ruch i konwersje (np. Google Analytics 4 z Consent Mode, lub rozwiązania privacy-first niewymagające uciążliwych banerów cookies, jak Plausible czy Umami).
* **Google Search Console & Bing Webmaster Tools:** Monitorowanie stanu indeksacji, błędów mobilnych i wyników Core Web Vitals.
* **Favicon i Web App Manifest:** Zestaw ikon strony dla przeglądarek, urządzeń Apple (`apple-touch-icon`) oraz ekranów głównych Androida (`manifest.webmanifest`).
* **Kompatybilność międzyprzeglądarkowa (Cross-Browser Testing):** Przetestowanie działania na silnikach Chromium (Chrome, Edge, Brave), WebKit (Safari na macOS i iOS – szczególnie ważne ze względu na specyfikę iOS!) oraz Gecko (Firefox).
* **Monitoring dostępności (Uptime Monitoring) i błędów:** Automatyczne powiadomienia w razie awarii serwera lub wygaśnięcia certyfikatu SSL/domeny.
