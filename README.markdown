JSON-RPC 2.0 Client/Server library for PHP

###Requirements
PHP 5.2.6+

###Used predefined classes/interfaces

###How do I use the client?
##Operation in nutshell

tutorial in wiki
###How do I use the client?
##Operation in nutshell

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
 - 0.1 - Az activityk közti kapcsolati logika és pár funkcionalitás megvalósítva

## TODO
 - A járat részletes adatait megjelenítő képernyő logikájának kidolgozása
 - Az lista utolsó elemének duplázásának eltávolítása
 - Kedvencek Activityn az első hozzáadáskor a járat középre ugrik
 - Megállók szerint kedvencekhez adás (Megállók activity ?)
 - UI