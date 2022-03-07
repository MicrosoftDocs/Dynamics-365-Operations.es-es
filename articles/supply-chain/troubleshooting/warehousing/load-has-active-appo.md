---
title: No puede confirmar un envío debido a un problema con el calendario
description: No puede confirmar un envío debido a un problema con el calendario
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938548"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a>No puede confirmar un envío debido a un problema con el calendario

Código de error: TRX2716

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> El tipo de calendario %1 requiere que se registre la entrada y salida de la cita %2.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

Existen citas activas para la carga. Por ejemplo, hay una regla que requiere que el conductor registre. Por lo tanto, la carga se encuentra actualmente en un estado en el que falla la confirmación del envío.

## <a name="resolution"></a>Resolución

Debe investigar y solucionar cualquier problema con las citas activas que están vinculadas a la carga.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En el panel Acciones, en la pestaña **Transporte**, en el grupo **Citas**, seleccione **Programación de citas**.
1. Siga uno de estos pasos:

    - Asegúrese de que el registro de entrada/salida del conductor esté completo para la cita.
    - Complete o cancele la cita.
    - Desactive la opción **Se requiere registro del conductor** para la regla de cita relacionada.
