# Standardy Nowoczesnej Strony Internetowej – Baza Wiedzy i Checklista (UX/UI, RWD, WCAG, SEO, CRO)

Praktyczne kompendium wiedzy oraz zestaw 75 punktów kontrolnych (w formie tabel „tak/nie") do projektowania, kodowania i audytowania nowoczesnych stron internetowych.

## 🎯 Do czego służy ten projekt i dla kogo jest przeznaczony?

Repozytorium łączy wymagania wizualne, techniczne, prawne oraz biznesowe (marketingowe) w jeden spójny system kontroli jakości. Zostało stworzone z myślą o:
* **Studentach kierunków IT, UX/UI i marketingu cyfrowego** – jako uporządkowana ściąga i lista kontrolna do projektów zaliczeniowych oraz komercyjnych.
* **Web Designerach i Frontend Developerach** – aby sprawdzić stronę przed oddaniem jej klientowi lub wdrożeniem na serwer produkcyjny.
* **Marketerach i właścicielach stron** – aby zweryfikować, czy strona jest widoczna w Google, bezpieczna prawnie (RODO, WCAG, Omnibus) i skutecznie zamienia ruch w zysk (CRO, CTA).

---

## 📂 Spis treści repozytorium

### 1. Dokumentacja merytoryczna (`docs/`)
* [00 – Spis treści i architektura bazy wiedzy](./docs/00-spis-tresci-i-architektura.md)
* [01 – Wygląd i funkcjonowanie strony (UX / UI)](./docs/01-wyglad-funkcjonowanie-ux-ui.md)
* [02 – Struktura strony i semantyczny HTML5](./docs/02-struktura-i-semantyka.md)
* [03 – Responsywność i adaptacja pod różne urządzenia (RWD)](./docs/03-responsywnosc-i-adaptacja-urzadzen.md)
* [04 – Dostępność cyfrowa: WCAG 2.0 / 2.1 / 2.2 (zasady POUR)](./docs/04-dostepnosc-wcag.md)
* [05 – Wydajność (Core Web Vitals), SEO, Bezpieczeństwo i Prawo (RODO)](./docs/05-kluczowe-skladowe-techniczne-i-prawne.md)
* [06 – Marketing, optymalizacja konwersji (CRO), przyciski CTA i zysk](./docs/06-marketing-konwersja-cta-i-zysk.md)

### 2. Tabele kontrolne – Checklista (`checklist/`)
* [Checklista 01: UX / UI – Wygląd i funkcjonowanie (12 pkt)](./checklist/01-ux-ui.md)
* [Checklista 02: Struktura i semantyka (10 pkt)](./checklist/02-struktura-i-semantyka.md)
* [Checklista 03: Responsywność i adaptacja urządzeń – RWD (10 pkt)](./checklist/03-responsywnosc-rwd.md)
* [Checklista 04: Dostępność cyfrowa – WCAG (14 pkt)](./checklist/04-dostepnosc-wcag.md)
* [Checklista 05: Technika, prawo, bezpieczeństwo i SEO (15 pkt)](./checklist/05-technika-prawo-seo.md)
* [Checklista 06: Marketing, konwersja (CRO), CTA i zysk (14 pkt)](./checklist/06-marketing-cta.md)
* 📊 **[Podsumowanie i TOP 10 najważniejszych punktów](./checklist/podsumowanie.md)**

---

## 🗺️ Mapa strony (6 głównych obszarów standardów)

| Obszar | Zakres | Do czego służy | Link do checklisty |
| :--- | :--- | :--- | :--- |
| **1. UX / UI** | Hierarchia wizualna (*Above the Fold*, wzorce F i Z), zasada kolorów `60-30-10`, Dark Mode, czytelna typografia, intuicyjna nawigacja, 6 stanów elementów interaktywnych, projektowanie i walidacja formularzy, *Skeleton Screens*. | Zapewnia estetyczny wygląd, czytelność tekstu i wygodne korzystanie z interfejsu bez przeciążania użytkownika. | [01-ux-ui.md](./checklist/01-ux-ui.md) |
| **2. Struktura i semantyka** | Architektura informacji (mapa strony, strona `404`, strony prawne), układ sekcji krok po kroku (od Hero po Footer), semantyczny HTML5 (`<header>`, `<nav>`, `<main>`, `<footer>`), hierarchia nagłówków `H1`–`H6`, `<button>` vs `<a>`. | Porządkuje budowę podstron i kod HTML, aby strona była zrozumiała dla ludzi, wyszukiwarek i czytników ekranu. | [02-struktura-i-semantyka.md](./checklist/02-struktura-i-semantyka.md) |
| **3. Responsywność (RWD)** | Podejście *Mobile-First*, strefa kciuka (*Thumb Zone*), 5 zakresów szerokości (`320px` do `1440px+`), `<meta name="viewport">`, Flexbox, CSS Grid, `@container`, funkcja `clamp()`, dotyk vs kursor (`:hover`), pola dotykowe, responsywne obrazy (`srcset`, `<picture>`) i tabele. | Dostosowuje układ, czcionki, obrazy i przyciski do każdego ekranu – od małych smartfonów po monitory 4K. | [03-responsywnosc-rwd.md](./checklist/03-responsywnosc-rwd.md) |
| **4. Dostępność (WCAG)** | Standard WCAG 2.0 / 2.1 / 2.2 (poziomy A, AA, AAA) i 4 filary **POUR**: teksty `alt`, napisy do wideo, kontrast (`4.5:1` / `3:1`), powiększanie 200%/400%, pełna obsługa klawiaturą, `Skip Link`, widoczny fokus, język `lang`, obsługa błędów i atrybuty WAI-ARIA (`aria-live`). | Umożliwia korzystanie ze strony osobom z niepełnosprawnościami (wzroku, słuchu, ruchu, poznawczymi) i zapewnia zgodność z prawem (EAA). | [04-dostepnosc-wcag.md](./checklist/04-dostepnosc-wcag.md) |
| **5. Technika, prawo i SEO** | Szybkość i **Core Web Vitals** (`LCP ≤ 2.5s`, `INP ≤ 200ms`, `CLS < 0.1`), obrazy WebP/AVIF, fonty `WOFF2`, meta tagi, Open Graph, `sitemap.xml`, `robots.txt`, Schema.org (JSON-LD), HTTPS/SSL, nagłówki bezpieczeństwa (CSP, HSTS), ochrona formularzy, backupy, RODO (*Consent Mode v2*) i dyrektywa Omnibus. | Dba o szybkie ładowanie, wysoką pozycję w Google, ochronę przed atakami hakerskimi oraz brak kar prawnych. | [05-technika-prawo-seo.md](./checklist/05-technika-prawo-seo.md) |
| **6. Marketing, CRO i CTA** | Równanie konwersji MECLABS, projektowanie przycisków **CTA** (`Czasownik + Rezultat`, *Click Triggers*, Primary vs Secondary CTA), propozycja wartości w Hero (test 5 sekund), frameworki PAS i AIDA, kontekstowy *Social Proof*, psychologia cenników (3 pakiety, brak ukrytych kosztów), *Lead Magnets*, *Multi-Step Forms*, *Guest Checkout* oraz mapy ciepła. | Zamienia odwiedzających stronę w klientów i generuje mierzalny zysk (ROI) dla firmy. | [06-marketing-cta.md](./checklist/06-marketing-cta.md) |

---

## 🛠️ Jak korzystać z checklisty?

1. **Sklonuj lub skopiuj repozytorium** do swojego projektu jako listę kontrolną przed wdrożeniem strony.
2. **Zacznij od najważniejszych punktów:** Otwórz plik [checklist/podsumowanie.md](./checklist/podsumowanie.md) i sprawdź tabelę **TOP 10 najważniejszych punktów** oraz wszystkie punkty z priorytetem `wysoki` (47 punktów).
3. **Weryfikuj obszar po obszarze:** Otwieraj kolejne pliki od [01-ux-ui.md](./checklist/01-ux-ui.md) do [06-marketing-cta.md](./checklist/06-marketing-cta.md).
4. **Wykonuj proste testy z kolumny „Jak sprawdzić":** Większość punktów sprawdzisz bezpłatnie za pomocą narzędzi deweloperskich w przeglądarce (klawisz `F12` → zakładki *Elements*, *Network*, *Rendering*, *Lighthouse*), klawisza `Tab` oraz telefonu.
5. **Odhaczaj wykonane zadania:** W kolumnie `Status` zamieniaj znak `☐` na `☑` (lub `- [ ]` na `- [x]`). Jeśli potrzebujesz dokładniejszego wyjaśnienia teorii, kliknij link w kolumnie `Źródło (plik + sekcja)`, który przeniesie Cię prosto do odpowiedniego rozdziału w katalogu `docs/`.

---

## 📚 Lista źródeł i standardów (użytych w bazie wiedzy)

Wszystkie wytyczne w tym repozytorium opierają się na standardach i badaniach instytucji opisanych w plikach `docs/00`–`06`:
* **W3C / Web Accessibility Initiative (WAI)** – twórcy standardu **WCAG 2.0, 2.1 oraz 2.2** i specyfikacji HTML5 / WAI-ARIA (oraz wymogi **Europejskiego Aktu o Dostępności – EAA**).
* **Nielsen Norman Group (NN/g – `nngroup.com`)** – badania eye-trackingowe (wzorce F i Z, ignorowanie zdjęć stockowych), Prawo Jakoba, czytelność mikrocopy oraz projektowanie przycisków CTA.
* **Baymard Institute (`baymard.com`)** – badania użyteczności e-commerce, koszyków zakupowych, formularzy, powodów porzucania koszyków (ukryte koszty, wymóg zakładania konta) oraz paraliżu decyzyjnego.
* **CXL Institute (`cxl.com/blog` – Peep Laja)** – metodologia *Conversion Rate Optimization (CRO)*, psychologia konwersji i hierarchia zaangażowania CTA.
* **Copyhackers (`copyhackers.com` – Joanna Wiebe)** – metodologia *Conversion Copywriting*, pisanie nagłówków, etykiet CTA i praca z głosem klienta.
* **MECLABS Institute** – heurystyczne równanie konwersji: $C = 4m + 3v + 2(i - f) - 2a$.
* **HubSpot & Unbounce (`unbounce.com`)** – architektura stron docelowych (*Landing Pages*), *Attention Ratio 1:1*, *Lead Magnets* i raporty konwersji.
* **Stanford Web Credibility Research** – badania nad wpływem projektu wizualnego na postrzeganą wiarygodność firmy.
* **Smashing Magazine (`smashingmagazine.com`) & Awwwards (`awwwards.com`)** – wzorce nowoczesnego projektowania UI/UX i techniki CSS.
* **Growth.Design (`growth.design`)** – studia przypadków z psychologii produktowej i monetyzacji.
* **Google (Web.dev / Search Central / Material Design) & Apple (iOS Guidelines)** – wskaźniki **Core Web Vitals** (LCP, INP, CLS), *Mobile-First Indexing*, *Google Consent Mode v2* oraz wytyczne wymiarów pól dotykowych (`44×44 px` / `48×48 dp`).

---

## ⚠️ Braki (Czego nie było w plikach źródłowych `00`–`06`)

Ponieważ repozytorium i checklista powstały wyłącznie na podstawie informacji zawartych w plikach `00`–`06`, poniższe zagadnienia nie zostały ujęte w tabelach kontrolnych:
1. **Proces wdrożeniowy CI/CD i środowiska testowe (*staging*)** – w plikach opisano kopie zapasowe i testowanie na przeglądarkach, ale brakuje opisu automatycznego wdrażania kodu (np. GitHub Actions) i testowania na serwerze *staging* przed publikacją na produkcji.
2. **Techniczne SEO dla stron wielojęzycznych (`hreflang`)** – wspomniano o przełączniku języka w nagłówku (plik `02`) oraz atrybucie `lang` (plik `04`), ale brakuje wytycznych dotyczących znaczników `<link rel="alternate" hreflang="...">` dla wyszukiwarek.
3. **Konfiguracja dostarczalności e-maili z formularzy (SPF, DKIM, DMARC, SMTP)** – dokładnie opisano budowę, walidację i zabezpieczenie formularzy przed botami, lecz brakuje wzmianki o konfiguracji rekordów DNS domeny, aby powiadomienia z formularzy nie trafiały do folderu SPAM.
4. **Szczegółowa specyfikacja doboru parametrów hostingu i domeny** – wspomniano o CDN, serwerach NVMe i monitoringu wygaśnięcia domeny/SSL, ale bez szczegółowych kryteriów doboru planu serwerowego.

---

## 👤 Autor i Licencja

* **Autor:** Opracowano w ramach projektu standardów nowoczesnej strony internetowej (`mo_ochko`).
* **Licencja:** Projekt udostępniany na licencji **[MIT](./LICENSE)** – możesz go swobodnie kopiować, modyfikować i wykorzystywać w projektach studenckich oraz komercyjnych.
