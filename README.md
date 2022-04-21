# 2021l4web-app-mockup-Adam-Safr
Webová aplikace pro školní ligu v malé kopané
* Slouží k vylepšení dosavadního papírového systému školní ligy
* Lepší přehlednost pro účastníky i fanoušky
* Přehledný seznam všech informací prezentován jinde než na papíře u tělocvičny
* Zajímavé statisky vycházející z výsledků

Web bude přístupný všem studentům školy a nejlépe aby vyžadoval pouze jedno přihlášení přes Office účet - automatické **ne**odhlašování.
Pokud se přihlásí nějaký tělocvikář, měl by mít možnost do systému zapisovat výsledky zápasů, čas střelení gólu, způsob střelení gólu a jméno střelce. Učitel také do systému zadá rozložení týmů ve skupině. Zbytek si vypočítá systém sám; včetně rozlosování zápasů.

## Rozložení stránek
* Jako `index.html` je stránka *Pravidla* se základními informacemi a pravidly
* Další stránka je *Skupiny*, kde se nachází tabulky vylosovaných skupin včetně výsledků jednotlivých zápasů ve skupině
* Stránka *Program* zobrazuje harmonogram jednotlivých zápasů včetně odpočtu dnů do zápasů
* Na stránce *Pavouk* je postupový pavouk týmů a výsledné pořadí týmů
* Poslední stránka *Statistiky* nabízí mnoho zajímavých statistik vycházejících z výsledků zápasů

## Barvy
+ ![#3566B9](https://via.placeholder.com/15/3566B9?text=+) `#3566B9` 
	+ Veškerý modrý text
	+ `background-color` menu
	+ Pozadí tlačítek
	+ Pozadí headeru u tabulek se statistikami
	+ Ikony "otevřít a sbalit"
+ ![#1A1A1A](https://via.placeholder.com/15/1A1A1A?text=+) `#1A1A1A` 
	+ `font-color` hlavního textu, nadpisů, textů v tabulkách a harmonogramu
+ ![#F5F5F5](https://via.placeholder.com/15/F5F5F5?text=+) `#F5F5F5` 
	+ `background-color` celého body
+ ![#FFFFFF](https://via.placeholder.com/15/FFFFFF?text=+) `#FFFFFF` 
	+ `background-color` jako pozadí textových částí, pozadí tabulek skupin, pozadí harmonogramu, pozadí části se statistikami

## Font
+ Pro veškerý text je použit bezpatkový font [Oswald](https://fonts.google.com/specimen/Oswald)
+ Nadpisy typu `h1` mají velikost `40px`
+ Napdisy typu `h2` mají velikost `32px`
+ Text `p` má velikost `18px`
+ Text v menu má velikost `20px`

## Navigační menu
* Menu se nachází na topu obrazovky a **ne**má `position: fixed`
* Menu je rozdělené na tři části
	* Vlevo se nachází název webu
	* Uprostřed je logo školy, které přesně v půlce přechází z menu pryč
	* V pravé části se nachází navigační prvky

## Stránka Pravidla
* Na stránce se nachází tři statické sekce
* Sekce s pravidly hry, sekce s informacemi o postupu a sekce s informacemi pro studenty, kteří se chtějí zúčastnit
* Všechny texty se získají od pana Zákouckého

## Stránka Skupiny
* Na stránce se zobrazují všechny vylosované skupiny
* Skupiny zadají do systému tělocvikáři
* První dva týmy postupují do čtvrtfinále
* Kliknutím na ikonu *Detaily zápasů* se rozbalí seznam všech zápasů ve skupině
	* Seznam se vysune z pod-tabulky s krátkou animací, kdykoliv se dá opětovným kliknutím na ikonu zavřít (zasunout);
	* Při rozbalení se ikona *Detaily zápasů* natočí o 180 stupňů;
	* Jsou zde vidět výsledky všech zápasů,
		* střelci gólů, 
		* minuta střelení gólu (seřezeno logicky podle času vzestupně), 
		* zda byl gól střelen z penalty - označení (P),
		* zda byl gól vlastní - označení (vl.).
	* Při mobilním zobrazení jsou karty zápasů zobrazeny po jedné pod sebou.
	* Při dostatečně velkém zobrazení jsou karty zápasů zobrazeny vedle sebe:
		* Od šířky obrazovky `768px` se zobrazí karty zápasů pod sebe po dvojicích;
			* Dvojice obsahuje právě dvě stejně široké karty, výška je daná velikostí větší karty;
			* Následující dvojice začína `10px` pod předchozí;
		* Od šířky obrazovky `1350px` se zobrazí karty zápasů pod sebe po trojicích;
			* Logika celikosti stejná jako u předchozí velikosti;
		* Od šířky obrazovky `2500px` se zobrazí karty zápasů pod sebe po čtveřicích;

### Jednotlivé tabulky skupin
* Každá tabulka ukazuje počet odehraných zápasů, výher, proher, remíz a skóre
	* Podle odehraných zápasů se tyto údaje mění
		* Přidáním zápasu do databáze se tabulky aktualizují a přepočítají se údaje
	* Počet bodů určuje řadí v tabulce
		* Výhra zápasu +3 body pro vítěze
		* Remíza zápasu +1 bod pro oba týmy
	* V případě shodného počtu bodů se rozhoduje podle výsledku vzájemného zápasu

## Stránka Program
* Na stránce se nachází jediná sekce s daty zápasů, která se dá filtrovat
* Systém sám vylosuje rozpis zápasů tak, aby:
	* Hrál každý s každým pouze jednou;
	* Týmy hráli pouze v týdnu od pondělí do pátku;
	* Každá skupina hrála jiný týden - nestane se, že skupina A již bude mít odehráno 2x více zápasů než jiná skupina;
* Na stránce se nachází filtrování podle skupin, spočátku jsou všechny filtry zabalené
* Po kliknutí na ikonu u dané skupiny se rozbalí rozpis pro danou skupinu
	* V první kolonce je napsáno kdo s kým hraje (pod headingem Zápas)
	* V prostřední kolonce je datum uskutečnění zápasu (pod headingem Datum)
	* V poslední kolonce je číslo počtu dnů do zápasu (pod headingem Počet dní do zápasu):
		* Pokud je počet dní více než 3, je číslo modrou barvou;
		* Pokud je počet dní 3 a méně, je číslo žlutou barvou;
		* Pokud je počet dní 0 (tzn. hraje se dnes), je číslo červenou barvou;
	* Kolonky mají zarovnání textu na střed 
	* Velikost kolonek není stejná: 
		* Největší je kolonka s datem
* Rozpis je pevný a po vylosování se nemění

## Stránka Pavouk
* Pro neznalé - pavouk je označení pro vyřazovací systém rozpisu utkání :tw-1f609:
* Na stránce je graficky upravený rozpis utkání
* Do čtvrtfinále postupují první dva z každé skupiny
	* Vítěz skupiny hraje s druhým z jiné skupiny, konkrétně:
		* Vítěz skupiny A hraje s druhým skupiny B
		* Vítěz skupiny B hraje s druhým skupiny A
		* Vítěz skupiny C hraje s druhým skupiny D
		* Vítěz skupiny D hraje s druhým skupiny C
* Do semifinále postoupí vítězové čtvrtfinále, kteří hrají proti sobě:
	* Vítěz čtvrfinále č. 1 hraje s vítězem čtvrtfinále č. 3
		* Vítěz čtvrtfinále mezi A1/B2 hraje proti vítězi C1/D2
		* Vítěz čtvrtfinále mezi B1/A2 hraje proti vítězi D1/C2

### Jednotlivé prvky
* Jednotlivé zápasy jsou vypsány v bloku
	* Jednotlivé bloky jsou ve čtvrtfinále a semifinále stejně dlouhé
	* U finále je pouze jeden blok, a ten je široký jako dva předchozí i s mezerou
* Blok má pozadí v barvě  ![#E0E0E0](https://via.placeholder.com/15/E0E0E0?text=+) `#E0E0E0` 
* Pod blokem se zápasem následuje blok s datumem zápasu a ikonou rozbalení
	* Datum i ikona je hlavní modrou barvou
	* Pozadí tohoto menšího bloku je čistě bílé
	* Text je výrazně menší
	* Kliknutím na ikonu se rozbalí karta utkání, stejně jako to funfuje na stránky *Skupiny*
* V dolní části je sekce Pořadí
	* Zde je výsledné pořadí týmů
	* Na posledním místě je tým s nejméně body
		* V případě shody rozhoduje rozdíl skóre
			* Rozdíl počtu vstřelených gólů a počtu obdržených gólů, čím menší číslo, tím horší výsledek
	* Od posledního do čtvrtého místa je vše napsané stejným stylem
		* Třetí a druhé místo je mnohem větší
		* Vítěz je největší
		
## Stránka Statistiky
* Tato stránka zobrazuje tabulky NEJ statistik
* Rozdělení je na týmové a hráčské statistiky
* Tabulky mají stejnou velikost a zobrazují šest nejlepších v dané statistice
* Nadpis tabulky a první místo mají pozadí hlavní modrou barvou
* Ostatní místa jsou oddělena šedou linkou
* Po kliknutí na ikonu *Celé pořadí* se rozvine tabulka a zobrazí se statistiky až úplně do konce

###  Týmové statistiky
* Zobrazení statistik týkajících se pouze jednotlivých mužstev
* Pokud je číslo 0, neřadí se do danée tabulky (0 gólů, 0 penalt, 0 karet, atd...)
* Tabulka *Góly* zobrazuje nejlépe střílející týmy
	* Vychází z databáze zápasů a řadí týmy podle toho, kdo dá nejvíc gólů
	* V případě rovnosti je na lepším umístění tým, který má lepší skóre
* Tabulka *Obdržené góly* zobrazuje řadí týmy, které dostali nejvíce gólů
	* ČÍm více gólů tým dostal, tím je v tabulce výše
* Tabulka *Penalty* udává počet nejvíce zahrávaných penalt

###  Hráčské statistiky
* Statistiky jednotlivých hráčů
* Tabulka *Góly* zobrazuje nejlepší střelce
	* Vychází ze součtu gólů ke jménu
	* Vítěz vyhlášen jako nejlepší střelec
* Tabulka *Žluté karty* zobrazuje hráče s nejvíce žlutými kartami
	* Vychází ze zápisu v kartě utkání
* Tabulka *Asistence* udává hráče s nejvíce asistencemi
	* Vítěz vyhlášen jako nejlepší nahravač

## End