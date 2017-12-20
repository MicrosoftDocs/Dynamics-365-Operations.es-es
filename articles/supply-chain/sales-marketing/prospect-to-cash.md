---
title: Prospect to cash
description: "Este tema proporciona una visión general de la solución Prospect to cash entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 11/17/2017
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
ms.sourcegitcommit: 788e64476094e84eb4d438890776306c05b20582
ms.openlocfilehash: 762699cf68ec8a9df5db20d7dd33bc9248f0a36e
ms.contentlocale: es-es
ms.lasthandoff: 12/11/2017

---

# <a name="prospect-to-cash"></a>Prospect to cash

[!include[banner](../includes/banner.md)]

La solución Prospect to cash proporciona una sincronización directa en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y Microsoft Dynamics 365 for Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales. A medida que los datos fluyen entre Finance and Operations y Sales, puede realizar ventas y actividades de marketing en Sales y controlar el cumplimiento de pedidos mediante la gestión de inventario en Finance and Operations.

En la versión actual, la solución Prospect to cash proporciona los siguientes tipos de sincronización directa:

- [Mantener cuentas en Sales y sincronizarlas directamente de Sales a Finance and Operations](accounts-template-mapping-direct.md)
- [Mantener productos en Finance and Operations y sincronizarlos directamente con Sales](products-template-mapping-direct.md)
- [Mantener contactos en Sales y sincronizarlos directamente con contactos o clientes de Finance and Operations](contacts-template-mapping-direct.md)
- [Sincronizar presupuestos de ventas directamente desde Sales a Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
- [Sincronizar pedidos de ventas directamente desde Finance and Operations a Sales](sales-order-template-mapping-direct.md)
- [Sincronizar pedidos de ventas directamente entre Sales y Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
- [Sincronizar facturas de ventas directamente desde Finance and Operations a Sales](sales-invoice-template-mapping-direct.md)

En versiones anteriores, la solución Prospect to cash proporcionaba los siguientes tipos de sincronización no directa:

- [Mantener cuentas en Sales y sincronizarlas con Finance and Operations](accounts-template-mapping.md)
- [Mantener contactos en Sales y sincronizarlos con Finance and Operations](contacts-template-mapping.md)
- [Mantener productos en Finance and Operations y sincronizarlos con Sales](products-template-mapping.md)
- [Crear presupuestos de ventas en Sales y sincronizarlos con Finance and Operations](sales-quotation-template-mapping.md)
- [Crear pedidos de ventas en Finance and Operations y sincronizarlos con Sales](sales-order-template-mapping.md)
- [Crear facturas de ventas en Finance and Operations y sincronizarlas con Sales](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos del sistema para Finance and Operations

Para usar la solución Prospect to cash, debe instalar los componentes siguientes:

### <a name="july-2017"></a>Julio de 2017 

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Julio de 2017) con la actualización de plataforma 8 (compilación de aplicación 7.2.11792.56024 con la compilación de plataforma 7.0.4565.16212)
- Las siguientes revisiones para Finance and Operations:

    - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Esta revisión le permite sincronizar los pedidos de ventas de Sales a Finance and Operations mediante la característica de integración de datos. También ofrece varias mejoras más.
    - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Esta revisión le permite sincronizar la línea de pedidos de ventas de Finance and Operations a Sales mediante la característica de integración de datos.
    - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Esta revisión le permite sincronizar los pedidos de ventas de Finance and Operations a Sales mediante la característica de integración de datos.

    > [!NOTE]
    > Solo debe instalar KB4045570 porque la instalación incluye los cambios de los otros artículos de la Microsoft Knowledge Base (KB).

### <a name="november-2016-version-1611"></a>Noviembre de 2016 (versión 1611)

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (noviembre de 2016) con la actualización de plataforma 8 o versiones posteriores

- Las siguientes revisiones para Finance and Operations:

    - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Permite la sincronización del pedido de ventas con el integrador de los datos, de Microsoft Dynamics 365 for Finance and Operations a Sales 
    - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Permite la sincronización de la línea y el encabezado del pedido de ventas con el integrador de los datos, de Microsoft Dynamics 365 for Finance and Operations a Sales
    - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Se necesita soporte para la integración de Prospect to cash mediante entidades de datos
    
    > [!NOTE]
    > Tras instalar las revisiones tiene que activar el trabajo por lotes siguiente del formulario SalesPopulateProspectToCash. Este formulario está oculto ya que es necesario solo una vez. Para obtener acceso a él, agregue la siguiente dirección de navegador una vez que haya iniciado sesión en el entorno: &mi=action:SalesPopulateProspectToCash E.g. https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash En el formulario que se abre haga clic en Aceptar.
    Esto rellenará un nuevo campo "LineCreationSequnceNumber“ en las tablas de “SalesLine”, “SalesQuotationLine” y “CustInvoiceTrans” con valores únicos y actualizará la lista de productos. Esto es necesario para que la integración de P2C funcione en 7.1


## <a name="system-requirements-for-sales"></a>Requisitos del sistema para Sales

Para usar la solución Prospect to cash, debe instalar los componentes siguientes:

- Microsoft Dynamics 365 for Sales, versión 1612 (8.2.1.207) (DB 8.2.1.207) en línea
- Solución Prospect to cash para Microsoft Dynamics 365 for Sales, versión 1.15.0.0 (v15) 

   > [!NOTE]
   >
   > Las plantillas con las versiones 1.0.0.0 y 1.0.0.1 se admiten en la solución Prospect to cash para Microsoft Dynamics 365 for Sales, versión 1.14.1.0
   >
   > Las plantillas con las versiones 2.0.0.0 y 2.1.0.0 se admiten en la solución Prospect to cash para Microsoft Dynamics 365 for Sales, versión 1.15.0.0

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Instalar la solución Prospect to cash para Sales

1. Descargue el [archivo .zip que contiene el paquete con la solución Prospect to cash para Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) desde CustomerSource.
2. Compruebe que el archivo zip está desbloqueado. Si no, cuando intente instalar el paquete de la solución, aparecerá un mensaje de error indicando que no se encontró ningún paquete de importación. Para desbloquear el archivo zip, haga clic con el botón secundario en el archivo y seleccione **Propiedades**. A continuación seleccione **Desbloquear**.
3. Descomprima el archivo y ejecute **PackageDeployer.exe**.
4. Instale la solución Prospect to cash en su instancia de Sales:

    1. Seleccione **Office 365** como tipo de implementación.
    2. Seleccione **Mostrar opciones avanzadas**.
    3. Para realizar una instalación rápida, seleccione una región. Si selecciona **No lo sé**, el sistema buscará todas las regiones y le llevará más tiempo realizar la instalación.
    4. Escriba el nombre de usuario y la contraseña de un usuario administrador que tenga derechos de instalación.

