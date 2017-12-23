# Podmienky
*Niekedy v programe chceme, aby sa program rozhodol a spravil niečo podľa stavu premenných. Napr. v hre chceme aby ak hráč vystrelí, nech vyletí guľka a trafí tam kam mieri. Zároveň chceme, aby sa to nestalo ak nemá náboje.*

## Logické výrazy
Možno ste už mali v škole na matematike výrokovú logiku. Logika sa zaoberá výrokmi a ich pravdivosťou. Táto časť matematiky je pri programovaní veľmi užitočná, my si preto jej základy v rýchlosti vysvetlíme.

**Výrok** je každá veta, o ktorej má zmysel povedať, či je pravdivá alebo nepravdivá. Napr. *Vonku prší.* je výrok - môžte byť pravdivý alebo nepravdivý podľa toho, či vonku práve prší. *Bude zajtra pršať?* nie je výrok. Výrok nemôže byť súčasne pravdivý aj nepravdivý.
Výroky v matematike označujeme veľkými tlačenými písmenami - A, B, C... Vieme napr. povedať, že A je výrok *2 + 2 = 5* a výrok B je *9 je deliteľné 3ma*. Pravdivosť výroku označujeme buď 0(nepravda) alebo 1(pravda). S výrokmi vieme robiť operácie (označíme ich ako v C++, matematici majú na ne svoje označenia):

- A && B - logická spojka "a zároveň", A && B je pravdivé ak je pravdivý výrok A aj výrok B.
- A || B - spojka "alebo", A || B je pravdivý ak je jeden z výrokov A, B pravdivý - teda ak sú aj oba.
- !A - negácia, je pravdivá ak A je nepravdivé a nepravdivá ak A je pravdivé.

***Cvičenie 1***
*Máme tri výroky A, B a C a výraz **(( (!A) || B) && C)**. Nájdite všetky možné hodnoty A, B a C pri ktorých je formula pravdivá.*
 
***Cvičenie 2***
*Vytvorte negáciu výroku "2 < 3"*

Ako získame v C++ výroky? V C++ máme typ premennej `bool`, ktorý môže nadobudnuť hodnoty `true` alebo `false` - tiež môžme zapísať ako 1 a 0. Tiež máme porovnávacie operátory ktorými vieme porovnať nejaké premenné alebo hodnoty.

```
#include <iostream>
using namespace std;
int main()
{
	bool a = (1==3);			// rovna sa	. vsimnite si dve rovna sa. Jedno by znamenalo priradenie.
	bool b = (1<'3');			// menej ako
	bool c = (2>3);			// viac ako
	int x, y;
	cin >> x >> y;
	bool d = (x <= y);			// menej alebo rovne ako
	bool e = (x >= y);			// viac alebo rovne ako
	bool f = (x != y);			// nerovna sa
	cout<< a <<" "<< b <<" "<< c <<" "<< d <<" "<< e <<" "<<f;
	return 0;
}
```
Tiež vieme používať logické spojky o ktorých sme si povedali.

```
#include <iostream>
using namespace std;
int main()
{
	int x,y,z;
	cin >> x >> y >> z;
	bool a = ((x==y) && (x == z));			
	bool b = ((x!=y) || (x==z));
	bool c = !(x==y);
	bool d = (c || (x==y));
	bool e = (x > 3);
	
	cout<< a <<" "<< b <<" "<< c <<" "<< d <<" "<< e;
	return 0;
}
```
***Cvičenie 3***
*Skúste si rôzne čísla a predpovedajte pre ne výstup posledných dvoch programov. Overujte si vaše tipy spustením programov.*


## If
Chceme naprogramovať jednoduchý program - na vstupe dostane jedno číslo a vypíše, či je toto číslo väčšie od 1000. 
Potrebujeme sa tu nejako rozhodnúť, čo vypíšeme podľa výsledku logickej operácie `x >= 1000`. Na toto nám slúži `if`.


```
#include <iostream>
using namespace std;
int main()
{
	int x;
	cin >> x;
	if(x > 0)				//Pokial plati podmienka, vykona sa blok kodu v ife
	{
		cout << "Vacsie od 0\n";
	}
	return 0;
}
```
***Cvičenie 4***
*Nečítajte text ďalej než nespravíte toto cvičenie. Dorobte do predošlého programu dva ďalšie ify, aby vypísal "1000" ak je číslo na vstupe rovné 1000 a "Mensie od 1000" ak je menšie.*

## Else
Často chceme, aby sa kód rozhodol a vykonal niečo ak platí podmienka a niečo iné ak neplatí - aj v cvičení 4 ste to spravili. Aby sme nemuseli vždy písať if so znegovanou podmienkou, existuje príkaz `else`

```
#include <iostream>
using namespace std;
int main()
{
	int x;
	cin >> x;
	if(x > 1000)
	{
		cout << "Vacsie od 1000\n";
	}
	else
	{
		if(x == 1000)
		{
			cout << "Rovne 1000\n";
		}
		else
		{
			cout << "Mensie od 1000\n";
		}
	}
	return 0;
}
```
Stále je to veľa písania, a čím viac možností by sme mali, tým viac by sme museli písať. Tretia možnosť podmienok - `else if` funguje ako `else` aj `if` zároveň - vykoná sa, len ak sa `if` nevykonal a zároveň ak je splnená podmienka v jeho `if`.
```
#include <iostream>
using namespace std;
int main()
{
	int x;
	cin >> x;
	if(x > 1000)
	{
		cout << "Vacsie od 1000\n";
	}
	else if(x == 1000)
	{
		cout << "Rovne 1000\n";
	}
	else
	{
		cout << "Mensie od 1000\n";
	}
	return 0;
}
```

***Cvičenie 5***
*Naprogramujte jednoduchú kalkulačku. Na vstupe budú postupne prvé číslo, znamienko +, -, * , / a druhé číslo. Teda napr. `1 + 87`. Na výstup vráťte výsledok operácie (pri delení napíšte celočíselný podiel a zvyšok po delení).
Príklad vstupu:
`10 / 3`
Výstup:
`3 1`*

***Cvičenie 6***
*Na testovači vyriešte úlohy Zvyšok po delení 7, Akéže je znamienko a Rovnaké čísla. *

## Zložitejšie ify
Už sme si ukázali na začiatku, ako môžme spájať logické výrazy do zložitejších pomocou operácii. Toto môžme aj v ife.

```
#include <iostream>
using namespace std;
int main()
{
	int x, y, z;
	cin >> x >> y >> z;
	if(x >= y && x >= z)
		cout << "x je najvacsie\n";
	return 0;
}
```

## Bloky programu
Za ifom nasleduje takzvaný **blok programu**, ktorý sa vykoná pokiaľ je podmienka pravdivá. S blokmi programu sa budeme stretávať často, preto je dobré si o nich niečo povedať.

Pokiaľ má blok len jeden príkaz, môže sa písať bez kučeravých zátvoriek.
```
#include <iostream>
using namespace std;
int main()
{
	int x, y, z;
	cin >> x >> y >> z;
	if(x >= y && x >= z)
		cout << "x je najvacsie\n";
	return 0;
}
```
Pokiaľ má blok viac ako len jeden príkaz, musíme jazyku povedať odkiaľ pokiaľ je tento blok kučeravými zátvorkami. V bloku môže byť ľubovoľne veľa príkazov a aj ďalšie, vnorené bloky.
```
#include <iostream>
using namespace std;
int main()
{
	int x, y, z;
	cin >> x >> y >> z;
	if(x + y + z == 0)
	{
		cout << "Sucet x, y a z je 0.\n";
	}
	else 
	{
		cout << "Sucet x, y a z nie je 0.\n";
		if(x + y == 0)
		{
			cout << "Sucet x a y je 0.\n";
		}
		if(x + z == 0)
		{
			cout << "Sucet x a z je 0.\n";
		}
		if(z + y == 0)
		{
			cout << "Sucet y a z je 0.\n";
		}
		
	}
	return 0;
}
```
V predošlom príklade by sme vnútorné bloky mohli napísať aj bez kučeravých zátvoriek.

Zaujímava vec je, ako sa premenné správajú v blokoch. Nemôžme vytvoriť dve premenné s rovnakým názvom v jednom bloku. Premenná má ale istú životnosť, existuje len v bloku v ktorom bola vytvorená.
```
#include <iostream>
using namespace std;
int main()
{
	if(10 == 10)
	{
		int a = 5, b = 6;
	}
	cout << a << " " << b << "\n";			\\ Chyba - a ani b tu uz neexistuju
	return 0;
}
```

 V bloku môžme používať premenné, ktoré sme vytvorili mimo bloku a vieme meniť ich hodnoty.
 
```
#include <iostream>
using namespace std;
int main()
{
	int a = 5, b = 6;
	if(10 == 10)
	{
		a = 10;
		b++;
	}
	cout << a << " " << b << "\n";
	return 0;
}
```

A teraz najväčšie prekvapenie - vyskúšajte si nasledujúci program.

```
#include <iostream>
using namespace std;
int main()
{
	int a = 5, b = 6;
	if(10 == 10)
	{
		int a = 10, b = 8;
		b++;
		cout << a << " " << b << "\n";
	}
	cout << a << " " << b << "\n";
	return 0;
}
```

Premenné vytvorené v bloku dočasne nahradia tie mimo neho ak majú rovnaký názov. Niekedy sa nám to hodí, ale treba si na toto správanie dávať pozor.

***Cvičenie 7***
*Na testovači vyriešte úlohy Najmenší, Prostredný a Nenajväčší. Skúste pri tom použiť čo najmenej ifov - dávajte prednosť zloženým podmienkam.*

***Cvičenie 8***
*Napíšte program, ktorý dostane na vstupe číslo mesiaca - od 1 do 12 a vypíše, koľko dní má tento mesiac.*

***Cvičenie 9***
*Napíšte program, ktorý dostane na vstupe 3 dĺžky úsečok. Výstup bude `ANO` ak môžu byť stranami jedneho trojuholníka a `NIE` ak nemôžu.*

***Cvičenie 10***
*Veľká časť programovania spočíva v hľadaní informácii. Nájdite si, čo je `switch` v C++ a ako ho používať. Potom skúste pomocout `switch` vyriešiť nasledujúcu úlohu - na vstupe dostanete číslo od 1 po 7. Na výstup vypíšte slovom toľkatý deň v týždni - pre vstup 1 teda výstup bude `Pondelok` a pre vstup `7` to bude `Nedela`.*
