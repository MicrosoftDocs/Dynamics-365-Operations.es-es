---
title: Notificar como terminado a una ubicación controlada mediante matrículas de entidad desde un dispositivo de tarjetas de trabajo
description: En este tema se describe el proceso para completar los productos terminados en un pedido de producción al inventario cuando una matrícula de entidad controla la ubicación.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
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
ms.openlocfilehash: 63073035941cd2ef343c65364536fe76a9b71430
ms.sourcegitcommit: af36eb17b36092a3101bbfc96486b25036676558
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2020
ms.locfileid: "2935131"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Notificar como terminado a una ubicación controlada mediante matrículas de entidad desde un dispositivo de tarjetas de trabajo 

El proceso denominado Informar como terminado completa los productos terminados en un pedido de producción al inventario. Si el producto terminado se habilita para los procesos avanzado de almacenes, el producto se notifica como finalizado a una ubicación denominada la ubicación de salida de la producción. Para obtener información sobre la configuración de la ubicación de salida de producción, consulte [Ubicación de salida de producción](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Si la ubicación de salida de producción está controlada por una matrícula, se debe proporcionar una matrícula cuando se notifique su fin. El campo **Matrícula de entidad** estará visible en el **Informe de progreso** en la página **Dispositivo de tarjeta de trabajo**. El campo solo es visible en el cuadro **Informar progreso** al informar sobre la última operación del pedido de producción y cuando el artículo para el pedido de producción está habilitado para los procesos de gestión de almacenes. 

Hay dos opciones para proporcionar la matrícula
- El usuario selecciona matrícula existente en el campo de matrícula.
- La matrícula se genera automáticamente a partir de una secuencia numérica y se establece de forma predeterminada en el campo de matrícula.

La opción de generar automáticamente la matrícula se configura seleccionando la opción **Generar matrícula de entidad de almacén** en la página **Configurar tarjeta de trabajo para dispositivos**.
