---
title: "Jak przechowywać bitcoiny?"
date: 2020-12-26
draft: false
tags:
  - bitcoin
---

<p style="text-align: center;"><span style="color: #f03838;">artykuł wolny od linków afiliacyjnych</span></p>

# TL;DR

Najwyższy możliwy poziom bezpieczeństwa zapewniają **portfele sprzętowe**. Nigdy nie trzymaj bitcoinów na giełdach ani portfelach online.

# Portfele sprzętowe

Nie zarabiamy na polecaniu tych produktów. Linki w artykułach nie są afiliacyjne.

Portfele sprzętowe są optymalnym wyborem dla ogromnej większość użytkowników.

Portfele sprzętowe świetnie nadają się jako tzw "cold storage". W przeciwieństwie do klasycznego "paper walleta", portfele sprzętowe dają pełną elastyczność dysponowania środkami bez ryzykownego wgrywania klucza prywatnego na laptopa czy smartphona. Produkty te prowadzą użytkownika za rękę, minimalizując liczbę błędów jakie może popełnić.

Siła portfeli sprzętowych polega na tym, że klucz prywatny nigdy nie dotyka komputera. Wszystkie wrażliwe operacje realizowane są poza komputerem, na portfelu sprzętowym. Przykładami takich sprzętowych operacji są inicjalne wygenerowanie klucza prywatnego, generowanie i wyświetlanie na zaufanym ekranie kolejnych adresów do przyjmowania bitcoinów, oraz oczywiście samo podpisywanie transakcji wychodzących.

[Który portfel sprzętowy wybrać?]({{< ref "ktory-portfel-sprzetowy-wybrac.md" >}} "About Us")


# Portfele Concierge Multisig

Najwyższy możliwy poziom bezpieczeństwa można uzyskać stosując zaawansowane rozwiązania "concierge multisig". Wadą jest wysoka cena, rzędu $1800 rocznie oraz utrata prywatności względem usługodawcy.

W tym rozwiązaniu uwolnienie środków wymaga podpisania transakcji więcej niż jednym kluczem prywatnym (2-z-3 lub 3-z-5) z użyciem  dedykowanej do tego aplikacji mobilnej.

Klucze prywatne są podzielone pomiędzy użytkownika i firmę concierge w taki sposób, żeby użytkownik mógł **samodzielnie** dysponować swoimi środkami. Jednocześnie, w przypadku utraty jednego klucza przez użytkownika, firma dokłada swój "awaryjny" klucz aby umożliwić odzyskanie środków i przywrócenie standardowego setupu. Dodatkowo, firma otacza użytkownika pomocą techniczną 24/7 i doradztwem w zakresie bezpiecznego obchodzenia się z kluczami.

Jedynym godnym polecenia rozwiązaniem w tym momencie jest [Casa Keymaster](https://keys.casa/keymaster/) w wersji nie niższej niż Platinum 3-of-5. W tym modelu użytkownik kontroluje 3 portfele sprzętowe, czwarty klucz ma na smartphonie, a piąty klucz posiada firma. Nawet po utracie jednego z kluczy, użytkownik wciąż samodzielnie dysponuje środkami. Przy jednoczesnej utracie dwóch kluczy konieczne jest skorzystanie z awaryjnego klucza zarządzanego przez firmę.

Nie sugerujemy:

* Usług concierge wymagających podania jakichkolwiek danych osobowych (KYC)
* Pakietów Casa Keymaster Silver 2-of-3 ani Gold 2-of-3; wydają się one oferować niższe bezpieczeństwo niż samodzielnie zarządzany portfel sprzętowy
* Samodzielnego setupu multisig z użyciem bezpłatnych narzędzi, chyba że użytkownik jest silny technicznie i dokładnie rozumie co robi

# Nie: na giełdach i portfelach online

**Nie kontrolujesz kluczy prywatnych? Bitcoiny nie są Twoje**. Powierzenie bitcoinów w przechowanie nawet najbardziej zaufanej i renomowanej firmie zawsze kończy się tak samo: utratą środków. Najlepiej wyjaśnia to [wpis Bitmara na forum Bitcoin](https://forum.bitcoin.pl/viewtopic.php?f=93&t=32616).

Dodatkowo, wiążesz wtedy bitcoiny z tożsamością, co de facto oznacza nieodwracalne upublicznienie Twojego salda, przychodów i wydatków. Pamiętaj, że transakcje kryptowalutowe są publicznie widoczne - również dla kryminalistów i służb państwowych.

Jeśli jesteś daytradarem, musisz wkalkulować okresową utratę środków na giełdzie. Musisz też z dużą wrażliwością śledzić poczynania giełdy, wszelkie wpadki i nietypowe wydarzenia oraz doświadczenia innych osób. Niektórzy traderzy dodatkowo stosują wypłatę środków na noc i weekend, zmniejszając statystyczne ryzyko nawet o połowę.

# Nie: brain wallet

To pomysł polegający na pamiętaniu frazy, z której wywodzi się klucz prywatny. Proste frazy nie są sekretem, są obserwowane przez boty, środki z nich znikną natychmiast. Z kolei skomplikowane i unikalne frazy zostaną nieuchronnie zapomniane przez użytkownika; najczęściej też mimo pozornego skomplikowania mają zbyt małą entropię by wytrzymać lata.

# Nie: własne pomysły

Niestandardowe rozwiązania i własne pomysły w zarządzaniu kluczami prywatnymi to **zły pomysł**.

Paradoksalnie, najczęściej ofiarą takiego kombinowania padają osoby techniczne i zaawansowani użytkownicy. Zakładają oni, że wymyślą lepszą metodę niż obecne najlepsze praktyki, wypracowane na przestrzeni 12 lat przez silnie techniczną społeczność kryptowalut. Potencjalne usprawnienia wymagają szerokiego peer-review.

Własne rozwiązania najczęściej kończą się **przypadkową** utratą środków w wyniku złego wyważenia ryzyk i nieświadomości wielowymiarowości zagadnienia (np zginął jeden element systemu, po latach użytkownik zapomniał swoje silne hasło; użytkownik zapomniał jak skonstruowany był system, sekret wyciekł w zupełnie nieoczekiwany sposób, itp).


# Komentarz do innych metod

**Laptop** - nadaje się tylko do niewielkich kwot i eksperymentowania. To właśnie komputery najczęściej padają ofiarą malware kradnącego kryptowaluty. Dotyczy to również użytkowników macOS i Linuksa. Część ataków ma charakter uniwersalny, niezależny od systemu operacyjnego. Nie ma natomiast problemu, żeby używać komputera w parze z portfelem sprzętowym do dużych kwot.

**Smartphone** - podobnie jak laptop, nadaje się tylko do niewielkich kwot i eksperymentowania. Smartphone jest bezpieczniejszy niż komputer bo aplikacje są od siebie odizolowane. Malware wciąż jednak istnieje i jest prawdopodobny - zwłaszcza na słuchawkach z przestarzałym Androidem. 

**Paper wallet** - to przestarzała ale niestety wciąż popularna metoda "cold storage". Choć bezpieczniejsza niż trzymanie kluczy na Windowsie, niesie jednak ze sobą [szereg ryzyk](https://en.bitcoin.it/wiki/Paper_wallet), co sprawia że nie już jest zalecana. Paper wallet jest też szalenie niewygodny - nie daje możliwości częściowej wypłaty środków; w swoim modelu bezpieczeństwa zakłada uruchamianie komputera z "ulotnego" systemu typu Tails aby uniknąć ryzyk związanych z malware.
