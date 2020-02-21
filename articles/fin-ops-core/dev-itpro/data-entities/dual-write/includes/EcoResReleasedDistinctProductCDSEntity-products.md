## <a name="cds-released-distinct-products-to-products"></a>CDS lanzó productos únicos a productos

Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Common Data Service.

Campo de Finance and Operations | Tipo de asignación | Otro campo de Dynamics 365 | Valor predeterminado
---|---|---|---
PRODUCTNUMBER | >> | msdyn_productnumber | 
PRODUCTNAME | >> | name | 
PRODUCTDESCRIPTION | >> | descripción | 
ITEMNUMBER | >> | msdyn_itemnumber | 
CURRENCYCODE | >> | transactioncurrencyid.isocurrencycode | 
SALESUNITSYMBOL | >> | defaultuomid.msdyn_symbol | 
SALESPRICE | >> | precio | 
UNITCOST | >> | currentcost | 
PRODUCTTYPE | >> | producttypecode | 
SALESUNITDECIMALPRECISION | >> | quantitydecimal | 0
ISCATCHWEIGHTPRODUCT | >> | msdyn_iscatchweight | 
PRODUCTCOLORID | >> | msdyn_productcolor.msdyn_productcolorname | 
PRODUCTCONFIGURATIONID | >> | msdyn_productconfiguration.msdyn_productconfiguration | 
PRODUCTSIZEID | >> | msdyn_productsize.msdyn_productsize | 
PRODUCTSTYLEID | >> | msdyn_productstyle.msdyn_productstyle | 
