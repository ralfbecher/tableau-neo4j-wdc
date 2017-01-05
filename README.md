# Neo4j Web Data Connector v2.0

This Tableau WDC implements WDC version 2.1.2 and can be used with Tableau v10.1 or later and Neo4j v3.0.4 or later:

[https://tableau.github.io/webdataconnector/docs/wdc_library_versions](https://tableau.github.io/webdataconnector/docs/wdc_library_versions)

For details on Tableau's Web Data Connector and the WDC SDK please visit:

[http://tableau.github.io/webdataconnector](http://tableau.github.io/webdataconnector)

This WDC uses the Neo4j Driver for Javascript which implements the [Bolt](https://en.wikipedia.org/wiki/Bolt_%28network_protocol%29) network protocol:

[https://github.com/neo4j/neo4j-javascript-driver](https://github.com/neo4j/neo4j-javascript-driver)

## Usage

The Neo4j WDC v2.0 can be used directly via GitHub Page URL:

[http://ralfbecher.github.io/tableau-neo4j-wdc/v2/Neo4jWdc2.html](http://ralfbecher.github.io/tableau-neo4j-wdc/v2/Neo4jWdc2.html) (copy URL)

![Neo4j WDC 2](tableau-neo4j-wdc2.png)

### Connector Parameters

1. **Data Source Name**: the name for the data source in the Tableau Workbook
2. **Neo4j URL**: URL to connect a Neo4j server, usually ```bolt://<server>``` when default Bolt port or ```bolt://<server>:<port>```
3. **Username/Password**: authentication credentials
4. **Inspect Rows for Schema**: number of sample rows (default: 1000) to inspect JSON result set (can contain complex objects) 
from Cypher queries for used properties, important to build the table schema with columns for Tableau; set to 1 when first 
row includes all properties
5. **Cypher Queries**: a list to add up to 5 Cypher queries for execution; use a table name per query in left column; 
tables can then be joined in Tableau data wizard later

![Neo4j WDC 2 Tableau Data Wizard](tableau-neo4j-wdc2-wizard.png)

<!---
### Run Neo4j WDC as Server Extension

Copy the extension library ```neo4j-web-extension-tableau-wdc-2.0.0.jar``` into the server’s plugin directory: 

```cp neo4j-web-extension-tableau-wdc-2.0.0.jar $NEO4J_SERVER_HOME/plugins```

Edit ```conf/neo4j.conf``` to register the package name with an endpoint:

```
#Comma separated list of JAXRS packages containing JAXRS Resource, one package name for each mountpoint.
dbms.unmanaged_extension_classes=org.neo4j.tableau.wdc=/tableau/wdc
```

Restart the server:

```/path/to/neo/bin/neo4j restart```

Then navigate in browser to the extension URL including HTTP Basic Authentication as URL parameters to start the Neo4j WDC Form:

```http://<username>:<password>@localhost:7474/tableau/wdc/```
--->

## Previous Version

The Neo4j WDC v1.0 can still be used via new URL:

[http://ralfbecher.github.io/tableau-neo4j-wdc/v1/Neo4jWdc.html](http://ralfbecher.github.io/tableau-neo4j-wdc/v1/Neo4jWdc.html)

![Neo4j WDC](tableau-neo4j-wdc.png)

## Author

**Ralf Becher**

+ [irregular.bi](http://irregular.bi)
* [twitter/irregularbi](http://twitter.com/irregularbi)
* [github.com/ralfbecher](http://github.com/ralfbecher)

## License

Copyright © 2016 Ralf Becher

Released under the MIT license.

***