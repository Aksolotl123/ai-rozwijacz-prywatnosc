---
title: AI Rozwijacz — polityka prywatności
---

# Polityka prywatności aplikacji „AI Rozwijacz”

Obowiązuje od: 22 września 2026 r.
Aplikacja: AI Rozwijacz (Android, identyfikator `pl.airozwijacz.menu`)
Kontakt w sprawach prywatności: [tuz.lukasz@gmail.com](mailto:tuz.lukasz@gmail.com)

## W skrócie

- Aplikacja pomaga pisać wiadomości i odpowiadać na nie z pomocą AI.
- **Autor aplikacji nie zbiera żadnych danych** — poza zgłoszeniem odpowiedzi AI, które sam wyślesz e-mailem. Aplikacja nie ma własnego serwera, kont użytkowników, reklam ani analityki.
- Domyślnie AI działa **na telefonie** (Gemini Nano / Gemma przez Android AICore) — nic nie wychodzi do internetu.
- Do chmury (Google albo Anthropic) trafia treść **tylko wtedy, gdy sam wybierzesz** taki silnik i podasz własny klucz API,
  albo gdy sam przekażesz polecenie do aplikacji Claude/Gemini.
- Niczego nie wysyłamy za Ciebie — wiadomość wychodzi do odbiorcy wyłącznie po naciśnięciu „Wyślij”.

## Jakie dane aplikacja przetwarza

| Dane | Skąd | Po co | Gdzie |
|---|---|---|---|
| Tekst, który zaznaczysz lub udostępnisz aplikacji | od Ciebie | żeby zredagować z niego wiadomość | w pamięci telefonu |
| Treść powiadomień z komunikatorów (nadawca, wiadomości) | uprawnienie „Dostęp do powiadomień”, które sam włączasz | żeby pokazać rozmowę i zaproponować odpowiedź; w trybie „hub” — żeby wyświetlić własne powiadomienie z przyciskami AI | w pamięci telefonu; historia rozmów — patrz niżej |
| Historia rozmów | z kolejnych powiadomień i Twoich odpowiedzi | żeby AI widziało wątek, a nie jedno zdanie | na telefonie, zaszyfrowana (AES‑256/GCM, klucz w Android Keystore); tylko gdy „Pamiętaj historię” jest włączone |
| Klucze API (Gemini, Anthropic) — opcjonalne | od Ciebie | żeby korzystać z płatnych modeli w chmurze na Twoim koncie | na telefonie, zaszyfrowane kluczem z Android Keystore |
| Log użycia (silnik, czasy, co zrobiono z wynikiem) | aplikacja | porównywanie silników; eksport CSV na Twoje żądanie | na telefonie; treść tylko po włączeniu opcji „Zapisuj treść w logu” |

Aplikacja zajmuje się wyłącznie rozmowami z komunikatorów zaznaczonych w Ustawieniach („Z których aplikacji czytać rozmowy”).
Powiadomień innych aplikacji nie zapisuje i nie przetwarza.

## Kiedy dane opuszczają telefon

| Co wybierzesz | Co jest wysyłane | Do kogo | Na jakich zasadach |
|---|---|---|---|
| „Normalne · Gemma” (domyślnie) | nic | — | — |
| Gemini API („Rozbudowane”, Twój klucz) | Twoja notatka; przy odpowiadaniu także do 20 ostatnich wiadomości rozmowy i do 5 Twoich wcześniejszych odpowiedzi (wzorzec stylu) | Google (Gemini API) | [warunki Gemini API](https://ai.google.dev/gemini-api/terms) i [polityka prywatności Google](https://policies.google.com/privacy) — na Twoim koncie |
| Claude API (Twój klucz) | jak wyżej | Anthropic | [zasady Anthropic](https://www.anthropic.com/legal/privacy) — na Twoim koncie |
| „Zapytaj Claude'a / Gemini” | to samo polecenie trafia do aplikacji Claude albo Gemini na Twoim telefonie; wysyłasz je sam | Anthropic / Google w ramach Twojego konta w tych aplikacjach | zasady tych aplikacji |
| „⚑ Zgłoś odpowiedź AI” | e-mail z treścią tej jednej odpowiedzi AI, nazwą silnika i wersją aplikacji (bez Twojej notatki i rozmowy); otwiera się w Twojej aplikacji pocztowej, wysyłasz go sam | autor aplikacji (tuz.lukasz@gmail.com) | zgłoszenie służy wyłącznie ocenie i poprawie odpowiedzi AI; usuniemy je na prośbę wysłaną na ten sam adres |
| „Kopia zapasowa” historii | plik zaszyfrowany Twoim hasłem (PBKDF2 + AES‑256/GCM) — tam, gdzie go sam udostępnisz (np. Dysk Google) | wybrana przez Ciebie usługa | bez hasła pliku nie da się odczytać — także autorowi |

Przy silnikach w chmurze okienko odpowiedzi zawsze pokazuje, dokąd trafi rozmowa. Bez internetu (albo z „Wymuś tryb offline”)
generowanie przechodzi na model na telefonie.

Biblioteka Google ML Kit, przez którą działa model na telefonie, przesyła do Google anonimowe metryki użycia API
(według dokumentacji Google — bez treści poleceń i odpowiedzi).

## Uprawnienia

- **Dostęp do powiadomień** — włączasz go sam w ustawieniach systemu; bez niego działa pisanie z menu zaznaczania tekstu.
- **Powiadomienia** — przycisk „✨ Odpowiedz z AI” i tryb „hub”.
- **Internet** — tylko dla silników w chmurze, które sam wybierzesz.
- **Ukrywanie nakładek innych aplikacji** — ochrona przed podstawieniem fałszywego przycisku nad „Wyślij”.

## Przechowywanie i usuwanie

- Historię rozmów możesz usunąć w całości albo po jednej rozmowie (Ustawienia → Historia rozmów) i wyłączyć jej zapis.
  Odznaczenie komunikatora usuwa też jego historię.
- Log wyczyścisz w Ustawieniach → Log.
- Klucze API usuniesz przyciskiem „Usuń” w Ustawieniach.
- Odinstalowanie aplikacji usuwa wszystkie jej dane z telefonu. Aplikacja nie korzysta z systemowych kopii zapasowych
  ani przenoszenia danych na nowy telefon.

Danych przesłanych do Google lub Anthropic (przy silnikach w chmurze) nie przechowuje autor aplikacji — obowiązują zasady
tych firm dla Twojego konta.

## Bezpieczeństwo

Zapisane dane są szyfrowane kluczem z Android Keystore, połączenia z API idą wyłącznie przez HTTPS, a klucze API — tylko
w nagłówku żądania do właściwego serwera.

## Wiek

Aplikacja jest przeznaczona dla osób pełnoletnich. W Google Play jej grupa docelowa to 18 lat i więcej.

## Zmiany

Istotne zmiany w tym, co opuszcza telefon, ogłosimy w aplikacji (ekran informacyjny pojawi się ponownie) i na tej stronie.
