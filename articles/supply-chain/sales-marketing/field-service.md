---
title: "Iintegración con Microsoft Dynamics 365 for Field Service"
description: "Este tema proporciona una visión general de la integración con Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a57e23691a6b4d48c6b8dd6d1f61fc9730365b39
ms.openlocfilehash: 0c1268d2fddcf7b28ecfc3197f21e9d30a5a5855
ms.contentlocale: es-es
ms.lasthandoff: 05/31/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Iintegración con Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations habilita la sincronización de los procesos empresariales entre Finance and Operations y Microsoft Dynamics 365 for Field Service. Los escenarios de integración se configuran utilizando las plantillas extensibles integradoras del Common Data Service (CDS) para habilitar la sincronización de procesos empresariales.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

La primera fase de la integración entre Field Service y Finance and Operations se enfoca en habilitar pedidos y acuerdos de trabajo en Field Service para facturar en Finance and Operations. El flujo admitido comienza en Field Service, donde la información de pedidos de trabajo se sincroniza con Finance and Operations como pedidos de ventas. En Finance and Operations, se facturan los pedidos de ventas para generar documentos de factura. Además, la información de las facturas de acuerdos de Field Service se sincroniza con Finance and Operations. El integrador de los datos de Microsoft Dynamics 365 sincroniza datos mediante proyectos personalizables. Las plantillas estándar se pueden usar para crear proyectos personalizados de integración donde la norma adicional estándar y los campos personalizados, y también las entidades, se pueden asignar para ajustar la integración y para cumplir con los requisitos específicos.

La primera fase de la integración entre Field Service y Finance and Operations permite la sincronización de los elementos siguientes:

- [Productos de Finance and Operations con productos de Field Service que incluyen información del tipo de producto](field-service-product.md)
- [Pedidos de trabajo en Field Service con pedidos de ventas en Finance and Operations](field-service-work-order.md)
- [Facturas en Field Service con facturas de texto libre en Finance and Operations](field-service-invoice.md)

Para ver un ejemplo de cómo puede sincronizar un pedido de trabajo entre Field Service y Finance and Operations, observe el breve vídeo de YouTube [Sincronizar un pedido de trabajo entre Dynamics 365 for Field Service and Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos del sistema para Finance and Operations
La integración Field Service admite las siguientes versiones:

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a>Dynamics 365 for Finance and Operations vesión 8.0 (abril 2018) o posterior

- Dynamics 365 for Finance and Operations versión 8.0 (abril de 2018) fue emitido en abril de 2018 y tiene un número de compilacion de la aplicación 8.0.30.8020 con la plataforma actualiza 15 (7.0.4841.35234). 

## <a name="system-requirements-for-field-service"></a>Requisitos del sistema para Field Service
Para usar la solución de integración de Field Service, debe instalar los componentes siguientes:

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a>Microsoft Dynamics 365 for Field Service 9.0 o posterior

- Dynamics 365 for Field Service versión 1612 (9.0.1.733) (DB 9.0.1.733) en línea o una versión posterior.
- Solución Prospect to Cash (P2C) para Dynamics 365, versión 1.15.0.1 o versión posterior. La solución está disponible para descarga desde [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Solución de integración de Field Service para Dynamics 365, versión 1.0.0.0 o una versión posterior. La solución está disponible para descarga desde [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).

