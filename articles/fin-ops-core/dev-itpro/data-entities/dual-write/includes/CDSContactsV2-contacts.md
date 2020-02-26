## <a name="cds-contacts-v2-to-contacts"></a>Contactos V2 de CDS para contactos

Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Common Data Service.

Filtro de origen: (AssociatedContactType = 1)

Filtro de origen invertido: msdyn_contactforvendor eq true y msdyn_sellable eq false y msdyn_contactpersonid ne ''

Campo de Finance and Operations | Tipo de asignación | Otro campo de Dynamics 365 | Valor predeterminado
---|---|---|---
CONTACTPERSONPARTYNUMBER | = | msdyn_partynumber | 
ASSOCIATEDCONTACTTYPE | << | none | Proveedor
FIRSTNAME | = | firstname | 
MIDDLENAME | = | middlename | 
LASTNAME | = | lastname | 
ASSOCIATEDCONTACTNUMBER | = | msdyn_vendorcontactid.msdyn_vendoraccountnumber | 
PRIMARYADDRESSCITY | = | address1_city | 
PRIMARYADDRESSCOUNTRYREGIONID | = | address1_country | 
PRIMARYADDRESSCOUNTYID | = | address1_county | 
PRIMARYFAXNUMBER | = | fax | 
PRIMARYADDRESSSTATEID | = | address1_stateorprovince | 
PRIMARYADDRESSSTREET | = | address1_line1 | 
PRIMARYADDRESSZIPCODE | = | address1_postalcode | 
PRIMARYPHONENUMBER | = | telephone1 | 
PRIMARYEMAILADDRESS | = | emailaddress1 | 
EMPLOYMENTDEPARTMENT | = | departamento | 
NOTAS | = | descripción | 
SEXO | >< | gendercode | 
GOVERNMENTIDENTIFICATIONNUMBER | = | governmentid | 
PRIMARYURL | = | websiteurl | 
MARITALSTATUS | >< | familystatuscode | 
ISRECEIVINGDIRECTMAIL | >< | donotemail | 
EMPLOYMENTPROFESSION | = | jobtitle | 
SPOUSENAME | = | spousesname | 
none | >> | msdyn_contactforvendor | Verdadero
CONTACTPERSONID | = | msdyn_contactpersonid | 
