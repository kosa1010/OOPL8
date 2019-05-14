# OOPL8
Klasy abstrakcyjne

## Zadanie 0
#### [Polimorfizm, interfejsy i klasy wewnętrzne](http://edu.pjwstk.edu.pl/wyklady/poj/scb/Polimorf/Polimorf.html)

Klasa w której zadeklarowano jakąkolwiek metodę abstrakcyjną jest klasą abstrakcyjną i musi być opatrzona specyfikatorem `abstract`. Metoda abstrakcyjna nie ma implementacji (ciała) i winna być zadeklarowana ze specyfikatorem `abstract`. Metody abstrakcyjne to takie, co do których nie wiemy jeszcze jaka może być ich konkretna implementacja (lub nie chcemy tego przesądzać), ale wiemy, że powinny wystąpić w zestawie metod każdej konkretnej klasy dziedziczącej klasę abstrakcyjną. Konkretna implementacja (definicja w klasie kodu metody) może być bardzo różna, w zależności od konkretnego rodzaju obiektów, które opisuje dana klasa. **Abstrakcyjność klasy oznacza, iż nie można tworzyć jej egzemplarzy (obiektów)**.

## Zadanie 1

Zmodyfikuj klasę `Product` z poprzedniego laboratorium tak aby stała się klasą abstrakcyjną zob.
kod poniżej. Uzupełnij enkapsulację danych w klasie **i utwórz konstruktor**.

```java
public abstract class Product {

    private double price;
    private String name;
    private String describe;

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    public abstract void buy();

    public abstract void showInfo();
}
```

Utwórz klasę pochodną, po klasie `Product`, która nie będzie już klasą abstrakcyjną zob. kod poniżej.

```java
public class Tractor extends Product {

    public Tractor(String name, double price, String describe) {
        super(name, price, describe);
    }

    public void buy() {
        System.out.println(
                "I bought a black tractor, capaciticy 2400!");
    }

    public void showInfo() {
        System.out.println(
                "Price:" + getPrice()
                + " name:" + getName()
                + " describe:" + getDescribe()
        );
    }
}
```

## Zadanie 2

W oparciu o klasę `Product` zdefiniuj produkty tj.: `Book`, `Jam`, `Medicines`, `Pen`, `Chocolate`. Czy produkty typu ubranie, lekarstwa, narzędzia powinny być opisane klasami abstrakcyjnymi czy nieabstrakcyjnymi? 

## Zadanie 3

Utwórz kolekcję produktów w postaci tablicy 10-elementowej i dodaj do tej tablicy następujące produkty: `Book`, `Chocolate`, `Book`, `Pen`, `Jam`, `Medicines`, `Jam`, `Chocolate`, `Pen`, `Book`, `Tractor`. Następnie przejdź kolekcję przy użyciu pętli iteracyjnej i wywołaj dla każdego elementu metody `buy()` i `showInfo()`. Przeanalizuj wyświetlone wyniki i opisz (komentarz).

## Zadanie 4

Utwórz klasę abstrakcyjną `GeometricFigure`, zawierającą metodę abstrakcyjną `calcField()` (dla każdej figury geometrycznej można obliczyć pole). Utwórz dwie klasy pochodne - dziedziczące po klasie - `GeometricFigure`, które również są klasami abstrakcyjnymi: `FlatFigure` oraz `SpatialFigure`. Dla figury płaskiej dodaj metodę abstrakcyjną `calcPerimeter()`, oraz przesłoń metodę `toString()`, która zwróci informację: `"Obliczanie parametrów figury płaskiej"`. Dla figury przestrzennej dodaj metodę abstrakcyjną `calcSize()` oraz przesłoń metodę `toString()`, tak aby zwracała informację: `"Obliczanie parametrów figury przestrzennej"`. Utwórz następujące klasy pochodne dziedziczące odpowiednio po klasach `FlatFigure` i `SpatialFigure`: `Square`, `Rectangle`, `Triangle`, `Trapezoid`, `Parallelogram`, `Rhombus`, `Circle`, `Cube`, `Cuboid`, `Sphere`, `Roller`, `Cone`. Dla tych klas utwórz odpowiednie struktury danych opisujące te figury (np. koło posiada parametr promienia `r`), oraz zastosuj hermetyzację danych (parametry figur muszą być liczbami dodatnimi). Dla utworzonych klas zaimplementuj metody abstrakcyjne dodając w ich ciałach odpowiednie funkcjonalności. Dla utworzonych klas przesłoń również metodę `toString()`, tak aby zwracany łańcuch składał się z konkatenacji dwóch łańcuchów: wartości zwróconej z metody `toString()` klasy pochodnej oraz informacji opisującej parametry danej figury (również obliczone pole, obwód względnie objętość). 

## Zadanie 5

Utwórz 15-elementową tablicę przechowującą różne figury geometryczne. Przejdź tablicę przy użyciu pętli `while` i wywołaj dla każdego elementu tablicy metodę toString(). Przeanalizuj wyświetlone wyniki i opisz (komentarz).

###### Opracował dr inż. Wojciech Kozioł

###### Źródła

* http://edu.pjwstk.edu.pl/wyklady/poj/scb/Polimorf/Polimorf.html
