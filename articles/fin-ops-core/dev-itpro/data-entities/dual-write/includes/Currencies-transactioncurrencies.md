## <a name="currencies-to-transactioncurrencies"></a>Divisas para transactioncurrencies

Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Common Data Service.

Filtro de origen: ((CURRENCYCODE != "999"))

Campo de Finance and Operations | Tipo de asignación | Otro campo de Dynamics 365 | Valor predeterminado
---|---|---|---
CURRENCYCODE | = | isocurrencycode | 
NOMBRE | = | currencyname | 
SYMBOL | = | currencysymbol | 
none | >> | exchangerate | 1
