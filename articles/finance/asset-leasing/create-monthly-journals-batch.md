---
title: Crear movimientos de diario mensuales en lote
description: Este tema explica cómo crear asientos de diario en un lote para ayudar a aumentar la eficiencia cuando se registran los gastos de arrendamiento mensuales.
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6fd1815620095909e290fd03c404d964baa04a94
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241571"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Crear movimientos de diario mensuales en lote

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear asientos de diario en un lote para ayudar a aumentar la eficiencia cuando se registran los gastos de arrendamiento mensuales. El procesamiento por lotes se puede utilizar para crear asientos de diario a partir de múltiples programaciones. Estos asientos de diario pueden incluir pagos de arrendamientos, amortización de pasivos, amortización de activos por derecho de uso (ROU) y gastos a cargo del arrendatario en un arrendamiento de capital. También puede utilizar el procesamiento por lotes para realizar el reconocimiento inicial de varios arrendamientos al mismo tiempo o para crear ajustes de transición para varios arrendamientos al mismo tiempo.

Para configurar un trabajo por lotes o procesar facturas de pago, depreciación o intereses para varios arrendamientos, vaya a **Arrendamiento de activos \> Periódico \> Creación de diario por lotes**. En el cuadro de diálogo que aparece, puede seleccionar la programación desde la que se deben crear las entradas del diario. También puede especificar si el proceso por lotes debe ejecutarse para entidades, grupos de arrendamiento o libros de arrendamiento específicos.

> [!NOTE]
> Las transacciones posteriores, como los programas de amortización de pasivos, los pagos, la depreciación y los gastos, se contabilizarán solo después de que se registre el reconocimiento inicial de los arrendamientos correspondientes.
>
> Se crean las entradas del diario, pero no se contabilizarán hasta que seleccione el comando **Ejecutar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]