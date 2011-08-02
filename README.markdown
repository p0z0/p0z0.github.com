JSON-RPC 2.0 Client/Server library for PHP
##Introduction
###Requirements
PHP 5.2.6+

###Used predefined classes/interfaces
 - `Countable` - `lib/utils/ObjectList` 
 - `Iterator` - `lib/utils/ObjectList`
 - `Exception` - `lib/server/JsonRpcExceptions`

##How do I use the client?
After you instantiate the `JsonRpcClient` with server url, there have two option to send a request. 
###Single request
To trigger a single request you have two way:
Use PHP `__call()` magic method,

    $client = new JsonRpcClient('http://serverurl';
    // you interested in returning value, so it can not be a notification
    $client->add(1,2);

or using `JsonRpcClient` `call()` method.

    $client = new JsonRpcClient('http://serverurl';
    // you interested in returning value
    $client->call(new RpcRequest('add',array()));

    // sent a notification, server response nothing
    $client->call(new RpcRequest('update',array('one',10),true));
    
    //every member have setter except id
    $request = new RpcRequest('add');
    $request->setParams(array(1,2.8));
    $client->call($request);

Both method returning an object if the request is not a notification. The object contain `id`,`jsonrpc` and `result` field if the process was successful, otherwise`error` insted of `result`. The `error` object has three members, `message`,`code` and `data` is optional.

###Batch request

###Operation in nutshell
 - `Constants` - Adatbázishoz Intentekhez és egyebekhez használt állandók
 - `DbConnector` - Adatbázis kapcsolat
 - `LineHandler` - XXML
 - `Logger` - "kisalfoldvolan" taggel logol a LongCat-be
 - `SharedDialogs` - `Activity` k által használt azonos `Dialog` elemek
 - `SpecifiedLineHandler` - XML

tutorial in wiki

##How do I use the server?
###Operation in nutshell
 - `Constants` - Adatbázishoz Intentekhez és egyebekhez használt állandók
 - `DbConnector` - Adatbázis kapcsolat
 - `LineHandler` - XXML
 - `Logger` - "kisalfoldvolan" taggel logol a LongCat-be
 - `SharedDialogs` - `Activity` k által használt azonos `Dialog` elemek
 - `SpecifiedLineHandler` - XML

##com.github.pozo.volan.utils
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