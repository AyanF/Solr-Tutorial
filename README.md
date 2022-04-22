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
   <fieldType name="currency" class="solr.CurrencyField" currencyConfig="currency.xml" defaultCurrency="USD" precisionStep="8"/>  
   
7. Create currency.xml file (clone from this repository)
    
8. Go to Schema in Solr UI and add the fields with given parameters for our JSON Books data

    title - type="string", uninvertible="false", docValues="false", indexed="true", required="true", stored="true"
    author - type="string", uninvertible="false", docValues="true", indexed="true", required="true", stored="false"
    genre - type="strings", indexed="true", stored="false", uninvertible="false", docValues="true", multiValued="true", required="true"
    date - type="pdate", uninvertible="false", indexed="true", required="true", stored="true"
    price - type="currency", uninvertible="false", indexed="true", required="true", stored="true"
    inStock - type="boolean", uninvertible="false", default="true", indexed="true", stored="true"
    type -     type="string", uninvertible="false", indexed="true", required="true", stored="true", docValues="false"
    summary - type="string", uninvertible="false", docValues="true", indexed="false", stored="false" 
    

