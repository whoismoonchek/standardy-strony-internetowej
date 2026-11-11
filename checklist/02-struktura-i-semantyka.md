# Checklista: 2. Struktura i semantyka

⬅️ [Poprzedni obszar: UX / UI](./01-ux-ui.md) | 🏠 [README](../README.md) | 📖 [Dokumentacja źródłowa](../docs/02-struktura-i-semantyka.md) | ➡️ [Następny obszar: Responsywność](./03-responsywnosc-rwd.md)

---

## Tabela kontrolna (10 punktów)

| Lp. | Wymaganie (1 zdanie, tak/nie) | Dlaczego ważne | Jak sprawdzić | Priorytet | Status | Źródło (plik + sekcja) |
| :--- | :--- | :--- | :--- | :--- | :---: | :--- |
| **2.1** | Serwis ma logiczną strukturę piramidy (Poziom 0: Strona główna → Poziom 1: Kategorie/Usługi → Poziom 2: Podkategorie/Oferty). | Ułatwia orientację użytkownikom oraz indeksowanie robotom wyszukiwarek. | Rozrysuj lub sprawdź drzewo podstron i menu nawigacyjne. | wysoki | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.1)](../docs/02-struktura-i-semantyka.md) |
| **2.2** | Strona posiada dedykowaną stronę błędu `404` (z informacją, wyszukiwarką i linkiem do strony głównej) oraz stronę/komunikat podziękowania po wysłaniu formularza. | Użytkownik nie zostaje w „ślepym zaułku" po wpisaniu złego adresu URL lub wysłaniu wiadomości. | Wpisz nieistniejący adres URL (np. `/test-brak-strony`) oraz wyślij testowo formularz. | średni | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.1)](../docs/02-struktura-i-semantyka.md) |
| **2.3** | W serwisie znajdują się podstrony prawne: Polityka prywatności, Polityka cookies, Regulamin oraz Deklaracja dostępności. | Są to obowiązkowe dokumenty wymagane przez przepisy prawa i standardy dostępności. | Sprawdź, czy linki do tych dokumentów działają i znajdują się w stopce strony. | wysoki | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.1)](../docs/02-struktura-i-semantyka.md) |
| **2.4** | Główne menu nawigacyjne w nagłówku zawiera maksymalnie 5–7 pozycji oraz wyróżniony przycisk głównej akcji (CTA). | Zbyt dużo pozycji w menu przytłacza użytkownika i utrudnia wybór. | Policz elementy w głównym menu górnym (`<header><nav>`). | średni | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.2)](../docs/02-struktura-i-semantyka.md) |
| **2.5** | Sekcje na stronie ułożone są w logicznej kolejności decyzyjnej: Nagłówek → Hero → Dowód społeczny (Social Proof) → Oferta/Rozwiązanie → Case Studies/Opinie → FAQ → Końcowe CTA → Stopka. | Kolejne sekcje odpowiadają na pytania użytkownika we właściwym momencie. | Przewiń stronę od góry do dołu i porównaj kolejność sekcji z tym schematem. | średni | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.2)](../docs/02-struktura-i-semantyka.md) |
| **2.6** | Stopka (`<footer>`) zawiera pełną mapę linków, dane kontaktowe i rejestrowe firmy (NIP, adres), linki do social mediów, dokumentów prawnych i praw autorskich. | Buduje wiarygodność firmy i daje szybki dostęp do informacji formalnych na każdej podstronie. | Przewiń na sam dół strony i sprawdź zawartość elementu `<footer>`. | wysoki | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.2)](../docs/02-struktura-i-semantyka.md) |
| **2.7** | Kod strony używa semantycznych znaczników HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`) zamiast samych bloków `<div>`. | Pozwala czytnikom ekranu i robotom wyszukiwarek zrozumieć rolę każdej części strony. | Zbadaj kod źródłowy strony (F12 → Elements) i sprawdź obecność znaczników semantycznych. | wysoki | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.3)](../docs/02-struktura-i-semantyka.md) |
| **2.8** | Gdy na stronie jest więcej niż jedna nawigacja (`<nav>`), każda ma unikalny atrybut `aria-label` (np. „Główna nawigacja", „Nawigacja w stopce"). | Osoby korzystające z czytników ekranu mogą łatwo odróżnić menu górne od dolnego. | Wyszukaj w kodzie HTML wszystkie znaczniki `<nav>` i sprawdź ich atrybut `aria-label`. | średni | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.3)](../docs/02-struktura-i-semantyka.md) |
| **2.9** | Na każdej podstronie jest dokładnie jeden nagłówek `<h1>`, a kolejne nagłówki (`<h2>`–`<h6>`) tworzą hierarchię bez pomijania poziomów (np. brak skoku z `<h2>` od razu do `<h4>`). | Zachowuje prawidłowy konspekt dokumentu dla SEO i osób niewidomych. | Użyj wtyczki typu HeadingsMap lub sprawdź w kodzie kolejność znaczników `<h1>`–`<h6>`. | wysoki | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.3)](../docs/02-struktura-i-semantyka.md) |
| **2.10** | Do zmiany adresu URL użyto znacznika `<a>`, a do wykonywania akcji na stronie (np. wysłanie formularza, otwarcie modala/menu) użyto `<button>` (nigdy `<div onclick="...">`). | Zapewnia natywną obsługę klawiatury i poprawne działanie z czytnikami ekranu. | Zbadaj w kodzie (F12) przyciski i linki, sprawdzając ich tagi HTML. | wysoki | ☐ | [02-struktura-i-semantyka.md (Sekcja 2.3)](../docs/02-struktura-i-semantyka.md) |

---

📊 [Przejdź do podsumowania i TOP 10](./podsumowanie.md)
