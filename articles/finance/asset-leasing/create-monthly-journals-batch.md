---
title: Crear movimientos de diario mensuales en lote
description: Este tema explica cómo crear asientos de diario en un lote para ayudar a aumentar la eficiencia cuando se registran los gastos de arrendamiento mensuales.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 22e2892a6866123ecf0e72511bdce19fe12895df
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344862"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Crear movimientos de diario mensuales en lote

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Este tema explica cómo crear asientos de diario en un lote para ayudar a aumentar la eficiencia cuando se registran los gastos de arrendamiento mensuales. El procesamiento por lotes se puede utilizar para crear asientos de diario a partir de múltiples programaciones. Estos asientos de diario pueden incluir pagos de arrendamientos, amortización de pasivos, amortización de activos por derecho de uso (ROU) y gastos a cargo del arrendatario en un arrendamiento de capital. También puede utilizar el procesamiento por lotes para realizar el reconocimiento inicial de varios arrendamientos al mismo tiempo o para crear ajustes de transición para varios arrendamientos al mismo tiempo.

Para configurar un trabajo por lotes o procesar facturas de pago, depreciación o intereses para varios arrendamientos, vaya a **Arrendamiento de activos \> Periódico \> Creación de diario por lotes**. En el cuadro de diálogo que aparece, puede seleccionar la programación desde la que se deben crear las entradas del diario. También puede especificar si el proceso por lotes debe ejecutarse para entidades, grupos de arrendamiento o libros de arrendamiento específicos.

> [!NOTE]
> Las transacciones posteriores, como los programas de amortización de pasivos, los pagos, la depreciación y los gastos, se contabilizarán solo después de que se registre el reconocimiento inicial de los arrendamientos correspondientes.
>
> Se crean las entradas del diario, pero no se contabilizarán hasta que seleccione el comando **Ejecutar**.

Para contabilizar el diario de reconocimiento inicial en una fecha diferente a la fecha de inicio del arrendamiento, seleccione **Asignar la fecha de registro del reconocimiento inicial**. Aparecerá un campo **Fecha** donde podrá especificar la fecha de registro correcta.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
