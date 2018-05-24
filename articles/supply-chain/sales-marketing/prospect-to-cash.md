---
title: Prospect to cash
description: "Este tema proporciona una visión general de la solución Prospect to cash entre Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f43b3943ce27c44cc0b4756d1d5f23e3be093273
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="prospect-to-cash"></a>Prospect to cash

[!include [banner](../includes/banner.md)]

La solución Prospect to cash proporciona una sincronización directa en Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Sales. Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales. A medida que los datos fluyen entre Finance and Operations y Sales, puede realizar ventas y actividades de marketing en Sales y controlar el cumplimiento de pedidos mediante la gestión de inventario en Finance and Operations. 

Para obtener más información sobre la integración Prospect to cash, observe el breve vídeo de YouTube:

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

[Integración de cliente potencial a cliente (vídeo de YouTube)](https://youtu.be/AVV9x5x-XCg) 

En la versión actual, la solución Prospect to cash proporciona los siguientes tipos de sincronización directa:

- [Mantener cuentas en Sales y sincronizarlas directamente de Sales a Finance and Operations](accounts-template-mapping-direct.md)
- [Mantener productos en Finance and Operations y sincronizarlos directamente con Sales](products-template-mapping-direct.md)
- [Mantener contactos en Sales y sincronizarlos directamente con contactos o clientes de Finance and Operations](contacts-template-mapping-direct.md)
- [Sincronizar presupuesto de ventas directamente de Sales a Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
- [Sincronizar pedidos de ventas entre Sales y Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
- [Sincronizar factura de ventas directamente de Sales a Finance and Operations](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos del sistema para Finance and Operations
La integración de Prospect to cash es compatible en las siguientes versiones:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (dicembre de 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (diciembre de 2017) - Compilación de aplicación 7.3.11971.56116 con actualización 12 de la plataforma (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise Edition (Julio 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (Julio de 2017) - con la actualización de plataforma 8 (compilación de aplicación 7.2.11792.56024 con la compilación de plataforma 7.0.4565.16212).
- Los revisiones siguientes son obligatorias:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Esta revisión le permite sincronizar los pedidos de ventas de Sales a Finance and Operations mediante la característica de integración de datos. También ofrece varias mejoras más.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Esta revisión le permite sincronizar la línea de pedidos de ventas de Finance and Operations a Sales mediante la característica de integración de datos.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Esta revisión le permite sincronizar los pedidos de ventas de Finance and Operations a Sales mediante la característica de integración de datos.

    > [!NOTE]
    > Solo debe instalar KB4045570 porque la instalación incluye los cambios de las otras revisiones. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations vesión 1611 (Noviembre 2016)

- Dynamics 365 for Finance and Operations, versión 1611 (noviembre de 2016) con la actualización de plataforma 8 o versiones posteriores

- Los revisiones siguientes son obligatorias:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Permite la sincronización del pedido de ventas con el integrador de datos, de Finance and Operations a Sales. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Permite la sincronización de encabezados y líneas con el integrador de datos, de Finance and Operations a Sales.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Se necesita soporte para la integración de Prospect to cash mediante entidades de datos.
    
    > [!NOTE]
    > Tras instalar las revisiones, tiene que activar el trabajo por lotes siguiente del formulario **SalesPopulateProspectToCash**. Este formulario está oculto ya que es necesario solo una vez. Para acceder al formulario, inicie sesión en el entorno y agregue lo siguiente a la dirección URL en la dirección de su navegador: *&mi=action:SalesPopulateProspectToCash*, por ejemplo, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Cuado se abra el formulario, haga clic en Aceptar. Esto rellenará un nuevo campo **LineCreationSequnceNumber** en las tablas de **SalesLine**, **SalesQuotationLine** y **CustInvoiceTrans** con valores únicos y actualizará la lista de productos. Esto es necesario para que la integración Proscpect to cash funcione.


## <a name="system-requirements-for-sales"></a>Requisitos del sistema para Sales

Para usar la solución Prospect to cash, debe instalar los componentes siguientes:

- Dynamics 365 for Sales, versión 1612 (8.2.1.207) (DB 8.2.1.207) en línea o una versión posterior
- Solución Prospect to Cash para Dynamics 365 for Sales, versión 1.15.00 o posterior. La solución está disponible para descarga desde AppSource. [Descargue Dynamics 365, Prospect to cash](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).

