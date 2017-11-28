# Úvod do C++

# Čo je to vlastne program?
*O čom tu celý čas rozprávame? Čo je to program? Čo je to algoritmus? Čo je to programovací jazyk? Ak si
myslíš, že tieto základy už vieš, môžeš túto sekciu preskočiť, inak si ju radšej prečítaj.*

**Algoritmus** je  postupnosť  niekoľkých  dobre  definovaných  inštrukcií  –  krokov,  ktorá  slúži  na  vykonanie nejakej úlohy. Napríklad algoritmus na uvarenie čaju môže byť nasledovný:
```
Zoberieme pohár, vrecúško čaju a rýchlovarnú kanvicu.
Naplníme kanvicu vodou, zapojíme do zásuvky a zapneme. 
Kým voda nevrie, čakáme. 
Do pohára vložíme vrecúško čaju a zalejeme vriacou vodou.
Kanvicu vypneme a vypojíme zo zásuvky.
Počkáme 8 minút a potom vyberieme vrecúško.
```
Super, vieme uvariť čaj (teda ak máme kanvicu atď. .), ale v tejto chvíli nás zaujímajú počítače. A počítač nevie  naplniť  kanvicu  vodou,  ani  nevie,  čo  je  kanvica  alebo  čo  je  voda.  Predošlý  algoritmus  je  ozajstným *algoritmom* len vtedy, ak vieme, čo znamenajú jednotlivé úkony (napríklad čo znamená zobrať pohár).

Keď budeme vytvárať algoritmy pre počítače, tak budeme používať celkom iné inštrukcie – také, ktorým počítač rozumie a vie ich aj vykonávať.
Medzi inštrukcie, ktoré počítač vie vykonávať patria napríklad jednoduché aritmetické operácie (sčítanie, delenie. . . ), čítanie z pamäte, ukladanie do pamäte, ale aj mnoho ďalších.
Avšak aby im dobre rozumel, musia byť zapísané ako hromada núl a jednotiek. A tým zase veľmi nerozumieme my ľudia. Preto existujú *programovacie jazyky*. Tie sú (väčšinou) dobre čitateľné ľuďmi a navyše si ich vie počítač prepísať do svojich jednotiek a núl.

My sa budeme zaoberať programovacím jazykom C++, ktorý patrí medzi vyššie programovacie jazyky – to znamená, že sa lepšie číta ľuďmi a zvláda toho oveľa viac ako nižšie.

**Program** je skupina inštrukcií v nejakom programovacom jazyku. A tieto programy obvykle niečo robia, inak by nám boli nanič.
V  našom  prípade  budeme  pracovať  s  programami,  ktoré  načítajú  nejaký  vstup  a  vypíšu  nejaký  výstup. 
**Vstup** je všetko, čo program dostane od nás. V našom prípade to bude väčšinou text, ktorý napíšeme do konzoly. 
**Výstup** je to, čo náš program vráti naspäť. U nás teda pôjde o to, čo vypíše do konzoly program.
Napríklad sčítací program môže načítať dve čísla a vypísať ich súčet.  Vstup by vyzeral takto:
```12 17```
A výstup by vyzeral takto:
```29```
Čím zložitejšie programy, tým zložitejšie sú vstupy a výstupy. Pri počítačovej hre sú vstupy klávesy, ktoré stláčate alebo kliknutia myše. Výstupy sú to, čo vidíte na monitore alebo zvuk z reproduktorov. 

**Kompilácia** je prepis programu napísaného v programovacom jazyku do strojového kódu (jednotiek a núl), ktorý dokáže počítač spustiť. Za nás bude kompiláciu vykonávať online kompilátor - aby ste si na počítač nič nemuseli inštalovať.

#####Cvičenie 1
*Treba všetky programovacie jazyky kompilovať? Skúste nájsť, aký je rozdiel medzi interpretovanými a kompilovanými jazykmi a nájsť príklad na oba typy.*

Poďme teda naprogramovať náš prvý program!

 
# Náš prvý program
*Tu by som vás chcel poprosiť, aby ste nekopírovali programy pomocou Ctrl-C a Ctrl-V. Lepšie a rýchlejšie sa naučíte, ak vám to prejde cez prsty a sami si ich napíšete*

```
#include <iostream>

int main()
{
	std::cout << "Ahoj!";
	return 0;
}
```

Poďme si po riadkoch rozobrať tento program.

Prvý riadok programu je `#include <iostream>`. Toto nám dovolí používať funkcie na vstup a výstup do konzoly. Tento náš prvý program nemá žiaden vstup, ale len výstup. 
Na treťom riadku je `int main()`. Main označuje začiatok programu, všetko čo je v jeho tele ( medzi kučeravými zátvorkami `{` a `}`) sú príkazy, ktoré náš program vykoná. 
Na piatom riadku je `std::cout << "Ahoj!\n";`. `std::cout` je naša konzola, kam vypisujeme výstup programu. `<<` nám v tomto prípade hovorí, že posielame to z pravej strany na ľavú. Teda posielame text `"Ahoj\n"` do výstupu na konzolu. Je to v skutočnosti trochu zložitejšie, ale toto nám na zažiatok stačí. Texty v programe dávame medzi dvojité úvodzovky - `""`. 
Šiesty riadok - `return 0;` nám hovorí, že program má vrátiť hodnotu 0. Operačný systém, ktorý spustí náš program, očakáva, že mu povieme, či sa programu podarilo spraviť čo chcel, alebo nie. To mu povieme tak, že mu vrátime hodnotu. Hodnota 0 znamená, že program zbehol bez chyby. 
Na poslednom riadku ukončíme telo funkcie main druhou kučeravou zátvorkou.

Nespomenuli sme si ešte jednu vec - niektoré riadky majú na konci `;`. Bodkočiarka v C++ označuje koniec príkazu. V našom programe sú len dva príkazy - jednym vypíšeme text `Ahoj` a druhým vrátime systému hodnotu 0. 

## Poďme to spustiť!
Aby ste si nič nemuseli inštalovať, rozhodli sme sa používať online editor. Tento editor nájdete na stránke [tu](https://www.onlinegdb.com/online_c++_compiler). Napíšte tam váš program a kliknite na zelené tlačítko **Run**. Dole v konzole uvidíte vypísané `Ahoj!`. 

*Pokiaľ budete mať s hocijakým cvičením problém, vždy sme tu na slacku my alebo spolužiaci. Skúste najprv prejsť všetky cvičenia predtým než budete pokračovať v texte*

#####Cvičenie 2
*Skúste meniť váš program. Zmeňte `Ahoj` na `Ahoj C++`, `main` na `mai`, odstráňte kučeravé zátvorky alebo len jednu z nich, zmažte `std` z pred `cout` a tak ďalej. Zistite, ktoré programy sa vám dajú spustiť a ktoré nie. Väčšina zmien spôsobí, že vám kompilátor povie, že máte chybu. Prečítajte si ju a sledujte, ako sa zmení keď spravíte niečo iné.*
#####Cvičenie 3
*Použite dva krát príkaz `std::cout` - teda akoby ste chceli dva krát vypísať na konzolu. Jeden dajte nad  `return 0` a druhý pod. Popremýšľajte, čo takýto program spraví a overte si to spustením. Potom dajte obidva pred `return 0` a pozrite sa, čo spraví váš program teraz.*


Pri druhej časti cvičenia 2 ste zistili, že sa vám obe veci vypíšu hneď za seba, na jeden riadok. Je to preto, že `std::cout` nám vypíše len to, čo mu pošleme, a nikde sme mu neposlali, že má vytlačiť koniec riadku. Vo väčšine programovacích jazykoch je koncom riadkov priradený znak `'\n'`. 
```
#include <iostream>

int main()
{
	std::cout << "Ahoj!\n";
	std::cout << "Pisem na novy riadok!\n";
	return 0;
}
```
#####Cvičenie 4
*Skúste predošlý program napísať tak, že použijete len jeden príkaz std::cout.*
##Komentáre
Občas potrebujeme do programu napísať vysvetlenie toho čo robíme - komentár. Komentáre kompilátor ignoruje, preto do nich môžme napísať čokoľvek. 
```
#include <iostream>
//Toto je jednoriadkovy komentar, oznacuje sa dvoma lomitkami

/*
Ked chceme komentar na viac riadkov,
pouzivame lomitko s hviezdickou
*/
int main()
{
	std::cout << "Ahoj!";	//Komentar moze byt aj tu
	return 0;
}
```
Je veľa rôznych názorov, prečo a kedy písať komentáre. My budeme občas komentáre používať, aby sme vám priamo v kóde vysvetlili, čo kód robí.
## Using namespace std
Doteraz sme si nevysvetlili, prečo príkaz `std::cout` vyzerá tak zložito a škaredo. Čo znamená `std` a prečo tam sú tie dve dvojbodky? Toto je zložitejší a zatiaľ menej zaujímavý koncept v C++, zjednodušene sa dá pvoedať, že `cout` patrí do `std` a tak keď ho používame, musíme najprv povedať kde ho chceme hľadať. Kebyže ale máme v programe veľa rôznych vecí v `std` a nechce sa nám to písať vždy, keď niečo odtiaľ použijeme, vieme povedať kompilátoru, nech všetko skúsi hľadať rovno v `std`, tým, že na začiatok programu dáme `using namespace std;`.
```
#include <iostream>
using namespace std;
int main()
{
	cout << "Ahoj!\n";
	cout << "Pisem na novy riadok!\n";
	return 0;
}
```
Hneď je to krajšie! Pozor ale, proti `using namespace std` vo veľkých projektoch existuje veľa výhrad, vy to ale zatiaľ môžte bežne používať.

#####Cvičenie 5
*Predstav sa nám :) Naprogramuj program, ktorý vypíše, ako sa voláš, na akú školu chodíš, koľkaták si a koľko máš rokov. Môžeš nám o sebe napísať aj hocičo ďalšie, napr. čo by si sa chcel naučiť v tomto kurze. Fungujúci zdrojový kód programu nám prosím pošli cez Slack.*


##Testovač
Aby sme nemuseli všetky vaše úlohy testovať ručne, našli sme testovač ktorý to bude robiť za nás. Testovač sa nachádza na stránke [tu](https://testovac.ksp.sk/wiki/), musíte sa zaregistrovať. Tvoju prezývku nám pošli cez Slack, môžeš aj v rámci cvičenia 5. 
Až budete zaregistrovaní a prihlásení, nájdite si prvú úlohu zo sady *Úvod do programovania* - **Ahoj**. 
V úlohe odovzdávate váš program (musíte si ho stiahnúť na počítač, ak ho píšete v online editore, je to jedno z tlačítok - šipka smerujúca nadol)  a testovač vám automaticky povie, či je správny. Úloha je veľmi jednoduchá, skúste ju vyriešiť :)



Tak držím palce v plnení úloh, píšte, ak máte hocijaké nejasnosti alebo problémy. O týždeň si povieme niečo o premenných a o tom, ako načítavať vstup z konzoly. Veľa šťastia :) 




