---
title: Flujos de trabajo de adquisición y abastecimiento
description: Algunas organizaciones requieren que las solicitudes de compra y los pedidos de compra los apruebe un usuario distinto a la persona que especificó la transacción. Para configurar un proceso de aprobación, puede crear un flujo de trabajo.
author: GalynaFedorova
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ebfd96690eea762d0797db1b485544d957d17ce0
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671937"
---
# <a name="procurement-and-sourcing-workflows"></a>Flujos de trabajo de adquisición y abastecimiento

[!include [banner](../includes/banner.md)]

Algunas organizaciones requieren que las solicitudes de compra y los pedidos de compra los apruebe un usuario distinto a la persona que especificó la transacción. Para configurar un proceso de aprobación, puede crear un flujo de trabajo.

Un flujo de trabajo representa un proceso empresarial. El flujo de trabajo define cómo se gestiona un documento en el sistema e indica quién debe completar una tarea o aprobar un documento. El uso del sistema de flujo de trabajo en su organización le ofrece varias ventajas:

- **Procesos coherentes**: puede definir el proceso de aprobación para documentos específicos como, por ejemplo, solicitudes de compra e informes de gastos. El sistema de flujo de trabajo le ayuda a garantizar que los documentos se procesan y se aprueban de manera coherente y eficaz.
- **Visibilidad de procesos**: puede realizar el seguimiento del estado, el historial y las medidas de rendimiento de una instancia de flujo de trabajo determinada. De este modo puede determinar si los cambios deben realizarse en el flujo de trabajo para mejorar la eficacia.
- **Lista de trabajo centralizada**: los usuarios pueden ver una lista de trabajo centralizada para ver las tareas y las aprobaciones de flujo de trabajo que tienen asignadas en todos los flujos de trabajo en los que participan. Esta lista de trabajo está disponible en la página Elementos de trabajo.

## <a name="the-types-of-workflows-that-you-can-create"></a> Tipos de flujo de trabajo que puede crear

Los siguientes tipos de flujo de trabajo están disponibles para Adquisición y abastecimiento.

| Tipo | Use este tipo para |
|---|---|
| Revisión de solicitudes de compra | Crear flujos de trabajo de aprobación y revisión para solicitudes de compra. |
| Revisión de líneas de solicitud de compra | Crear flujos de trabajo de aprobación y revisión para líneas de solicitudes de compra. |
| Flujo de trabajo del pedido de compra | Crear flujos de trabajo de aprobación y revisión para pedidos de compra. |
| Flujo de trabajo de línea del pedido de compra | Crear flujos de trabajo de aprobación y revisión para líneas de pedidos de compra. |
| Flujo de trabajo de solicitud de adición de proveedor | Cree su revisión y flujos de trabajo de aprobación para agregar nuevos proveedores mediante solicitudes de proveedor. |

> [!IMPORTANT]
> Cuando agrega un nuevo flujo de trabajo, también puede ver los siguientes flujos de trabajo obsoletos enumerados en el cuadro de diálogo **Crear flujo de trabajo**. Estos están relacionados con la funcionalidad *Acuse de recibo* que estaba disponible en [Dynamics AX 2012](/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), pero que ahora ha quedado obsoleto. Actualmente, estos flujos de trabajo no son compatibles.
> 
> - Flujo de trabajo de notificación de fecha de vencimiento de entrega
> - Flujo de trabajo de notificación de factura recibida
> - Flujo de trabajo de notificación con error de albarán
> - Flujo de trabajo de notificación de rechazo de albarán sin confirmar

## <a name="creating-a-workflow"></a>Creación de un flujo de trabajo

Para crear un flujo de trabajo, vaya a Adquisición y abastecimiento &gt; Configuración &gt; Flujos de trabajo de adquisición y abastecimiento, y cree un nuevo flujo de trabajo seleccionando el tipo de flujo de trabajo que desee crear. 

En el lienzo del flujo de trabajo puede arrastrar elementos de flujo de trabajo al diseñador y vincular los elementos en un flujo. Se deben configurar los elementos del flujo de trabajo. Para los elementos de flujo de trabajo de aprobación y de tarea puede configurar qué participante debe actuar.

## <a name="types-of-participants"></a>Tipos de participantes

Puede asignar un paso de aprobación a los siguientes grupos de participantes.

| Grupo de usuarios | Descripción |
|---|---|
| Participante | Asignar el paso de aprobación a los miembros de un grupo o rol. |
| Jerarquía | Asignar el paso de aprobación a los usuarios de una jerarquía organizativa específica. |
| Usuario del flujo de trabajo | Asignar el paso de aprobación a los usuarios de este flujo de trabajo. |
| Cola | Asignar el paso de aprobación a una cola de elementos de trabajo. |
| Usuario | Asigne el paso de aprobación a usuarios específicos. |

## <a name="additional-resources"></a>Recursos adicionales

- [Definición de flujos de trabajo de procesos empresariales para solicitudes de compra](https://www.microsoft.com/download/details.aspx?id=101821)
- [Flujo de trabajo de solicitudes de compra](purchase-requisitions-workflow.md)
- [Incorporación de proveedores](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]