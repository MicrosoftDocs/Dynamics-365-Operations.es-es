---
title: Paquete de orquestación de aplicaciones de escritura dual separada
description: El paquete de orquestación de aplicaciones de escritura dual ya no es un paquete único, sino que se ha separado en paquetes más pequeños. Este artículo explica las soluciones y los mapas que contiene cada paquete, y su dependencia de otros paquetes.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: 7f2a9b9e52b80c0feae0ac0dcb1ddf0a5c0cd27c
ms.sourcegitcommit: 8aba7d2f45ef03a14f33f4b430ce92a11c876e2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2022
ms.locfileid: "9884126"
---
# <a name="separated-dual-write-application-orchestration-package"></a>Paquete de orquestación de aplicaciones de escritura dual separada

[!include [banner](../../includes/banner.md)]



Anteriormente, el paquete de orquestación de aplicaciones de escritura dual era un paquete único que contenía las siguientes soluciones:

- Notas de Dynamics 365
- Delimitador común de finanzas y operaciones de Dynamics 365
- Mapas de entidad de escritura dual de finanzas y operaciones de Dynamics 365
- Aplicación Administración de activos de Dynamics 365
- Administración de activos de Dynamics 365
- Común de HCM
- Dynamics 365 Supply Chain extendido
- Dynamics 365 Finance Extended
- Finanzas y operaciones de Dynamics 365 comunes
- Empresa de Dynamics 365
- Tipos de cambio de divisas
- Field Service Common

Debido a que era un paquete único, este paquete creaba una situación de "todo o nada" para los clientes. Sin embargo, Microsoft ahora lo ha separado en paquetes más pequeños. Por lo tanto, los clientes pueden seleccionar solo los paquetes para las soluciones que necesite. Por ejemplo, si es un cliente de Microsoft Dynamics 365 Supply Chain Management y no requiere integración con Dynamics 365 Human Resources, notas y gestión de activos, puede excluir esas soluciones de las soluciones que están instaladas. Debido a que los nombres de la solución subyacente, el editor y las versiones del mapa siguen siendo los mismos, este cambio no es rotundo. Se actualizarán las instalaciones existentes.

![Paquete separado.](media/separated-package-1.png)

Este artículo explica las soluciones y los mapas que contiene cada paquete, y su dependencia de otros paquetes.

## <a name="dual-write-application-core"></a>Núcleo de aplicación de doble escritura

El paquete Núcleo de la aplicación de doble escritura permite a los usuarios instalar y configurar la escritura doble sin ninguna aplicación de interacción con el cliente. Contiene las siguientes cinco soluciones.

| Nombre único                           | Nombre para mostrar                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Empresa de Dynamics 365                       |
| Dynamics365FinanceAndOperationsCommon | Finanzas y operaciones de Dynamics 365 comunes |
| CurrencyExchangeRates                 | Tipos de cambio de divisas                    |
| msdyn_DualWriteAppCoreMaps            | Mapas de entidades centrales de aplicaciones de doble escritura   |
| msdyn_DualWriteAppCoreAnchor          | Anclaje de núcleo de aplicaciones de doble escritura        |

Los siguientes mapas están disponibles en este paquete.

| Aplicaciones de finanzas y operaciones     | Aplicaciones Customer Engagement                    |
|---------------------------------|---------------------------------------------|
| Unidad operativa                  | msdyn_internalorganizations                 |
| Jerarquía organizativa          | msdyn_internalorganizationhierarchies       |
| Entidades jurídicas                  | msdyn_internalorganizations                 |
| Entidades jurídicas                  | cdm_companies                               |
| Propósitos de jerarquía organizativa | msdyn_internalorganizationhierarchypurposes |
| Par de divisas del tipo de cambio     | msdyn_currencyexchangeratepairs             |
| Afijos de nombre                    | msdyn_nameaffixes                           |
| Tipo de cambio              | msdyn_exchangeratetypes                     |
| Tipos de cambio CDS              | msdyn_currencyexchangerates                 |
| Tipo de jerarquía organizativa     | msdyn_internalorganizationhierarchytypes    |
| Divisas                      | transactioncurrencies                       |
| Entidad de guías de realidad mixta     | msmrw_guides                                |

**Información de dependencia**

El paquete Núcleo de la aplicación de doble escritura no depende de otros paquetes.

## <a name="dual-write-human-resources"></a>Human Resources de doble escritura

El paquete de recursos humanos de doble escritura contiene las soluciones y los mapas necesarios para sincronizar los datos de recursos humanos. Contiene las siguientes tres soluciones.

| Nombre único                | Nombre para mostrar                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | Común de HCM                               |
| msdyn_Dynamics365HCMMaps   | Mapas de entidades de Dynamics 365 Human Resources |
| msdyn_Dynamics365HCMAnchor | Anclaje de Dynamics 365 Human Resources      |

Los siguientes mapas están disponibles en este paquete.

| Aplicaciones de finanzas y operaciones | Aplicaciones Customer Engagement         |
|-----------------------------|----------------------------------|
| Orígenes étnicos              | cdm_ethnicorigins                |
| Función de trabajo de compensación   | cdm_jobfunctions                 |
| Puestos V2                | cdm_jobpositions                 |
| Trabajos                        | cdm_jobs                         |
| Tipo de trabajo de compensación       | cdm_jobtypes                     |
| Códigos de idioma              | cdm_languages                    |
| Tipo de puesto               | cdm_positiontypes                |
| Asignaciones del trabajador del puesto | cdm_positionworkerassignmentmaps |
| Estado de excombatiente              | cdm_veteranstatuses              |
| Trabajador                      | cdm_workers                      |
| Empleo por empresa      | cdm_employments                  |

**Información de dependencia**

El paquete de Human Resources de doble escritura depende del paquete de núcleo de aplicación de doble escritura. Por lo tanto, debe instalar el paquete Núcleo de la aplicación de escritura dual antes de instalar el paquete de Recursos humanos de escritura dual.

## <a name="dual-write-supply-chain"></a>Cadena de suministro de doble escritura

El paquete de cadena de suministro de doble escritura contiene las soluciones y los mapas necesarios para sincronizar los datos de Supply Chain Management. Contiene las siguientes tres soluciones.

| Nombre único                                | Nombre para mostrar                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain extendido                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Mapas de entidad extendidos de Dynamics 365 Supply Chain Management |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Anclaje de Dynamics 365 Supply Chain Management extendido      |

Los siguientes mapas están disponibles en este paquete.

| Aplicaciones de finanzas y operaciones                 | Aplicaciones Customer Engagement                      |
|---------------------------------------------|-----------------------------------------------|
| Unidades                                       | uoms                                          |
| Encabezado de pedidos de ventas de CDS                     | salesorders                                   |
| Líneas de pedido de ventas de CDS                       | salesorderdetails                             |
| Encabezado de presupuesto de ventas de CDS                  | presupuestos                                        |
| Líneas de presupuesto de ventas de CDS                   | quotedetails                                  |
| Productos únicos emitidos por CDS              | productos                                      |
| Zonas de almacén                             | msdyn_warehousezones                          |
| Grupos de zonas de almacén                       | msdyn_warehousezonegroups                     |
| Líneas de trabajo de almacén                        | msdyn_warehouseworklines                      |
| Encabezados de trabajo de almacén                      | msdyn_warehouseworkheaders                    |
| Almacenes                                  | msdyn_warehouses                              |
| Pasillo del inventario                             | msdyn_warehouseaisles                         |
| Conversiones de unidades                            | msdyn_unitofmeasureconversions                |
| Condiciones de entrega                           | msdyn_termsofdeliveries                       |
| Modos de entrega                           | msdyn_shipvias                                |
| Estilos de producto maestro                       | msdyn_sharedproductstyles                     |
| Líneas de factura de ventas V2                      | invoicedetails                                |
| Encabezados de factura de ventas V2                    | facturas                                      |
| Tamaños de producto maestro                        | msdyn_sharedproductsizes                      |
| Productos liberados V2                        | msdyn_sharedproductdetails                    |
| Configuraciones de producto maestro               | msdyn_sharedproductconfigurations             |
| Colores de producto maestro                       | msdyn_sharedproductcolors                     |
| Códigos de origen de pedido de ventas                    | msdyn_salesorderorigins                       |
| Encabezado de recepción de producto                      | msdyn_purchaseorderreceipts                   |
| Línea de recepción de producto                        | msdyn_purchaseorderreceiptproducts            |
| Encabezados de pedido de compra V2                   | msdyn_purchaseorders                          |
| Entidad de línea de pedido de compra de CDS eliminada provisionalmente | msdyn_purchaseorderproducts                   |
| Entidad de línea de pedido de compras de CDS              | msdyn_purchaseorderproducts                   |
| Grupos de dimensiones de seguimiento                   | msdyn_producttrackingdimensiongroups          |
| Estilos                                      | msdyn_productstyles                           |
| Grupos de dimensiones de almacenamiento                    | msdyn_productstoragedimensiongroups           |
| Conversiones de unidades específicas del producto           | msdyn_productspecificunitofmeasureconversions |
| Configuración de pedido predeterminada del producto V2           | msdyn_productspecificdefaultordersettings     |
| Tamaños                                       | msdyn_productsizes                            |
| Grupos de dimensiones de producto                    | msdyn_productdimensiongroups                  |
| Configuración predeterminada de pedido                      | msdyn_productdefaultordersettings             |
| Configuraciones                              | msdyn_productconfigurations                   |
| Todos los productos                                | msdyn_globalproducts                          |
| Colores                                      | msdyn_productcolors                           |
| Roles de jerarquía de categorías de producto            | msdyn_productcategoryhierarchyroles           |
| Jerarquías de categorías de producto                | msdyn_productcategoryhierarchies              |
| Asignaciones de categorías de producto                | msdyn_productcategoryassignments              |
| Categorías de productos                          | msdyn_productcategories                       |
| Ubicaciones de almacén                         | msdyn_inventorylocations                      |
| Inventario CDS en                            | msdyn_inventoryonhandentries                  |
| Categorías de productos                          | msdyn_productcategories                       |
| Inventario CDS en                            | msdyn_inventoryonhandrequests                 |
| Código de barras identificado por número de producto           | msdyn_productbarcodes                         |
| Tarjeta de fidelización                                | msdyn_loyaltycards                            |
| Puntos de recompensa de fidelización                       | msdyn_loyaltyrewardpoints                     |
| Grupos de clientes de precios                       | msdyn_pricecustomergroups                     |
| Sitios                                       | msdyn_operationalsites                        |
| Líneas de presupuesto de ventas de CDS                   | quotedetails                                  |
| Líneas de pedido de ventas de CDS                       | salesorderdetails                             |

**Información de dependencia**

El paquete Cadena de suministro de escritura dual depende de los siguientes tres paquetes. Por lo tanto, debe instalar estos paquetes antes de instalar el paquete Cadena de suministro de escritura dual.

- Paquete de núcleo de aplicación de doble escritura
- Paquete de Finance de doble escritura
- Paquete de Human Resources de doble escritura
- Tablas comunes de Dynamics 365 HR

## <a name="dual-write-finance"></a>Finance de doble escritura

El paquete de Finance de doble escritura contiene las soluciones y los mapas necesarios para sincronizar los datos de Dynamics 365 Finance. Contiene las siguientes cuatro soluciones.

| Nombre único                            | Nombre para mostrar                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Mapas de entidades de Dynamics 365 Finance Extended |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Delimitador de Dynamics 365 Finance Extended      |

Los siguientes mapas están disponibles en este paquete.

| Aplicaciones de finanzas y operaciones             | Aplicaciones Customer Engagement        |
|-----------------------------------------|---------------------------------|
| Grupos de retenciones de impuestos                  | msdyn_withholdingtaxgroups      |
| Contactos de CDS V2 (Cliente)              | contactos                        |
| Contactos de CDS V2 (Proveedor)                | contactos                        |
| Clientes V3                            | contactos                        |
| Códigos de retenciones de impuestos                   | msdyn_withholdingtaxcodes       |
| Proveedores V2                              | msdyn_vendors                   |
| Método de pago de proveedor                   | msdyn_vendorpaymentmethods      |
| Grupos de proveedores                           | msdyn_vendorgroups              |
| Plan de cuentas                       | msdyn_chartofaccountses         |
| Grupos de registro contable de impuestos de ventas V2      | msdyn_taxpostinggroups          |
| Grupo de impuestos de artículos                    | msdyn_taxitemgroups             |
| Grupos de impuestos                        | msdyn_taxgroups                 |
| Entidad de código de exención de impuestos para CDS        | msdyn_taxexemptcodes            |
| Grupos de clientes                         | msdyn_customergroups            |
| Método de pago de cliente                 | msdyn_customerpaymentmethods    |
| Dimensiones financieras                    | msdyn_dimensionattributes       |
| Autoridades fiscales                   | msdyn_taxauthorities            |
| Formato de dimensión financiera              | msdyn_financialdimensionformats |
| Período de calendario fiscal                  | msdyn_fiscalcalendarperiods     |
| Entidad de integración de calendario fiscal      | msdyn_fiscalcalendars           |
| Entidad de integración de año de calendario fiscal | msdyn_fiscalcalendaryears       |
| Condiciones de pago                        | msdyn_paymentterms              |
| Multivencimientos                        | msdyn_paymentschedules          |
| Líneas de multivencimientos                  | msdyn_paymentschedulelines      |
| Días de pago de CDS                        | msdyn_paymentdays               |
| Líneas de días de pago de CDS V2                | msdyn_paymentdaylines           |
| Cuenta principal                            | msdyn_mainaccounts              |
| Categorías de cuenta principal                 | msdyn_mainaccountcategories     |
| Contabilidad                                  | msdyn_ledgers                   |
| Clientes V3                            | cuentas                        |

**Información de dependencia**

El paquete de Finance de doble escritura depende del paquete de núcleo de aplicación de doble escritura. Por lo tanto, debe instalar el paquete Núcleo de la aplicación de escritura dual antes de instalar el paquete de Finance de escritura dual.

## <a name="dual-write-notes"></a>Notas de la doble escritura

El paquete de Notas de doble escritura contiene las soluciones y los mapas necesarios para sincronizar los datos de notas o anotaciones. Contiene las siguientes cuatro soluciones.

| Nombre único                  | Nombre para mostrar                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Notas de Dynamics 365             |
| Dynamics365NotesExtended     | Notas de Dynamics 365 extendido    |
| msdyn_Dynamics365NotesMaps   | Mapas de entidades de notas de Dynamics 365 |
| msdyn_Dynamics365NotesAnchor | Anclaje de notas de Dynamics 365      |

Los siguientes mapas están disponibles en este paquete.

| Finanzas y operaciones                     | Customer Engagement |
|--------------------------------------------|---------------------|
| Datos adjuntos de documento de encabezado de pedido de ventas    | anotaciones         |
| Archivos adjuntos de clientes                       | anotaciones         |
| Documentos adjuntos de proveedor                | anotaciones         |
| Datos adjuntos de documento de encabezado de pedido de compra | anotaciones         |

**Información de dependencia**

El paquete Notas de escritura dual depende de los siguientes dos paquetes. Por lo tanto, debe instalar estos paquetes antes de instalar el paquete Cadena de suministro de Notas de doble escritura.

- Paquete de núcleo de aplicación de doble escritura
- Paquete de Finance de doble escritura

## <a name="dual-write-asset-management"></a>Administración de activos de doble escritura

El paquete de Administración de activos de doble escritura contiene las soluciones y los mapas necesarios para sincronizar los datos de Supply Chain Management o Dynamics 365 Field Service. Contiene las siguientes cuatro soluciones.

| Nombre único                          | Nombre para mostrar                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Administración de activos de Dynamics 365             |
| Dynamics365AssetManagementApp        | Aplicación Administración de activos de Dynamics365          |
| msdyn_DualWriteAssetManagementMaps   | Mapas de entidades de Administración de activos de Dynamics 365 |
| msdyn_DualWriteAssetManagementAnchor | Anclaje de Administración de activos de Dynamics 365      |

Los siguientes mapas están disponibles en este paquete.

| Aplicaciones de finanzas y operaciones                           | Aplicaciones Customer Engagement                |
|-------------------------------------------------------|-----------------------------------------|
| Administración de activos de garantía                             | msdyn_warranties                        |
| Administración de activos de modelos                               | msdyn_models                            |
| Administración de activos de fabricantes                        | msdyn_manufacturers                     |
| Administración de activos de tipos de ubicación técnica            | msdyn_functionallocationtypes           |
| Administración de activos de ubicaciones técnicas                 | msdyn_functionallocations               |
| Administración de activos ubicación técnica de estados de ciclo de vida | msdyn_functionallocationlifecyclestates |
| Administración de activos ubicación técnica de modelos de ciclo de vida | msdyn_functionallocationlifecyclemodels |
| Administración de activos de activos                               | msdyn_customerassets                    |
| Administración de activos de tipos de activos                          | msdyn_customerassetcategories           |
| Administración de activos de activos de estados de ciclos de vida               | msdyn_assetlifecyclestates              |
| Administración de activos de activos de modelos de ciclos de vida               | msdyn_assetlifecyclemodels              |

**Información de dependencia**

El paquete de Administración de activos de doble escritura depende del paquete de núcleo de aplicación de doble escritura. Por lo tanto, debe instalar el paquete Núcleo de la aplicación de escritura dual antes de instalar el paquete de Administración de activos de escritura dual.

## <a name="packages-required-for-project-operations"></a>Paquetes necesarios para Project Operations
Project Operations depende de los siguientes paquetes. Por lo tanto, debe instalar estos paquetes antes de instalar Project Operations.

- Paquete de núcleo de aplicación de doble escritura
- Paquete de Finance de doble escritura
- Paquete de cadena de suministro de doble escritura
- Paquete de Administración de activos de doble escritura
- Paquete de Human Resources de doble escritura

## <a name="dual-write-party-and-global-address-book-solutions"></a>Soluciones de libreta de direcciones global y de parte de escritura dual

El paquete de libreta de direcciones global y de grupo de escritura dual contiene las siguientes soluciones y mapas necesarios para sincronizar los datos de la libreta de direcciones global y de grupo. 

| Nombre único                       | Nombre para mostrar                            |
|-----------------------------------|-----------------------------------------|
| Parte                             | Parte                                   |
| Dynamics365GABExtended            | Dynamics 365 GAB ampliado               |
| Dynamics365GABDualWriteEntityMaps | Mapas de entidad de escritura dual de Dynamics 365 GAB |
| Dynamics365GABParty_Anchor        | Dynamics 365 GAB y parte              |

Los siguientes mapas están disponibles en este paquete.

| Aplicaciones de finanzas y operaciones | Aplicaciones Customer Engagement | 
|-----------------------------|--------------------------|
| Partes de CDS | msdyn_parties | 
| Ubicaciones de dirección postal de CDS | msdyn_postaladdresscollections | 
| Historial de dirección postal de CDS V2 | msdyn_postaladdresses | 
| Ubicaciones de dirección postal de entidad CDS | msdyn_partypostaladdresses | 
| Contactos de parte V3 | msdyn_partyelectronicaddresses | 
| Clientes V3 | cuentas | 
| Clientes V3 | contactos | 
| Proveedores V2 | msdyn_vendors | 
| Cargos de persona de contacto | msdyn_salescontactpersontitles | 
| Despedidas de agradecimiento | msdyn_complimentaryclosings | 
| Formas de saludo | msdyn_salutations | 
| Roles de toma de decisiones | msdyn_decisionmakingroles | 
| Funciones de trabajo de empleo | msdyn_employmentjobfunctions | 
| Niveles de fidelización | msdyn_loyaltylevels | 
| Tipos de carácter personal | msdyn_personalcharactertypes | 
| Contactos V2 | msdyn_contactforparties | 
| Encabezado de presupuesto de ventas de CDS | presupuestos | 
| Encabezado de pedidos de ventas de CDS | salesorders | 
| Encabezados de factura de ventas V2 | facturas | 
| Roles de dirección CDS | msdyn_addressroles |

**Información de dependencia**

Las soluciones de libreta de direcciones global y de parte de escritura dual dependen de los siguientes tres paquetes. Por lo tanto, debe instalar estos paquetes antes de instalar el paquete de soluciones de libreta de direcciones global y de parte de doble escritura.

- Paquete de núcleo de aplicación de doble escritura
- Paquete de Finance de doble escritura
- Paquete de cadena de suministro de doble escritura

