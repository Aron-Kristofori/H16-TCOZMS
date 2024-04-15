---
share: "true"
---

1. Princíp fungovania vstupno výstupného súborového systému
	1. 
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
	1. 
5. Spôsoby ako zistiť informácie o súboroch
6. Serializácia a deserializácia
	1. Serializácia je jav, pri ktorom sa stav objektu aj s údajmi konvertuje (serializuje) do prenosného formátu
	2. Deserializácia je opak, serializovaný objekt sa načítáva z úložiska 
	3. Objekty sa dajú serializovať do viacerých formátov ako sú: binárny formát, XML, JSON
7. Program - ktorý zapíše do súboru náhodne čísla, a chceme zistiť z tohoto súboru najmenšie číslo v súbore a počet párnych čísiel
8. Vysvetlite ak sú základné ekonomické voľby, ktorým čelí každá spoločnosť