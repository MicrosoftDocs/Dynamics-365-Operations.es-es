---
title: Flujos de trabajo de acuerdos de gestión de devoluciones
description: Este tema explica cómo configurar un flujo de trabajo de gestión de devoluciones para aprobar y activar acuerdos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee342de6d069131e230120c5d65aef58da8e632a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020396"
---
# <a name="rebate-management-deal-workflows"></a>Flujos de trabajo de acuerdos de gestión de devoluciones

[!include [banner](../includes/banner.md)]

Para aprobar acuerdos de devoluciones, la gestión de devoluciones utiliza la misma plataforma de flujo de trabajo que otras aplicaciones de Finance and Operations. Hay dos procesos de trabajo asociados con cada flujo de trabajo:

- Un elemento del flujo de trabajo activa el trato para que el usuario o el proceso del flujo de trabajo puedan aprobar las transacciones.
- Un elemento del flujo de trabajo aprueba el acuerdo.

Antes de poder utilizar una oferta de devolución, debe estar activa en el módulo **Gestión de devoluciones**. Para activar una oferta, primero debe crear y configurar un *Flujo de trabajo de la operación de gestión de devoluciones*.

Una vez que se activa un flujo de trabajo para la gestión de devoluciones, los usuarios no pueden aprobar acuerdos manualmente. El flujo de trabajo debe usarse siempre.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Crear y administrar flujos de trabajo de acuerdos de gestión de devoluciones

Para trabajar con sus flujos de trabajo de gestión de devoluciones de acuerdos, vaya a **Gestión de devoluciones \> Configuración \> Flujos de trabajo de gestión de devoluciones**. Allí, puede ver, crear y actualizar flujos de trabajo según sea necesario. Solo un flujo de trabajo de este tipo puede estar activa a la vez. Para obtener más información sobre los flujos de trabajo, cómo trabajar con la página **Flujos de trabajo de gestión de devoluciones** y cómo crear flujos de trabajo, consulte [Descripción general del sistema de flujo de trabajo](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) y sus temas relacionados.

## <a name="use-a-workflow-to-activate-a-deal"></a>Utilice un flujo de trabajo para activar un acuerdo

Para activar un acuerdo a través de un flujo de trabajo, ábralo (por ejemplo, en la página **Todas las ofertas de gestión de devoluciones**). Luego, en el panel de acciones, seleccione **Flujo de trabajo \> Enviar**. Una vez que el nuevo acuerdo se haya procesado y aprobado a través del flujo de trabajo, estará activo y listo para usar.

Una vez que se ha activado un acuerdo, no puede cambiar su configuración. Si debe cambiar una oferta activa, desactívela y luego cree una nueva oferta. Si el nuevo acuerdo se parece al anterior, puede crearlo copiando el anterior.
