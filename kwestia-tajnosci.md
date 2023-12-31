### Anonimowy użytkownik

Jest to system, w którym składane głosy są widoczne publiczne oraz grupa użytkowników jest zamknięta. Jedyną możliwością zapewnienia anonimowości bez znacznego skomplikowania systemu jest pozwolenie już zweryfikowanym kontom użytkownika na zrzeczenie się prawa głosu na rzecz nowego konta, pozbawionego już danych personalnych. Operacja wykonana grupowo pozwoli na rozmycie pewności co do autorstwa poszczególnych operacji proporcjonalnie do liczebności grona, w jakim ta operacja jest wykonywana oraz wykładniczo w stosunku do liczby powtórzeń takiej operacji.

W systemie jest to realizowane poprzez akceptacji pojedynczej komendy zawierającej listę nowych kluczy publicznych, z których każdy przynależy do jednego z autorów tej komendy, lista jest posortowana binarnie rosnąco
W ramach struktury samej komendy zamiast pojedynczego aktualnego publicznego klucza autora mamy listę wielu autorów, posortowaną binarnie rosnąco.
Komenda jest podpisana sygnaturą każdego z autorów komendy w kolejności odpowiedniej do listy autorów.

Procedura uzgadniania puli kluczy:
- w komunikacji między użytkownikami pośredniczy serwer.
- serwer udostępnia listę kluczy publicznych użytkowników biorących udział w procedurze.
- użytkownicy zaopatrują się w te klucze równolegle z innych źródeł i porównują je z kluczami wysłanymi przez serwer, ma to zapobiegać przed możliwością podsłuchiwania dalszej komunikacji przy pomocy `man in the middle`.
- każdy użytkownik generuje klucz publiczny dla nowego konta i wysyła go poprzez serwer, do każdego użytkownika zostaje wysłana TOR-podobna wiadomość. Klucz zapakowany jest kilkukrotnie w poleceniu nakazującym przesłanie treści do kolejnego użytkownika. Do szyfrowania używane są klucze publiczne użytkowników. Na koniec każdy użytkownik który otrzymał klucz przesyła go do serwera. Operacja ta ma na celu zatarcie informacji do kogo dany klucz należy.
- serwer przygotowuje komendę tworzącą nowe konta, przesyła ją każdemu użytkownikowi by ten ją sprawdził oraz sporządził sygnaturę, którą odsyła zwykłym kanałem.
- serwer wprowadza komendę do systemu.