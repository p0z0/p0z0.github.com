Kisalföld Volán helyi menetrendjeit (Győr, Sopron, Mosonmagyaróvár) magában foglaló alkalmazás Androidra

##Célok
A `BpMenetrend` hez hasonló működés és felület kialakítása, ezek közül is az előző az elsőszámú

##Felépítés
Jelenleg az alkalmazás négy csomagból áll

###com.github.pozo.volan
Az alkalmazás `Activity` osztályait tartalmazza,

 - `LineDetailsActivity` - egy kiválasztott járat részletes leírása
 - `ListofFavoritesActivity` - kezdő képernyő, a kedvencnek jelölt járatokat tartalmazza
 - `ListofLinesActivity` - a választott város összes járatát megjeleníti egy `ListView` ban

###com.github.pozo.volan.adapters
Listák adapter osztályait tartalmazza

###com.github.pozo.volan.items
XML olvasás közben használt osztályok

###com.github.pozo.volan.utils
Segéd osztályok

 - `Constants` - Adatbázishoz Intentekhez és egyebekhez használt állandók
 - `DbConnector` - Adatbázis kapcsolat
 - `LineHandler` - XXML
 - `Logger` - "kisalfoldvolan" taggel logol a LongCat-be
 - `SharedDialogs` - `Activity` k által használt azonos `Dialog` elemek
 - `SpecifiedLineHandler` - XML

##Működés
Az alkalmazás forrásként XML fájlokat használ amik a kvrt.hu oldalról származnak mégpedig:

 - Győr - Aktuális menetrend érvényes : 2010.12.12-től
 - Sopron - Aktuális menetrend érvényes : 2011.04.01-től
 - Mosonmagyaróvár - Érvényes : 2011.05.01-től

A `ListofFavoritesActivity` az alkalmazáshoz használt adatbázisból kiolvassa a rekordokat. Az `Activity` oszályok `Intent` segítségével kommonikálnak, amiknek a paraméterei a `Constants` osztályban vannak. A beállítás  `SharedPreferences` segítségével van megvalósítva ami egy XML-ben tárolja az aktuális város nevét.

##Jelenlegi állapot
 - 0.1 -Működés szempontjából a járat részleteit megjelenítő képernyő még nincs kész


## Fejlesztési célok
