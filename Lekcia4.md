# Premenné a vstup
*Naposledy sme si ukázali, ako vykonávať jednu vec alebo druhú. Občas chceme vykonávať jednu vec viac krát. To si ukážeme dnes.*

##While cyklus
`Cyklus` nazývame blok programu, ktorý sa niekoľko krát za sebou opakuje. 
Najjednoduchší spôsob, ako spraviť je cyklus použiť `while` cyklus. `while` funguje veľmi podobne príkazu `if` - tiež berie len jednu podmienku. Zatiaľčo `if` splnil kód v svojom bloku len raz, `while` ho bude plniť dokým podmienka nebude pravdivá.
 
```
#include <iostream>
using namespace std;
int main()
{
	int x = -1;
	while(x >= 0)
	{
		cin >> x;	
		cout << x << "\n";
	}
	
	return 0;
}
```

#####Cvičenie 1
*Spustite si predošlý program a zistite, kedy sa ukončí. Všimnite si, že ak prvé číslo na vstupe bude záporné, program nám ho vypíše tiež! Upravte ho tak, aby sa do cyklu v takom prípade nedostal a nevypísal nič.*

Klasický princíp, s ktorým sa veľmi často stretnete, je takzvaná premenná *counter*, ktorý nám počíta v ktorom opakovaní cyklu práve sme. *Counter* môžte ísť zhora dole alebo zdola hore a je väčšinou typu `int`. Najčastejšie ho označujeme písmenami *i,j,k...*.
```
#include <iostream>
using namespace std;
int main()
{
	int i = 1;
	while(i <= 10 )
	{
		cout << 5*i << "\n" ;
		i++;
	}
	
	return 0;
}
```

V tomto prípade premenná *i* je náš counter v cykle ktorý ide od *1* po *10*. 

#####Cvičenie 2
*Vyriešte na testovači úlohy Cykly sú super a pásik.*

#####Cvičenie 3
*Sami si vygooglite, aký presne je rozdiel medzi `while` a `do while` cyklami.*
##For cyklus
Najčastejší typ cyklu aký zažijeme má veľmi jednoduchú štruktúru - nastav countru hodnotu, pozri sa na podmienku, sprav nejaké príkazy a zmeň hodnotu countru.  
```
#include <iostream>
using namespace std;
int main()
{
	int i = 1;					//Nastavenie countru
	while(i <= 10 )			//Podmienka
	{
		cout << 5*i << "\n" ;	
		i++;				//Zmena countru
	}
	
	return 0;
}
```
Aby nám C++ uľahčilo prácu s takýmito cyklami, vznikol takzvaný `for` cyklus. Ten má následovnú štruktúru:
`for(nastavenie; podmienka; zmena hodnot){ telo cyklu }`
Konkrétny príklad - prepíšeme predchadzajúci program do `for`.
```
#include <iostream>
using namespace std;
int main()
{
	for(int i=1; i <= 10; i++ )
	{
		cout << 5*i << "\n" ;
	}
	return 0;
}
```
#####Cvičenie 4
*Opäť vyriešte na testovači úlohy Cykly sú super a pásik - pomocout for cyklu.*

Dôležitá poznámka - premenné ktoré vytvoríme vo `for` sú vytvorené v bloku programu, ktorý patrí `for` cyklu. Takže ak by sme spravili
```
#include <iostream>
using namespace std;
int main()
{
	for(int i=1; i <= 10; i++ )
	{
		cout << 5*i << "\n" ;
	}
		cout << 5*i << "\n";
	return 0;
}
```

tak nám kompilátor povie, že premenná `i` na riadku 9 nie je definovaná. Toto nám umožňuje nazývať  countre v rôznych `for` cykloch `i`.
```
#include <iostream>
using namespace std;
int main()
{
	for(int i=1; i <= 10; i++ )
	{
		cout << 5*i << "\n" ;
	}
	for(int i=1; i <= 10; i++ )
	{
		cout << 10*i << "\n" ;
	}
	return 0;
}
```
##Vnorené cykly
Tak ako sme mali vnorené bloky `if`, môžme mať aj vnorené bloky cyklov - či už `while` alebo `for`. Môžme mať aj `if` v cykle a môžme miešať rôzne typy cyklov - každý blok programu je akoby program sám o sebe. Pozorne si pozrite následujúci program, uhádnite čo robí a potom ho spustite.

```
#include <iostream>
using namespace std;
int main()
{
	for(int i=1; i <= 10; i++ )
	{
		for(int j=1; j <= 10; j++ )
		{
			cout << i*j << " ";
		}
		cout << "\n";
	}

	return 0;
}
```

#####Cvičenie 5
*Na testovači vyriešte úlohy Obdĺžnik a Trojuholník.*

Chceli by sme vám ukázať pár zložitejších programov, ktoré cykly využívajú. Prvý z nich dostane dve čísla. Následne vypíše všetky čísla od prvého po druhé.

```
#include <iostream>
using namespace std;
int main()
{
	int zaciatok, koniec;
	cin >> zaciatok >> koniec;
	if(zaciatok < koniec)
	{
		for(int i=zaciatok;zaciatok <= koniec; zaciatok++)
		{
			cout << i << "\n";
		}
	}
	else
	{
		for(int i=koniec;koniec >= zaciatok; i--)
		{
			cout << i << "\n";
		}
	}
	return 0;
}
```
Tento príklad vám má ukázať `for` cyklus idúci zhora nadol. Ďalší príklad by nemalo byť ťažké pochopiť.
```
#include <iostream>
using namespace std;
int main()
{
	int x = -1;
	while(x < 0)
	{
		cout << "Prosim zadaj kladne cislo.\n";
		cin >> x;
	}
	
	cout << "Konecne, zadal si " << x << "\n";
	return 0;
}
```

#####Cvičenie 6
*Naštudujte si, čo robia príkazy `break` a `continue`, a aký je medzi nimi rozdiel.*

##Ako hľadať chyby?
Váš program často nebude robiť to, čo od neho chcete. V takom prípade sú dve možnosti - buď je celý váš postup zlý alebo máte v programe chybu. Takýmto chybám sa hovorí **bug**, z anglického chrobák. Je to vraj preto, lebo prvý bug bol reálne chrobák zaseknutý v počítači. Kto vie koľko je na tomto príbehu pravdy.
S bugmi sa stretnete veľmi často. Zo začiatku to budú bugy ako použitie *if(x = y)* miesto *if(if == y)*. Častým bugom pri cykloch je takzvaný *off-by-one* - o jedna vedľa. Je to vtedy, keď sa cyklus vykoná o jedenkrát viac alebo menej ako by sa reálne mal - napr. ak chceme aby sa cyklus vykonal *n* krát a dáme mu `for(int i=0;i<=n;i++)`.  Veľmi zaujímavý bug, ktorý môže už u vás nastať je zacyklenie programu - napr. cyklus `for(int i=0;i<n;)` je zaujímavý kandidát. Takýto program bude bežať donekonečna.
Keď sa vo vašom programe vyskytne bug, spočiatku neviete, čo sa deje. Musíte ako detektív vyšetrovať, čo sa stalo a kde presne váš program zlyhal. Ako na to?
Najjednoduchší spôsob sú takzvané debugovacie výpisy. Znamená to, že si občas vypíšeme niečo, čo nie je súčasťou výstupu programu, ktorý chceme ale pomôže nám to pri debugovaní. Vieme si vypisovať napr. hodnoty premenných, v koľkatej iterácii cyklu práve sme alebo či sme sa dostali do ifu.
S debugovaním ešte strávite veľa času a postupne sa sami naučíte, ako nájsť chybu a opraviť ju.
#####Cvičenie 7
*Vyriešte na testovači úlohy Pyramída, Najväčší, Fibonacci. Pri týchto úlohach sa môžu vyskytnúť problémy - treba pri nich premýšľať oveľa viac ako pri predošlých. Na takýchto úlohach si začínate precvičovať vaše algoritmické myslenie. Možno sa stretnete aj s nejakým bugom. Odporúčame vám pri nich stráviť čo najviac času, a ak sa nepohnete tak nám napísať.*

