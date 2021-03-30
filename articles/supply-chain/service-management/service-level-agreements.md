---
title: Visión general de los contratos de nivel de servicio
description: En un contrato de nivel de servicio, el cliente acuerda un tiempo de respuesta mínimo desde que la empresa de servicios registra el problema y hasta que se resuelve el problema.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b626d490b5abb948943df25c956c48084953da7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214331"
---
# <a name="service-level-agreements-overview"></a>Visión general de los contratos de nivel de servicio       

[!include [banner](../includes/banner.md)]


Un acuerdo de nivel de servicio (SLA) es un acuerdo entre una empresa de servicio y un cliente de servicio. En un SLA, el cliente acuerda un tiempo de respuesta mínimo desde que la empresa de servicios registra el problema y hasta que se resuelve el problema.

Un SLA impone un modo estándar de servicio que se ofrece a los clientes e indica a una empresa de servicio cuándo debería realizar un trabajo de servicio.

Se puede crear el número de SLA que se desee para ofrecer a los clientes de servicio distintos niveles de servicio.

## <a name="create-a-service-level-agreement"></a>Crear un acuerdo de nivel de servicio

1.  Haga clic en **Gestión de servicio** \> **Configurar** \> **Contratos de servicio** \> **Contratos de nivel de servicio**.

2.  Escriba un nombre para el contrato de nivel de servicio en el campo **Contrato de nivel de servicio**.

3.  Escriba el tiempo que desea asignar a la finalización de las llamadas de servicio vinculados al acuerdo de nivel de servicio. Seleccione un calendario si desea basar el contrato de nivel de servicio en un calendario específico.

## <a name="apply-a-service-level-agreement"></a>Aplicar un acuerdo de nivel de servicio

El SLA se aplica directamente a un acuerdo de servicio.

Los pedidos de servicio que crea manualmente y vincula a un acuerdo de servicio con un SLA se miden con este SLA.

Los pedidos de servicio que cree automáticamente no se vinculan a un SLA.

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a>Aplicar el acuerdo de nivel de servicio al acuerdo de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**. Seleccione el acuerdo de servicio al que desea aplicar el SLA y, a continuación, haga clic en **Editar** en el **Panel de acciones**.

2.  En el campo **Contrato de nivel de servicio**, seleccione el SLA que desea asignar.

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a>Aplicar el acuerdo de nivel de servicio al grupo de acuerdos de servicio

1.  Haga clic en **Gestión de servicio** \> **Configurar** \> **Contratos de servicio** \> **Grupos de contrato de servicio**.

2.  En el campo **Contrato de nivel de servicio**, seleccione el SLA que desea asignar.

## <a name="track-time-on-a-service-order-against-an-sla"></a>Realizar un seguimiento del tiempo en un pedido de servicio contra un SLA

Cuando se crea un nuevo pedido de servicio para un acuerdo de servicio al cual se ha asignado un SLA, el intervalo de tiempo para la entrega del servicio se inicia y el sistema comienza a realizar un seguimiento del plazo de entrega. Además, puede configurar las siguientes opciones:

  - Puede iniciar y detener grabaciones de tiempo en el pedido de servicio para registrar el tiempo total que se dedica en pedidos de servicio.

  - Puede supervisar la conformidad con el intervalo de tiempo definido en el acuerdo de nivel de servicio.

  - Puede definir códigos de motivo que se deban configurar si se supera el intervalo de tiempo del acuerdo de nivel de servicio.

## <a name="see-also"></a>Consulte también

[Ver conformidad con contratos de nivel de servicio](view-compliance-with-service-level-agreements.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]