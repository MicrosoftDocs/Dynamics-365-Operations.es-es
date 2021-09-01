---
title: Descripciones predeterminadas para el libro mayor
description: Las descripciones predeterminadas se pueden utilizar para actualizar el campo Descripción en las contabilizaciones de comprobantes en el libro mayor.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c68d0ae43ee2350225a0a0e32578f300b8faebe18aa575a5f737a49fd4c0c1a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736728"
---
# <a name="default-descriptions-for-the-general-ledger"></a>Descripciones predeterminadas para el libro mayor

[!include [banner](../../includes/banner.md)]

Las descripciones predeterminadas se pueden utilizar para actualizar el campo **Descripción** en las contabilizaciones de comprobantes en el libro mayor. Esta funcionalidad se ha mejorado para que funcione con el costo de aterrizaje.

Para configurar descripciones predeterminadas para las contabilizaciones del libro mayor, vaya a **Administración organizacional \> Configuración \> Descripciones predeterminadas**.

La siguiente tabla enumera los nuevos valores que se han agregado para el campo **Descripción** en la página **Descripciones predeterminadas** para respaldar el costo de aterrizaje.

| Tipo de descripción | Notas |
|---|---|
| Gestión de costes de importación: acumulación de costes | Cuando se registra una factura de orden de compra, se procesa una acumulación de costos para estimar los costos del viaje. Se pueden especificar descripciones predeterminadas para agregar el número de viaje a la descripción. Use *%4* para el número de envío. |
| Gestión de costes de importación: pedido de mercancía en tránsito | Si utiliza el procesamiento en tránsito, se registra la factura de la orden de compra y las mercancías se registran en una cuenta de mercancías en tránsito. Se pueden especificar descripciones predeterminadas para agregar el número de pedido en tránsito a la descripción. Use *%4* para el número de pedido en tránsito. |
| Inventario - cierre - ajuste | Cuando se procesa la factura de cuentas por pagar (AP) para un costo de viaje, se procesa un ajuste de inventario para estimar los costos de viaje. Se pueden especificar descripciones predeterminadas para agregar el número de viaje a la descripción. Use *%4* para el número de envío. |

Para obtener más información sobre cómo trabajar con la página **Descripciones predeterminadas**, vea [Configurar descripciones predeterminadas para la publicación automática](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).
