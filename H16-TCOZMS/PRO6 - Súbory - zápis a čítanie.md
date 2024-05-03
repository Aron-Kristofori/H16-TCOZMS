---
share: "true"
---

1. Princíp fungovania vstupno výstupného súborového systému (ChatGPT)
	Vstupno-výstupný (I/O) súborový systém je základný mechanizmus, ktorý umožňuje programom komunikovať so súbormi a ďalšími zariadeniami (ako napríklad tlačiarne, klávesnice, displeje atď.) na počítači. Jeho princíp fungovania môže byť zhrnutý v niekoľkých krokoch:
	1. **Otvorenie súboru**: Program požiada operačný systém o otvorenie konkrétneho súboru, ktorý chce použiť na vstup alebo výstup.
	2. **Priradenie deskriptora súboru**: Operačný systém priradí deskriptor súboru programu. Deskriptor je abstraktný odkaz, ktorý program používa na identifikáciu súboru v ďalších operáciách vstupu a výstupu.    
	3. **Čítanie alebo zápis dát**: Program môže čítať dáta zo súboru (v prípade vstupného operácie) alebo zapisovať dáta do súboru (v prípade výstupného operácie). Tieto operácie sa vykonávajú pomocou deskriptora súboru.
	3. **Uzavretie súboru**: Po dokončení práce so súborom program uzavrie súbor. Tým sa uvoľnia zdroje, ktoré boli priradené k súboru, a zabráni sa nežiaducemu zápisu alebo čítaniu dát.    
	4. **Správa chýb a výnimiek**: Počas procesu vstupu a výstupu môžu nastať chyby, ako napríklad nedostupnosť súboru, nedostatočné povolenie na prístup a ďalšie. Program musí správne spracovať tieto chyby a výnimky, aby užívateľovi poskytol vhodné oznámenie.
	Celý tento proces zabezpečuje, že programy môžu efektívne a spoľahlivo pracovať so súbormi a ďalšími zariadeniami, čím umožňuje užívateľom manipulovať s dátami na počítači.

2. Metódy a objekty použivané pri súborových vstupno/výstupných operáciach

```cpp
#include <fstream>

int main() {
    // Vytvorenie objektu file na manipulácia so súborom
    std::fstream file("test.txt", std::ios::in | std::ios::out);

    // Kontrola či súbor je otvorený
    if (file.is_open()) {
        // Zápis dát do súboru
        file << "Hello, world!\n";

        // Načítanie dát zo súboru
        std::string line;
        file >> line;
        std::cout << "Data read from file: " << line << std::endl;

        // Presunúť ukazovateľ na začiatok súboru
        file.seekg(0);

        // Čítanie celého súboru po riadku
        std::string content;
        while (std::getline(file, line)) {
            content += line + "\n";
        }
        std::cout << "File content:\n" << content << std::endl;
        
        // Uzatvorenie súboru
        file.close();
    }
    return 0;
}
```

```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Otvoriť súbor
        using (FileStream file = new FileStream("test.txt", FileMode.OpenOrCreate, FileAccess.ReadWrite))
        {
            // Zápis textových údajov do súboru
            StreamWriter writer = new StreamWriter(file);
            writer.WriteLine("Hello, world!");
            writer.Flush();

            // Presunút ukazovateľ na začiatok súboru
            file.Seek(0, SeekOrigin.Begin);

            // Prečítať údaje zo súboru
            StreamReader reader = new StreamReader(file);
            string line = reader.ReadLine();
            Console.WriteLine("Údaje zo súboru: " + line);

        }
    }
}

```
3. Charakteristika jednotlivých typov súborov
	1. Binárne súbory
		- údaje v binárnych súboroch reprezentujú vlastný formát
	2. Textové súbory
		- textové súbory sú určené na ukladanie textových znakov pomocou viacerých formátov alebo kodóvaní
		- najčastejšie sa využíva UTF-8
4. Spôsoby zapisovania a načítania súborov
	1. neviem
5. Spôsoby ako zistiť informácie o súboroch
	1. neviem
6. Serializácia a deserializácia
	-  Serializácia je jav, pri ktorom sa stav objektu aj s údajmi konvertuje (serializuje) do prenosného formátu
	- Deserializácia je opak, serializovaný objekt sa načítáva z úložiska 
	- Objekty sa dajú serializovať do viacerých formátov ako sú: binárny formát, XML, JSON
7. Program - ktorý zapíše do súboru náhodne čísla, a chceme zistiť z tohoto súboru najmenšie číslo v súbore a počet párnych čísiel
```c#
using System;
using System.IO;
using System.Linq;

namespace TCOZMS_Subory
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int min = 1;
            int max = 10;
            int pocet = 5;
            using(FileStream file1 = new FileStream("vstup.txt", FileMode.OpenOrCreate, FileAccess.ReadWrite))
            {
                StreamWriter sw = new StreamWriter(file1);
                Random gen = new Random();
                for(int i = 0; i < 5; i++) {
                sw.WriteLine(gen.Next(min, max));
                }
                sw.Close();
                file1.Close();
            }
            int parne = 0;
            int najmensie = max;
            using (FileStream file2 = new FileStream("vstup.txt", FileMode.Open, FileAccess.Read))
            {
                StreamReader sr = new StreamReader(file2);
                while(!sr.EndOfStream)
                {    
                    int cislo = Convert.ToInt32(sr.ReadLine());
                    //debug
                    Console.WriteLine(cislo);
                    if (cislo % 2 == 0)
                    { parne++; }
                    if( cislo <= najmensie)
                    {
                        najmensie = cislo;
                    }    
                }
                sr.Close();
            file2.Close();
            }
            Console.WriteLine("Pocet parnych cisel je: " + parne);
            Console.WriteLine("Najmensie cislo je: " + najmensie);
            Console.ReadKey();
        }
    }
}

```
8. Vysvetlite ak sú základné ekonomické voľby, ktorým čelí každá spoločnosť