---
title: Integrar Dynamics 365 Supply Chain Management (Administración de activos) con Dynamics 365 Guides
description: Este tema explica cómo integrar el módulo Administración de activos en Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides para aprovechar las guías de realidad mixta en sus flujos de trabajo diarios de servicio y mantenimiento.
author: kamaybac
manager: tfehr
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: ae26012d236a44bfa0c8453bdc660671ddee82a4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000293"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>Integrar Dynamics 365 Supply Chain Management (Administración de activos) con Dynamics 365 Guides

Puede integrar el módulo **Administración de activos** en Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides para aprovechar las guías de realidad mixta en sus flujos de trabajo diarios de servicio y mantenimiento. Si una guía está asociada con una orden de trabajo de Administración de activos, un trabajador que abra la lista de comprobación de mantenimiento de órdenes de trabajo en la aplicación móvil Supply Chain Management (Dynamics 365) verá que hay una guía disponible. El trabajador puede encontrar y abrir la guía en la aplicación Dynamics 365 Guides HoloLens.

## <a name="prerequisites"></a>Requisitos previos

Antes de poder adjuntar guías a las órdenes de trabajo de gestión de activos, debe completar estos requisitos previos:

- [Configurar Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md), versión 10.0.9 o posterior.
- [Activar la escritura dual para las aplicaciones de Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- [Activar transacción](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) para la función **MRGuidesFeature**. (Para entornos de producción, primero debe enviar un ticket de soporte para que su inquilino se agregue al grupo de transacciones).
- [Activar las siguientes teclas de configuración](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) en la página **Configuración de la licencia**:

    - Gestión de activos \> Gestión de activos de realidad mixta
    - Realidad mixta \> Guía de realidad mixta

- [Configurar Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution), versión 200.0.0.96 o posterior.

## <a name="use-dynamics-365-guides-with-asset-management"></a>Usar Dynamics 365 Guides con Administración de activos

Para asociar una guía, utiliza una línea de lista de comprobación de mantenimiento en Administración de activos. Puede crear la asociación a través de una plantilla de lista de comprobación de mantenimiento, un tipo de trabajo de mantenimiento o una orden de trabajo, porque las tres contienen líneas de lista de comprobación de mantenimiento. Puede ahorrar tiempo utilizando una plantilla, ya que una plantilla se puede asociar con todos los tipos de trabajos de mantenimiento que la utilizan. Por ejemplo, una guía asociada con un tipo de trabajo de mantenimiento se asocia automáticamente con todas las órdenes de trabajo que especifican ese tipo de trabajo. Por otro lado, una guía que está asociada directamente con una orden de trabajo existe solo para esa orden de trabajo.

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>Asociar una guía con una plantilla de lista de verificación de mantenimiento

Para asociar una guía con una plantilla de lista de verificación de mantenimiento, siga estos pasos.

1. Cree una guía utilizando las aplicaciones Dynamics 365 Guides PC y HoloLens. Los temas siguientes contienen información sobre cómo crear una guía:

    - [Usar la aplicación para PC para crear una guía](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [Utilizar la aplicación HoloLens para colocar los hologramas](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. En Supply Chain Management, [creae una plantilla de lista de verificación de mantenimiento](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).
1. Asocie la guía que creó con una línea de lista de verificación de mantenimiento en la nueva plantilla de lista de verificación de mantenimiento:

    1. En la ficha desplegable **Líneas de control de mantenimiento**, seleccione la línea con la que desea asociar la guía.
    1. En la ficha desplegable **Guías asociadas**, seleccione **Agregar guía**.

        ![Asociar una guía con una línea de lista de verificación de mantenimiento](media/am-guides-integration-add-guide.png "Asociar una guía con una línea de lista de verificación de mantenimiento")

    1. En el campo **Nombre**, seleccione una guía y luego seleccione **Guardar**.

        ![Seleccione una guía en el campo Nombre](media/am-guides-integration-select-guide.png "Seleccione una guía en el campo Nombre")

1. Asocie la plantilla de lista de verificación de mantenimiento con un tipo de trabajo:

    1. [Cree un tipo de trabajo de mantenimiento](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) o seleccione un tipo de trabajo de mantenimiento existente.
    1. En el Panel Acciones, seleccione **Tipos de trabajo de mantenimiento predeterminados**.

        ![Botón de tipos predeterminados de trabajo de mantenimiento](media/am-guides-integration-job-defaults.png "Botón de tipos predeterminados de trabajo de mantenimiento")

    1. Cree una línea y luego seleccione **Guardar**.

        ![Crear una línea](media/am-guides-integration-add-line.png "Crear una línea")

    1. En el panel Acciones, seleccione **Lista de comprobación de mantenimiento**.

        ![Botón de lista de comprobación de mantenimiento](media/am-guides-integration-maintenance-checklist.png "Botón de lista de comprobación de mantenimiento")

    1. En la ficha desplegable **Líneas de control de mantenimiento**, agregue una línea y luego cambie el valor del campo **Tipo** a **Plantilla**.

        ![Cambiar el valor de Tipo](media/am-guides-integration-checklist-lines.png "Cambiar el valor de Tipo")

    1. En la ficha desplegable **Detalles de línea**, en el campo **Modelo**,seleccione la plantilla con la que asoció la guía y luego seleccione **Guardar**.

        ![Seleccione la plantilla](media/am-guides-integration-checklist-line-details.png "Seleccionar la plantilla")

1. [Cree una orden de trabajo](work-orders/manually-created-workorders.md#create-work-order) y luego seleccione el tipo de trabajo de mantenimiento que utiliza la plantilla de la lista de verificación de mantenimiento con la que asoció la guía. La guía se asocia automáticamente con la orden de trabajo.

    ![Seleccionar un tipo de trabajo de mantenimiento](media/am-guides-integration-create-work-order.png "Seleccionar un tipo de trabajo de mantenimiento")

1. Vea la guía asociada a la orden de trabajo y trabajadores:

    1. Abra el [Espacio de trabajo móvil de gestión de activos](asset-management-mobile-workspace.md) para acceder a la orden de trabajo.
    1. [Abra la lista de verificación de mantenimiento](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) para la orden de trabajo.
    1. Seleccione una línea de lista de verificación para ver la guía asociada.

        ![Guía asociada con una línea de lista de verificación](media/am-guides-integration-show-guide.png "Guía asociada con una línea de lista de verificación")

    1. Abra la guía en HoloLens.

        ![Abrir la guía en HoloLens](media/am-guides-integration-hololens-select.png "Abrir la guía en HoloLens")

> [!NOTE]
> También puede asociar una guía directamente en la lista de verificación de mantenimiento de una orden de trabajo o un tipo de trabajo.

> [!IMPORTANT]
> Existe un problema conocido en el que, cuando se asocia una plantilla de lista de verificación de mantenimiento con un tipo de trabajo de mantenimiento predeterminado, la guía que está vinculada a la plantilla no aparece en la ficha desplegable **Guías asociadas** de la página **Tipo de trabajo de mantenimiento predeterminado**. Sin embargo, la guía aparecerá después de que ese tipo de trabajo se aplique a una orden de trabajo en la ficha desplegable **Guías asociadas**.

## <a name="see-also"></a>Consulte también

- [Visión general de doble escritura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [Visión general de la administración de activos](index.md)
