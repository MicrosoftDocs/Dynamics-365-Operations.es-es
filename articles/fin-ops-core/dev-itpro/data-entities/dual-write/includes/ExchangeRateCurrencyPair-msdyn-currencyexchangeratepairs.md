## <a name="exchange-rate-currency-pair-to-msdyn_currencyexchangeratepairs"></a>Par de divisas del tipo de cambio para msdyn_currencyexchangeratepairs

Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Common Data Service.

Campo de Finance and Operations | Tipo de asignación | Otro campo de Dynamics 365 | Valor predeterminado
---|---|---|---
EXCHANGERATEDISPLAYFACTOR | >< | msdyn_displayfactor | 
EXCHANGERATETYPENAME | = | msdyn_currencyexchangeratetypeid.msdyn_name | 
FROMCURRENCYCODE | = | msdyn_fromtransactioncurrencyid.isocurrencycode | 
TOCURRENCYCODE | = | msdyn_totransactioncurrencyid.isocurrencycode | 
