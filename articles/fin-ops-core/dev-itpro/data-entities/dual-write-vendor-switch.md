---
title: Cambiar entre los diseños de proveedor
description: ''
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
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
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 4e97ff0b0e6195b5e3703e15a0bb0de7644ef8d1
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772373"
---
# <a name="switch-between-vendor-designs"></a>Cambiar entre los diseños de proveedor

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a>Flujo de datos del proveedor 

Si usa otras aplicaciones de Dynamics 365 para el control de proveedores y desea aislar la información de proveedor de los clientes, use este diseño de proveedor básico.  

![Flujo básico del proveedor](media/dual-write-switch-1.png)
 
Si usa otras aplicaciones Dynamics 365 para el control de proveedores y desea seguir usando la entidad **Cuenta** para almacenar la información de proveedor, use este diseño de proveedor ampliado. En este diseño, la información de proveedor extendida, como el estado en espera del proveedor y el perfil de proveedor, se almacena en la entidad **proveedores** en Common Data Service. 

![Flujo ampliado del proveedor](media/dual-write-switch-2.png)
 
Siga los pasos siguientes para usar el diseño de proveedor extendido: 
 
1. El paquete de solución **SupplyChainCommon** contiene las plantillas el proceso de flujo de trabajo tal y como se muestra en la imagen siguiente.
    > [!div class="mx-imgBorder"]
    > ![Plantillas de proceso de flujo de trabajo](media/dual-write-switch-3.png)
2. Cree nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo: 
    1. Cree un nuevo proceso de flujo de trabajo para la entidad **Proveedor** mediante la plantilla del proceso de flujo de trabajo **Crear proveedores en la entidad cuenta** y haga clic en **Aceptar**. Este flujo de trabajo gestiona el escenario de creación de proveedor para la entidad **Cuenta**.
        > [!div class="mx-imgBorder"]
        > ![Crear proveedores en la entidad cuenta](media/dual-write-switch-4.png)
    2. Cree un nuevo proceso de flujo de trabajo para la entidad **Proveedor** mediante la plantilla del proceso de flujo de trabajo **Actualizar entidad Cuentas** y haga clic en **Aceptar**. Este flujo de trabajo gestiona el escenario de actualización de proveedor para la entidad **Cuenta**. 
        > [!div class="mx-imgBorder"]
        > ![Actualizar la entidad Cuentas](media/dual-write-switch-5.png)
    3. Cree nuevos procesos de flujo de trabajo a partir de las plantillas creadas en la entidad **Cuentas**. 
        > [!div class="mx-imgBorder"]
        > ![Crear proveedores en la entidad proveedores](media/dual-write-switch-6.png)
        > [!div class="mx-imgBorder"]
        > ![Actualizar la entidad de proveedores](media/dual-write-switch-7.png)
    4. Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o de fondo en función de sus requisitos. 
        > [!div class="mx-imgBorder"]
        > ![Convertir a un flujo de trabajo de fondo](media/dual-write-switch-8.png)
    5. Active los flujos de trabajo que ha creado en las entidades **Cuenta** y **Proveedor** para comenzar a utilizar la entidad **Cuenta** de Customer Engagement para almacenar información del proveedor. 
 
