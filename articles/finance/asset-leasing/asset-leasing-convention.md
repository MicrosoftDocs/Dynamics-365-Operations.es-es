---
title: Convenciones de arrendamiento de activos
description: En este tema se describen las convenciones de los activos arrendados.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: afc432d448f3b013dd8732120d7e8a50a9169343c705a75465e669156fd5e052
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740035"
---
# <a name="asset-leasing-conventions"></a>Convenciones de arrendamiento de activos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este tema se describen las convenciones de los activos arrendados. Las convenciones de arrendamiento se utilizan para determinar la fecha de inicio de un libro de arrendamiento. Si la convención de arrendamiento se establece en **Ninguna**, la fecha de inicio es la misma que la fecha de inicio del arrendamiento (es decir, el valor del campo **Fecha de inicio del arrendamiento**). Si la convención de arrendamiento se establece en **Mes entero**, la fecha de inicio es el primer día del mes en el que cae la fecha de comienzo del arrendamiento.

La fecha de comienzo determina la fecha de inicio del período para los programas de amortización de pasivos y depreciación de activos. Los gastos por intereses y los gastos de depreciación se contabilizan en la fecha de cierre del período de los anexos correspondientes. El asiento de diario de reconocimiento y ajuste inicial se contabiliza en la fecha de comienzo.

> [!NOTE]
> La característica de convenciones de arrendamiento debe activarse a través de la administración de características. En el espacio de trabajo **Gestión de funciones**, busque y seleccione la característica denominada **Convenio de arrendamiento para arrendamiento de activos** y luego seleccione **Habilitar ahora**.

Las convenciones de arrendamiento se asignan a la configuración de un libro de activos de arrendamiento.

Para ver o asignar la convención de arrendamiento, siga estos pasos.

1. Vaya a **Arrendamiento de activos \> Configuración \> Libros de arrendamiento**.
2. En el campo **Convención de arrendamiento**, seleccione uno de los siguientes valores.

    | Convención de arrendamiento | Descripción |
    |--------------------|-------------|
    | None               | Los programas de amortización de pasivos y depreciación de activos comienzan en la fecha de inicio del arrendamiento, porque la fecha de comienzo es igual a la fecha de inicio del arrendamiento. La fecha de finalización es un mes después. Esta convención de arrendamiento no garantiza que los intereses se contabilicen el último día de cada mes. |
    | Mes completo         | Para los arrendamientos que tienen una fecha de inicio que ocurre en cualquier momento durante el mes, los programas de amortización de pasivos y depreciación de activos comienzan a acumular gastos el primer día de ese mes. Esta convención de arrendamiento asegura que los intereses se devenguen el último día de cada mes para todo el mes. |

3. Seleccione **Guardar**.

Cuando se crea un arrendamiento, la fecha de comienzo de cada libro se introduce automáticamente en función de la fecha de inicio que se introduce para el arrendamiento y la convención de arrendamiento que se especifica para el libro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
