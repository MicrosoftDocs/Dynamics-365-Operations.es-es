---
title: Configurar tipos indexados
description: En este tema se explica cómo configurar tipos indexados. Se requieren tipos indexados si su organización asocia los importes de pago de arrendamientos con un conjunto de tipos indexados.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 40f230a9d69a142b18eb27a2d5e420dbadc600d2
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880969"
---
# <a name="set-up-index-rates"></a>Configurar tipos indexados

[!include [banner](../includes/banner.md)]

Si los pagos de arrendamientos dependen de un índice, los tipos indexados se pueden agregar y mantener en el sistema. Para revalorizar los pagos de arrendamientos de la página **Tipo de tipo indexado**, el proceso de revalorización del tipo indexado utiliza el tipo indexado más reciente desde la fecha de la revalorización.

Para agregar tipos de tipo indexado y tipos indexados, siga estos pasos.

1. Vaya a **Arrendamiento de activos \> Configuración \> Tipo de tipo indexado**.
2. Seleccione **Nuevo**.
3. En los campos correspondientes, introduzca el tipo de tipo y el nombre del tipo indexado.
4. Para agregar un nuevo valor de tipo indexado, seleccione el tipo de tipo indexado y luego seleccione **Agregar**.
5. Seleccione la fecha de inicio efectiva del tipo y seleccione el valor del tipo.

Debe seleccionar **Diferencia de valor de tipo indexado** o **Valor de tipo indexado** como método de tipo indexado.

- Seleccione el método **Diferencia de valor de tipo indexado** para calcular un nuevo pago por arrendamiento, basado en la diferencia entre el tipo indexado en la fecha de inicio y el tipo indexado más reciente. El tipo indexado se define en el campo **Tipo indexado (%)**.
- Seleccione el método **Valor de tipo indexado** para calcular el pago del arrendamiento utilizando el porcentaje que se especifica en el campo **Tipo indexado (%)**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
