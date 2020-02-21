## <a name="withholding-tax-codes-to-msdyn_withholdingtaxcodes"></a>Códigos de retención de impuestos para msdyn_withholdingtaxcodes

Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Common Data Service.

Campo de Finance and Operations | Tipo de asignación | Otro campo de Dynamics 365 | Valor predeterminado
---|---|---|---
WITHHOLDINGCODE | = | msdyn_name | 
WITHHOLDINGTAXNAME | = | msdyn_description | 
WITHHOLDINGTAXROUNDOFF | = | msdyn_roundoff | 
WITHHOLDINGTAXROUNDOFFTYPE | >< | msdyn_roundofftype | 
CURRENCYCODEID | = | msdyn_currency.isocurrencycode | 
WITHHOLDINGTAXBASE | >< | msdyn_taxableamountorigin | 
