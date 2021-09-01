---
title: Usar códigos de motivo de etapa
description: El código de motivo se usa para indicar por qué se canceló un contrato de nivel de servicio (SLA) o por qué se superó el límite de tiempo de un pedido de servicio establecido en el SLA.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2e823a2e015c4bf22da8eff94e2bc85c813c03b5bb744aa4ce52c95dcaff898
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753852"
---
# <a name="use-stage-reason-codes"></a>Usar códigos de motivo de etapa 

[!include [banner](../includes/banner.md)]


El código de motivo se usa para indicar por qué se canceló un contrato de nivel de servicio (SLA) o por qué se superó el límite de tiempo de un pedido de servicio establecido en el SLA.

También puede especificar que es necesario especificar un código de motivo cuando un SLA se cancela o cuando el límite de tiempo supera el tiempo que se especifica en el SLA para el pedido de servicio.

Si indicó que es necesario especificar un código de motivo, debe especificar un código de motivo en las situaciones siguientes:

  - Cuando un pedido de servicio se traslada a una etapa que detiene el registro de tiempo en comparación con el SLA para el pedido de servicio.

  - Cuando se realiza la aprobación final del pedido de servicio.

  - Cuando el registro de tiempo se detiene manualmente.

## <a name="set-up-reason-codes"></a>Configurar códigos de motivos

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Pedidos de servicio** \> **Códigos de motivo de etapa**.

2.  En el formulario **Códigos de motivo de etapa**, haga clic en **Nuevo** para crear un nuevo código de motivo.

3.  En el campo **Código de motivo de etapa**, especifique un código de motivo de etapa única.

4.  En el campo **Descripción**, especifique una descripción para el código de motivo de etapa.

5.  Cierre el formulario para guardar los cambios.

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>Exigir códigos de motivo cuando se cancele un acuerdo de nivel de servicio

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Parámetros de la gestión de servicio**.

2.  En el formulario **Parámetros de gestión de servicio**, haga clic en el vínculo **General** y seleccione la casilla de verificación **Código de motivo al cancelar** .

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>Exigir códigos de motivo cuando un pedido de servicio supere el tiempo límite establecido en un contrato de nivel de servicio

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Parámetros de la gestión de servicio**.

2.  En el formulario **Parámetros de gestión de servicio**, haga clic en el vínculo **General** y seleccione la casilla de verificación **Código de motivo al superar el tiempo** .

## <a name="see-also"></a>Consulte también

[Iniciar y detener registro de horas en un pedido de servicio](start-and-stop-time-recording-on-a-service-order.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]