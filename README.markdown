JSON-RPC 2.0 Client/Server library for PHP
##Introduction
###Requirements
PHP 5.2.6+

###Used predefined classes and interfaces
 - `Countable` @ `lib/utils/ObjectList` 
 - `Iterator` @ `lib/utils/ObjectList`
 - `Exception` @ `lib/server/JsonRpcExceptions`

##How do I use the client?
After you instantiate the `JsonRpcClient` with the server URL, there have two option to send a request. Both method using the `RpcRequest` class @ 'lib/client/' which help us to sending a well formatted request.
###Single request
####Sending a request
So, triggering a single request you can:
Using the PHP `__call()` magic method,

    $client = new JsonRpcClient('http://serverurl');
    // notification not allowed here
    $response = $client->add(1,2);

Using `JsonRpcClient` `call()` method:

    $client = new JsonRpcClient('http://serverurl');
    $response = $client->call(new RpcRequest('add',array(1,9.8)));

    // a notification, server will response nothing
    $response = $client->call(new RpcRequest('update',array('one',10),true));
    
    //every member has setter except id
    $request = new RpcRequest('add');
    $request->setParams(array(1,2.8));
    $response = $client->call($request);

####Accepting the response
If the request is not a notification, and the process was successful, the response will return an object which contain `id`,`jsonrpc` and `result` fields, otherwise the result object will contain `error` instead of `result`. The `error` object has three members, `message`,`code` and `data` which is optional.

###Batch request
####Sending a request

####Accepting the response

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