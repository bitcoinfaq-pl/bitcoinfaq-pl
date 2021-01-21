---
title: "Jak zmniejszyć opłaty za transakcje w sieci Bitcoin?"
date: 2020-12-26
draft: false
tags:
  - bitcoin
---

<p style="text-align: center;"><span style="color: #f03838;">artykuł wolny od linków afiliacyjnych</span></p>

# TL;DR

Średnie opłaty za transakcje Bitcoin są dość wysokie, rzędu $2 - $6 na koniec 2020.
Jednak w wielu przypadkach można je zmniejszyć **nawet do kilkudziesięciu polskich groszy**.

Trzymaj środki na nowoczesnych adresach bech32.
Korzystaj z portfeli z obsługą RBF.
Ustawiaj symboliczne opłaty sieciowe jeśli transakcja nie jest pilna.

Pojęcia "opłata transakcyjna" i "opłata sieciowa" oznaczają to samo i używane są zamiennie.  

# Płać ze swojego portfela, nie z giełdy

Tylko wtedy masz niezbędną kontrolę nad transakcją i możliwość zdefiniowania dowolnie niskiej opłaty transakcyjnej.


# Przenieś swoje środki na adres bech32

W portfelach jest to określane jako **bech32** lub **native segwit**.

Transakcje z adresów bech32 (`bc1...`) są aż **~50% tańsze** niż transakcje z klasycznych adresów nie-segwitowych. Są również ~10% tańsze od transakcji z adresów segwit w wersji kompatybilnościowej (`3...`).

Z adresów bech32 można płacić na dowolne adresy. Odbiorca może mieć stary portfel.

Jednak przyjmować możemy bitcoiny wyłącznie z nowoczesnych portfeli obsługujących bech32. Jeśli to jest niepraktyczne w Twoim zastosowaniu, to jako minimum przenieś środki na adres segwit w wersji kompatybilnej wstecz. W portfelach jest ona określana jako **segwit compatibility** lub **P2SH**.

<small>
Technikalia: transakcje wydające segwitowe środki są tańsze bo dostają 75% zniżki na bajty podpisów (witness data).
Transakcje wydające segwitowe środki "z adresów" bech32 są dodatkowo tańsze, bo wtedy inputy zajmują mniej fizycznych bajtów.
</small>


# Ustaw RBF (Replace By Fee)

W ustawieniach portfela zdefiniuj, żeby wszystkie transakcje były wysyłane z flagą Replace By Fee. Nowoczesne portfele mają to domyślnie ustawione. Niestety, niektóre portfele nie dają takiej możliwości - należy ich unikać.

Ma to dwie konsekwencje:

* możliwość podbicia opłaty post-factum czyli w już wysłanej transakcji; ściślej, nowa transakcja z wyższą opłatą zastąpi starą jeszcze niepotwierdzoną
* transakcja RBF zostanie przez odbiorcę uznana dopiero po potwierdzeniu sieciowym; nie zadziała zatem natychmiastowe doładowanie komórki (tzw 0-conf)

Przykładowe nowoczesne portfele z obsługą RBF:

* [Wasabi](https://docs.wasabiwallet.io/)
* [Electrum](https://electrum.org/)
* [Samourai](https://samouraiwallet.com/)

Efektywnie, RBF daje dynamiczną kontrolę "tanio" versus "szybko".


# Ustaw opłatę sieciową na podstawie mempool.space

[Mempool.space](https://mempool.space/) to symulator pokazujący, które transakcje wejdą do następnego bloku.

Jeśli zależy Ci na szybkim potwierdzeniu, ustaw medianę opłaty sat/vb dla następnego bloku (zakreślone na czerwono poniżej).

![Example](/mempool.space.png)


# Brak pośpiechu? Ustaw 5 sat/vB

Najpierw upewnij się, że masz ustawiony RBF. Jeśli **nie zależy Ci na czasie**, ustaw niewielką opłatę sieciową **5 sat/vB**. Dla typowej transakcji bech32 oznacza to opłatę  ~**90 groszy za całą transakcję** według kursów z grudnia 2020. Czas oczekiwania to kilka dni w normalnych warunkach. Najczęściej takie transakcje potwierdzają się w weekend.

Technicznie transakcja jest prawidłowa już od 1 sat/vB. Takie super tanie transakcje również okresowo się potwierdzają. Może to jednak wymagać okresowego ponownego wysyłania jej do sieci - zatem opcja raczej dla świadomych i cierpliwych użytkowników.

Osobiście wysyłam niemal wszystkie transakcje z opłatą transakcyjną 2-5 sat/vB.


# Nie obawiaj się, że środki "utkną na zawsze"

Z przyzwyczajenia dałeś opłatę bliską zeru do przesłania swoich bitcoinowych oszczędności życia. Nagle cena BTC eksplodowała i sieć jest zupełnie zapchana. Twoja transakcja utknęła, bez żadnych widoków na potwierdzenie. Co teraz???

Po pierwsze, transakcję RBF możesz zawsze zastąpić nową transakcją, z wyższą opłatą. To jest najważniejszy mechanizm, jaki powinieneś stosować. Pierwsza i niezawodna linia obrony.

Po drugie, nawet jeśli zaniedbałeś RBF, możesz wykorzystać resztę z transakcji. W tej sytuacji przesyłasz resztę sam do siebie w nowej transakcji z wyższą ("podwójną") opłatą. Ta transakcja-dziecko efektywnie płaci za swojego rodzica (Child Pays For Parent - CPFP). Oczywiście, nie dotyczy to sytuacji, w której opróżniłeś cały portfel.

Po trzecie, nawet jeśli nie masz ani flagi RBF ani reszty w portfelu, do dyspozycji są komercyjne akceleratory jak https://pushtx.btc.com/ czy http://btcstrike.com/ w których możesz zapłacić "out of band" za potwierdzenie swojej transakcji. Akceleratory oferowane są przez mining poole - to one decydują które transakcje dostają sie do bloku.

Po czwarte, nawet jeśli zaniechałeś wszelkich najlepszych praktyk, wysłałeś z giełdy i nie masz teraz kontroli nad transakcją, a giełda zastosowała symboliczną opłatę i transakcja "wisi". Boisz się korzystać z akceleratorów bo może to scam. Otóż, giełda musi kiedyś odzyskać swoją resztę! Typowo giełda okresowo konsoliduje takie reszty. Wtedy giełda w transakcji konsolidującej efektywnie zrobi CPFP (nie ma innej możliwości), pociągając za sobą Twoją oczekującą transakcję. Tyle, że to może zająć tygodnie lub miesiące w skrajnym przypadku.

Po piąte, obciążenie sieci jest zawsze sinusoidalne. Podąża za ceną i hypem na kryptowaluty. Jakkolwiek beznadziejnie wygląda sytuacja, wcześniej czy później kolejka zostanie rozładowana i Twoja transakcja potwierdzi się, nawet jeśli miałoby to zająć miesiące. Bardziej prawdopodobne: transakcja wcześniej wypadnie z pamięci węzłów sieci Bitcoin. Wtedy będziesz mógł łatwo wydać te same środki w innej transakcji. Nie kasuj zatem starych kluczy!

Jest wiele warstw bezpieczeństwa: **dopóki masz klucze prywatne, środki nie zginą**.


# Podsumowanie

Od ręki możesz obniżyć wszystkie opłaty o połowę dzięki bech32.
Dodatkowo, dla transakcji które nie są pilne, możesz stosować zupełnie symboliczne opłaty.
Przed wysłaniem transakcji **ustaw RBF** aby mieć pełną kontrolę nad sytuacją i możliwość podbicia opłaty.

