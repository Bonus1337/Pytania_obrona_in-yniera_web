<template>
  <div :class="{ 'dark-mode': darkMode }">
    <button @click="darkMode = !darkMode">💡</button>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień podstawowe procesy instancji bazy danych Oracle i opisz rolę
        jednego z nich.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Proces serwera</li>
      <p>
        Odpowiada za komunikację między kientem a serwerem, przetwarzanie ządań
        uytkownika i udostępnianie danych z bazy danych.
      </p>

      <li>Proces tła</li>
      <p>
        Proces, który działa w tle i zajmuje się rónymi zadaniami, takimi jak
        kontrola integralności danych, zarządzanie pamięcią czy wykonywanie
        kopii zapasowych
      </p>

      <li>Proces zarządzania pamięcią</li>
      <p>
        Odpowiada za zarządzanie pamięcią w bazie danych i przypisywania jej do
        odpowiednich procesów
      </p>

      <p>
        Proces serwera jest bardzo wannym procesem, poniewa to on umozliwia
        uytkownikom korzystanie z bazy danych. Kiedy uytkownik chce uzyskać
        dostęp do danych, wysyła zapytanie do serwera, który następnie
        przetwarza ądanie i zwraca wynik. Bez procesu serwera nie byłoby mozliwe
        korzystanie z bazy danych
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień podstawowe struktury wchodzące w skład SGA instancji bazy Oracle
        i opisz rolę jednej z nich
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Buffer Cashe</li>
      <p>
        Pamięć podręczna, w której baza danych przechowuje dane wczytane z
        dysku. Jej rolą jest przyspieszenie dostępu do danych, poniewaz
        wczytywanie danych z tej pamięci jest szybsze niz z dysku. Zazwyczja
        przechowuje dane jak bloki, tabele, indeksy.
      </p>
      <li>Shared Pool</li>
      <p>
        Pamięć gdzie są przechowywane informacje o sesjach uytkowników oraz
        informacje o wykonywanych zapytaniach. Dzięki temu baza danych Oracle
        moe wykonywać szybciej zapytania uytkowników i bardziej efektownie.
      </p>
      <li>Redo Log Buffer</li>
      <p>
        Pamięć w której baza danych przechowuje informacje o zmiennych w danych,
        które muszą być zapisane na dysku. przechowuje informacje o zmiennych w
        czasie rzeczywistym, a następnie zapisuje je w Redo Log Files.
      </p>

      <p>
        Redo Log Buffer umoliwia bezpiecznie przechowywać informacje o zmianach
        w danych, które muszą być zapisane na dysku. W przypadku awarii lub
        utraty zasilania, baza danych moe przywrócić stan danych zapisanych w
        Redo Log Files
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień tryby zatrzymywania instancji bazy Oracle i opisz jeden z nich
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Shutdown Immediate</li>
      <p>
        Zatrzymuje bazę natychmiastowo. Wszystkie transakcje zostają zakończone,
        a sesja uytkowników zamknięta. Dane niezapisane zostają zapisane. Tryb
        stosowany w przypadku awarii / konserwacji
      </p>
      <li>Shutdown Normal</li>
      <p>
        Baza danych zostaje zamknięta ale nie kończy aktywnych transakcji. Sesje
        uytkowników zostają zamknięte ale baza czeka na zakończenie transakcji.
      </p>
      <li>Shutdown Immediate with Abort</li>
      <p>
        Natychmiastowo zatrzymuje baze ale bez czekania na zakonczenie aktywnych
        transakcji. Sesje uzytkownika zostaja zamkniete, a baza nie czeka na
        zakończenie transakcji
      </p>
      <p>
        W trybie Shutdown Immediate baza danych natychmiastowo zatrzymuje swoją
        pracę, wszystkie transakcje zostaną zakończone, a sesje użytkowników
        zostaną zamknięte. Wszystkie zmiany, które nie zostały jeszcze zapisane
        na dysku, zostaną zapisane, co zapobiegnie utracie danych. Tryb ten jest
        bardzo szybki i niezawodny, ale należy używać go ostrożnie, ponieważ
        aktywne transakcje mogą zostać przerwane, co może prowadzić do utraty
        danych lub niezgodności w bazie danych.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień fazy uruchamiania instancji bazy Oracle i opisz jeden z nich.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>STARTUP NOMOUNT</li>
      <p>
        Uruchamianie bazy danych ale bez montowania. Brak dostępności bazy
        danych dla uytkowników i nie mona wykonywać operacji na bazie
      </p>
      <li>STARTUP MOUNT</li>
      <p>
        Montowanie bazy danych ale bez otwarcia. Baza dostępna tylko dla
        administratorów bazy danych, którzy mogą wykonywać operacje na poziomie
        plików takie jak tworzenie usuwanie lub zmiana rozmiaru plików
      </p>
      <li>STARTUP OPEN</li>
      <p>Jest w pełni dostępna dla uytkowników</p>
      <p>
        STARTUP OPEN Faza uruchamiania instancji bazy danych. W tym trybie baza
        danych jest w pełni dostępna dla użytkowników, którzy mogą wykonywać
        operacje na danych.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów rolę jaką odgrywają przestrzenie tabel bazy danych Oracle</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Przestrzenie tabel w bazie danych Oracle są niezbędne dla efektywnego
        zarządzania pamięcią dyskową i umożliwiają uniknięcie problemów
        związanych z brakiem miejsca na dysku.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów pojęcie transakcji w realacyjncyh bazach danych</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Transakcja w bazach danych to jednostka pracy, która wykonuje jedno lub
        więcej poleceń SQL. Musi być wykonywana jako całość lub w ogóle nie być
        wykonywana, zgodnie z zasadami ACID. Dzięki temu zapewniają integralność
        danych i unikają problemów związanych z jednoczesnym dostępem do tych
        samych danych przez różne aplikacje lub użytkowników. W przypadku awarii
        lub błędu, baza danych cofa wszystkie zmiany dokonane przez transakcję
        do poprzedniego stabilnego stanu bazy danych (rollback).
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymień podstawowe grupy poleceń języka SQL i omów jedną z nich</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Polecenia DDL</li>
      <p>
        Słuą do tworzenia, modyfikowania i usuwania struktury bazy danych, takie
        jak tabele, widoki, indeksy
      </p>
      <li>Polecenia DML</li>
      <p>Słuą do dodawania, aktualizowania lub usuwania rekordów do tabeli</p>
      <li>Polecenia DQL</li>
      <p>Słuą do wyświetlania danych</p>
      <li>Polecenia DCL</li>
      <p>Słuą do zarządzania uprawnieniami dostępu do bazy danych</p>
      <p>
        Polecenia DDL, które służą do tworzenia, modyfikowania i usuwania
        struktury bazy danych. Przykładowo, polecenie CREATE TABLE służy do
        tworzenia nowej tabeli, a polecenie ALTER TABLE umożliwia modyfikację
        istniejącej tabeli, na przykład dodanie nowych kolumn lub zmiana typu
        danych. Usuwanie tabeli z bazy danych jest możliwe za pomocą polecenia
        DROP TABLE. Polecenia DDL są bardzo ważne, ponieważ pozwalają na
        definiowanie struktury bazy danych, która jest potrzebna do
        przechowywania i zarządzania danymi.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Omów pojęcie normalizacji w modelu relacyjnym i scharakteryzuj jedną z
        postaci normalnych
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Tabele w bazie danych są projektowane w taki sposób, aby kada tabela
        zawierała tylko unikalne dane, a zaleznosci miedzy nimi byly jasno
        okreslone i spójne.Jedną z postaci normalnych jest pierwsza postać
        normalna (1NF). Aby tabela spełniała wymagania pierwszej postaci
        normalnej, każda jej komórka powinna zawierać tylko pojedynczą wartość,
        a nie zestaw wartości lub tablice. Ponadto, tabela powinna mieć unikalny
        identyfikator (klucz główny), który jednoznacznie identyfikuje każdy
        rekord w tabeli. Dzięki temu minimalizowane są powtórzenia danych i
        eliminowane anomalie.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymień podstawowe operacje algebry realacji i omów jedną z nich</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Selekcja (SELECT)</li>
      <p>Wybiera określone rekordy z relacji spełniające określone warunki</p>
      <li>Projekcja (PROJECT)</li>
      <p>Wybiera określone kolumny z relacji</p>
      <li>Łączenie (JOIN)</li>
      <p>
        Łączy rekordy z dwóch lub więcej relacji na podstawie określonych
        warunków
      </p>
      <li>Różnica (DIFFERENCE)</li>
      <p>Zwraca rekordy z jednej relacji, które nie występują w drugiej</p>
      <li>Suma (UNION)</li>
      <p>
        Zwraca zbiór rekordów zawierający rekordy ze wszystkich relacji bez
        powtórzeń
      </p>
      <p>
        Selekcja wybiera określone rekordy z relacji spełniające określone
        warunki. Na przykład, polecenie SELECT * FROM tabela WHERE warunek
        wybierze wszystkie rekordy z tabeli, które spełniają określony warunek.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów rolę i typy indeksów w relacyjnych bazach danych</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Pozwalają na szybsze wyszukiwanie i sortowanie rekordów w tabelach bazy
        danych.
      </p>
      <li>Indeks podstawowy (Primary Index)</li>
      <p>
        Torzony na kolumnie, która jest kluczem głównym tabeli. Zapewnia
        unikatowość wartości w kolumnie i przyspiesza wyszukiwanie rekordów po
        kluczy głownym
      </p>
      <li>Indeks złożony (Secondary Index)</li>
      <p>
        Umoliwia szybkie wyszukiwanie i sortowanie rekordów po wartościach w
        kolumnach indeksowych
      </p>
      <li>Indeks bitmapowy (Bitmap Index)</li>
      <p>
        Indeks bitmapowy tworzy mapę bitową dla każdej wartości w kolumnie i
        umożliwia szybkie wyszukiwanie rekordów zawierających określone
        wartości.
      </p>
      <li>Indeks funkcjonalny (Function-based Index)</li>
      <p>
        Tworzony na podstawie funkcji matematycznych lub logicznych stosowanych
        na wartościach w kolumnie. Umożliwia szybkie wyszukiwanie i sortowanie
        rekordów po wartościach uzyskiwanych przez funkcje.
      </p>
      <li>Indeks pełnotekstowy (Full-text Index)</li>
      <p>
        Stosowany w przypadku, gdy tabela zawiera duże ilości tekstu. Indeks
        pełnotekstowy umożliwia szybkie wyszukiwanie rekordów po określonych
        słowach lub frazach w tekście.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymień podstawowe moduły klasy ERP i omów jeden z nich</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        ERP (Enterprise Resource Planning) to system informatyczny, który
        integruje różne procesy biznesowe w organizacji, takie jak zarządzanie
        finansami, produkcją, sprzedażą, logistyką, magazynem czy personelem.
        Podstawowe moduły klasy ERP to:
      </p>
      <li>Moduł finansowo-księgowy</li>
      <p>
        umoliwia prowadzenie ewidencji finansowej, w tym księgowości, budetów,
        płatności, fakturowania oraz raportowania finansowego.
      </p>
      <li>Moduł produkcji</li>
      <p>
        Pozwala na planowanie, kontrolę i optymalizację procesów produkcyjnych
      </p>
      <li>Moduł sprzedazy</li>
      <p>
        Umozliwia zarządzanie procesami sprzeday, w tym ofertami, zamówieniami,
        kontraktami, a take relacjami z klientem
      </p>
      <li>Moduł personalny</li>
      <p>
        Umoliwia zarządzanie kadrami, planowanie pracy, wynagrodzeniami i
        szkoleniami
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień typy procesów roboczych w systemie SAP NetWeaver i omów rolę
        jednego z nich.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Procesy biznesowe</li>
      <p>
        Sekwencja powiązanych ze sobą działań biznesowych, które pozwalaną na
        realizację określonego celu. Ich aytomatyzacja i monitorowanie zapewnia
        zwiększenie efektywności i kontroli nad działanami biznesowymi
      </p>
      <li>Proces Integralny</li>
      <p>
        Integrują róne aplikacje i systemy w organizacji, umoliwiając
        przesyłanie danych między nimi.
      </p>
      <li>Procesy automatyzacji</li>
      <p>
        Proces w którym zadania wykonywane przez uzytkowników są zautomatyzowane
        przy pomocy reguł biznesowych lub algorytmów
      </p>
      <p>
        Rolą procesu integracji jest umoliwienie wymiany danych między rónymi
        aplikacjami i systemami w organizacji. Dzięki temu moliwe jest
        zapewnienie jednolitej i spójnej bazy danych, co przekłada się na
        poprawę jakości informacji i zwiększenie efektywności działąń
        biznesowych. W ramach procesu integracyjnego w SAP NetWeaver mozna
        wykorzystać rózne standardy i protokoły jak SOAP, HTTP, FTP. Pozwalają
        one na łatwą integrację z róznymi aplikacjami i systemami
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień typy użytkowników w systemie SAP NetWeaver i omów rolę jednego z
        nich.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Użytkownik końcowy</li>
      <p>
        Osoba, która korzysta z róznych aplikacji SAP w celu wykonania
        określonych zadań biznesowych
      </p>
      <li>Administrator systemu</li>
      <p>
        Osoba odpowiedzialna za zarządzanie i konfiguracje systemu SAP
        NetWeaver. Instaluje i aktualizuje system, zarządza uzytkownikami i
        rolami.
      </p>
      <li>Deweloper</li>
      <p>
        Osoba która tworzy i rozwija aplikacje. Zajmują się programowaniem w
        języku ABAP, projektowaniem interfejsów uzytkownika i testami
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień typy urządzeń w podsystemie wydruku w systemie SAP NetWeaver i
        omów rolę jednego z nich.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Drukarka lokalna</li>
      <p>
        Urządzenie podłączone bezpośrednio do komputera uzytkownika. Drukarka
        lokalna moze być wykorzystywana do wydruku raportów, formularzy i innych
        dokumentów z systemu SAP
      </p>
      <li>Drukarka sieciowa</li>
      <p>
        Urządzenie podłączone do sieci komputerowej, która umozliwia
        wykorzystywanie przez wiele uzytkownikow w roznych miejscach
      </p>
      <li>Drukarka SAP</li>
      <p>
        Urzadzenie specjalnie zaprojektowane do wydruku dokumentow z systemu
        SAP. Pozwalaja na drukowanie raportow faktur, etykiet i innych
        dokumentow w sposob zoptymalizowany pod katem specyfikacji SAP
      </p>
      <p>
        Drukarka sieciowa - umozliwia wielu uzytkownikom korzystanie z jednego
        urzadzenia, co przyczynia sie do zwiekszenia wydajnosci i oszczędności w
        firmie. Pozwala na drukowanie dokumentów z dowolnego miejsca w sieci, co
        ułatwia pracę zespołową i umozliwia szybsze przetwarzanie infrmacji.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień składowe czasu odpowiedzi w systemie SAP NetWeaver i omów jedną z
        nich
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Czas przetwarzania serwera</li>
      <p>
        Czas który serwer potrzebuje na przetworzenie zapytania i wygenerowanie
        odpowiedzi. Zalezy od mocy obliczeniowej serwera oraz od liczby i
        złozoności wykonywanych operacji.
      </p>
      <li>Czas przetwarzania sieciowego</li>
      <p>
        Czas który potrzebny jest na przesłanie danych między kientem a serwerem
        przez sieć. Zaley od przepustowości sieci oraz wielkości przesyłanych
        danych.
      </p>
      <li>Czas przetwarzanie klienta</li>
      <p>
        Czas który potrzebny jest na przetworzenie danych przez klienta, np.
        wyświetlenie wyników zapytania lub na wykonanie obliczeń po stronie
        klienta.
      </p>
      <p>
        Przetwarzanie serwera jest to czas, który jest potrzeby na przetworzenie
        zapytania i wygenerowanie odpowiedzi przez serwer. Składowa ta moze być
        uzalezniona od wielu czynników, takich jak załoznosc wykonywanych
        operacji, obciązenie serwera, konfiguracji serwera oraz ilosci dostępnej
        pamięci.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Opóźnienie propagancji; transmisji; przetwarzania; kolejkowania.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Opóźnienie propagacji</li>
      <p>
        Czas potrzebny na przesłanie sygnału lub informacji przez medium
        transmisyjne, np. przewód, kabel czy falę radiową. Opóźnienie zalezy od
        długości trasy, jaką musi pokonać zygnał, a takze od szybkosci
        rozchodzenia sie sygnalu w danym medium.
      </p>
      <li>Opóźnienie transmisji</li>
      <p>
        Czas potrzebny na wysłanie bitów danych przez medium transmisyjne.
        Opóźnienie transmisji zalezy od szybkości transmisji.
      </p>
      <li>Opóźnienie przetwarzania</li>
      <p>
        Czas potrzebny na przetworzenie danych przez urządzenie, np procesor,
        pamięć podręczną, czy kartę sieciową.
      </p>
      <li>Opóźnienie kolejkowania</li>
      <p>
        Czas potrzebny na oczekiwanie w kolejce do przetwarzania danych przez
        urządzenie np. router, przełącznik sieciowy czy serwer.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Co to jest Servie Worker i opisz jego funkcje.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Service Worker to technologia stosowana w aplikacjach webowych,
        umożliwiająca tworzenie procesów w tle, które działają niezależnie od
        samej strony internetowej i mają zdolność do obsługi zapytań sieciowych
        oraz zarządzania pamięcią podręczną.
      </p>
      <p>Główne funkcje Service Workera to:</p>
      <li>Obsługa zapytań sieciowych offline</li>
      <p>
        Service Worker może przechowywać kopie danych na urządzeniu użytkownika,
        co pozwala na wyświetlanie treści nawet bez połączenia z siecią.
      </p>
      <li>Zarządzanie pamięcią podręczną</li>
      <p>
        Dzięki Service Workerowi, aplikacja może przechowywać pewne dane w
        pamięci podręcznej, co znacznie przyspiesza ładowanie strony i zmniejsza
        ilość zapytań do serwera.
      </p>
      <li>Powiadomienia</li>
      <p>
        Service Worker pozwala na wyświetlanie powiadomień użytkownikowi, nawet
        gdy strona internetowa jest zamknięta.
      </p>
      <li>Przetwarzanie tła</li>
      <p>
        Service Worker umożliwia wykonywanie operacji w tle, np. synchronizacja
        danych z serwerem lub aktualizacja aplikacji.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Omów optymalną listę kontrolną progresywnej aplikacji internetowej.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Optymalna lista kontrolna progresywnej aplikacji internetowej (PWA) to
        zestaw wskazówek i najlepszych praktyk dla twórców aplikacji, którzy
        chcą zapewnić jak najlepsze wrażenia użytkownikom.
      </p>
      <li>Responsywność</li>
      <p>
        Strona internetowa powinna być responsywna, co oznacza, że powinna
        dostosowywać się do różnych rozmiarów ekranów i urządzeń.
      </p>
      <li>Dostępność offline</li>
      <p>
        PWA powinna umożliwiać korzystanie z aplikacji bez połączenia z
        internetem, dzięki możliwości przechowywania danych w pamięci
        podręcznej.
      </p>
      <li>Szybkość ładowania</li>
      <p>
        Strona internetowa powinna ładować się szybko, co zwiększa szanse na
        pozyskanie i utrzymanie użytkowników.
      </p>
      <li>Użyteczność</li>
      <p>
        PWA powinna być intuicyjna w użyciu, a funkcje powinny być łatwo
        dostępne i zrozumiałe dla użytkowników.
      </p>
      <li>Bezpieczeństwo</li>
      <p>
        Strona internetowa powinna być zabezpieczona przed atakami, a
        użytkownicy powinni czuć się bezpiecznie podczas korzystania z
        aplikacji.
      </p>
      <li>Dostępność na urządzeniach mobilnych</li>
      <p>
        PWA powinna działać bezproblemowo na różnych urządzeniach mobilnych, a
        interfejs powinien być zaprojektowany z myślą o użytkownikach
        korzystających z ekranów dotykowych.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów wytażenia warunkowe.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Wyrażenia warunkowe to instrukcje programistyczne, które pozwalają na
        wykonanie pewnych czynności w zależności od spełnienia określonych
        warunków
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Co to jest przeciążanie metod.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Przeciążanie metod to mechanizm programowania obiektowego, który pozwala
        na definiowanie wielu metod o tej samej nazwie, ale różniących się listą
        parametrów.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Czym są ptętle - pętla while i do while.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Pętla "while" to instrukcja programistyczna, która wykonuje blok kodu,
        dopóki określony warunek jest prawdziwy. Warunek jest sprawdzany przed
        wykonaniem bloku kodu. Jeśli warunek jest fałszywy już na początku, blok
        kodu nie zostanie wykonany ani razu.
      </p>
      <p>
        Pętla "do while" to instrukcja programistyczna, która wykonuje blok kodu
        przynajmniej raz, a następnie sprawdza, czy warunek jest prawdziwy, aby
        określić, czy kontynuować wykonanie bloku kodu. Jeśli warunek jest
        fałszywy, pętla zostanie przerwana.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Podaj Międzynarodowy Standard ISO, który opisuje ISO C++.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        MISO C++ to standard języka programowania C++, który jest opisany przez
        Międzynarodową Organizację Normalizacyjną (ISO). Standard ten został
        opublikowany jako ISO/IEC 14882 w 1998 roku, a następnie został
        zaktualizowany w 2003 roku (ISO/IEC 14882:2003) oraz 2011 roku (ISO/IEC
        14882:2011).
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Podaj różnicę między operatorem "==" a "='.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Operator "==" (równa się) jest operatorem porównania w językach
        programowania, który zwraca wartość logiczną "true" lub "false" w
        zależności od tego, czy dwa wyrażenia są równe sobie. Operator ten jest
        używany do porównywania wartości, które są przechowywane w zmiennych,
        obiektach lub wyrażeniach.
      </p>
      <p>
        Operator "=" (przypisanie) jest operatorem przypisania, który służy do
        przypisywania wartości jednej zmiennej lub obiektu do innej zmiennej lub
        obiektu. Operator ten nie porównuje wartości, ale zamiast tego
        przypisuje wartość z prawej strony do zmiennej lub obiektu po lewej
        stronie.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Jakie jest zastosowanie funkcji getchar()?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        W skrócie, funkcja getchar() jest używana do wczytywania pojedynczych
        znaków z wejścia standardowego i ma wiele zastosowań w programowaniu, od
        pobierania danych od użytkownika do przetwarzania plików tekstowych.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymień i omów planistów w systemie operacyjnym.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Planista czasowy</li>
      <p>
        Alokuje procesor na podstawie czasu przydzielonego dla każdego procesu.
        Zwykle używa się go w systemach czasu rzeczywistego.
      </p>
      <li>Planista zdarzeniowy</li>
      <p>
        Alokuje procesor na podstawie zdarzeń, takich jak żądania
        wejścia-wyjścia, wywołania systemowe lub przerwania.
      </p>
      <li>Planista priorytetowy</li>
      <p>
        Alokuje procesor na podstawie priorytetów procesów. Procesy o wyższym
        priorytecie mają pierwszeństwo w dostępie do procesora.
      </p>
      <li>Planista proporcjonalny</li>
      <p>
        Alokuje procesor w sposób proporcjonalny do przypisanych mu udziałów
        zasobów.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      darkMode: true,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

h1 {
  font-size: 28px;
  font-weight: bold;
  margin: 20px 0;
}

h2 {
  font-size: 24px;
  font-weight: bold;
  margin: 10px 0;
}

p {
  font-size: 16px;
  margin: 5px 0;
}

.question {
  background-color: #eee;
  padding: 10px;
}

.answer {
  background-color: #f7f7f7;
  padding: 10px;
  margin-left: 20px;
}
ul {
  list-style: disc;
  margin-left: 20px;
  padding-left: 20px;
}

ol {
  list-style: decimal;
  margin-left: 20px;
  padding-left: 20px;
}

li {
  font-size: 16px;
  margin: 5px 0;
  padding-top: 20px;
}
div.dark-mode {
  background-color: #333;
  color: #fff;
}

.question.dark-mode {
  background-color: #444;
}

.answer.dark-mode {
  background-color: #555;
}

ul.dark-mode {
  color: #fff;
}

ol.dark-mode {
  color: #fff;
}

li.dark-mode {
  color: #fff;
}
.dark-mode-toggle {
  background-color: transparent;
  border: none;
  color: #fff;
  cursor: pointer;
  font-size: 24px;
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 9999;
}

.dark-mode-toggle:hover {
  color: #f0f0f0;
}

.dark-mode-toggle i {
  transition: transform 0.3s ease-in-out;
}

.dark-mode-toggle.dark-mode i {
  transform: rotate(180deg);
}
</style>
