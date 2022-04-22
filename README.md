Solr Tutorial for beginners

1. Download and unzip Solr
 
2. Open a new terminal in Solr directory & navigate to bin folder
 
3. Start Solr by using the command :
 
    ./solr start
    
4.Create a new core :

  ./solr create -c sampleCore 
  
5. Log on to :

   http://localhost:8983/solr/#/sampleCore/core-overview
   
   your core is live
   
6. Add Field type currency in managed-schema.xml :

   fieldType name="currency" class="solr.CurrencyField" currencyConfig="currency.xml" defaultCurrency="USD" precisionStep="8"
   
7. Create currency.xml file (clone from this repository)
    
8. Go to Schema in Solr UI and add the fields with given parameters for our JSON Books data

    1.title -
	
	 type="string", uninvertible="false", docValues="false", indexed="true", required="true", stored="true"

    2.author - 

	type="string", uninvertible="false", docValues="true", indexed="true", required="true", stored="false"

    3.genre -

	 type="strings", indexed="true", stored="false", uninvertible="false", docValues="true", multiValued="true", required="true"

    4.date -

	 type="pdate", uninvertible="false", indexed="true", required="true", stored="true"

    5.price -

	 type="currency", uninvertible="false", indexed="true", required="true", stored="true"

    6.inStock - 

	type="boolean", uninvertible="false", default="true", indexed="true", stored="true"

    7.type -  

	type="string", uninvertible="false", indexed="true", required="true", stored="true", docValues="false"

    8.summary - 

	type="string", uninvertible="false", docValues="true", indexed="false", stored="false" 

   9.quantity
	
	type="pint" uninvertible="false" docValues="false" indexed="false" stored="false" required="false"

9. Preparing JSON data

	example-

	{
		"id":"bookid"
		"title":"The Subtle Art Of Not Giving a "
		"author":"Mark Mason"
		"genre":"Self-help"
		"date":"1972-05-20T17:33:18Z"
		"price":43
		"inStock":"true"
		"type":"Paperback"
		"summary":"The Subtle Art of Not Giving a F*ck is a book that challenges the conventions of self-help by inviting the reader to NOT try, say no often 			and embrace negative thinking. Not giving a f*ck is about being comfortable with being different and caring about something more important 			than adversity."
	}

10. Run JSON queries from Postman.
	

    

