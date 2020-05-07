---
title: Cadena de dependencia de entidad (orden de sincronización)
description: Este tema especifica el orden de sincronización que debe seguir para crear datos de inicio.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9ae14703941b97308bca5845eeac3eb9b181ae75
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275496"
---
# <a name="entity-dependency-chain-synchronization-order"></a>Cadena de dependencia de entidad (orden de sincronización)

[!include [banner](../../includes/banner.md)]

Este tema especifica el orden de sincronización que debe seguir para crear los datos iniciales si no está utilizando las dependencias de entidad proporcionadas por la característica **sincronización inicial**. Si no está usando **sincronización inicial**, debe ejecutar cada mapa de entidad individualmente.

## <a name="dynamics-365-supply-chain-management-entities"></a>Entidades de Dynamics 365 Supply Chain Management

Las siguientes entidades de Supply Chain Management se listan en el orden en el que debe habilitarlas.

| Nombre de asignación en la página de doble escritura | Nombre de metadatos de la entidad en Supply Chain Management | Nombre de metadatos de la entidad en Common Data Service | Notas |
|---|---|---|---|
| Unidades ... uoms                                                                      | UnitOfMeasureEntity                                    | uom                                          | |
| Conversiones de unidades ... msdyn_unitofmeasureconversions                                 | UnitOfMeasureConversionEntity                          | msdyn_unitofmeasureconversion                | |
| Todos los productos ... msdyn_globalproducts                                               | EcoResEveryProductEntity                               | msdyn_globalproduct                          | |
| Grupos de dimensiones de productos ... msdyn_productdimensiongroups                           | EcoResProductDimensionGroupEntity                      | msdyn_productdimensiongroup                  | |
| Grupos de dimensiones de almacenamiento ... msdyn_productstoragedimensiongroups                    | EcoResStorageDimensionGroupEntity                      | msdyn_productstoragedimensiongroup           | |
| Grupos de dimensiones de seguimiento ... msdyn_producttrackingdimensiongroups                  | EcoResTrackingDimensionGroupEntity                     | msdyn_producttrackingdimensiongroup          | |
| Colores ... msdyn_productcolors                                                      | EcoResProductColorEntity                               | msdyn_productcolor                           | |
| Tamaños ... msdyn_productsizes                                                        | EcoResProductSizeEntity                                | msdyn_productsize                            | |
| Estilos ... msdyn_productstyles                                                      | EcoResProductStyleEntity                               | msdyn_productstyle                           | |
| Configuraciones ... msdyn_productconfigurations                                      | EcoResProductConfigurationEntity                       | msdyn_productconfiguration                   | |
| Productos lanzados V2 ... msdyn_sharedproductdetails                                 | EcoResReleasedProductV2Entity                          | msdyn_sharedproductdetail                    | |
| Common Data Service lanzó productos únicos ... productos                         | EcoResReleasedDistinctProductCommon Data ServiceEntity | producto                                      | |
| Código de barras identificado de número de producto ... msdyn_productbarcodes                         | EcoResProductNumberIdentifiedBarcodeEntity             | msdyn_productbarcode                         | |
| Configuración de pedido predeterminada ... msdyn_productdefaultordersettings                        | InventProductDefaultOrderSettingsEntity                | msdyn_productdefaultordersetting             | |
| Configuración de pedido predeterminada del producto V2 ... msdyn_productspecificdefaultordersettings     | InventProductSpecificOrderSettingsV2Entity             | msdyn_productspecificdefaultordersetting     | |
| Conversiones de unidades específicas del producto ... msdyn_productspecificunitofmeasureconversions | EcoResProductSpecificUnitConversionEntity              | msdyn_productspecificunitofmeasureconversion | |
| Sitios ... msdyn_operationalsites                                                    | InventOperationalSiteEntity                            | msdyn_operationalsite                        | |
| Almacenes ... msdyn_warehouses                                                     | InventWarehouseEntity                                  | msdyn_warehouse                              | Ver [nota 1](#scm-notes). |
| Colores de producto maestro ... msdyn_sharedproductcolors                                 | EcoResProductMasterColorEntity                         | msdyn_sharedproductcolor                     | |
| Tamaños de producto maestro ... msdyn_sharedproductsizes                                   | EcoResProductMasterSizeEntity                          | msdyn_sharedproductsize                      | |
| Estilos de producto maestro ... msdyn_sharedproductstyles                                 | EcoResProductMasterStyleEntity                         | msdyn_sharedproductstyle                     | |
| Configuraciones de producto maestro ... msdyn_sharedproductconfigurations                 | EcoResProductMasterConfigurationEntity                 | msdyn_sharedproductconfiguration             | |
| Categorías de productos ... msdyn_productcategories                                      | EcoResProductCategoryEntity                            | msdyn_productcategory                        | Ver [nota 2](#scm-notes). |
| Asignaciones de categorías de productos ... msdyn_productcategoryassignments                   | EcoResProductCategoryAssignmentEntity                  | msdyn_productcategoryassignment              | |
| Jerarquías de categorías de producto ... msdyn_productcategoryhierarchies                   | EcoResProductCategoryHierarchyEntity                   | msdyn_productcategoryhierarchy               | |
| Roles de jerarquía de categorías de producto ... msdyn_productcategoryhierarchyroles            | EcoResProductCategoryHierarchyRoleEntity               | msdyn_productcategoryhierarchyrole           | |
| Inventario de pasillo ... msdyn_warehouseaisles                                           | WMSWarehouseAisleEntity                                | msdyn_warehouseaisle                         | |
| Zonas de almacén ... msdyn_warehousezones                                            | WHSWarehouseZoneEntity                                 | msdyn_warehousezone                          | |
| Grupos de zona de almacén ... msdyn_warehousezonegroups                                 | WHSWarehouseZoneGroupEntity                            | msdyn_warehousezonegroup                     | |
| Ubicaciones de almacén ... msdyn_inventorylocations                                    | WMSWarehouseLocationEntity                             | msdyn_inventorylocation                      | Ver [nota 3](#scm-notes). |
| Encabezados de trabajo de almacén ... msdyn_warehouseworkheaders                               | WHSWarehouseWorkHeaderEntity                           | msdyn_warehouseworkheader                    | |
| Líneas de trabajo de almacén ... msdyn_warehouseworklines                                    | WHSWarehouseWorkLineEntity                             | msdyn_warehouseworklines                     | Ver [nota 4](#scm-notes). |
| Modos de entrega ... msdyn_shipvias                                                | DlvDeliveryModeEntity                                  | msdyn_shipvias                               | |
| Condiciones de entrega ... msdyn_termsofdeliveries                                       | DeliveryTermsEntity                                    | msdyn_termsofdelivery                        | |
| Códigos de origen del pedido de ventas ... msdyn_salesorderorigins                                | SalesOrderOriginEntity                                 | msdyn_salesorderorigin                       | |
| Encabezados de pedidos de ventas Common Data Service ... salesorders                             | SalesOrderHeaderCommon Data ServiceEntity              | salesorder                                   | |
| Líneas de pedido de ventas de Common Data Service ... salesorderdetails                         | SalesOrderLineCommon Data ServiceEntity                | salesorderdetails                            | |
| Encabezado de presupuesto de ventas de Common Data Service ... quotes                               | SalesQuotationHeaderCommon Data ServiceEntity          | presupuesto                                        | |
| Líneas de presupuesto de ventas de Common Data Service ... quotedetails                          | SalesQuotationLineCommon Data ServiceEntity            | QuoteDetails                                 | |
| Encabezados de factura de ventas V2 ... invoices                                               | SalesInvoiceHeaderV2Entity                             | facturar                                      | |
| Líneas de factura de ventas V2 ... invoicedetails                                           | SalesInvoiceLineV2Entity                               | invoicedetail                                | |

### <a name="mapping-specific-notes"></a><a id='scm-notes'></a>Notas específicas de asignación

1. Debido a la autodependencia, es posible que deba ejecutar la sincronización inicial dos veces.
2. De manera predeterminada, la sincronización inicial está desactivada debido a la relación principal-secundario (la plataforma no maneja los pedidos "inteligentes"). Por lo tanto, las categorías de productos existentes deben sincronizarse manualmente (por ejemplo, actualizando la descripción de la categoría) en el orden correcto (primero la categoría raíz, luego los hijos y luego los hijos de los hijos). Vaya a **Gestión de información de productos \> Configuración \> Categorías y atributos \> Jerarquías de categorías**. En la página **Jerarquías de categoría**, puede seleccionar cada jerarquía y ver las categorías de productos en ella.
3. La asignación de campos de búsqueda **ItemNumberInLocation** vacíos y la primera, segunda y tercera zonas de almacén adicionales harán que falle la sincronización inicial. Por lo tanto, estas asignaciones se eliminan por ahora.
4. La asignación del campo **CaptureWeight** vacío hará que falle la sincronización inicial. Por lo tanto, esta asignación se elimina por ahora.

### <a name="setup-related-information"></a>Información relacionada con la configuración

+ Cuando los registros se crean por primera vez en la entidad **Productos** en aplicaciones basadas en modelos en Dynamics 365, tienen un estado de **Borrador**. Para cambiar el estado a **Activo**, vaya a **Configuraciones \> Administración \> Ajustes del sistema \> Ventas** en la aplicación basada en modelos y establezca la opción **Crear productos en estado activo** a **Sí**.
+ Si crea registros en la entidad **Productos** en aplicaciones basadas en modelos en Dynamics 365 o en Common Data Service antes de habilitar la escritura dual, esos registros se actualizarán solo si la clave completa, incluyendo **Empresa**, coincide con los datos en la aplicación Finance and Operations.
+ La sincronización de la entidad **Productos** es unidireccional, desde aplicaciones Finance and Operations para Common Data Service. Si un campo asignado en la entidad **Productos** se actualiza la entidad en las aplicaciones basadas en modelos en Dynamics 365, la actualización se sobrescribirá durante la próxima sincronización desde la aplicación Finance and Operations.

### <a name="known-issues"></a>Problemas conocidos

- Se produce un error cuando una unidad se elimina en una aplicación Finance and Operations. Cuando las unidades de medida se sincronizan desde la aplicación Finance and Operations para Common Data Service, la primera unidad de una clase específica se creará como la unidad primaria y evitará la eliminación.

    **Mitigación:** primero borre la unidad en Common Data Service. Luego se puede eliminar en la aplicación Finance and Operations.

- Se produce un error cuando un sitio operacional se elimina en Common Data Service. El mensaje de error dice: "Infolog: Advertencia: la dirección principal no se puede eliminar.; Advertencia: El registro de la entidad no se pudo eliminar porque la validación falló para la siguiente fuente de datos: InventSiteLogisticsLocation (InventSiteLogisticsLocation)". Este error es causado por un problema en la entidad de datos en la aplicación Finance and Operations.

    **Mitigación:** puede eliminar el sitio en la aplicación Finance and Operations. El sitio se eliminará en Common Data Service si se está ejecutando el mapa de doble escritura correspondiente.

## <a name="dynamics-365-finance-entities"></a>Entidades de Dynamics 365 Finance

Las siguientes entidades para Dynamics 365 Finance se listan en el orden en el que debe habilitarlas.

| Nombre de asignación en la página de doble escritura | Nombre de metadatos de la entidad en Finance | Nombre de metadatos de la entidad en Common Data Service | Notas |
|---|---|---|---|
| Divisas ... transactioncurrencies                                            | CurrencyEntity                              | Divisa                                   | |
| Tipo de cambio ... msdyn_exchangeratetypes                                  | ExchangeRateTypeEntity                      | msdyn_exchangeratetype                     | |
| Par de divisas del tipo de cambio ... msdyn_currencyexchangeratepairs                 | ExchangeRateCurrencyPairEntity              | msdyn_currencyexchangeratepair             | |
| Tipos de cambio de Common Data Service ... msdyn_currencyexchangerates              | ExchangeRateCommon Data ServiceEntity       | msdyn_currencyexchangerate                 | Ver [nota 1](#fin-notes). |
| Entidad de integración del calendario fiscal ... msdyn_fiscalcalendars                    | FiscalCalendarEntity                        | msdyn_fiscalcalendar                       | |
| Entidad de integración del año del calendario fiscal ... msdyn_fiscalcalendaryears           | FiscalCalendarYearEntity                    | msdyn_fiscalcalendaryear                   | |
| Período de calendario fiscal ... msdyn_fiscalcalendarperiods                          | FiscalPeriodEntity                          | msdyn_fiscalcalendarperiod                 | |
| Tipo de jerarquía organizativa ... msdyn_internalorganizationhierarchytypes        | OMOrganizationHierarchyTypeEntity           | msdyn_internalorganizationhierarchytype    | Ver [nota 1](#fin-notes). |
| Propósitos de jerarquía organizativa ... msdyn_internalorganizationhierarchypurposes | OMOrganizationHierarchyPurposeEntity        | msdyn_internalorganizationhierarchypurpose | Ver [nota 1](#fin-notes). |
| Entidades jurídicas ... msdyn_internalorganizations                                  | OMLegalEntity                               | msdyn_internalorganization                 | Ver [nota 1](#fin-notes). |
| Entidades jurídicas ... cdm_companies                                                | OMLegalEntity                               | cdm_company                                | |
| Unidad operativa ... msdyn_internalorganizations                                  | OMOperatingUnitEntity                       | msdyn_internalorganization                 | Ver [nota 1](#fin-notes). |
| Jerarquía organizativa: publicada ... msdyn_internalorganizationhierarchies    | OMOrganizationHierarchyPublishedEntity      | msdyn_internalorganizationhierarchy        | Ver [nota 1](#fin-notes). |
| Afijos de nombre ... msdyn_nameaffixes                                              | DirNameAffixEntity                          | msdyn_nameaffix                            | |
| Días de pago Common Data Service ... msdyn_paymentdays                          | PaymentDayCommon Data ServiceEntity         | msdyn_paymentday                           | |
| Líneas de día de pago Common Data Service V2 ... msdyn_paymentdaylines              | PaymentDayLineCommon Data ServiceV2Entity   | msdyn_paymentdayline                       | |
| Multivencimientos ... msdyn_paymentschedules                                     | PaymentScheduleEntity                       | msdyn_paymentschedule                      | |
| Líneas de multivencimientos ... msdyn_paymentschedulelines                           | PaymentScheduleLineEntity                   | msdyn_paymentscheduleline                  | |
| Condiciones de pago ... msdyn_paymentterms                                         | PaymentTermEntity                           | msdyn_paymentterm                          | |
| Método de pago de cliente ... msdyn_customerpaymentmethods                        | CustomerPaymentMethodEntity                 | msdyn_customerpaymentmethod                | |
| Método de pago de proveedor ... msdyn_vendorpaymentmethods                            | VendorPaymentMethodEntity                   | msdyn_vendorpaymentmethod                  | |
| Grupos de clientes ... msdyn_customergroups                                        | CustCustomerGroupEntity                     | msdyn_customergroup                        | |
| Grupos de proveedores ... msdyn_vendorgroups                                            | VendVendorGroupEntity                       | msdyn_vendorgroup                          | |
| Grupos de impuestos de ventas ... msdyn_taxgroups                                            | TaxGroupEntity                              | msdyn_taxgroup                             | |
| Grupos de impuestos ... msdyn_taxitemgroups                                   | TaxItemGroupEntity                          | msdyn_taxitemgroup                         | |
| Grupos de registro contable de impuestos V2 ... msdyn_taxpostinggroups                   | TaxPostingGroupEntityV2                     | msdyn_taxpostinggroup                      | |
| Common Data Service de entidad Código de exención de impuestos ... msdyn_taxexemptcodes       | TaxExemptCodeCommon Data ServiceEntity      | msdyn_taxexemptcode                        | |
| Autoridades fiscales ... msdyn_taxauthorities                                  | TaxAuthorityEntity                          | msdyn_taxauthority                         | |
| Códigos de impuestos ... msdyn_taxcodes                                               | TaxCodeEntity                               | msdyn_taxcode                              | Ver [nota 1](#fin-notes). |
| Formato de dimensión financiera ... msdyn_financialdimensionformats                  | DimensionIntegrationFormatEntity            | msdyn_financialdimensionformat             | |
| Dimensiones financieras ... msdyn_dimensionattributes                              | DimensionAttributeEntity                    | msdyn_dimensionattribute                   | |
| Grupos de retenciones de impuestos ... msdyn_withholdingtaxgroups                           | TaxWithholdingGroupEntity                   | msdyn_withholdingtaxgroup                  | |
| Códigos de retención de impuestos ... msdyn_withholdingtaxcodes                             | TaxWithholdingTaxCodes                      | msdyn_withholdingtaxcode                   | |
| Plan de cuentas ... msdyn_chartofaccountses                                   | LedgerChartOfAccountsEntity                 | msdyn_chartofaccounts                      | |
| Libro mayor ... msdyn_ledgers                                                        | LedgerEntity                                | msdyn_ledger                               | Ver [nota 1](#fin-notes). |
| Categorías de cuenta principales ... msdyn_mainaccountcategories                         | MainAccountCategoryEntity                   | msdyn_mainaccountcategory                  | |
| Cuenta principal ... msdyn_mainaccounts                                             | MainAccountEntity                           | msdyn_mainaccount                          | |
| Clientes V3 ... cuentas                                                       | CustCustomerV3Entity                        | cuenta                                    | Ver [nota 2](#fin-notes). |
| Clientes V3 ... contactos                                                       | CustCustomerV3Entity                        | ponerse en contacto                                    | Ver [nota 3](#fin-notes). |
| Proveedores V2 ... msdyn_vendors                                                    | VendVendorV2Entity                          | msdyn_vendor                               | Ver [nota 2](#fin-notes). |
| Contactos V2 de Common Data Service ... contactos                                    | smmContactPersonCommon Data ServiceV2Entity | ponerse en contacto                                    | Ver [nota 4](#fin-notes). |
| Contactos V2 de Common Data Service ... contactos                                    | smmContactPersonCommon Data ServiceV2Entity | ponerse en contacto                                    | Ver [nota 5](#fin-notes). |

### <a name="mapping-specific-notes"></a><a id='fin-notes'></a>Notas específicas de asignación

1. La sincronización unidireccional se produce desde aplicaciones Finance and Operations para Common Data Service.
2. Debido a la autodependencia, es posible que deba ejecutar la sincronización más de una vez. Asegúrese de seleccionar **Cliente** como el tipo de relación cuando crea una cuenta utilizando la página **Cuentas** en Common Data Service. Si encuentra problemas con el campo **Contacto primario** durante la sincronización inicial, elimine ese campo de la asignación y luego vuelva a ejecutar la sincronización inicial. Después de que la sincronización inicial se complete con éxito, detenga la asignación y agregue el campo **Contacto primario** de nuevo. Luego comience el mapeo, pero omita la sincronización inicial. El valor del campo **Contacto primario** no se incluirá en la sincronización inicial y debe migrar manualmente los valores.
3. Asegúrese de configurar la opción **Vendible** a **Sí** en la página **Contactos** en Common Data Service cuando intenta crear un cliente de tipo **Persona**.
4. Esta asignación tiene un filtro en ambos lados para vincular los contactos del cliente. Abra los detalles de la asignación, seleccione el botón de filtro (símbolo de embudo) al lado del nombre de entidad **Sales.Contact** y asegúrese de que los criterios del archivo contengan **msdyn_contactforvendor eq true y msdyn_sellable eq false**.
5. Esta asignación tiene un filtro en ambos lados para vincular los contactos del proveedor. Abra los detalles de la asignación, seleccione el botón de filtro (símbolo de embudo) al lado del nombre de entidad **Sales.Contact** y asegúrese de que los criterios del filtro contengan **msdyn_contactforvendor eq true y msdyn_sellable eq false**. 

## <a name="dynamics-365-human-resources-entities"></a>Entidades de Dynamics 365 Human Resources

Las siguientes entidades para Dynamics 365 Human Resources se listan en el orden en el que debe habilitarlas.

| Nombre de asignación en la página de doble escritura | Nombre de metadatos de la entidad en Human Resources | Nombre de metadatos de la entidad en Common Data Service | Notas |
|---|---|---|---|
| cdm_jobfunction - Función de trabajo                                |                                   | cdm_jobfunction                  | |
| cdm_jobtypes - Tipos de trabajo                                      |                                   | cdm_jobtypes                     | |
| cdm_jobs - Empleos                                               |                                   | cdm_jobs                         | |
| cdm_jobs - Detalles del trabajo                                        |                                   | cdm_jobs                         | |
| cdm_positiontype - PositionType                               | HcmPositionTypeEntity             | cdm_positiontype                 | |
| cdm_jobpositions - Puesto base                              | HcmPositionBaseEntity             | cdm_jobposition                  | Ver [nota 1](#hr-notes). |
| cdm_jobposition - Detalles del puesto                            | HcmPositionDetailEntity           | cdm_jobposition                  | Ver [nota 1](#hr-notes). |
| cdm_jobposition - Duración del puesto                           | HcmPositionDurationEntity         | cdm_jobposition                  | Ver [nota 1](#hr-notes). |
| cdm_jobposition - Jerarquías del puesto                        | HcmPositionHierarchyEntity        | cdm_jobposition                  | Ver [nota 1](#hr-notes). |
| cdm_veteranstatus - Estado de veterano                            |                                   | cdm_veteranstatus                | |
| cdm_ethnicorigin - Origen étnico                              |                                   | cdm_ethnicorigin                 | |
| cdm_languagecode - Código de idioma                              |                                   | cdm_languagecode                 | |
| cdm_worker - Trabajador                                           | HcmWorkerEntity                   | cdm_worker                       | |
| cdm_employments - Empleos                                 |                                   | cdm_employments                  | |
| cdm_employments - Detalles del empleo                           |                                   | cdm_employments                  | |
| cdm_positionworkerassignmentmaps - Asignación del trabajador del puesto | HcmPositionWorkerAssignmentEntity | cdm_positionworkerassignmentmaps | Ver [nota 2](#hr-notes).|

### <a name="mapping-specific-notes"></a><a id='hr-notes'></a>Notas específicas de asignación

1. Una entidad Common Data Service se asigna a varias entidades de la aplicación Finance and Operations.
2. Esta asignación tiene una referencia propia.

## <a name="asset-management-entities"></a>Entidades de Administración de activos

Las siguientes entidades de Administración de activos para Dynamics 365 Supply Chain Management se listan en el orden en el que debe habilitarlas.

| Nombre de asignación en la página de doble escritura | Nombre de metadatos de la entidad en Administración de activos | Nombre de metadatos de la entidad en Common Data Service | Notas |
|---|---|---|---|
| FO.AssetManagementAssetLifecycleStates--Common Data Service.msdyn_assetlifecyclestates                           | Administración de activos de activos de estados de ciclos de vida               | msdyn_assetlifecyclestates               | |
| FO.AssetManagementAssetLifecycleModels--Common Data Service.msdyn_assetlifecyclemodels                           | Administración de activos de activos de modelos de ciclos de vida               | msdyn_assetlifecyclemodels               | |
| FO.AssetManagementFunctionalLocationLifecycleModels--Common Data Service.msdyn_functionallocationlifecyclemodels | Administración de activos ubicación técnica de modelos de ciclo de vida | msdyn_functionallocationlifecyclemodels  | |
| FO.AssetManagementFunctionalLocationLifecycleStates--Common Data Service.msdyn_functionallocationlifecyclestates | Administración de activos ubicación técnica de estados de ciclo de vida | msdyn_functionallocationlifecyclestates  | |
| FO.AssetManagementAssetTypes--Common Data Service.msdyn_customerassetcategories                                  | Administración de activos de tipos de activos                          | msdyn_customerassetcategories            | |
| FO.AssetManagementFunctionalLocationTypes--Common Data Service.msdyn_functionallocationtypes                     | Administración de activos de tipos de ubicación técnica            | msdyn_functionallocationtypes            | |
| FO.AssetManagementFunctionalLocations--Common Data Service.msdyn_functionallocations                             | Administración de activos de ubicaciones técnicas                 | msdyn_functionallocations                | Ver [la nota](#am-notes). |
| FO.AssetManagementAssets--Common Data Service.msdyn_customerassets                                               | Administración de activos de activos                               | msdyn_customerassets                     | Ver [la nota](#am-notes). |
| FO.AssetManagementManufacturers--Common Data Service.msdyn_manufacturers                                         | Administración de activos de fabricantes                        | msdyn_manufacturers                      | |
| FO.AssetManagementModels--Common Data Service.msdyn_models                                                       | Administración de activos de modelos                               | msdyn_models                             | |
| FO.AssetManagementWarranty--Common Data Service.msdyn_warranties                                                 | Administración de activos de garantía                             | msdyn_warranties                         | |

### <a name="mapping-specific-notes"></a><a id='am-notes'></a>Notas específicas de asignación

- Debido a la autodependencia, es posible que deba ejecutar la sincronización más de una vez.
