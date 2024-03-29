---
title: Configurar parámetros de arrendamiento (versión preliminar)
description: Este artículo describe las opciones de configuración para el arrendamiento de activos, como la información de seguridad y la configuración de contabilidad.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e878fa7634cfdcc6c0db19a91e771757c545505b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895091"
---
# <a name="configure-lease-parameters"></a>Configurar parámetros de arrendamiento

[!include [banner](../includes/banner.md)]

Varias opciones de configuración afectan al comportamiento del arrendamiento de activos. Estas configuraciones incluyen nombres de diarios, parámetros generales y configuraciones de perfil de publicación.

1. Vaya a **Arrendamiento de activos \> Configuración \> Parámetros de arrendamiento de activos**.
2. En la pestaña **Arrendamientos**, seleccione la ficha desplegable **General**.

    El parámetro **Permitir anulación de clasificación manual** determina si la clasificación de arrendamiento se puede anular antes de que se confirme la programación de pagos.

    El parámetro **Lote entre entidades** determina si puede publicar en otras entidades jurídicas desde la entidad jurídica actual. Si este parámetro está activado, puede crear asientos de diario para las entidades jurídicas a las que tiene acceso.

3. Seleccione la opción **Permitir la eliminación de arrendamientos confirmados** a **Sí** para permitir que se eliminen los arrendamientos que tienen programas de pago confirmados. Los arrendamientos no se pueden eliminar si tienen asociadas transacciones registradas o no registradas, independientemente de la configuración de esta opción. No puede restaurar un registro de arrendamiento después de eliminarlo. Si carga algún registro para un arrendamiento eliminado, ya sea manualmente o mediante entidades de datos, la información cargada se trata como nueva, no como una actualización de un arrendamiento existente.

    Si configura esta opción en **Sí** y el tipo de transición del libro es **Opción de recuperación acumulativa A o B**, el sistema establece el campo **Tipo de interés incremental del endeudamiento** al valor del campo **Tipo de interés incremental del endeudamiento en la transición**, en la página **Configuración del libro**. Si esta opción se establece en **No**, la tasa del arrendamiento principal se establece en el valor del campo **Tipo de interés incremental del endeudamiento** en la página **Detalles del libro**, independientemente del tipo de transición del libro.

4. Establezca la opción **Permitir reversiones de depreciación en el libro cerrado** en **Sí** para permitir la reversión de las transacciones de gastos de depreciación. Las transacciones de gastos se pueden revertir incluso cuando la versión del libro está cerrada.

    > [!NOTE]
    > Le recomendamos que mantenga esta opción configurada en **No**. La configuración de esta opción se utiliza como validación y control para evitar que una versión de libro cerrado se deprecie accidentalmente. Manteniendo la opción establecida en **No**, ayuda a mantener precisos el valor neto en los libros y los cálculos de depreciación futura.

5. Establezca la opción **Permitir el desglose del importe de pago** en **Sí** para permitir un desglose de los importes de pago en la ficha desplegable **Líneas de programación de pago** de la página **Arrendamiento**. Los tipos de desglose de pagos se definen en **Configuración** en la página **Tipos de importes de pago**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
