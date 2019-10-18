---
title: Visión general de la integración con Microsoft Dynamics 365 Field Service
description: Este tema proporciona una visión general de la integración con Microsoft Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 2a5c3e49f09bf4f1f90449db10d439f563ecc2c0
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249851"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>Visión general de la integración con Microsoft Dynamics 365 Field Service

[!include[banner](../includes/banner.md)]

Supply Chain Management permite la sincronización de procesos empresariales entre Dynamics 365 Supply Chain Management y Dynamics 365 Field Service. Los escenarios de integración se configuran utilizando las plantillas extensibles integradoras y Common Data Service para habilitar la sincronización de procesos empresariales.
Las plantillas estándar se pueden usar para crear proyectos personalizados de integración donde la norma adicional estándar, los campos personalizados, y las entidades, se pueden asignar para ajustar la integración y para cumplir con las necesidades empresariales. 

La integración de Field Service se efectúa sobre la funcionalidad existente de cliente potencial a cliente.

![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/field-service-integration.png)

La primera fase de la integración entre Field Service y Supply Chain Management se enfoca en habilitar pedidos y acuerdos de trabajo en Field Service para facturarlos en Supply Chain Management. El flujo admitido comienza en Field Service, donde la información de pedidos de trabajo se sincroniza con Supply Chain Management como pedidos de ventas. En Supply Chain Management, se facturan los pedidos de ventas para generar documentos de factura. Además, la información de las facturas de acuerdos de Field Service se sincroniza con Supply Chain Management. El integrador de los datos de Microsoft Dynamics 365 sincroniza datos mediante proyectos personalizables. Las plantillas estándar se pueden usar para crear proyectos personalizados de integración donde la norma adicional estándar y los campos personalizados, y también las entidades, se pueden asignar para ajustar la integración y para cumplir con los requisitos específicos.

La primera fase de la integración entre Field Service y Supply Chain Management permite la sincronización de los elementos siguientes:

- [Productos de Supply Chain Management con productos de Field Service que incluyen información del tipo de producto](field-service-product.md)
- [Pedidos de trabajo en Field Service con pedidos de ventas en Supply Chain Management](field-service-work-order.md)
- [Facturas en Field Service con facturas de texto libre en Supply Chain Management](field-service-invoice.md)

Para ver un ejemplo de cómo puede sincronizar un pedido de trabajo entre Field Service y Supply Chain Management, mire el breve vídeo de YouTube [Cómo sincronizar un pedido de trabajo con Microsoft Dynamics 365 Integration](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>Integración con Field Service, con información de inventario y de proyecto

La función adicional de esta segunda fase enfocada en dar a los técnicos de campo información clara acerca de la información de inventario de Supply Chain Management y que les permite actualizar niveles de inventario y realizar transferencias materiales. Además, las empresas que instalan o mantienen mercancías vendidas se beneficiarán de un mejor control y visibilidad sobre las ventas y el proceso de servicio completos con la integración desde proyectos.

### <a name="functionality-includes-integration-of"></a>La funcionalidad incluye la integración de:
- Información de almacén
- Información de inventario disponible
- Transferencias de inventario
- Ajustes de inventario
- Proyectos de Supply Chain Management conectados a pedidos de trabajo de Dynamics 365 Field Service
- Los pedidos de trabajo de Dynamics 365 Field Service vinculados a los proyectos Supply Chain Management, aplican este número de proyecto al pedido de ventas para permitir facturar desde el proyecto. 

![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>La segunda fase de la integración entre Field Service y Supply Chain Management permite la sincronización con las plantillas siguientes:
- Almacenes (Supply Chain Management a Field Service) - almacenes desde Supply Chain Management a Field Service [consulta avanzada] 
- Inventario de producto (Supply Chain Management a Field Service) - Información de nivel de inventario desde Supply Chain Management a Field Service [consulta avanzada] 
- Ajuste de inventario (de Field Service a Supply Chain Management) - Ajustes de inventario desde Field Service a Supply Chain Management [consulta avanzada] 
- Transferencias de inventario (de Field Service a Supply Chain Management) - Transferencias de inventario desde Field Service a Supply Chain Management [consulta avanzada] 
- Projectos (Supply Chain Management a Field Service) - Lista de proyectos desde Supply Chain Management a Field Service 
- Pedidos de trabajo con proyecto (Field Service a Supply Chain Management) - pedidos de trabajo en Field Service a pedidos de ventas en Supply Chain Management, con el soporte para el proyecto [consulta avanzada] 
- Productos de Field Service a la unidad de inventario (Supply Chain Management a Sales) - "productos liberados para ventas" de Supply Chain Management a "Productos" de ventas para Field Service, incluida la unidad de inventario 

## <a name="system-requirements"></a>Requisitos del sistema

### <a name="system-requirements-for-supply-chain-management"></a>Requisitos del sistema para Supply Chain Management
La integración Field Service admite las siguientes versiones:

- Dynamics 365 for Finance and Operations versión 8.1.2 (diciembre de 2018) se liberó en diciembre de 2018 y tiene un número de versión de aplicación 8.1.195 con la actualización de plataforma 22 (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Requisitos del sistema para Field Service
Para usar la solución de integración de Field Service, debe instalar los componentes siguientes:

- Field Service (versión 8.2.0.286) o una versión posterior de Dynamics 365 9.1.x - Publicada en noviembre de 2018
- Solución Prospect to Cash (P2C) para Dynamics 365, versión 1.15.0.1 o versión posterior. La solución está disponible para su descarga en [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Integración de Field Service, solución de proyectos e inventario para Dynamics 365, versión 2.0.0.0 o una versión posterior. La solución está disponible para su descarga en [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).
