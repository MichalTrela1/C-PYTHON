Wypożyczalnia Pojazdow

1. temat aplikacji
Mój projekt to prosta wypożyczalnia. Użytkownik może przypisać do siebie wybrany pojazd, może to byc samochod albo rower, co automatycznie zmienia status tego pojazdu na zajęty.

2. Rzeczowniki i główne klasy
Klasy, których użyłem to: "Vehicle", czyli klasa glowna (Pojazd), "Car" (Samochód), "Bike" (Rower) oraz "User" (Uzytkownik).

3. Właściwosci
W pojazdach mam: identyfikator (Id), nazwę (Name) i status dostepności (IsRented). W klasie użytkownika: "UserId", "UserName" i przypisany do niego pojazd (RentedVehicle).

4. Sposob dzialania
- Rent() w pojazdach - zmienia status "IsRented" na "TRUE" (zajęty),
- ShowInfo() - podaje rodzaj pojazdu
- "RentVehicle(Vehicle v)" w klasie User - przypisuj pojazd do klienta i od razu wywołuje jego wypożyczenie

5. Relacje między klasami
Zastosowałem dziedziczenie (samochód i rower dziedziczą po pojeździe) oraz agregację (obiekt User posiada w sobie obiekt Vehicle). Do tego w metodzie "RentVehicle" przekazuję obiekt jako parametr.

6. Zastosowania
- Abstrakcja: klasa "Vehicle" jest oznaczona jako "abstract" - jest tylko szablonem, nie mogę stworzyć w Main po prostu "pojazdu". Posiada też abstrakcyjną metodę "ShowInfo()"
- Enkapsulacja: Użyłem "private set" przy polach "Id" oraz "IsRented", dzieki czemu ręcznie nie da się zmienic statusu pojazdu
- Dziedziczenie: Klasy "Car" i "Bike" dziedziczą po "Vehicle", więc automatycznie dostają wszystkie cechy naszej klasy głównej
- Polimorfizm: Metoda "ShowInfo()" działa inaczej dla auta i w inny sposob dla roweru za pomoca "override". W "Main" wywołuję tą samą komendę, a program sam wie, jaki tekst wyświetlić.