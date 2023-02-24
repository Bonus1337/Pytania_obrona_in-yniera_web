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
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymień stany procesów systemach operacyjnych Microsoft.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Stan gotowości</li>
      <p>Proces jest gotowy do wykonania i oczekuje na przydział procesora.</p>
      <li>Stan wykonywania</li>
      <p>Proces jest aktualnie wykonywany przez procesor.</p>
      <li>Stan oczekiwania</li>
      <p>
        Proces oczekuje na zasoby lub na wykonanie pewnej operacji, np. oczekuje
        na zdarzenie wejścia-wyjścia.
      </p>
      <li>Stan zawieszenia</li>
      <p>
        Proces jest zawieszony, czyli nie jest wykonywany ani nie oczekuje na
        żadne zasoby.
      </p>
      <li>Stan zakończenia</li>
      <p>Proces zakończył swoje działanie.</p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymień stany procesów systemów unixowych.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Stan gotowości</li>
      <p>Proces jest gotowy do wykonania i oczekuje na przydział procesora.</p>
      <li>Stan wykonywania</li>
      <p>Proces jest aktualnie wykonywany przez procesor.</p>
      <li>Stan oczekiwania</li>
      <p>
        Proces oczekuje na zasoby lub na wykonanie pewnej operacji, np. oczekuje
        na zdarzenie wejścia-wyjścia.
      </p>
      <li>Stan zatrzymania</li>
      <p>Proces został zatrzymany i nie wykonuje żadnych operacji.</p>
      <li>Stan uśpienia</li>
      <p>
        Proces został uśpiony i oczekuje na zdarzenie, które spowoduje jego
        wybudzenie.
      </p>
      <li>Stan zombie</li>
      <p>
        Proces, który zakończył swoje działanie, ale jeszcze nie został usunięty
        z systemu.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów główne typy barw ze względu na skojarzenia.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Barwy ciepłe</li>
      <p>
        Czerwień, pomarańcz, żółć. Zwykle kojarzone z energią, namiętnością,
        pozytywnym nastawieniem, ale też niekiedy z agresją lub ryzykiem.
      </p>
      <li>Barwy zimne</li>
      <p>
        Niebieski, zielony, fiolet. Często kojarzone z spokojem, harmonią,
        naturą, ale także z obojętnością lub depresją.
      </p>
      <li>Barwy jaskrawe</li>
      <p>
        Fiolet, różowy, jaskrawa żółć. Wywołują skojarzenia z radością, zabawą,
        entuzjazmem, ale też mogą być uciążliwe dla oczu lub wywoływać uczucie
        chaosu.
      </p>
      <li>Barwy pastelowe</li>
      <p>
        Jasny róż, błękit, miętowy. Kojarzone z delikatnością, subtelnością,
        romantyzmem, ale też mogą być uważane za zbyt łagodne lub nudne.
      </p>
      <li>Barwy ziemi</li>
      <p>
        Brąz, khaki, beż. Często kojarzone z naturą, stabilnością,
        naturalnością, ale też mogą wywoływać skojarzenia z przestarzałością lub
        nudą.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Jak działa algorym bulge.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Algorytm Bulge wyróżnia się tym, że pozwala na zmniejszenie liczby
        operacji potrzebnych do wyznaczenia wartości własnych i wektorów
        własnych w porównaniu z innymi algorytmami, szczególnie gdy macierz
        wejściowa ma bardzo dużą liczbę wierszy i kolumn. Algorytm ten
        wykorzystywany jest w wielu dziedzinach nauki i technologii, w tym w
        przetwarzaniu sygnałów, analizie danych, fizyce i chemii.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów modelowanie w grafice 3D.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Proces modelowania polega na tworzeniu kształtu obiektu poprzez
        dodawanie, usuwanie i modyfikowanie geometrii. Dostępne są różne
        narzędzia pozwalające na dokładne kształtowanie modelu, w tym narzędzia
        do rysowania, wycinania, skalowania, obracania, czy dodawania tekstur.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymień pradygmaty programowania i omów szczegółowo jeden wybrany</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Programowanie imperatywne</li>
      <p>
        Program składa się z sekwencji instrukcji, które są wykonywane po kolei.
        Programista określa kroki, jakie powinien wykonać program, aby osiągnąć
        pożądany wynik. Podstawową strukturą kontrolną w tym paradygmacie jest
        instrukcja warunkowa (if) oraz pętla (for, while). Programowanie
        imperatywne koncentruje się na tym, co program ma zrobić, a nie na tym,
        jak to zrobić.
      </p>
      <li>Programowanie funkcyjne</li>
      <p>
        Program składa się z wywoływania funkcji, a nie z sekwencji instrukcji.
        Funkcje nie zmieniają stanu programu i nie mają efektów ubocznych, tzn.
        działają tylko na swoich argumentach i zwracają wartość. Programowanie
        funkcyjne koncentruje się na deklaratywnym opisie problemów, a nie na
        tym, jak te problemy mają zostać rozwiązane.
      </p>
      <li>Programowanie obiektowe</li>
      <p>
        Program składa się z obiektów, które mają swoje własności (atrybuty)
        oraz metody (operacje, które można wykonać na obiekcie). Programowanie
        obiektowe koncentruje się na modelowaniu świata rzeczywistego poprzez
        obiekty i relacje między nimi.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wzorzec programowania SOLID.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Zastosowanie zasad SOLID w projektowaniu aplikacji pomaga w tworzeniu
        elastycznego i łatwego w utrzymaniu kodu, co przekłada się na
        oszczędność czasu i pieniędzy w dalszej fazie rozwoju aplikacji.
      </p>
      <li>Single Responsibility Principle</li>
      <p>
        Asada pojedynczej odpowiedzialności: każda klasa powinna mieć tylko
        jedno, jasno zdefiniowane zadanie. Dzięki temu klasa jest łatwiejsza w
        utrzymaniu i zmianach.
      </p>
      <li>Open-Closed Principle</li>
      <p>
        Zasada otwarte-zamknięte: klasy powinny być otwarte na rozszerzenie, ale
        zamknięte na modyfikację. Zmiana zachowania klasy powinna odbywać się
        poprzez dziedziczenie i polimorfizm, a nie przez modyfikowanie
        istniejącego kodu.
      </p>
      <li>Liskov Substitution Principle</li>
      <p>
        Zasada podstawienia Liskov: obiekt klasy podrzędnej powinien być w
        stanie zastąpić obiekt klasy nadrzędnej bez zmiany spodziewanego
        zachowania programu. Innymi słowy, dziedziczenie powinno być używane
        tylko wtedy, gdy klasy naprawdę mają wspólną cechę i działają w sposób
        spójny.
      </p>
      <li>Interface Segregation Principle</li>
      <p>
        Zasada segregacji interfejsów: klienci nie powinni zależeć od
        interfejsów, których nie potrzebują. Zamiast tego powinny być tworzone
        bardziej specyficzne interfejsy, które zawierają tylko te metody, które
        są potrzebne w danym kontekście.
      </p>
      <li>Dependency Inversion Principle</li>
      <p>
        Zasada odwrócenia zależności: zależności między modułami powinny być
        oparte na abstrakcjach, a nie na konkretnych implementacjach. Innymi
        słowy, moduł wyższego poziomu nie powinien zależeć od modułu niższego
        poziomu, ale od abstrakcji, które zdefiniowały te moduły.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Scharakteryzuj obiekt typu pierwszoklasowego, podaj jego własności.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Obiekt typu pierwszoklasowego to pojęcie z dziedziny programowania
        obiektowego. Oznacza ono, że w danym języku programowania obiekty są
        traktowane jak wartości pierwszorzędne, podobnie jak liczby czy ciągi
        znaków. Oznacza to, że obiekty mogą być przekazywane jako argumenty
        funkcji, zwracane jako wyniki funkcji, a także przechowywane w
        zmiennych.
      </p>
      <li>Przypisywanie</li>
      <p>Można przypisać wartość obiektu do zmiennej.</p>
      <li>Przekazywanie jako argument</li>
      <p>Można przekazać obiekt jako argument funkcji.</p>
      <li>Zwracanie</li>
      <p>Funkcja może zwrócić obiekt jako wynik.</p>
      <li>Tworzenie dynamiczne</li>
      <p>Można tworzyć obiekty dynamicznie w trakcie działania programu.</p>
      <li>Klasa anonimowa</li>
      <p>
        Możliwe jest definiowanie obiektów bezpośrednio bez definiowania klasy.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów cechę oprogramowania : dopuszczalność.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Dopuszczalność to jedna z cech oprogramowania, która oznacza, że program
        spełnia wymagania określone w danym kontekście, np. zgodność z
        regulacjami prawno-technicznymi, standardami, politykami organizacji
        itp. Oprogramowanie dopuszczalne musi być zgodne z wszelkimi wymaganiami
        formalnymi, które określają, jakie funkcje i cechy powinny być obecne
        lub nieobecne w programie, jakie formaty danych są akceptowalne, jakie
        procedury testowania i weryfikacji należy stosować itp.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień cztery podstawowe działalności wspólne dla wszystkich procesów
        wytwarzania oprogramowania.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Planowanie</li>
      <p>
        Określenie celów, zadań i wymagań projektu, a także określenie
        harmonogramu i budżetu projektu.
      </p>
      <li>Analiza</li>
      <p>
        Zrozumienie wymagań użytkownika, stworzenie specyfikacji funkcjonalnej,
        a także określenie ograniczeń projektowych.
      </p>
      <li>Projektowanie</li>
      <p>
        Tworzenie projektu oprogramowania, takiego jak projekt systemu, projekt
        interfejsu użytkownika, projekt bazy danych, itp.
      </p>
      <li>Implementacja</li>
      <p>
        Faktyczne tworzenie i kodowanie oprogramowania, testowanie oraz
        integracja różnych modułów oprogramowania w całość.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Omów Perspektywę 4+1 - przyporządkuj odpowiednie rodzaje diagramów
        języka UML
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Perspektywa 4+1 to podejście do modelowania architektury systemu, które
        składa się z pięciu perspektyw lub widoków, a każda z perspektyw
        reprezentowana jest przez odpowiedni rodzaj diagramu UML.
      </p>
      <li>Widok logiczny</li>
      <p>
        Reprezentowany przez diagram klas - opisuje strukturę klas, relacje
        między nimi i ich zachowanie.
      </p>
      <li>Widok procesowy</li>
      <p>
        Reprezentowany przez diagramy sekwencji, diagramy aktywności, diagramy
        stanów - opisuje zachowanie systemu w czasie.
      </p>
      <li>Widok fizyczny</li>
      <p>
        Reprezentowany przez diagramy komponentów, diagramy wdrożenia - opisuje
        sposób, w jaki system jest fizycznie zorganizowany i wdrażany.
      </p>
      <li>Widok użytkownika</li>
      <p>
        Reprezentowany przez diagramy przypadków użycia - opisuje funkcjonalność
        systemu z perspektywy użytkownika
      </p>
      <li>Widok scenariuszy</li>
      <p>
        Reprezentowany przez scenariusze - opisuje interakcje między
        użytkownikami a systemem oraz między różnymi częściami systemu.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Omów elementy, które mają wplyw na postrzeganie obrazów jako wizerunków
        scen trójwymiarowych.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Perspektywy</li>
      <p>
        Kąt widzenia, z którego patrzymy na scenę, wpływa na proporcje obiektów
        i na ich pozycję względem siebie.
      </p>
      <li>Światła</li>
      <p>
        Oświetlenie sceny wpływa na kolor i intensywność obiektów, a także na
        cienie, które rzucane są na tle.
      </p>
      <li>Tekstury</li>
      <p>
        Detale i faktury obiektów mogą wpływać na to, jak odbieramy ich głębię i
        trójwymiarowość.
      </p>
      <li>Koloru</li>
      <p>
        Odpowiednio dobrana kolorystyka obiektów może pomóc w ich percepcji jako
        trójwymiarowych. Na przykład, ciemniejsze kolory mogą sugerować cienie,
        a jaśniejsze - odbicia świetlne.
      </p>
      <li>Rozdzielczości</li>
      <p>
        Im wyższa rozdzielczość obrazu, tym więcej detali i lepsza percepcja
        głębi.
      </p>
      <li>Ruchu</li>
      <p>
        Animacje i efekty ruchu mogą pomóc w tworzeniu złudzenia
        trójwymiarowości.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wskaż różnice między forward raytracing a backward raytracing.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Główną różnicą między forward raytracing a backward raytracing jest to,
        że pierwsza metoda wysyła promienie światła od źródła do kamery, a druga
        metoda od kamery do sceny. Forward raytracing jest szybszy i mniej
        skomplikowany, ale nie daje tak realistycznych efektów, jak backward
        raytracing, który jest bardziej czasochłonny, ale daje bardziej
        realistyczne wyniki.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów współrzędne sferyczne w grafice komputerowej.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Współrzędne sferyczne to sposób określenia położenia punktu w
        trójwymiarowej przestrzeni, w którym używane są trzy wartości: promień
        r, kąt azymutu θ (mierzony od osi x w płaszczyźnie xy) oraz kąt elewacji
        φ (mierzony od osi z).
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Podaj cztery warunki bezpieczeństwa systemu komputerowego.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Autoryzacja i uwierzytelnienie użytkowników</li>
      <p>
        By mieć dostęp do systemu, użytkownik musi zostać uwierzytelniony, a
        następnie autoryzowany, aby uzyskać dostęp do określonych zasobów.
      </p>
      <li>Ochrona przed zagrożeniami zewnętrznymi</li>
      <p>
        System musi być chroniony przed atakami z zewnątrz, takimi jak hakerzy,
        wirusy, złośliwe oprogramowanie, ataki DoS itp.
      </p>
      <li>Kontrola dostępu</li>
      <p>
        System musi umożliwiać określenie, kto ma dostęp do różnych zasobów,
        jakie działania są dozwolone i w jaki sposób mają być realizowane.
      </p>
      <li>Ciągła aktualizacja i monitorowanie</li>
      <p>
        System musi być aktualizowany, aby uwzględniać nowe zagrożenia, a także
        monitorowany w celu wykrywania i usuwania potencjalnych zagrożeń oraz
        reagowania na nie w sposób szybki i skuteczny.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Scharakteryzuj działanie IDS.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        IDS to skrót od Intrusion Detection System, czyli systemu wykrywania
        włamań. Jest to rodzaj oprogramowania lub sprzętu, którego celem jest
        monitorowanie systemu komputerowego w celu wykrycia i reagowania na
        próby nieautoryzowanego dostępu lub ataku. IDS działa na zasadzie
        analizy ruchu sieciowego oraz zachowań systemowych, a jego zadaniem jest
        wykrycie podejrzanych zdarzeń oraz powiadomienie administratora o tym
        fakcie
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Omow rolę API w bezpieczeństwie sieci i systemów teleinformatycznych.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Przede wszystkim umożliwiają one dostęp do funkcjonalności zewnętrznych
        systemów, usług i aplikacji, co może być wykorzystane do zwiększenia
        bezpieczeństwa poprzez integrację z narzędziami monitorującymi,
        systemami zarządzania tożsamością, firewallami czy systemami wykrywania
        ataków.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Omów nieprzenośność programów między różnymi procesorami lub
        niewykorzystywanie przez aplikacje wszystkich możliwości procesora.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Nieprzenośność programów między różnymi procesorami lub
        niewykorzystywanie przez aplikacje wszystkich możliwości procesora
        wynika z różnic w architekturze procesorów i sposobie działania
        poszczególnych instrukcji. W praktyce oznacza to, że programy pisane dla
        jednej platformy sprzętowej mogą nie działać na innej platformie, a
        nawet jeśli działają, to mogą działać wolniej lub nie wykorzystywać
        wszystkich możliwości procesora.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Co to jest chmura natywna?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Chmura natywna to koncepcja, w której aplikacje są tworzone i wdrażane z
        myślą o środowisku chmurowym, wykorzystując do tego celu narzędzia i
        usługi oferowane przez dostawców chmury publicznej. W odróżnieniu od
        tradycyjnych aplikacji, które są projektowane do działania w konkretnym
        środowisku, aplikacje natywne chmury są elastyczne, skalowalne i mogą
        działać w różnych chmurach. W ten sposób zapewniają one większą
        wydajność, dostępność i niezawodność w porównaniu do tradycyjnych
        aplikacji
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Co to jest asocjacja?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        W programowaniu obiektowym, asocjacja to relacja między dwoma klasami,
        która określa, że jedna klasa ma powiązania z obiektami z drugiej klasy.
        Asocjacja może być jednostronna lub obustronna, a także może mieć
        atrybuty i operacje. Może też posiadać kierunek, który określa, która
        klasa jest "właścicielem" relacji, a która jest "podrzędną". Asocjacje
        są ważnym narzędziem w projektowaniu obiektowym, pozwalającym na
        wyrażenie zależności między klasami i modelowanie rzeczywistych
        sytuacji.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów znaczenie wartości progowej w procesie decyzyjnym.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Wartość progowa to wartość graniczna, która decyduje o podjęciu
        konkretnej decyzji. W procesie decyzyjnym wartość progowa jest stosowana
        do porównywania wyników lub wskaźników z ustalonym poziomem akceptacji
        lub odrzucenia. Jeśli wynik lub wskaźnik przekracza wartość progową,
        podejmowana jest jedna decyzja, a jeśli nie, podejmowana jest inna
        decyzja.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omów kategorie decyzji wedlug stopnia ryzyka?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>Decyzje według stopnia ryzyka dzielimy na:</p>
      <li>Decyzje pewne</li>
      <p>
        Decyzje, które podejmujemy w oparciu o fakt, że znamy wszystkie możliwe
        wyniki i ich konsekwencje. W takim przypadku podejmujemy decyzje bez
        wahania, ponieważ jesteśmy pewni, że podjęcie określonego działania
        przyniesie oczekiwane skutki.
      </p>
      <li>Decyzje ryzykowne</li>
      <p>
        Decyzje, które podejmujemy w warunkach niepewności, gdzie nie znamy
        wszystkich możliwych wyników. W takim przypadku, podjęcie określonej
        decyzji wiąże się z ryzykiem. W celu zminimalizowania ryzyka, należy
        dokładnie przeanalizować dostępne opcje i oszacować ich konsekwencje.
      </p>
      <li>Decyzje niepewne</li>
      <p>
        Decyzje, które podejmujemy w warunkach braku wiedzy lub informacji. W
        takim przypadku podejmujemy decyzję na podstawie domysłów lub intuicji,
        ponieważ nie posiadamy wystarczającej ilości informacji, aby dokonać
        racjonalnej analizy sytuacji. W takim przypadku, podjęcie decyzji wiąże
        się z dużym ryzykiem i zawsze istnieje szansa na niepowodzenie.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Podaj dwa konkretne przyklady (nie tylko dziedziny) zastosowań systemów
        wbudowanych.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Urządzenia AGD</li>
      <p>
        Systemy wbudowane znajdują zastosowanie w urządzeniach AGD, takich jak
        pralki, lodówki, kuchenki mikrofalowe, które sterowane są przy pomocy
        mikrokontrolerów. Dzięki temu można zautomatyzować procesy, poprawić
        wydajność i bezpieczeństwo urządzeń.
      </p>
      <li>Motoryzacja</li>
      <p>
        Systemy wbudowane znajdują szerokie zastosowanie w motoryzacji, np. w
        samochodach. Kontrolują one wiele funkcji, takich jak sterowanie
        silnikiem, hamulcami, systemem audio i nawigacją. Systemy te są również
        odpowiedzialne za bezpieczeństwo, np. poprzez systemy ABS czy ESP.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Jakie dwa rodzaje połączeń ze światem zewnętrznym (i rodzaje
        odpowiadających im sygnałów) sa charakterystyczne dla komputerowych
        systemów wbudowanych?
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Wejścia/wyjścia cyfrowe</li>
      <p>
        (GPIO) służą do komunikacji z urządzeniami i czujnikami, które generują
        sygnały cyfrowe, takie jak przyciski, diody, enkodery itp. GPIO może
        działać w trybie wejścia, wyjścia lub wejścia/wyjścia.
      </p>
      <li>Interfejsy analogowo-cyfrowe (ADC) i cyfrowo-analogowe (DAC)</li>
      <p>
        Umożliwiają przetwarzanie sygnałów analogowych na sygnały cyfrowe i na
        odwrót. ADC służy do konwersji sygnałów analogowych (takich jak
        napięcie, temperatura, ciśnienie) na sygnały cyfrowe, które mogą być
        przetwarzane przez mikrokontroler. DAC z kolei służy do konwersji
        sygnałów cyfrowych na sygnały analogowe, takie jak np. sygnał audio.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Do czego służy magistrala komputera?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Magistrala komputera to połączenie kilku linii przesyłających informacje
        między różnymi urządzeniami w komputerze. Służy ona do przesyłania
        danych pomiędzy różnymi podzespołami komputera, takimi jak procesor,
        pamięć, karta graficzna, dysk twardy czy inne urządzenia
        wejścia/wyjścia. Magistrala umożliwia szybki transfer danych wewnątrz
        komputera, co jest kluczowe dla sprawnego działania systemu. Bez
        magistrali, urządzenia w komputerze nie byłyby w stanie ze sobą
        komunikować, co uniemożliwiłoby wykonywanie zadań przez system.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymienić podstawowe elementy skladowe procesora.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Jednostka arytmetyczno-logiczna (ALU)</li>
      <p>wykonuje operacje arytmetyczne i logiczne na danych,</p>
      <li>rejestr instrukcji</li>
      <p>przechowuje aktualnie wykonywaną instrukcję,</p>
      <li>rejestr licznika instrukcji</li>
      <p>
        zawiera adres pamięci, z którego pobierana jest następna instrukcja,
      </p>
      <li>rejestry ogólnego przeznaczenia</li>
      <p>przechowują dane tymczasowo używane przez procesor,</p>
      <li>kontroler przerwań</li>
      <p>
        odpowiada za obsługę przerwań zewnętrznych (np. od urządzeń
        peryferyjnych),
      </p>
      <li>jednostka zarządzania pamięcią</li>
      <p>zarządza operacjami odczytu i zapisu do pamięci,</p>
      <li>jednostka zarządzania wejściami/wyjściami</li>
      <p>obsługuje komunikację z urządzeniami peryferyjnymi.</p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Jakie są podstawowe kategorie rozkazów procesora?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Rozkazy transferu danych</li>
      <p>np. kopiowanie, przesyłanie danych)</p>
      <li>Rozkazy arytmetyczno-logiczne</li>
      <p>(np. dodawanie, mnożenie, porównanie)</p>
      <li>Rozkazy skoku</li>
      <p>(np. warunkowy lub bezwarunkowy skok do innej części programu)</p>
      <li>Rozkazy wejścia/wyjścia</li>
      <p>
        (np. przesyłanie danych z/do pamięci zewnętrznej lub urządzeń
        wejścia/wyjścia)
      </p>
      <li>Rozkazy sterujące</li>
      <p>(np. resetowanie procesora, zmiana trybu działania)</p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Na czym polega rekursja w wywoływaniu funkcji?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Rekursja to technika programowania, która polega na wywoływaniu funkcji
        samej w sobie. W czasie wykonywania programu, gdy funkcja jest
        wywoływana, może ona sama wywołać siebie, co prowadzi do kolejnego
        wywołania, aż do osiągnięcia określonego warunku końcowego. Warunek
        końcowy jest ważny, ponieważ zapobiega nieskończonemu wywoływaniu
        funkcji i prowadzi do powrotu wartości zwracanej przez funkcję na wyższy
        poziom. Przykładem zastosowania rekursji może być np. obliczanie silni,
        sumy ciągu lub drzewa binarnego.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Co to jest Abstrakcyjny Typ Danych (ADT)?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Abstrakcyjny Typ Danych (ADT) to model matematyczny lub konceptualny,
        który opisuje zbiór danych i operacji, które można wykonywać na tych
        danych. ADT ukrywa implementację danych, skupiając się na ich
        funkcjonalności i zachowaniu. Jest to ważne narzędzie programistyczne,
        które umożliwia tworzenie skomplikowanych struktur danych, a
        jednocześnie ułatwia ich użytkowanie i zapewnia izolację od pozostałych
        elementów programu.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Co to jest struktura danych?</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Wyszukiwanie binarne to algorytm służący do odnalezienia wartości w
        uporządkowanej tablicy. Polega na porównywaniu szukanej wartości z
        wartością środkowego elementu tablicy, a następnie porównywaniu z
        połowami tablicy, aż do odnalezienia szukanej wartości lub stwierdzenia,
        że nie występuje w tablicy. Dzięki temu algorytmowi można znacznie
        przyspieszyć proces wyszukiwania, szczególnie dla dużych zbiorów danych.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Definicje, rola, zadania systemu operacyjnego. Kryteria klasyfikacyjne
        systemów operacyjnych.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        System operacyjny to podstawowe oprogramowanie, które zarządza zasobami
        sprzętowymi i pozwala użytkownikom na wykonywanie zadań. System
        operacyjny pełni kilka ról, m.in. zapewnia interfejs użytkownika,
        zarządza pamięcią, plikami, wejściami/wyjściami oraz wykonuje rozkazy.
      </p>
      <p>Zadania systemu operacyjnego to m.in.:</p>
      <li>
        zarządzanie pamięcią, plikami, procesami, urządzeniami wejścia/wyjścia;
      </li>
      <li>obsługa zdarzeń i błędów;</li>
      <li>optymalizacja wykorzystania zasobów sprzętowych;</li>
      <li>zapewnienie bezpieczeństwa i poufności danych;</li>
      <li>
        udostępnianie interfejsów programistycznych (API) dla twórców aplikacji.
      </li>
      <p>Kryteria klasyfikacyjne systemów operacyjnych to m.in.:</p>
      <li>tryb pracy systemu (jeden lub kilka trybów);</li>
      <li>rodzaj zarządzania procesami (procesy jedno- lub wielozadaniowe);</li>
      <li>model pamięci (jeden lub wieloprogramowy);</li>
      <li>stopień zdecentralizowania (monolityczny, mikrojądro, hybrydowy);</li>
      <li>rodzaj systemu plików (lokalny, sieciowy);</li>
      <li>
        typ architektury sprzętowej (komputer osobisty, serwer, system
        wbudowany).
      </li>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Założenia architektury Johna von Neumanna.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Jednolitą pamięć dla danych i programów.</li>
      <li>Procesor wykonujący sekwencyjnie instrukcje pobierane z pamięci.</li>
      <li>
        Zastosowanie skończonej liczby prostych instrukcji, które mogą wykonywać
        operacje arytmetyczne, logiczne oraz operacje wejścia/wyjścia.
      </li>
      <li>
        Zastosowanie jednolitego systemu adresacji, który pozwala na odwoływanie
        się do dowolnej komórki pamięci za pomocą jednej liczby (adresu).
      </li>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Zarządzanie pamięcią operacyjną. Pamięć wirtualna</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Zarządzanie pamięcią operacyjną to proces, w którym system operacyjny
        zarządza pamięcią RAM w celu efektywnego alokowania, dealokowania i
        udostępniania pamięci dla programów. System operacyjny używa pamięci
        operacyjnej do przechowywania programów i danych, które są aktualnie
        wykonywane.
      </p>
      <p>
        Pamięć wirtualna to technika zarządzania pamięcią operacyjną, która
        umożliwia programom używanie więcej pamięci, niż jest fizycznie dostępne
        w RAM. Pamięć wirtualna tworzy wirtualny adres pamięci, który mapowany
        jest na fizyczny adres pamięci, kiedy dany fragment pamięci jest
        potrzebny. Dzięki temu programy mają dostęp do większej ilości pamięci
        niż jest faktycznie dostępne w pamięci RAM. System operacyjny kontroluje
        ten proces mapowania, aby zapewnić, że programy nie korzystają z
        pamięci, która jest już zajęta lub nieprzydzielona.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Planowanie przydziału procesora -szeregowanie zadań.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Planowanie przydziału procesora (ang. CPU scheduling) to proces
        decydujący o przydziale czasu procesora dla zadań w systemie
        operacyjnym. Jednym z podejść jest szeregowanie zadań, czyli ustalanie
        kolejności wykonywania zadań w kolejce.
      </p>
      <p>
        Szeregowanie zadań to proces, w którym system operacyjny wybiera
        kolejność wykonywania zadań, aby zapewnić, że wszystkie zadania są
        wykonywane w odpowiednim czasie. System operacyjny używa szeregowania
        zadań do zarządzania procesorami w celu zapewnienia, że programy są
        wykonywane w odpowiednim czasie.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Przetwarzanie wspólbieżne i synchronizacja procesów.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Przetwarzanie współbieżne to technika przetwarzania danych, w której
        wiele zadań wykonywanych jest jednocześnie, a procesy komunikują się ze
        sobą i koordynują swoje działania. W celu zapewnienia poprawności
        przetwarzania, konieczna jest synchronizacja procesów, czyli koordynacja
        ich wykonywania tak, aby uniknąć niepożądanych efektów, takich jak
        wyścigi (ang. race conditions) czy zakleszczenia (ang. deadlock).
      </p>
      <p>
        Synchronizacja procesów polega na stosowaniu technik, które zapewniają
        poprawne wykonywanie zadań przez procesy. Do najważniejszych technik
        należą semafory, muteksy, zmienne warunkowe, a także algorytmy
        wzajemnego wykluczania, takie jak algorytm Petersona czy Dekkera. Celem
        synchronizacji procesów jest zapewnienie spójności danych i uniknięcie
        konfliktów między procesami, a także efektywne wykorzystanie zasobów
        systemowych.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Wymień podział języków programowania na trzy stopnie. Wyjaśnij też
        pojęcia translacja, kompilacja, interpretacja.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Języki niskiego poziomu</li>
      <p>
        Są bliskie językowi maszynowemu i umożliwiają bezpośrednie wykorzystanie
        zasobów komputera.
      </p>
      <li>Języki średniego poziomu</li>
      <p>
        Stanowią połączenie między językami niskiego i wysokiego poziomu.
        Umożliwiają one programowanie na niższym poziomie abstrakcji niż języki
        wysokiego poziomu, ale jednocześnie są łatwiejsze w użyciu niż języki
        niskiego poziomu.
      </p>
      <li>Języki wysokiego poziomu</li>
      <p>
        Są najbardziej abstrakcyjne i pozwalają na pisanie kodu w sposób
        bardziej zrozumiały dla człowieka. Zazwyczaj są one łatwiejsze w użyciu
        niż języki niskiego i średniego poziomu, ale jednocześnie mogą być mniej
        wydajne.
      </p>
      <li>Translacja</li>
      <p>
        Proces przekształcania kodu źródłowego napisanego w jednym języku
        programowania na kod wynikowy w innym języku programowania.
      </p>
      <li>Kompilacja</li>
      <p>
        Proces przekształcania kodu źródłowego napisanego w języku programowania
        na kod maszynowy, który jest bezpośrednio wykonywany przez komputer.
      </p>
      <li>Interpretacja</li>
      <p>
        Proces bezpośredniego wykonywania kodu źródłowego programu przez
        interpreter. Interpreter przetwarza kod źródłowy na bieżąco i wykonuje
        go, zamiast kompilować kod na etapie przed uruchomieniem.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Pojęcie programowania. Etapy programowania proceduralnego.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Programowanie to proces tworzenia programów komputerowych, czyli zbiór
        instrukcji i procedur wykonujących określone zadania.
      </p>
      <p>Etapy programowania proceduralnego:</p>
      <li>Analiza problemu</li>
      <p>
        Polega na zrozumieniu, co ma zrobić program, jakie są wymagania, jakie
        dane wejściowe i wyjściowe są potrzebne itp.
      </p>
      <li>Projektowanie</li>
      <p>
        Na tym etapie projektuje się algorytmy i struktury danych, które zostaną
        użyte w programie, aby spełnić wymagania.
      </p>
      <li>Kodowanie</li>
      <p>Implementacja algorytmów i struktur danych w języku programowania.</p>
      <li>Testowanie</li>
      <p>
        Sprawdzenie, czy program działa poprawnie, czy generuje oczekiwane
        wyniki, czy obsługuje wszelkie możliwe przypadki.
      </p>
      <li>Wdrażanie</li>
      <p>Instalacja programu i dostarczenie go użytkownikowi.</p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Przekazywanie argumentów do funkcji w C++</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Przekazywanie argumentów do funkcji w C++ odbywa się przez wartość,
        wskaźnik lub referencję. Przekazywanie przez wartość powoduje utworzenie
        kopii argumentu, która jest przekazywana do funkcji. Przekazywanie przez
        wskaźnik powoduje przekazanie adresu argumentu do funkcji, co pozwala na
        modyfikowanie wartości argumentu w funkcji. Przekazywanie przez
        referencję to inny sposób przekazywania argumentów przez odwołanie się
        do oryginalnego argumentu, co pozwala na modyfikację wartości argumentu
        bez tworzenia jego kopii.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Wymień kolejne techniki programowania.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Programowanie strukturalne</li>
      <p>
        opiera się na stosowaniu strukturalnych metod projektowania i
        programowania.
      </p>
      <li>Programowanie obiektowe</li>
      <p>
        opiera się na idei tworzenia obiektów, które są instancjami klas i mają
        określone właściwości i metody.
      </p>
      <li>Programowanie funkcyjne</li>
      <p>
        opiera się na wykorzystaniu funkcji jako podstawowej jednostki
        programowej, wraz z zapewnieniem odpowiedniego sposobu przekazywania
        argumentów i wyników.
      </p>
      <li>Programowanie zdarzeniowe</li>
      <p>
        opiera się na obsłudze zdarzeń, które mogą być generowane przez
        użytkownika, system lub inne aplikacje.
      </p>
      <li>Programowanie reaktywne</li>
      <p>
        opiera się na reakcjach na zmiany stanu aplikacji, zamiast na
        sekwencyjnym przetwarzaniu instrukcji.
      </p>
      <li>Programowanie współbieżne</li>
      <p>
        opiera się na równoczesnym wykonywaniu wielu wątków lub procesów, w celu
        zwiększenia wydajności i responsywności systemu.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Podstawowe zasady OOP (Object Oriented Programming).</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Abstrakcja</li>
      <p>
        umożliwia ukrycie szczegółów implementacji i skupienie się na istotnych
        aspektach obiektów.
      </p>
      <li>Dziedziczenie</li>
      <p>
        umożliwia tworzenie hierarchii klas i dziedziczenie właściwości i metod
        po klasach nadrzędnych.
      </p>
      <li>Enkapsulacja</li>
      <p>
        umożliwia wielokrotne wykorzystanie kodu poprzez zastosowanie różnych
        implementacji dla tych samych metod w różnych klasach.
      </p>
      <li>Polimorfizm</li>
      <p>
        umożliwia ukrycie danych i metod wewnątrz klasy i zezwala na dostęp do
        nich tylko poprzez odpowiednie interfejsy.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Klasy, obiekty. Formalna składnia definiowania klasy.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Klasa to szablon lub wzorzec, na podstawie którego tworzone są konkretne
        obiekty. Obiekt to instancja klasy, która ma swoje własne cechy (pola) i
        zachowania (metody).
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>WKonstruktory, destruktory i ich zadania.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Konstruktor</li>
      <p>
        metoda wywoływana podczas tworzenia nowego obiektu danej klasy. Jego
        zadaniem jest przygotowanie obiektu do dalszego działania i
        inicjalizacja pól obiektu, np. ustalenie początkowych wartości pól.
      </p>
      <li>Destruktor</li>
      <p>
        metoda wywoływana automatycznie, gdy obiekt danej klasy jest usuwany z
        pamięci. Jego zadaniem jest zwolnienie zasobów zajmowanych przez obiekt,
        takich jak pamięć dynamiczna czy otwarte pliki. W C++ destruktor ma
        nazwę taką samą jak nazwa klasy, poprzedzoną znakiem tyldy (~).
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Operatory odwołania do składowych obiektu. Podać przyklady.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Operator odwołania do składowych obiektu w języku C++ to operator "->",
        który służy do dostępu do składowych obiektu poprzez wskaźnik na ten
        obiekt. Przykład użycia operatora "->" to np. dostęp do pola "age"
        obiektu klasy Person poprzez wskaźnik na ten obiekt:
      </p>
      <code>Person *personPtr = new Person(); personPtr->age = 30;</code>
      <p>w innych językach uywa się np obiek.nazwa_zmiennej</p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Omówić platforme NET Framework. Czy .NET Framework jest związana z
        konkretnym językiem programowania?
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        .NET Framework to platforma programistyczna opracowana przez firmę
        Microsoft. Zapewnia narzędzia i biblioteki programistyczne do tworzenia
        aplikacji na systemy Windows. Platforma .NET Framework składa się z
        ogólnego środowiska uruchomieniowego (Common Language Runtime - CLR),
        które obsługuje kompilację kodu do języka pośredniego (IL - Intermediate
        Language) oraz obsługuje zarządzanie pamięcią, wątkami, bezpieczeństwem
        i innymi kwestiami systemowymi.
      </p>
      <p>
        Platforma .NET Framework jest niezależna od języka programowania, co
        oznacza, że można pisać kod w różnych językach, takich jak C#, Visual
        Basic.NET, F#, C++/CLI czy IronPython, a następnie ten kod może być
        uruchomiony w środowisku CLR. Dlatego .NET Framework jest nazywany
        platformą wielojęzykową.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Co oznacza akronim RAD? Podać przykłady środowisk RAD.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Akronim RAD oznacza Rapid Application Development, czyli metodę
        szybkiego tworzenia aplikacji. Metoda ta zakłada szybkie tworzenie
        prototypów, iteracyjne testowanie i udzielanie szybkiej odpowiedzi na
        zmiany.
      </p>
      <p>Przykładowe środowiska RAD to:</p>
      <li>Microsoft Visual Studio</li>
      <li>Xcode</li>
      <li>IntelliJ IDEA</li>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Przykładowe problemy optymalizacyjne w zagadnieniach programowania
        liniowego. Metoda Simpleks.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Problemy alokacji zasobów</li>
      <p>
        jak zoptymalizować alokację surowców lub kosztów pracy, tak aby osiągnąć
        maksymalny zysk lub minimalny koszt.
      </p>
      <li>Problemy transportowe</li>
      <p>
        jak zoptymalizować koszty transportu, tak aby produkty dotarły do celu w
        minimalnym czasie i przy minimalnych kosztach.
      </p>
      <li>Problemy produkcji:</li>
      <p>
        jak zoptymalizować proces produkcyjny, tak aby zminimalizować koszty
        produkcji i zwiększyć zyski.
      </p>
      <p>
        Metoda Simpleks to jedna z najczęściej stosowanych metod rozwiązywania
        problemów programowania liniowego. Polega na iteracyjnym przeszukiwaniu
        wierzchołków wielościanu, który jest ograniczony przez nierówności. W
        każdej iteracji algorytm wybiera kolejny wierzchołek, który ma lepszą
        wartość funkcji celu i porusza się w kierunku wierzchołka, który daje
        lepsze wyniki. Proces kończy się, gdy nie ma już wierzchołków dających
        lepsze wyniki, co oznacza, że zostało znalezione rozwiązanie optymalne.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Omówić możliwości narzędzia Solver arkusza kalkulacyjnego Excel</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Solver to narzędzie dostępne w arkuszu kalkulacyjnym Excel, służące do
        rozwiązywania problemów optymalizacyjnych. Możliwe do rozwiązania
        problemy obejmują optymalizację liniową, nieliniową, dyskretną oraz z
        ograniczeniami równościowymi lub nierównościowymi. Solver wykorzystuje
        algorytm Simpleksa do znalezienia optymalnego rozwiązania. Użytkownik
        może zdefiniować cel optymalizacji, zmienne decyzyjne, ograniczenia i
        inne parametry, a Solver wyznaczy wartości zmiennych decyzyjnych, które
        optymalizują cel. Solver jest przydatny w wielu dziedzinach, w tym w
        biznesie, finansach, inżynierii i naukach społecznych.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>omów Problem komiwojażera</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Problem komiwojażera (ang. Traveling Salesman Problem, TSP) jest jednym
        z klasycznych problemów optymalizacyjnych w informatyce. Polega on na
        znalezieniu najkrótszej drogi przechodzącej przez wszystkie wierzchołki
        w pełnym grafie ważonym, tak aby każdy wierzchołek był odwiedzony
        dokładnie raz i zakończyła się wierzchołkiem startowym
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Algorytm, cechy algorytmu, struktury sterujące przebiegiem algorytmu,
        schemat blokowy.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Algorytm to skończony zestaw precyzyjnych instrukcji krok po kroku,
        które pozwalają na rozwiązanie określonego problemu lub zadania.
        Algorytm powinien mieć określone cechy, takie jak precyzyjność,
        wykonywalność, skończoność i determinizm.
      </p>
      <p>
        Struktury sterujące przebiegiem algorytmu to elementy, które pozwalają
        na wykonywanie określonych działań w zależności od określonych warunków.
        Wyróżniamy między innymi instrukcje warunkowe (if, switch), pętle
        (while, for, do-while), instrukcje skoku (break, continue, return) oraz
        funkcje.
      </p>
      <p>
        Schemat blokowy to graficzne przedstawienie algorytmu, w którym
        poszczególne instrukcje są zapisane jako bloki o określonych kształtach,
        połączone strzałkami wskazującymi na kolejność wykonywania instrukcji.
        Schemat blokowy pozwala na łatwiejsze zrozumienie algorytmu i jego
        przebiegu, a także na łatwiejsze wprowadzenie ewentualnych zmian czy
        modyfikacji.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>omów Złożoność obliczeniowa algorytmu</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Złożoność obliczeniowa algorytmu to miara, która określa, jak szybko
        rośnie czas wykonania algorytmu wraz z rozmiarem problemu. Czas ten jest
        zwykle mierzony w liczbie operacji elementarnych, które muszą zostać
        wykonane przez algorytm.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Przykładowe algorytmy sortujące. Porównanie ich złożoności czasowej.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Sortowanie bąbelkowe (Bubble sort)</li>
      <p>
        porównuje sąsiednie elementy i zamienia je, jeśli nie są w kolejności.
        Ma złożoność O(n^2) i jest stosunkowo wolny dla większych zbiorów
        danych.
      </p>
      <li>Sortowanie przez wstawianie (Insertion sort)</li>
      <p>
        przechodzi przez każdy element i umieszcza go w odpowiedniej pozycji w
        posortowanej już części tablicy. Ma złożoność O(n^2) i działa szybciej
        niż sortowanie bąbelkowe.
      </p>
      <li>Sortowanie szybkie (Quick sort)</li>
      <p>
        wybiera jeden element jako punkt odniesienia (tzw. pivot), porównuje
        pozostałe elementy z pivotem i umieszcza je po odpowiedniej stronie.
        Następnie wykonuje ten sam proces dla obu połówek tablicy. Ma złożoność
        O(n log n) i działa szybko dla większych zbiorów danych.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Przykładowe dynamiczne struktury danych.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Lista</li>
      <p>
        struktura umożliwiająca przechowywanie danych w postaci ciągu elementów,
        które są połączone ze sobą wskaźnikami.
      </p>
      <li>Stos</li>
      <p>
        struktura LIFO (Last-In-First-Out), w której nowe elementy dodawane są
        na wierzch, a usuwanie elementów odbywa się również od wierzchu.
      </p>
      <li>Kolejka</li>
      <p>
        struktura FIFO (First-In-First-Out), w której nowe elementy dodawane są
        na końcu, a usuwanie elementów odbywa się z początku.
      </p>
      <li>Drzewo</li>
      <p>
        struktura, w której każdy element ma jednego lub więcej potomków,
        tworząc drzewiastą strukturę.
      </p>
      <li>Graf</li>
      <p>
        struktura, w której elementy są połączone ze sobą krawędziami, tworząc
        graficzny model.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Dane, informacje, przetwarzanie danych, przetwarzanie informacji..
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Dane to nieprzetworzone informacje, które posiadają pewną wartość i
        znaczenie. Przetwarzanie danych to operacje wykonywane na danych, które
        zmieniają ich postać, organizację lub zawartość, aby uzyskać bardziej
        wartościowe informacje. Przetwarzanie informacji natomiast to
        wykorzystywanie uzyskanych informacji w celu podejmowania decyzji lub
        podejmowania działań.
      </p>
      <p>
        Przetwarzanie danych jest procesem transformacji danych w informacje, a
        przetwarzanie informacji jest procesem transformacji informacji w
        wiedzę, co pozwala na podejmowanie decyzji lub realizowanie działań.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Podstawowe założenie ilościowej teorii informacji. Jednostka informacji.
        Entropia informacyjna.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Podstawowe założenie ilościowej teorii informacji mówi, że informacja
        jest związana z redukcją niepewności lub entropii. Teoria informacji
        bada sposób, w jaki przekazywana jest informacja, w jaki sposób
        informacja jest kodowana, przetwarzana, przesyłana i odbierana.
        Jednostką informacji jest bit, który może przyjąć dwie wartości: 0 lub
        1. Entropia informacyjna to miara informacji zawartej w danym zbiorze
        lub źródle informacji. Im większa entropia, tym większa niepewność co do
        treści informacji, a tym samym większa ilość informacji zawarta w tym
        źródle. Entropia może być wykorzystywana do określania efektywności
        kodowania informacji, gdzie im mniejsza entropia, tym mniej bitów
        potrzebnych do reprezentowania informacji.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Dwuznakowe kodowanie komunikatów. Średnia długość słowa kodowego.
        Pojęcie i znaczenie redundancji sposobu kodowania. Kod zwarty.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Dwuznakowe kodowanie komunikatów to sposób kodowania informacji, w
        którym każdy symbol jest kodowany za pomocą sekwencji dwóch znaków (np.
        "0" i "1"). Średnia długość słowa kodowego w tym kodowaniu zależy od
        prawdopodobieństwa wystąpienia danego symbolu - im mniejsze
        prawdopodobieństwo, tym dłuższa sekwencja dwuznakowa potrzebna jest do
        zakodowania symbolu.
      </p>
      <p>
        Dwuznakowe kodowanie komunikatów to sposób kodowania informacji, w
        którym każdy symbol jest kodowany za pomocą sekwencji dwóch znaków (np.
        "0" i "1"). Średnia długość słowa kodowego w tym kodowaniu zależy od
        prawdopodobieństwa wystąpienia danego symbolu - im mniejsze
        prawdopodobieństwo, tym dłuższa sekwencja dwuznakowa potrzebna jest do
        zakodowania symbolu. Entropia informacyjna to teoretyczna dolna granica
        średniej długości słowa kodowego, która jest osiągana przy optymalnym
        kodowaniu z zachowaniem odpowiedniego prawdopodobieństwa wystąpienia
        symboli.
      </p>
      <p>
        Redundancja sposobu kodowania oznacza, że w kodowaniu używa się więcej
        znaków, niż jest to konieczne do zakodowania informacji. Kod zwarty to
        taki kod, w którym nie ma redundancji i jest optymalny w sensie
        minimalnej średniej długości słowa kodowego.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Arytmetyka binama. Uzupełnienia i odejmowanie przy pomocy uzupelnień.
        Definicje kodów liczb.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Arytmetyka binarn</li>
      <p>
        system matematyczny, który operuje na liczbach zapisanych w systemie
        dwójkowym. W tym systemie posługujemy się jedynie dwoma cyframi: 0 i 1.
        W arytmetyce binarnej stosuje się uzupełnienia, czyli metody
        reprezentowania liczb ujemnych.
      </p>
      <p>
        Uzupełnienie do dwóch to najprostszy sposób reprezentacji liczb
        ujemnych. Polega on na uzupełnieniu liczby binarnej do 1, dodaniu 1 i
        zapisaniu wyniku w postaci binarnej. Natomiast uzupełnienie do jedynki
        to metoda, w której każdy bit liczby binarnej jest zamieniany na
        przeciwny i do wyniku dodawana jest 1.
      </p>
      <p>
        W arytmetyce binarnej do dodawania liczb stosuje się dodawanie bitowe.
        Natomiast odejmowanie można przeprowadzić przy pomocy uzupełnień.
      </p>
      <p>
        W kodach liczb stosowane są różne sposoby kodowania liczb, np. kod
        binarny, kod uzupełnień do dwóch, kod uzupełnień do jedynki. Każdy z
        tych kodów ma swoje charakterystyczne cechy, np. kod uzupełnień do dwóch
        jest prostszy do implementacji w sprzęcie, natomiast kod uzupełnień do
        jedynki pozwala na wykonanie operacji dodawania i odejmowania bez
        konieczności wykonywania operacji zamiany znaku.
      </p>
      <p>
        Kod zwarty to metoda kodowania, w której stosuje się kod o stałej
        długości, niezależnej od wartości kodowanej liczby. W wyniku tej metody
        otrzymuje się mniejszą redundancję kodu, ale wymaga to większej liczby
        bitów w przypadku większych liczb.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Logika binama. Funkcje boolowskie. Cyfrowe układy logiczne. Półsumator,
        sumator.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>Logika binarna</li>
      <p>
        dziedzina matematyki zajmująca się operacjami na dwóch wartościach
        logicznych: prawda (1) i fałsz (0). Funkcje boolowskie to matematyczne
        wyrażenia, które przyjmują wartości 0 lub 1 w zależności od wartości
        wejściowych.
      </p>
      <li>Cyfrowe układy logiczne</li>
      <p>
        zestawy bramek logicznych, wykonujących określone operacje na danych
        binarnych. Półsumator to podstawowy układ logiczny, który dodaje dwie
        jednobitowe liczby. Sumator to bardziej zaawansowany układ, który
        pozwala na dodawanie wielobitowych liczb.
      </p>
      <p>
        W cyfrowych układach logicznych wykorzystuje się także bramki logiczne,
        takie jak np. bramki AND, OR, NOT, NAND, NOR, XOR, XNOR. Te bramki
        umożliwiają wykonywanie różnych operacji logicznych, a także budowanie
        bardziej skomplikowanych układów, takich jak rejestr przesuwny, licznik,
        czy też procesor.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>
        Języki formalne. Klasyfikacja Chomsky'ego gramatyk formalnych. Gramatyki
        bezkontekstowe. Notacja BNF.
      </h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Języki formalne to matematyczny sposób opisu języków. Klasyfikacja
        Chomsky'ego to podział na 4 typy gramatyk formalnych, od najmniej do
        najbardziej ograniczających. Gramatyki bezkontekstowe należą do klasy
        drugiej, a ich reguły opisują związki między symbolami, bez rozróżnienia
        ich kontekstu. Notacja BNF (Backus-Naur Form) to forma zapisu gramatyk
        bezkontekstowych, składająca się z reguł zdefiniowanych jako produkcje.
      </p>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Przykłady zastosowania pochodnej funkcji liczbowej.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>
        Obliczanie wartości ekstremów funkcji, tj. miejsc, w których funkcja
        osiąga maksimum lub minimum.
      </li>
      <li>
        Określanie monotoniczności funkcji, czyli w których przedziałach jest
        ona rosnąca lub malejąca.
      </li>
      <li>
        Obliczanie wartości pochodnych wyższych rzędów, które pozwalają na
        analizę bardziej skomplikowanych zachowań funkcji.
      </li>
      <li>
        Wykorzystanie pochodnej do obliczania przybliżonej wartości funkcji w
        okolicy danego punktu.
      </li>
      <li>
        Zastosowanie w mechanice jako pochodna położenia względem czasu,
        pozwalająca na obliczanie prędkości, przyspieszenia i innych parametrów
        ruchu.
      </li>
      <li>
        Zastosowanie w ekonomii i finansach do obliczania stóp zwrotu z
        inwestycji, szybkości wzrostu i spadku produkcji itp.
      </li>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Przykłady zastosowania calki oznaczonej.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <li>
        Obliczanie dystansu przebytego przez ciało: jeśli znamy prędkość ciała w
        każdym momencie, to możemy obliczyć drogę, jaką przebyło na danym
        odcinku czasu poprzez obliczenie całki oznaczonej prędkości.
      </li>
      <li>
        Obliczanie pracy wykonywanej przez siłę: jeśli znamy wartość siły
        działającej na ciało w każdym momencie, to możemy obliczyć pracę
        wykonaną przez tę siłę na danym odcinku drogi poprzez obliczenie całki
        oznaczonej siły.
      </li>
      <li>
        Obliczanie całkowitej wartości funkcji: jeśli znamy funkcję, to możemy
        obliczyć całkowitą wartość tej funkcji na danym odcinku poprzez
        obliczenie całki oznaczonej tej funkcji.
      </li>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Macierze i przykłady ich zastosowania.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Macierze to tablice liczb o określonej liczbie wierszy i kolumn, które
        są wykorzystywane do reprezentowania i manipulowania danymi numerycznymi
        lub algebraicznymi.
      </p>
      <li>Rozwiązywanie układów równań liniowych</li>
      <li>Transformacja geometryczna obiektów w grafice komputerowej</li>
      <li>Analiza sieci społecznych lub sieci przemysłowych</li>
      <li>Kryptografia i szyfrowanie danych</li>
      <li>Analiza danych statystycznych i eksploracja danych</li>
      <li>Mechanika kwantowa i obliczenia numeryczne</li>
    </div>
    <div class="question" :class="{ 'dark-mode': darkMode }">
      <h1>Znaczenie rozkladu normalnego.</h1>
    </div>
    <div class="answer" :class="{ 'dark-mode': darkMode }">
      <p>
        Rozkład normalny, zwany również rozkładem Gaussa, jest jednym z
        najważniejszych rozkładów prawdopodobieństwa w statystyce.
        Charakteryzuje się krzywą o kształcie dzwonu, w którym średnia, mediana
        i moda mają taką samą wartość. Wiele zjawisk w przyrodzie i
        społeczeństwie ma rozkład zbliżony do normalnego, co umożliwia
        wykorzystanie tego rozkładu do modelowania tych zjawisk i przewidywania
        ich zachowania w przyszłości. Rozkład normalny jest również kluczowy w
        teorii błędów pomiarowych i inferencji statystycznej.
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
