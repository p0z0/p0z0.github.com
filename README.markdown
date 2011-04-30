#first of all

###2.
`this` `is` `a` `test` 
###3.

    $container-> new Pimple();

### Above is just an example

<table>
	<tr>
		<td colspan="2" align="center">t1</td>
		<td colspan="2" align="center">t2</td>
		<td colspan="2" align="center">t3</td>
		<td colspan="2" align="center">t4</td>
		<td colspan="2" align="center">t5</td>
		<td colspan="2" align="center">t6</td>
		<td colspan="2" align="center">t7</td>
	</tr>
	<tr>
		<td>t1↦t2</td>
		<td>insert</td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td>t1↦t3</td>
		<td>insert</td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
</table>

<table width="400px">
	<tr>
		<td></td>
		<td align="center">t2</td>
		<td></td>
		<td align="center">t4</td>
		<td></td>
		<td align="center">t6</td>
		<td></td>
	</tr>
	<tr>
		<td align="center">t1</td>
		<td align="center">|</td>
		<td align="center">t3</td>
		<td align="center">|</td>
		<td align="center">t5</td>
		<td align="center">|</td>
		<td>t7</td>
	</tr>
	<tr>
		<td></td>
		<td align="center">inserted</td>
		<td></td>
		<td align="center">modified</td>
		<td></td>
		<td align="center">deleted</td>
		<td></td>
	</tr>
</table>


asd

###Mi ez?
A Kisalföld Volán helyi menetrendjeit (Győr, Sopron, Mosonmagyaróvár) magában foglaló alkalmazás Androidra

###Célok
A `BpMenetrend` hez hasonló működés és felület kialakítása, ezek közül is az előző az elsőszámú

###Felépítés
Jelenleg az alkalmazás négy csomagból áll

##com.github.pozo.volan
Az alkalmazás `Activity` osztályait tartalmazza,
 - `LineDetailsActivity` - egy kiválasztott járat részletes leírása
 - `ListofFavoritesActivity` - kezdő képernyő, a kedvencnek jelölt járatokat tartalmazza
 - `ListofLinesActivity` - a választott város összes járatát megjeleníti egy `ListView` ban

##com.github.pozo.volan.adapters
Listák adapter osztályait tartalmazza

##com.github.pozo.volan.items
XML olvasás közben használt osztályok

##com.github.pozo.volan.utils
Segéd osztályok
 - `Constants` - Adatbázishoz Intentekhez és egyebekhez használt állandók
 - `DbConnector` - Adatbázis kapcsolat
 - `LineHandler` - XXML
 - `Logger` - "kisalfoldvolan" taggel logol a LongCat-be
 - `SharedDialogs` - `Activity` k által használt azonos `Dialog` elemek
 - `SpecifiedLineHandler` - XML

###Működés
Az alkalmazás forrásként XML fájlokat használ amik a kvrt.hu oldalról származnak mégpedig:
 - Győr - Aktuális menetrend érvényes : 2010.12.12-től
 - Sopron - Aktuális menetrend érvényes : 2011.04.01-től
 - Mosonmagyaróvár - Érvényes : 2011.05.01-től
A `ListofFavoritesActivity` az alkalmazáshoz használt adatbázisból kiolvassa a rekordokat. Az `Activity` oszályok `Intent` segítségével kommonikálnak, amiknek a paraméterei a `Constants` osztályban vannak. A beállítás  `SharedPreferences` segítségével van megvalósítva ami egy XML-ben tárolja az aktuális város nevét.

###Jelenlegi állapot
 - 0.1 -Működés szempontjából a járat részleteit megjelenítő képernyő még nincs kész


### Fejlesztési célok
