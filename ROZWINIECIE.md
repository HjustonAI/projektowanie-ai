# Uzasadnienia, dylematy i przykłady projektowania z AI

To rozwinięcie [kontekstu projektowego](KONTEKST.md). Czytaj temat potrzebny do bieżącej
decyzji. Przykłady ilustrują sposób projektowania; nie są szablonami ani dodatkowymi
regułami dla każdego systemu.

## Gdzie szukać elegancji rozwiązania

Najpierw rozpoznaj funkcję, którą warto zachować. System może mieć mało elementów,
a mimo to wymagać od człowieka ciągłego przypominania kontekstu, kopiowania danych
i naprawiania odpowiedzi. Koszt nie zniknął — pozostał w codziennej pracy.
Z kolei większy plik instrukcji może uprościć cały system, jeśli pozwala usunąć
powielone procedury albo tłumaczenie tych samych zasad przy każdej sesji.

Pomysłowość jest szczególnie wartościowa, gdy zmienia sposób rozwiązania problemu.
W projekcie Wiki wspólna operacja mogła zachować swoje znaczenie, a lokalna instrukcja
opisywać rozstrzygnięcia właściwe dla danej dziedziny. Nie trzeba było wybierać między
jednym sztywnym przebiegiem dla wszystkich a pisaniem od zera całego narzędzia dla każdej wiki.
Takie połączenie stabilnego zamiaru z adaptacyjnym wykonaniem warto rozważać także gdzie indziej.

Przy porównywaniu rozwiązań prześledź ich użycie: ile trzeba rozumieć na wejściu,
co zrobi AI, czym zajmie się operator i co trzeba będzie poprawić po zmianie potrzeb.
Rozważ również rozwiązanie odważniejsze, jeśli daje istotną korzyść. „Najprostsze”
nie oznacza automatycznie pierwszego znanego sposobu ani najmniejszej możliwej funkcji.
Gdy złożoność jest potrzebna, pokaż, za jaką zdolność nią płacimy.

## Od reguł do użytecznych rozstrzygnięć

Instrukcja jest przydatna, gdy kieruje uwagę modelu na to, co istotne dla zadania.
Samo „myśl krytycznie” nie wskazuje, czego szukać. Rozbudowana lista warunków też może
nie pomóc, jeśli odrywa ocenę od sensu materiału. Dobra procedura podaje cel, podstawę
oceny i rozróżnienia, które mają zmienić działanie.

Przykład instrukcji narzucającej formę:

> Każdy materiał oznacz jednym ze statusów. Zawsze przygotuj tabelę ryzyk i trzy warianty.
> Przejdź dalej dopiero, gdy wszystkie pola będą wypełnione.

Przykład instrukcji opisującej potrzebną ocenę:

> Rozpoznaj, kto przekazuje informację i o czym może wiarygodnie powiedzieć. Ustal,
> czy materiał wnosi nową wiedzę, potwierdza wcześniejszą, czy się z nią różni.
> Zachowaj różnicę między decyzją człowieka a propozycją. Istotną niepewność wyjaśnij
> tak, żeby odbiorca rozumiał jej wpływ na zadanie. Dobierz zapis do materiału.

Drugi zapis daje podstawę do pracy także z nietypowym źródłem. Nie wymaga jednak,
aby odpowiedź zawsze zawierała opis wszystkich tych czynności. Gdy odbiorca potrzebuje
konkretnej tabeli albo narzędzie wymaga schematu danych, taka forma staje się uzasadniona
przez zastosowanie.

Proces myślowy może obejmować rozpoznanie sprzeczności, zmianę perspektywy, ocenę źródła,
porównanie rozwiązań albo podważenie własnej propozycji. Dobierz to, co pomaga wykonać
daną pracę. Wymienienie wielu nazw metod samo w sobie nie tworzy inteligentnego systemu.

## Kontekst jako materiał inżynierski

Context as code oznacza tutaj świadome projektowanie i utrzymywanie kontekstu jako
elementu działającego systemu. Zmiana instrukcji może zmienić sposób podejmowania decyzji;
zmiana dostępnej wiedzy — ich podstawę; zmiana przekazania zadania — zdolność współpracownika
do jego wykonania. Dlatego ważne są granice znaczeń, zależności, pochodzenie i możliwość
zrozumienia zmiany. Samo zapisanie promptu w pliku nie rozwiązuje tych zagadnień.

Przykład z projektowania agentów: reguła „nie podawaj liczby uczestników” utrwala chwilowy
brak danych jako zakaz działania roli. Po potwierdzeniu liczby instrukcja staje się
przeszkodą. „Podawaj liczbę na podstawie aktualnego kontekstu; odróżniaj prognozę,
limit i liczbę wolnych miejsc” opisuje trwały sposób pracy. Konkretne wartości oraz
ich status pozostają w wiedzy o przedsięwzięciu.

Podobnie rozróżniaj procedurę i stan zadania. Procedura pomaga prowadzić daną klasę pracy;
stan mówi, co wykonano w tym przypadku i co pozostaje otwarte. Jeśli chwilowy stan
jest powielony w wielu instrukcjach, jego zmiana wymaga odszukania wszystkich kopii.
Jedno odnajdywalne miejsce i wskazanie, kiedy do niego sięgnąć, często wystarczą.

Kontekst nie musi być w całości obecny od początku rozmowy. Zaprojektuj wejście,
z którego sesja rozumie zadanie i potrafi dotrzeć do potrzebnych materiałów. Przy
przekazywaniu pracy ustal, co odbiorca faktycznie otrzyma: treść zlecenia, instrukcję,
wyciąg wiedzy, dostęp do źródła czy tylko jego ścieżkę. Odsyłacz do niedostępnego pliku
nie przekazuje jego treści.

Wyciąg może być potrzebny, by agent pracował samodzielnie. Zachowaj jego przeznaczenie
i pochodzenie. To świadoma kopia na potrzeby zadania, a nie niezależne potwierdzenie
źródła. Dobór odpowiedzialności za aktualizację należy do projektu; nie wynika z samego
istnienia pliku konieczność budowy automatycznej synchronizacji.

## Niedeterministyczność i odpowiedzialny osąd

W systemie opartym na LLM wiele różnych odpowiedzi może być dobrych. Projektuj przestrzeń
użytecznych zachowań: co wynik ma umożliwiać, na jakiej podstawie może powstać i których
istotnych znaczeń nie może zgubić. Różnica w długości, nagłówkach czy sposobie wyjaśnienia
nie musi oznaczać pogorszenia działania.

Ta swoboda jest szczególnie cenna przy interpretacji niepełnych potrzeb, łączeniu wiedzy,
tworzeniu koncepcji i rozpatrywaniu nowych sytuacji. Nie usuwa potrzeby dokładności tam,
gdzie wynik da się jednoznacznie obliczyć. Model może ocenić znaczenie różnicy między
źródłami, a narzędzie porównać bajty plików. Model może zaproponować układ materiału,
a obliczenie sprawdzić, czy podane wymiary mieszczą się w dostępnym miejscu.

Rozróżniaj preferencję projektową, faktyczne wymaganie odbiorcy i ograniczenie techniczne.
Brak arbitralnego limitu długości instrukcji nie znosi pojemności kontekstu używanego
środowiska. Prośba zapisana w Markdown może kierować modelem, lecz nie jest techniczną
blokadą dostępu. Gdy potrzebna jest gwarancja, dobierz mechanizm, który rzeczywiście
może ją zapewnić. Nie rozszerzaj z tego powodu kontroli na każdą decyzję wymagającą osądu.

## Harness jako tworzywo projektu

Harness jest środowiskiem pracy modelu: dostarcza kontekst i narzędzia oraz określa,
jak można uruchamiać zadania i przekazywać pracę. Rozpoznaj możliwości konkretnego
środowiska przed zaprojektowaniem mechanizmu, który ma je wykorzystywać. Dokumentacja,
lokalna konfiguracja i obserwacja działania odpowiadają na różne pytania; odróżniaj
to, co opisano, od tego, co sprawdzono w danym zastosowaniu.

Przykładowa sytuacja: specjalista potrzebuje oceny drugiej roli. Zanim powstanie własny
koordynator z kolejką, formatem wiadomości i rejestrem stanów, rozważ istniejące
delegowanie zadania. Jeśli zapewnia potrzebne przekazanie kontekstu i powrót wyniku,
może wystarczyć dobrze zaprojektowane zlecenie. Osobny mechanizm może być uzasadniony,
gdy pojawi się rzeczywista potrzeba, np. trwałej kolejki lub wznowienia zadań po awarii.

Delegowanie również ma koszt: przygotowanie kontekstu, oczekiwanie, integrację odpowiedzi
i możliwe rozbieżności. Dodatkowa rola pomaga, gdy wnosi potrzebną perspektywę lub zdolność,
odciąża kontekst albo pozwala wykonać niezależną pracę. Samo istnienie wielu agentów
nie świadczy o inteligencji rozwiązania.

Instrukcje opisuj przez zamiar i potrzebne zachowanie. Szczegóły właściwe danemu narzędziu
umieszczaj tam, gdzie są używane. Dzięki temu zmiana harnessu nie wymaga ponownego
odkrywania sensu całego projektu, choć nadal może wymagać adaptacji i rzeczywistych prób.

## Współpraca, która zachowuje rozumienie

„Outsource thinking but not understanding” oznacza tu powierzenie AI pracy analitycznej
przy zachowaniu przez człowieka rozumienia rozwiązania i wpływu na jego kierunek.
Model powinien samodzielnie rozpoznawać możliwości, przygotowywać warianty i pokazywać
istotne konsekwencje. Operator nie powinien zastępować go w każdej drobnej decyzji.

Przy ważnym wyborze pokaż różnicę w pracy użytkownika. Na przykład „lokalne kopie mogą
rozwijać się niezależnie; wspólna aktualizacja wymaga oceny zgodności” mówi więcej niż
sama lista technik przechowywania plików. Zadawaj pytania, które zmieniają rozwiązanie,
i wykorzystuj odpowiedzi już obecne w rozmowie lub materiałach.

Odróżniaj upoważnienie do wykonania pracy od decyzji o jej kierunku. Zlecenie może już
obejmować wszystkie potrzebne kroki, więc osobne pytanie o każdy z nich utrudnia pracę.
Jeśli jednak pozostaje wybór, od którego zależy projekt, nie zastępuj go domysłem.
W czasie oczekiwania można wykonywać pracę niezależną od tej odpowiedzi.

Zapisuj ustalenia wystarczająco jasno, by kolejna sesja mogła kontynuować. Rekomendacja
modelu nie powinna z czasem wyglądać jak decyzja człowieka. Do zachowania tej różnicy
często wystarcza zwykłe zdanie; nie każda współpraca potrzebuje osobnego systemu zatwierdzeń.

## Rozwijanie przez doświadczenie i upraszczanie

Gdy potrzeba próby, wybierz zadanie, które rozstrzygnie istotną niewiadomą. Czy nowa sesja
odnajdzie podstawę pracy? Czy przekazany kontekst wystarczy odbiorcy? Czy proces poradzi
sobie z inną dziedziną? Sam odczyt poprawnie wyglądających instrukcji nie odpowiada
na pytania o rzeczywiste zachowanie. Jedna udana próba nie dowodzi też niezawodności.

Po niepowodzeniu rozpoznaj, czego zabrakło. Jeśli model myli propozycję z ustaleniem,
przyczyną może być niejasne pochodzenie materiału. Dopisanie „nigdy się nie myl” niczego
tu nie wyjaśnia. Jeśli kolejna sesja wymaga podpowiedzi z rozmowy autora, potrzebne
rozstrzygnięcie mogło nie trafić do kontekstu. Jeśli współpracownik nie widzi źródła,
problem może leżeć w sposobie przekazania, a nie w jego instrukcji roli.

Po poprawce rozważ, co stało się zbędne. Wyraźny podział odpowiedzialności może pozwolić
usunąć powtarzane ostrzeżenia. Jedna lokalna procedura może zastąpić kilka rozchodzących
się opisów. Dobrze przekazana wiedza może usunąć potrzebę ponawiania wywiadu. Zachowuj
szczegół, który pomaga rozstrzygać przyszłe sytuacje; koszt treści wynika z jej przydatności,
a nie z przekroczenia z góry ustalonej liczby słów.

## Pochodzenie i zakres tej syntezy

Tekst jest syntezą przygotowaną przez AI na podstawie rozmów autora i doświadczeń
z projektów, w których LLM wykonuje część pracy: wiki prowadzonej z udziałem agentów
oraz systemu współpracujących agentów. Materiały zebrano 2026-10-28. Nie jest to zapis,
że autor osobno wypowiedział lub zatwierdził każde sformułowanie. Przykłady są
ilustracjami, nie wynikami prób działania tej instrukcji.

KONTEKST.md i ROZWINIECIE.md można przenosić razem; sam KONTEKST.md także działa jako
materiał wejściowy. Ogólna filozofia nie zakłada posiadania wiki, zarządcy, konkretnych
katalogów, nazw operacji ani określonego sposobu dystrybucji.
