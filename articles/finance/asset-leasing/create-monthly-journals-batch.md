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
ms.openlocfilehash: 7f46f289c58c32c535dd20fb510cf2812625c49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971337"
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