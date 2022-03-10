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
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f18c3bd95901303379c460d026bc944cee809b7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576673"
---
# <a name="rebate-management-deal-workflows"></a>Flujos de trabajo de acuerdos de gestión de devoluciones

[!include [banner](../includes/banner.md)]

Para aprobar acuerdos de devoluciones, la gestión de devoluciones utiliza la misma plataforma de flujo de trabajo que otras aplicaciones de Finance and Operations. Hay dos procesos de trabajo asociados con cada flujo de trabajo:

- Un elemento del flujo de trabajo aprueba el acuerdo.
- Un elemento del flujo de trabajo activa el trato para que el usuario o el proceso del flujo de trabajo puedan aprobar las transacciones.

Antes de poder utilizar una oferta de devolución, debe estar activa en el módulo **Gestión de devoluciones**. Para activar una oferta, primero debe crear y configurar un *Flujo de trabajo de la operación de gestión de devoluciones*.

Los usuarios no pueden aprobar acuerdos manualmente. El flujo de trabajo debe usarse siempre.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Crear y administrar flujos de trabajo de acuerdos de gestión de devoluciones

Para trabajar con sus flujos de trabajo de gestión de devoluciones de acuerdos, vaya a **Gestión de devoluciones \> Configuración \> Flujos de trabajo de gestión de devoluciones**. Allí, puede ver, crear y actualizar flujos de trabajo según sea necesario. Solo un flujo de trabajo de este tipo puede estar activa a la vez. Para obtener más información sobre los flujos de trabajo, cómo trabajar con la página **Flujos de trabajo de gestión de devoluciones** y cómo crear flujos de trabajo, consulte [Descripción general del sistema de flujo de trabajo](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) y sus temas relacionados.

## <a name="use-a-workflow-to-activate-a-deal"></a>Utilice un flujo de trabajo para activar un acuerdo

Para activar un acuerdo a través de un flujo de trabajo, ábralo (por ejemplo, en la página **Todas las ofertas de gestión de devoluciones**). Luego, en el panel de acciones, seleccione **Flujo de trabajo \> Enviar**. Una vez que el nuevo acuerdo se haya procesado y aprobado a través del flujo de trabajo, estará activo y listo para usar.

Una vez que se ha activado un acuerdo, no puede cambiar la mayoría de su configuración. Si debe cambiar una oferta activa, primero desactívela y luego cree una nueva oferta. Si el nuevo acuerdo se parece al anterior, puede crearlo copiando el anterior.

Puede cambiar la siguiente configuración para una oferta después de que se haya activado:

- Conciliar antes de
- Garantía acumulativa
- Perfil de contabilización
- Perfil de contabilización para la garantía
- Notas de documentos
- Divisa
- Fecha de inicio
- Fecha de finalización

Además, se pueden eliminar las líneas de reembolso.
