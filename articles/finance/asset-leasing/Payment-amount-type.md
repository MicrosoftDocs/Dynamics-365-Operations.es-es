---
title: Agregar tipos de importes de pago
description: En este artículo se explica cómo configurar tipos de importes de pago en Arrendamiento de activos.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 03fc903e6cfe78ef2fed7e3a0744a8f809f6892d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891620"
---
# <a name="add-payment-amount-types"></a>Agregar tipos de importes de pago

[!include [banner](../includes/banner.md)]

Este artículo describe cómo configurar tipos de importes de pago en Arrendamiento de activos. De esta forma, puede detallar el importe del pago del arrendamiento en lugar de agregar el importe de la suma global en las líneas del cronograma de pagos.

Para agregar tipos de importe de pago, siga estos pasos.

1. Vaya a **Arrendamiento de activos \> Configuración \> Tipos de importes de pago**.
2. Seleccione **Nuevo**.
3. Introduzca el nuevo tipo de pago y una descripción.

> [!NOTE]
> Para la revaluación del índice IFRS 16, debe crear un tipo de importe de pago y marcarlo como **Se usa para la revalorización del índice IFRS16**. Este tipo de importe de pago se utilizará cuando el proceso de revaluación del índice se ejecute contra el libro IFRS 16, y tendrá en cuenta los cambios que ocurrieron debido al proceso de revaluación del índice.
>
> Cuando la opción **Desglose de pagos** en el contrato de arrendamiento se establece en **Sí**, si se ejecuta la revalorización del índice para IFRS 16, pero no hay ningún tipo de pago para IFRS 16, el proceso no se completará.

Solo se puede marcar un registro como **Utilizado para la revaluación del índice IFRS 16**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
