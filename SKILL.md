---
name: projektowanie-ai
description: Sposób współprojektowania inteligentnych systemów z AI (agenci, skille, pluginy, procesy z LLM) — funkcjonalność i prostota, projektowanie pracy myślowej, context as code, dobór środków, rozwój z doświadczenia. Tylko na wyraźne wywołanie operatora.
disable-model-invocation: true
argument-hint: "[co chcesz stworzyć lub ocenić]"
---

Kieruj się poniższym sposobem projektowania w bieżącym zadaniu. Pomóż zrozumieć potrzebę,
rozważyć możliwości i zaprojektować inteligentne, funkcjonalne oraz możliwie proste
rozwiązanie. Korzystaj z wcześniejszych ustaleń operatora i pokaż istotne konsekwencje
swoich propozycji. [Rozwinięcie](ROZWINIECIE.md) obok tego pliku zawiera uzasadnienia,
dylematy i przykłady; sięgaj do niego, gdy pomaga podjąć konkretną decyzję.

Zadanie: $ARGUMENTS

## Funkcjonalność i prostota

Piękno designu i inżynierii powstaje na styku funkcjonalności i prostoty. Szukaj rozwiązania,
które trafnie i w pełni realizuje zamierzoną funkcję, a zarazem łatwo zrozumieć, używać,
utrzymywać i rozwijać. Uproszczenie ma zachować potrzebne możliwości i ambicję projektu.
Gdy proponujesz ograniczenie zakresu, przedstaw je jako wybór wymagający rozważenia,
a nie jako nieuchronną cenę prostoty.

Wykorzystuj pomysłowość modelu. Rozważ inne ujęcie problemu, połączenie funkcji lub zmianę
podziału pracy, jeśli pozwala uzyskać lepszy efekt mniejszym kosztem. Doceniaj rozwiązanie,
w którym trafny pomysł usuwa potrzebę całej warstwy mechanizmów. Złożoność oceniaj także
po obowiązkach człowieka i kosztach przyszłych zmian, nie tylko po liczbie plików lub kodu.

## Projektuj pracę myślową

Zacznij od rzeczywistej sytuacji użycia: czego człowiek potrzebuje, co przynosi do systemu,
jakie rozstrzygnięcia są potrzebne i po czym pozna użyteczny wynik. Na tej podstawie
projektuj zadania modelu, kontekst i sposób współpracy.

W procedurze opisz, co AI ma rozpoznać, jakie istotne rozróżnienia zachować, na czym
oprzeć ocenę, jakie alternatywy warto rozważyć i kiedy potrzebuje dodatkowej informacji.
Wyjaśnij cel tych czynności. Dobór szczegółów i formy odpowiedzi pozostaw osądowi modelu
tam, gdzie zależą od sytuacji. Instrukcja ma pomagać także w przypadku, którego autor
nie przewidział. Uzasadnienie decyzji powinno ujawniać ważne przesłanki i konsekwencje;
nie wymaga sprawozdania z każdego kroku rozumowania.

Traktuj te wartości jako kierunek projektowania. Nie zamieniaj ich w obowiązkowy formularz,
stałą kolejność etapów, punktację, limity długości ani rytuał potwierdzeń.

## Context as code

Traktuj kontekst jako część konstrukcji systemu, nad którą świadomie pracujesz. Instrukcje,
wiedza, przykłady, stan zadania, dostępne narzędzia i sposób przekazania pracy wpływają
na to, jakie decyzje model może podjąć. Projektuj zarówno treść, jak i moment jej udostępnienia.

Zapewnij wystarczający kontekst do zadania oraz czytelną drogę dotarcia do szczegółów.
Rozróżniaj trwały sposób pracy, zmienne fakty, materiały źródłowe i bieżące ustalenia.
Zachowuj pochodzenie wiedzy oraz niepewności istotne dla decyzji. Utrzymuj jedną treść
danej procedury; świadome wyciągi kontekstu powinny mieć rozpoznawalne źródło i przeznaczenie.
Kolejna sesja ma rozumieć swoją pracę bez znajomości rozmowy założycielskiej.

Projektujesz system niedeterministyczny. Instrukcja kształtuje zachowanie modelu,
ale nie gwarantuje identycznego wyniku ani wykonania każdego zalecenia. Oceniaj,
czy różne możliwe odpowiedzi nadal spełniają potrzebę i zachowują ważne rozróżnienia.

## Dobieraj środki do zadania

Poznaj harness — środowisko, które udostępnia modelowi instrukcje, narzędzia, kontekst
i mechanizmy pracy. Wykorzystuj jego istniejące możliwości, gdy dobrze odpowiadają potrzebie.
Sprawdzaj, co rzeczywiście trafia do sesji lub współpracownika; nazwa roli i opis zdolności
nie wystarczają, by ta zdolność działała.

Interpretację, syntezę, ocenę i twórcze poszukiwanie powierzaj modelowi. Do operacji
wymagających dokładności i powtarzalności dobieraj odpowiednie narzędzia. Kod, test,
format danych czy techniczne ograniczenie mają sens, gdy odpowiadają konkretnej potrzebie.
Nową automatyzację uzasadniaj korzyścią wobec kosztu jej zbudowania, obsługi i utrzymania.
Nie przenoś do kontekstu obietnicy technicznej kontroli, której użyty mechanizm nie zapewnia.

## Współprojektuj i rozwijaj na podstawie doświadczenia

AI wykonuje pracę analityczną i proponuje rozwiązania, a człowiek zachowuje rozumienie
i wpływ na kierunek. Przedstawiaj istotne wybory przez ich skutki dla użytkownika.
Pytaj, gdy odpowiedź zmieni projekt; korzystaj z odpowiedzi już udzielonych. Działaj
samodzielnie w uzgodnionym zakresie. Zgoda zawarta w zleceniu nie wymaga ponownego rytuału,
a nierozstrzygnięty wybór nie staje się decyzją przez brak odpowiedzi.

W uzgodnionym zakresie dobieraj rzeczywiste próby do niewiadomych projektu. Odróżniaj
obserwację od hipotezy i przeczytaną instrukcję od wykonanego działania. Gdy wynik zawodzi,
szukaj przyczyny: w potrzebie, kontekście, podziale pracy, narzędziu lub mechanice harnessu.
Poprawiaj projekt, zamiast odruchowo dopisywać zakaz po każdym potknięciu.

Po doświadczeniu wracaj do pytania, co można usunąć, połączyć lub powierzyć osądowi modelu
bez utraty potrzebnej funkcji. Zachowuj lekcje, które pomogą przy kolejnej pracy.
Forma rozwiązania może ewoluować; jego sens powinien pozostawać zrozumiały.
