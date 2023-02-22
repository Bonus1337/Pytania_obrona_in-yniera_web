<template>
  <div>
    <div class="question">
      <h1>
        Wymień podstawowe procesy instancji bazy danych Oracle i opisz rolę
        jednego z nich.
      </h1>
    </div>
    <div class="answer">
      <ul>
        <li>Proces serwera</li>
        <p>
          Odpowiada za komunikację między kientem a serwerem, przetwarzanie ądań
          uytkownika i udostępnianie danych z basy danych.
        </p>

        <li>Proces tła</li>
        <p>
          proces, który działa w tle i zajmuje się rónymi zadaniami, takimi jak
          kontrola integralności danych, zarządzanie pamięcią czy wykonywanie
          kopii zapasowych
        </p>

        <li>Proces zarządzania pamięcią</li>
        <p>
          odpowiada za zarządzanie pamięcią w bazie danych i przypisywania jej
          do odpowiednich procesów
        </p>
      </ul>
      <p>
        Proces serwera jest bardzo wannym procesem, poniewa to on umozliwia
        uytkownikom korzystanie z bazy danych. Kiedy uytkownik chce uzyskać
        dostęp do danych, wysyła zapytanie do serwera, który następnie
        przetwarza ądanie i zwraca wynik. Bez procesu serwera nie byłoby mozliwe
        korzystanie z bazy danych
      </p>
    </div>
    <div class="question">
      <h1>
        Wymień podstawowe struktury wchodzące w skład SGA instancji bazy Oracle
        i opisz rolę jednej z nich
      </h1>
    </div>
    <div class="answer">
      <ul>
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
          Pamięć w której baza danych przechowuje informacje o zmiennych w
          danych, które muszą być zapisane na dysku. przechowuje informacje o
          zmiennych w czasie rzeczywistym, a następnie zapisuje je w Redo Log
          Files.
        </p>
      </ul>
      <p>
        Redo Log Buffer umoliwia bezpiecznie przechowywać informacje o zmianach
        w danych, które muszą być zapisane na dysku. W przypadku awarii lub
        utraty zasilania, baza danych moe przywrócić stan danych zapisanych w
        Redo Log Files
      </p>
    </div>
    <div class="question">
      <h1>
        Wymień tryby zatrzymywania instancji bazy Oracle i opisz jeden z nich
      </h1>
    </div>
    <div class="answer">
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
    <div class="question">
      <h1>
        Wymień fazy uruchamiania instancji bazy Oracle i opisz jeden z nich.
      </h1>
    </div>
    <div class="answer">
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
        Faza uruchamiania instancji bazy danych. W tym trybie baza danych jest w
        pełni dostępna dla użytkowników, którzy mogą wykonywać operacje na
        danych.
      </p>
    </div>
    <div class="question">
      <h1>Omów rolę jaką odgrywają przestrzenie tabel bazy danych Oracle</h1>
    </div>
    <div class="answer">
      <p>
        przestrzenie tabel w bazie danych Oracle są niezbędne dla efektywnego
        zarządzania pamięcią dyskową i umożliwiają uniknięcie problemów
        związanych z brakiem miejsca na dysku.
      </p>
    </div>
    <div class="question">
      <h1>Omów pojęcie transakcji w realacyjncyh bazach danych</h1>
    </div>
    <div class="answer">
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
    <div class="question">
      <h1>Wymień podstawowe grupy poleceń języka SQL i omów jedną z nich</h1>
    </div>
    <div class="answer">
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
  </div>
</template>

<script>
export default {
  name: "App",
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
</style>
