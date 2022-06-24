---
title: Descripciones predeterminadas para el libro mayor
description: Las descripciones predeterminadas se pueden utilizar para actualizar el campo Descripción en las contabilizaciones de comprobantes en el libro mayor.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7020c39dd599be047e07caa391d6d4c69c426328
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889559"
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
