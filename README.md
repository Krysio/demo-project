# Projekty systemu e-voting realizujący model demokracji płynnej oparty o blockchain

W przeciwieństwie do wielu projektów, struktura blockchain nie jest oparta a mechanizmy transakcyjne zaczerpnięte z krypto walut.

Głównym zadaniem przedstawionego systemu jest zebranie woli uprawnionych do tego użytkowników w sposób niepodważalny oraz odporny na modyfikacje. Będąc przy tym zdecentralizowany oraz zapewniając anonimowość jeśli ta jest pożądana.

Zbierana wola użytkowników umieszczana jest w dostępnym publicznie blockchain'ie, który później stanowi źródło faktów oraz może zostać poddany analizie przez zewnętrzne aplikacje zliczające.

Mechanizm działania jest maksymalnie prosty, tak aby był łatwy do zrozumienia oraz nie stanowił wyzwania dla przeciętnego komputera w 2023r w przypadku uruchomienia minimalnej instancji węzła tego systemu.

## Blockchain

Bloki w tym systemie tworzone są w równych odstępach czasu. Węzły nie rywalizują o wytworzenie bloku, wszystkie dążą one do uzyskania takich samych bloków ze wszystkimi danymi jakie należy w nich umieścić, a które się pojawią w sieci systemu.

Transakcje, a raczej polecenia, które umieszczane są w blokach, tak jak one również zawierają odwołanie do poprzedniego bloku w łańcuchu. Dodatkowo autor polecenia musi je podpisać cyfrowo. Te dwa elementy, w połączeniu z wartościowaniem bloku w postaci liczby zawartych poleceń, zabezpiecza blockchain przed modyfikacjami oraz sprowadza konsensus do demokratycznego aktu realizowanego przez samych użytkowników systemu.

Tak dokładnie polecenia nie wskazują na poprzedni blok a na ten o jeden wcześniejszy. Ten zabieg nie powinien wiele zmienić w kwestii bezpieczeństwa a wiąże się z usprawnieniem procesu osiągania konsensusu.
#### Blockchain publiczny, ale zamknięty

Aby z systemu mogły korzystać tylko osoby do tego uprawnione wymagane jest stworzenie przeznaczonej do tego infrastruktury publicznej w postaci osób pełniących funkcje urzędnicze. System przewiduje istnienie kont administratorskich, które będą poświadczać konta użytkowników wprowadzanych do systemu.
#### Kadencje

W rozumieniu systemu jest to okres, w którym dane konto posiada uprawnienia do korzystania z systemu i nie zostanie ono odebrane automatycznie. Najprawdopodobniej kadencjami będą kwartały. Aby użytkownik mógł korzystać z systemu w następnej kadencji będzie musiał podjąć odpowiednie działania, które zostaną objaśnione później.
Wprowadzenie kadencji powiązane jest zapewnieniem anonimowości w systemie, upraszcza implementacje oraz zmniejsza zapotrzebowanie na zasoby po stronie instancji węzła systemu. W przypadku blockchain ogranicza to konieczność przechowywania bardzo starych bloków.
## Użytkownik

Użytkownik w systemie reprezentowany jest przez klucz publiczny, który wcześniej został wprowadzony oraz poświadczony przez admiratora systemu. Aby klucz był ważny w danej kadencji, użytkownik musi go aktywować komendą, w której podaje namiary na blok, w którym jego klucz został dodany do systemu. Klucz jest ważny przez ograniczoną ilość kadencji, po tym czasie konieczne jest wprowadzenie nowego klucza lub odnowienie go przez administratora systemu.
#### Anonimowość

Zwykłe konto użytkownika można w łatwy sposób powiązać z rzeczywistą osobą, system w żaden sposób tego nie utrudnia.
Anonimowość realizowana jest poprzez jawnego przeniesienia uprawnień na nowe konto. Operacja realizowana jest przez grupę użytkowników a jej efektem jest pula nowych kluczy publicznych w identycznej liczbie. Brak jest tutaj danych pozwalających kto jest właścicielem danego nowego klucza, spada tutaj pewność przynależności kluczy proporcjonalnie do liczby uczestników tej operacji. Operacja może zostać powtórzona kilkukrotnie z różnymi grupami użytkowników.
Tak nowo utworzone konta są automatycznie aktywowane w danej kadencji i tylko na jej okres. Potem operację należy powtórzyć.

W węzłach użytkownik jest również identyfikowany poprzez hash jego klucza publicznego. Dzięki mechanizmom aktywacji kluczy w kadencjach węzeł w danych podręcznych musi przechowywać jedynie zbiór takich hash'y w liczbie równej liczby użytkowników systemu. Dla 50 milionów użytkowników taki zbiór nie powinien być większy niż 2GB.
## Mechanizmy poparcia

Użytkownik posiada ograniczoną liczbę punktów poparcia, które może przekazać innym użytkownikom. Użytkownik posiadający odpowiednią liczbę punktów poparcia może wprowadzać w odpowiedniej liczbie inicjatywy poddawane głosowaniom lub zbieraniu podpisów. Węzły systemu informacje z tym związane przechowywać będą w bazie danych, której rozmiar nie powinien przekroczyć 10GB dla 50 milionów użytkowników.
## Demokracja

W systemie pojawiać się będą głosowania oraz zbiórki podpisów, użytkownik zareaguje na nie odpowiadającym poleceniem, które wyśle do systemu. Węzeł zweryfikuje ważność konta oraz poprawność podpisu oraz umieści polecenie w bloku. Wyniki zostaną odczytane z łańcucha bloków przez aplikacje zewnętrzne.
#### Demokracja płynna

W puli poleceń znajduje się możliwość przekazania własnego głosu innemu użytkownikowi. To czy takie głosowanie zostanie uwzględnione leży po stronie aplikacji zliczających wyniki.
#### Tajność głosowania

Tajność głosowania realizowana jest poprzez dołączenie do inicjatywy klucza publicznego. Oddawane głosy w takim przypadku są odpowiednio szyfrowane przy pomocy tego klucza. Klucz prywatny jest ujawniany po zakończeniu głosowania, przy którego pomocy aplikacje zewnętrzne mogą odczytać wyniki.


