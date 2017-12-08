# Premenné a vstup
*V minulej lekcii sme si povedali o tom, ako vyzerá program v C++. Vieme už vypísať texty na obrazovku. Takéto programy sú ale dosť nudné - nijako neinteragujú s uživateľom a vždy robia to isté. Dnes to zmeníme a naučíme sa, ako si od uživateľa niečo vypýtať a ako to vieme uložiť.*

##Premenné
**Premennú** si vieme predstaviť ako krabicu, ktorá má meno a je v nej uložená hodnota. Napr. v premennej *x* by mohla byť hodnota *40*. Premenné sú verné svojmu pomenovaniu a ich hodnoty preto vieme meniť. Takejto zmene hovoríme *priradenie*. Premennej *x* tak môžeme neskôr v programe priradiť novú hodnotu.

```
#include <iostream>
using namespace std;
int main()
{
	int x;
	x = 40;
	cout << "X ma hodnotu " << x << "\n";
	x = 30;
	cout << "Teraz ma X hodnotu " << x << "\n";
	return 0;
}
```

V tomto programe sa objavilo viacero vecí, ktoré sme doteraz nepoznali.
Prvý zaujímavý riadok je `int x;`. Na tomto riadku sme si vytvorili novú premennú. Každú premennú musíme vytvoriť predtým, než ju použijeme. Premennú vytvárame syntaxou `typ_premennej nazov_premennej;`
V C++ má každá premenná svoj **typ**, ktorý nám hovorí, aké operácie s ňou môžeme robiť a čo za hodnotu je v nej uložená. Prvý typ s ktorým sa zoznamujeme je `int` - označuje celé číslo so znamienkom v rozsahu od -2 147 483 648 do 2 147 483 647.
To je divné, prečo má premenná tak pevne stanovený rozsah čísel, ktoré v nej môžu byť? A prečo práve na takéto čísla?  Súvisí to s tým, ako sú čísla reálne reprezentované v pamäti počítača.

###Pamäť počítača
Počítač si musí počas behu programu pamätať momentálnu hodnotu premennej. Počítače nerozumejú ničomu inému okrem elektrických signálov a to tiež len dvom typom - buď signál je vysielaný alebo nie je. Pamäť počítača si preto vieme predstaviť ako dlhý pás núl a jednotiek. Keď si chce náš program zapamätať premennú, musí si v tejto pamäti vyhradiť miesto, kde si ju bude pamätať. Tento blok pamäte musí mať začiatok aj koniec - `int` má 32 bitov, to znamená, že v pamäti obsadil 32 pozícii, na ktorých sú nuly alebo jednotky.
Hodnota našej premennej sa na týchto miestach nachádza v **binárnej sústave**.

#####Cvičenie 1
*Zistite (vygooglite), čo je binárna sústava a ako prevádzať čísla z binárnej do našej, desiatkovej. Preveďte tieto čísla : 256, 255, 28 z desiatkovej do binárnej.*

#####Cvičenie 2
*Koľko rôznych čísel vieme zapísať pomocou 8 núl a jednotiek? Koľko pomocou 32? Toto cvičenie vám dá aj odpoveď na otázku, prečo má `int` obmedzenú hodnotu.*

Poznáme aj iné typy ako `int`. Ukážeme si ich na nasledujúcom programe. Všimnite si, že premenným vieme priradzovať hodnoty hneď pri vytváraní.

```
#include <iostream>
using namespace std;
int main()
{
	char c = 'A';				// char označuje premennú s jednym písmenom
	bool a = true;				// bool môže byť buď pravda (true) alebo nepravda (false)
	// Môžeme deklarovať aj viac premenných rovnakého typu na jednom riadku
	// Jednotlivé premenné oddelujeme čiarkou
	int x = 40, y = 4000000;
	// Celé číslo, ale 64 bitové namiesto 32. L na konci konštanty 999999999999L
	// znamená, že konštanta je 64 bitová.
	long long int velkeCislo = 999999999999L;
	unsigned int ux = 5;		// Celé nezáporné 32 bitové číslo, unsigned vieme dávať aj pred long long int
	double d = 3.14			// Číslo s desatinnou čiarkou
	return 0;
}
```

My zatiaľ budeme používať len premenné typu `int` a `long long int`. K ostatným typom sa dostaneme neskôr. Pri všetkých cvičeniach môžete rátať s tým, že sa vám všetky výsledky zmestia do `int`. Ak nie, upozorníme na to.
S premennými sme si ukázali už aj prvú operáciu - priradenie hodnoty. Premennej môžeme priradiť aj hodnotu inej premennej.

#####Cvičenie 3
*Čo spraví nasledujúci program? Najprv skúste na papieri uhádnuť, potom si to overte spustením.*

```
#include <iostream>
using namespace std;
int main()
{
	int a = 10, b = 400, x = 20, y = -123;
	x = a;
	a = b;
	b = x;
	y = b;
	x = 1;
	cout << a << " " << b << " " << x << " " << y << "\n";
	return 0;
}
```

##Vstup
Náš program často potrebuje interagovať s užívateľom a získavať od neho vstup - chceme zistiť, čo za klávesy stlačil alebo ako pohol myšou. My opäť začneme od najjednoduchšej formy vstupu, a to vstupom do konzoly.

```
#include <iostream>
using namespace std;
int main()
{
	int x;
	cin >> x;		// Načítame do x hodnotu, ktorú užívateľ zadá do konzoly
	cout << x << "\n";	// Vypíšeme hodnotu naspäť
	return 0;
}
```

Príkaz `cin` je podobný ako `cout` - oba slúžia na manipuláciu s konzolou. Všimnite si, že pri `cout` idú šípky opačným smerom ako pri `cin`. V `cout` posielame hodnotu z premennej do konzoly (`cout << x`), zatiaľčo pri `cin` čítame hodnotu z konzoly do premennej (`cin >> x`). Šípky tak vystihujú smer prúdenia dát, a jednoduchšie si tak spomeniete, ktoré treba použiť.

#####Cvičenie 4
*Vyriešte úlohy **cislo** a úlohu **zamena** na testovači.*

##Operácie s premennými
S premennými toho vieme robiť omnoho viac, ako si len zapamätávať nejaké hodnoty. Najdôležitejšie sú rôzne aritmetické operácie.  Pred tým, než tento program spustíte, skúste sa zamyslieť, čo vypíše pri vstupoch `1 2`, `5 10` a `3 3`. Potom si vaše výsledky overte.

```
#include <iostream>
using namespace std;
int main()
{
	int x, y;
	cin >> x;		// Načítame do x hodnotu, ktorú uživateľ zadá do konzoly
	y = x * 2;		// Násobenie
	y = y + 5;		// Sčítavanie - vieme k premennej priradiť jej hodnotu plus niečo
	x = y - x;		// Aj toto vieme spraviť
	y = -y;

	cout << x << " " << y - 8 << "\n";
	return 0;
}
```

Veľmi častá operácia je pripočítavanie nejakého čísla, často jednotky, k premennej. Toto nazývame inkrementovanie. Opak toho, teda odpočítavanie, nazývame dekrementovanie.

```
#include <iostream>
using namespace std;
int main()
{
	int x;
	cin >> x;

	// Tieto tri riadky robia to isté, inkrementujú x - je to len rozličná syntax
	x = x + 1;
	x += 1;
	++x;

	// Aj s násobením to ide
	x = x * 2;
	x *= 2;

	cout << x << "\n";
	return 0;
}
```

#####Cvičenie 5
*Povedali sme si, že `int` má rozsah od od -2 147 483 648 do 2 147 483 647. Čo sa stane, ak do intu dáme túto maximálnu hodnotu a potom ho zvýšime o 1? Naprogramujte program, ktorým to zistíte.*

#####Cvičenie 6
*Napíšte program, ktorý na vstupe dostane celé číslo a na výstup vypíše jeho druhú mocninu.*

Vieme teda sčitavať, násobiť, odpočítavať... Ešte sme si nespomenuli delenie. Nachádzame sa momentálne len v celých číslach, teda nie každé delenie nám dá presný výsledok. V C++ nám celočíselné delenie vráti výsledok zaokrúhlený nadol. Teda ak by bol výsledok *4.8*, vráti sa nám do celých čísel *4*. Delenie inak funguje rovnako ako ostatné operácie.
V celých číslach existuje aj druhá operácia súvisiaca s delením, zvyšok po delení. Napr. 5 má zvyšok 2 po delení 3. Táto operácia sa v programovaní využíva prekvapivo často.

#####Cvičenie 7
*Napíšte program, ktorý na vstupe dostane dve čísla a vypíše ich súčet, súčin, podiel a zvyšok po delení.*

#####Cvičenie 8
*Vyriešte na testovači úlohu obdĺžnik a priemer.*

#####Cvičenie 9
*Medzi typmi premenných, ktoré sme si ukázali bol aj `char`. Skúste k premennej typu `char` pripočítať malé celé číslo (napr. 2). Skúste `char` inkrementovať. Aké hodnoty sa vypíšu? Zistite, koľko bitov má char a čo je ASCII tabuľka.*

#####Cvičenie 10
*Čo sa stane ak vydelíme alebo spravíme zvyšok po delení nulou?*

#####Cvičenie 11
*Zistite čo najviac o reálnych číslach typu `double`. Skúste si v programe zadefinovať pár takýchto premenných a skúste si ich vydeliť, vynásobiť... Zistite, čo sa deje ak ku `int` pripočítame `double` a naopak.*
