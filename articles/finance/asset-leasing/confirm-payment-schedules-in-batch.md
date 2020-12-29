---
title: Confirmar programaciones de pago de arrendamiento de activos en un lote
description: Este tema explica cómo confirmar varias programaciones de pago en un lote.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b5a90b96ac598d145e2b0697627de04731b55f59
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447807"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>Confirmar programaciones de pago de arrendamiento de activos en un lote

[!include [banner](../includes/banner.md)]

Este tema explica cómo confirmar varias programaciones de pago en un lote. Los programas de pago se confirman en forma de arrendamiento a arrendamiento o mediante el proceso de confirmación por lotes. Un movimiento de diario solo se puede registrar frente a un arrendamiento que tenga una programación de pagos confirmada. La confirmación de la programación de pagos sirve como aprobación final de la información financiera para el arrendamiento. Todos los cambios futuros en la información financiera del arrendamiento, como los pagos y el plazo del arrendamiento, constituyen un ajuste del arrendamiento y deben procesarse de esa manera.

Para confirmar varias programaciones de pago, siga estos pasos.

1. Vaya a **Arrendamiento de activos \> Periódico \> Lote de confirmación**.
2. En la página **Lote de confirmación**, seleccione **Lote de confirmación**.
3. En el cuadro de diálogo que aparece, filtre según los libros que desea confirmar.

    - Para confirmar todos los libros en un grupo de arrendamiento específico, seleccione el grupo en el campo **Grupo de arrendamiento**.
    - Para confirmar libros específicos, seleccione los libros en el campo **Id. del libro**.
    - Para confirmar todos los libros, active el parámetro **Para todos los libros**.

La información de los libros recién confirmados se muestra en la página **Libros confirmados**. Una vez confirmadas las programaciones de pago, los asientos de diario de reconocimiento inicial se pueden contabilizar frente a los arrendamientos.
