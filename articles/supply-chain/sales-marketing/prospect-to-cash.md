---
title: Prospect to cash
description: "Este tema proporciona una visión general de la solución Prospect to cash entre Dynamics 365 for Sales y Dynamics 365 for Finance and Operations, Enterprise Edition y Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 2accf77c5241adff7ad1648737dde451153fde46
ms.contentlocale: es-es
ms.lasthandoff: 11/14/2017

---

# <a name="prospect-to-cash"></a>Prospect to cash  

[!include[banner](../includes/banner.md)]

La solución Prospect to cash usa una opción de [integración de datos](/common-data-service/entity-reference/dynamics-365-integration) para sincronizar los datos a través de instancias de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y Dynamics 365 for Sales a través de Common Data Service (CDS). Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y datos de facturación de ventas entre Finance and Operations y Sales. A medida que los datos fluyen entre Finance and Operations y Sales, puede realizar ventas y actividades de marketing en Sales y gestionar el cumplimiento de pedidos con la gestión de inventario en Finance and Operations. 

Esta solución proporciona integración en las siguientes áreas: 

-   [Mantener cuentas en Sales y sincronizarlas con Finance and Operations](accounts-template-mapping.md)
-   [Mantener contactos en Sales y sincronizarlos con Finance and Operations](contacts-template-mapping.md)
-   [Mantener productos en Finance and Operations y sincronizarlos con Sales](products-template-mapping.md)
-   [Crear presupuestos de ventas en Sales y sincronizarlos con Finance and Operations](sales-quotation-template-mapping.md)
-   [Crear pedidos de ventas en Finance and Operations y sincronizarlos con Sales](sales-order-template-mapping.md)
-   [Crear facturas de ventas en Finance and Operations y sincronizarlas con Sales](sales-invoice-template-mapping.md)

Esta solución proporciona sincronización directa en las siguientes áreas:

-   [Mantener cuentas en Sales y sincronizarlas directamente de Sales a Finance and Operations](accounts-template-mapping-direct.md)
-   [Mantener productos en Finance and Operations y sincronizarlos directamente con Sales](products-template-mapping-direct.md)
-   [Mantener contactos en Sales y sincronizarlos directamente con contactos o clientes de Finance and Operations](contacts-template-mapping-direct.md)
-   [Sincronizar directamente encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
-   [Crear pedidos de ventas en Finance and Operations y sincronizarlos directamente con Sales](sales-order-template-mapping-direct.md)
-  [Sincronizar encabezados y líneas de pedido de ventas directamente entre Sales y Finance and Operations](sales-order-template-mapping-between-sales-fin.md)
-   [Sincronizar pedidos de ventas directamente entre Sales y Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
-   [Crear facturas de ventas en Finance and Operations y sincronizarlos directamente con Sales](sales-invoice-template-mapping-direct.md)


## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Requisitos del sistema para Dynamics 365 for Finance and Operations, Enterprise Edition

Para usar la solución Prospect to cash, debe instalar lo siguiente:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Julio de 2017) con la actualización de plataforma 8 (aplicación 7.2.11792.56024 con la plataforma 7.0.4565.16212)

- Revisiones de Dynamics 365 for Finance and Operations, Enterprise Edition, (julio de 2017).
        
    -  [KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - Esta revisión habilita soporte para la sincronización de pedidos de ventas con la característica de integración de datos de Sales a Finance and Operations, junto con otras mejoras.

    -  [KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2): esta revisión le permite sincronizar la línea de pedidos de ventas con la característica de integración de datos, de Finance and Operations a Sales.
        
    -  [KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2): esta revisión le permite sincronizar los pedidos de ventas con la característica de integración de datos, de Finance and Operations a Sales.

**Nota**: solo debe instalar KB4045570 porque la instalación incluye los cambios de las otras KB.
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a>Requisitos del sistema para Dynamics 365 for Sales

Para usar la solución Prospect to cash, debe instalar lo siguiente:

- Dynamics 365 for Sales, versión 1612 (8.2.1.207) (DB 8.2.1.207) en línea.
- Solución Prospect to cash para Dynamics 365 for Sales, versión 1.14.0.0 (v14) o posterior.

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Instalar la solución Prospect to cash para Sales

- Descargue el [archivo .zip que contiene el paquete con la solución Prospect to cash para Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) en CustomerSource.

- Asegúrese de que el archivo .zip esté desbloqueado para que así no vea el mensaje de error "No se encontró ningún paquete de importación" al instalar el paquete de la solución. Para desbloquear el archivo, haga lo siguiente:

    -  Haga clic con el botón derecho en el archivo .zip.
    -  Seleccione **Propiedades** y **Desbloquear**. 

- Descomprima el archivo y ejecute PackageDeployer.exe.

- Instale la solución Prospect to cash en su instancia de Sales.

    - Seleccione el tipo de implementación **Office 365**.
    - Seleccione **Mostrar opciones avanzadas**.
    - Para realizar una instalación rápida, seleccione **Región**. Si selecciona **No lo se**, el sistema busca todas las regiones y le llevará más tiempo realizar la instalación.
    - Escriba el **nombre de usuario** y la **contraseña** de un usuario administrador que tenga los derechos de usuario necesarios para realizar la instalación.

