---
title: Notificar como terminado a una ubicación controlada mediante matrículas de entidad desde un dispositivo de tarjetas de trabajo
description: En este tema se describe el proceso para completar los productos terminados en un pedido de producción al inventario cuando una matrícula de entidad controla la ubicación.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: 35ad27a6b8a52bfd086fbe4fc57b1681ff88fd5b
ms.sourcegitcommit: 58db26b7edf02e7c33aaaf1c934e3263aa74b01f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "1995151"
---
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Notificar como terminado a una ubicación controlada mediante matrículas de entidad desde un dispositivo de tarjetas de trabajo 

El proceso denominado Informar como terminado completa los productos terminados en un pedido de producción al inventario. Si el producto terminado se habilita para los procesos avanzado de almacenes, el producto se notifica como finalizado a una ubicación denominada la ubicación de salida de la producción. Para obtener información sobre la configuración de la ubicación de salida de producción, consulte [Ubicación de salida de producción](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Debe seleccionar un número de matrícula de entidad de almacén para completar esta tarea. Si la ubicación de salida de la producción está configurada para ser seguida por la matrícula de entidad, entonces debe incluirse una matrícula de entidad de almacén cuando se informe de la ubicación de salida de producción como finalizada. El campo **Matrícula de entidad** estará visible en el **Informe de progreso** en la página **Dispositivo de tarjeta de trabajo**. El campo sólo está visible en el **Informe de progreso** al notificar la última operación del pedido de producción. El campo solo se muestra si el artículo para el pedido de producción se habilita para los procesos de la gestión de almacenes. 
