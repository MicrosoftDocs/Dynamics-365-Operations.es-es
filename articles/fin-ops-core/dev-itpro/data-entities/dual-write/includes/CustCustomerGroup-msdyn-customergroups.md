## <a name="customer-groups-to-msdyn_customergroups"></a>Grupos de clientes para msdyn_customergroups

Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Common Data Service.

Campo de Finance and Operations | Tipo de asignación | Otro campo de Dynamics 365 | Valor predeterminado
---|---|---|---
CUSTOMERGROUPID | = | msdyn_groupid | 
DESCRIPCIÓN | = | msdyn_description | 
ISSALESTAXINCLUDEDINPRICE | >< | msdyn_issalestaxincludedinprice | 
PAYMENTTERMID | = | msdyn_paymenttermid.msdyn_name | 
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn_clearingperiodpaymenttermname.msdyn_name | 
