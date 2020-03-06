# C++ string class alapjainak megismerése.

A string class objektjei szöveges adatok tárolására alkalmasak. 
Használatához a programunk elején includeolnunk kell a string header fájlt(#include \<string\>).
A class objektjeit egyszerűbb kezelni, mint a már megszokott C stílusú stringeket(Char tömbök).
Tekinthetünk a class objektjeire úgy, mintha sima változók lennének.    
(A példákban nem használom a 'using namespace std;' utasítást.)

## Érték adása az objecteknek, alap műveletek.
----------------------------------------------------------------------------------------------------------------------------------------
**String objectnek adhatunk értéket úgy, mintha egy sima változó lenne.**
```cpp
std::string str = "Hello World";
std::cout << str; // Kiírja, hogy Hello World.
```
----------------------------------------------------------------------------------------------------------------------------------------
**Egy stringet hozzárendelhetünk egy másik stringhez egyszerűen.**
```cpp
std::string str2 = " my name";
std::string str3 = str2; // Ilyenkor a 'my_string' értékét átmásoltuk 'str2'-be.
str3 = "test"; // Valid, ilyenkor a már meglévő érték helyett az általunk megadottat fogja tárolni.
```
----------------------------------------------------------------------------------------------------------------------------------------
**A már jól ismert C stílusú char tömbökkel ezt megvalósítani kicsit több munka.**
```C
char arr[22] = "adc is weak";
char arr2[20] = arr; // Error. C stílusú stringeknél saját magunknak kellene átmásolni az értékel például egy strcpy() függvénnyel. 
 ```
---------------------------------------------------------------------------------------------------------------------------------------
**String osztállyal egyszerű a stringek összefűzése is!**
```cpp
std::string str4 = str + str2; // str4 jelenleg a következőt tárolja: "Hello World my name".
str4 += " Jeff."; // str4 string végéhez hozzácsatoltunk még szöveget.
```
----------------------------------------------------------------------------------------------------------------------------------------
**Figyeljük meg a következő példát.**
```C
char arr3[10] = "ahri"; // OK
strcat(arr3, " is the best girl."); // Memória probléma.
 ```
A(z) strcat() függvény megpróbálná mind a 18 karaktert átmásolni az arr3 tömbbe, viszont így már átfutna a szomszédos memóriába.    
Szerencsére a string class okosabb ennél, és amikor szükséges automatikusan átméretezi a változót amivel dolgozunk, ahogy a fentebbi példákban is láthatjuk.

---------------------------------------------------------------------------------------------------------------------------------------

## String input, elemek elérése.

**Input beolvasásához, használhatjuk a következőt.**
```cpp
std::string str5;

std::cin >> str5; // Ebben az esetben a legelső 'space'-ig megy a cin, és azt olvassuk be str5-be.

std::getline(std::cin, str5); // Teljes sor beolvasása str5-be. Ilyenkor a "newline" karakterig olvasunk be adatot a változónkba.
```
----------------------------------------------------------------------------------------------------------------------------------------
**Stringünk egyes karaktereihez közvetlenül hozzáférhetünk a [] operátor használatával pont úgy, mintha átlagos tömbbel dolgoznánk.**
```cpp
std::string str6 = "Test String.";
std::cout << str6[5]; // Output: S
str6[0] = 'B'; // str6 most "Best String"
 ```
----------------------------------------------------------------------------------------------------------------------------------------
## Tagfüggvények.
**Mint tudjuk egy osztálynak lehetnek tagfüggvényei, melyekhez a következő módon férhetünk hozzá: object.Function_Name(arguments)**    
**Ez pontosan így van a string classnál is. Nézzünk meg néhány példát.**

**Length** tagfüggvény.    
Ez a tagfüggvény visszatér a stringben lévő karakterek számával.

```cpp
std::string str7 = "hello";
int len = str7.length();

std::cout << "str7: " << str7 << " | Karakterek szama: " << len; // Output: "str7: hello | Karakterek szama: 5"
 ```
---------------------------------------------------------------------------------------------------------------------------------------- 
**Replace** tagfüggvény.    
Kicseréli egy std::string általunk megadott részét valami más stringre.
```cpp
std::string str8 = "Soraka is the best champion in League of Legends.";
str8.replace(0, 6, "Ezreal");
std::cout << str8; // Output: "Ezreal is the best champion in League of Legends."
```
----------------------------------------------------------------------------------------------------------------------------------------
**FONTOS:** *Az imént megnéztünk néhány tagfüggvényt, viszont létezik ezeken kívül több is, melyeknek ismerete nagyban megkönnyítheti munkánkat. A string class tagfüggvényeit, és a hozzájuk tartozó leírást elérhetjük a következő linken: https://en.cppreference.com/w/cpp/string/basic_string*


## Gyakori hiba inputnál, mi történik és hogy javíthatjuk.
















