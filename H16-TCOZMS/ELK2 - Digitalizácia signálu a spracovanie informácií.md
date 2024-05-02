---
share: "true"
---

# A
1. nakreslite a popíšte rozdiely medzi analógovým, číslicovým a digitálnym signálom
	- Analógovy signál - je spojitý, môže nadobudnút ľubovolnú hodnotu, informáciu nesie amplitúda signálu
	- Digitálny signál - diskrétny, nespojitý signál, informácie tu reprezentuje binárne kódovanie signál je buď HIGH alebo LOW (HIGH - 1, LOW - 0)
	
2. objasnite význam digitalizácie informácií
	- 
3. popíšte časové priebehy na vstupoch a výstupoch časovačov TON a TOF
	- 
4. popíšte základné kroky potrebné na digitalizáciu analógového signaĺu
	- 
5. vysvetlite, aké finančné zdroje môže využívať výrobca PC a zaraďte PC do majetku podniku
	- 
# B 
1. popíšte PDU na L2
	- Frame je PDU na vrstve L2
	- enkapsuluje PDU z L3 (packet)
	- pridáva Header a Footer
	- Header obsahuje minimálne
		- Preambula 10101010 * 7 bajtov
		- Start Frame Delimiter 101010**11**
		- MAC adresy: source a destination, pre WLAN možú byť ešte zvyšné 2 MAC adresy
		- protokol na vyššej vrstve
	- samotný packet
	- Footer
		- FCS (Frame Check Sequence)
		- systém na overenie či vo frame nedošlo k porušeniu údajov
2. popíšte spôsoby komunikácie half duplex a full duplex
	- Half-Duplex
		- médium je schopné len jednosmernej komunikácie
		- starý ethernet štandard pomocou Hubov, Coaxial
		- Ethernet bol elektricky vždy schopný full-duplex, limitáciou nie je kábel ale sieť okolo neho (1. pár - TX, 2. pár - RX, 3. pár - napájanie, 4. pár - rezerva)
			- Ethernet huby boli lacnejšie zariadenia t. j. CSMA-CD, zariadenia museli počúvať či niekto posiela keď oni vysielali aby detegovali kolíziu
		- WLAN siete
		- Jedno vlákno optiky je half-duplex, moderná optika už vie full-duplex na jednom vlákne ak je multimode ale inác dve vlákna pri single mode
	- Full-Duplex
		- médium je obojsmerné, zariadenie môže vysielať aj prijímať informácie naraz
3. vysvetlite spôsob komunikácie na spoločnom médiu
	- dva métody prístupu CSMA-CD, CSMA-CA
	- CSMA-CD - collision detection - ethernet half-duplex
	- CSMA-CA - collision avoidance - bezdrôtové siete
# C
1. popíšte MAC tabuľku
	- tabuľka MAC adries, priradená k portom na switchi
	- switch robí prepínacie rozhodnutia na základe tejto tabuľky
	- napr. pri cut-through switching, switch si načíta rámec po deštinačnú MAC adresu a začne ho prepínať na port
	- naplnenie MAC tabuľky sa deje keď príde rámec na port a zapíše sa jeho source adresa
	- ak swtich nemá v MAC tabuľke deštinačnú adresu rámca tak rámec daľej posiela na každý port okrem toho, na ktorom ho dostal
1. popíšte manažovanie switchu na L2
	- zabezpečenie vzdialeného prístupu cez SSH
	- autentifikácia užívateľov cez lokálny účet alebo AAA
	- pripojenie na swtich cez virutálne rozhranie (int vlan x)
	- zaheslovanie konzolového a EXEC mód prístupu
