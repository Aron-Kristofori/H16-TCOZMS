---
share: "true"
---

### Príkazy, prepínač, cykly
+
#### Relačné a logické operátory

- **vytváranie a vyhodnocovanie podmienených príkazov**: Podmienené príkazy sú základom pre riadenie toku programu. Používajú sa na vykonanie rôznych častí kódu v závislosti od splnenia určitých podmienok.
- **príkaz `if()`**: Príkaz `if()` sa používa na vykonanie kódu, ak je splnená určitá podmienka. V zátvorkách sa nachádza podmienka, ktorá sa vyhodnocuje ako `true` alebo `false`.
- **rozšírenie podmienených príkazov pomocou `else()` a `if else()`**: Okrem jednoduchého `if` môžeme použiť aj `else`, aby sme definovali blok kódu, ktorý sa vykoná, ak podmienka `if` nie je splnená. Príkaz `else if()` umožňuje pridanie ďalších podmienok pre overenie.

#### Podmienený príkaz - všetko o ňom

- Podmienený príkaz je konštrukt, ktorý umožňuje rozhodovanie o tom, ktorý blok kódu sa má vykonať na základe splnenia určitej podmienky. Je to jedna z najzákladnejších a najdôležitejších štruktúr v programovaní.

#### Prepínač - rozdiel medzi C++ a C#

- V jazykoch C++ a C# sa prepínač (switch) používa na vetvenie programu na základe hodnoty určenej premennej. 
- Hlavný rozdiel medzi C++ a C# spočíva v tom, že V C# nemôže prepadnúť kontrola ďalšiemu prípadu (case) potom ako sa podmienka zhoduje v jednom z nich. Aby sme sa vynorili z prepínača musíme použit príkaz `break;` alebo `return();` a `throw();`. Naopak, prepínač v jazyku C++ pokračuje do ďalších prípadov ak nepoužijeme príkaz `break;`. 

#### Použitie cyklov - ako fungujú

- Cykly sú konštrukcie v programovaní, ktoré umožňujú opakované vykonanie určitého bloku kódu.
- Hlavné typy cyklov sú `for`, `while` a `do while`.
- Cyklus `for` sa používa, keď počet iterácií je známy vopred.
- Cyklus `while` sa používa, keď počet iterácií nie je známy vopred a vykonáva sa, kým je podmienka porušená.
- Cyklus `do while` je podobný `while`, ale vykoná sa aspoň raz, aj keď podmienka na začiatku nie je splnená.

#### Spôsoby predčasného ukončenia cyklu

- Predčasné ukončenie cyklu je proces, ktorý umožňuje programu skončiť cyklus pred jeho bežným koncom.
- Používa sa pre zlepšenie efektivity programu alebo na vyhnutie sa nežiaducim situáciám.
- Spôsoby predčasného ukončenia cyklu zahŕňajú použitie príkazov `break`, `continue` alebo zmienku o zastavení cyklu pomocou vhodnej podmienky.

#### Predčasné ukončenie iterácie

- Predčasné ukončenie iterácie sa používa na preskočenie aktuálnej iterácie cyklu a presunutie sa k ďalšej iterácii.
- V C++ a C# môže byť dosiahnuté pomocou príkazu `continue`, ktorý preskočí zostávajúci kód v tele cyklu a pokračuje na ďalšiu iteráciu.

#### Program - nájdenie najmenšieho čísla

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {3, 1, 4, 1, 5, 9, 2, 6, 5};
    int min = arr[0];
    for(int i = 1; i < 9; ++i) {
        if(arr[i] < min) {
            min = arr[i];
        }
    }
    cout << "Najmenšie číslo v poli je: " << min << endl;
    return 0;
}
```

#### Úloha štátu v trhovej ekonomike

- Štát má v trhovej ekonomike niekoľko úloh:
  - **Regulácia**: Štát zasahuje do ekonomiky prostredníctvom regulácií a zákonov, aby udržal spravodlivý trh a zabránil monopolom, klamavým praktikám a ďalším negatívnym javom.
  - **Poskytovanie verejných statkov a služieb**: Štát poskytuje verejné statky a služby, ktoré sú pre spoločnosť dôležité, ale neziskové alebo ťažko ziskové pre súkromný sektor, ako sú obrana, zdravotníctvo a vzdelanie.
  - **Redistribúcia bohatstva**: Štát môže zasahovať do ekonomiky prostredníctvom daní a sociálnych programov na vyrovnávanie rozdielov v bohatstve a zabezpečenie sociálnej stability.