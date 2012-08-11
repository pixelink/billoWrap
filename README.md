# Billomat API

## billoWrap

Parameters
----------

### bmId

Param: string

This is your billomID  which you use to login in your right Domain


### bmApiKey

Param: string

This is the billomat API Key.
Here you can find how to activate your API Key under the Headline Authentication.
Here you can find it http://www.billomat.com/en/api/basics/


### dataType

Param: boolen
Default: TRUE

Output data in JSON-Object, false otherwise for XML-Object. Also you can use NULL to output data in HTML.


### convertData

Param: boolen
Default: FALSE

Converts the dataobject if "TRUE" to Array. Use "NULL" for get HTML header.

### useSocket

Notice: not yet ready for usage

Param: boolen
Defaul: FALSE

If true the request is done by socket, otherwise by curl.


## Usage Example

Now take a look how we retrive Data from the "billomat API" we choose for this example to get all our Clients
    <?php
        require_once 'billowrap.php';

        $bmId = 'YourBillomatID'; // this is your billomatID you use to login
        $bmApiKey = 'YourApiKey'; // the API Key you will got it from billomat settings check the explanation http://www.billomat.com/en/api/basics/
	$dataType = true; // Set to true, to output JSON Object, false otherwise for XML Object
	$convertData = false; // Convert the JSON or XML data to Array 

    
        $billoWrap = new billoWrap($bmId, $bmApiKey, $dataType, $convertData);
    
        $data = $billoWrap->getClients();
        print_r($data);
    ?>


Now we want to choose one special Client, therefor we only define the id for it.
    <?php
        require_once 'billowrap.php';
    
        $billoWrap = new billoWrap('YourBillomatID', 'YourApiKey', DataType, ConvertToArray);

        $id = 12345; // the Client you want to show
    
        $data = $billoWrap->getClients($id); 
        print_r($data);
    ?>


## Changelog