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
####Request
So, triggering a single request you can:
Using the PHP `__call()` magic method,

    $client = new JsonRpcClient('http://serverurl';
    // notification not allowed
    $response = $client->add(1,2);
    
    if($response->)
echo $response->result;

Using `JsonRpcClient` `call()` method.

    $client = new JsonRpcClient('http://serverurl';
    // you interested in returning value
    $client->call(new RpcRequest('add',array()));

    // sent a notification, server response nothing
    $client->call(new RpcRequest('update',array('one',10),true));
    
    //every member have setter except id
    $request = new RpcRequest('add');
    $request->setParams(array(1,2.8));
    $client->call($request);

####Response
If the request is not a notification it will return an object which contain `id`,`jsonrpc` and `result` field if the process was successful, otherwise the result object will contain `error` instead of `result`. The `error` object has three members, `message`,`code` and `data` which is optional.

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