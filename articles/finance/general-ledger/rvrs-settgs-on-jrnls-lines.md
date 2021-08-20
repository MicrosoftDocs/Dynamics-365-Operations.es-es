---
title: Configuración de reversiones en diarios y líneas
description: Este tema trata sobre por qué un asiento de reversión introducido en un diario general podría no incluirse en la transacción registrada.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d0659fbd814d3fb86b2f4a1ecb6162614ab8a4f125029fbb04f08cc5fb52b45c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780831"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Configuración de reversiones en diarios y líneas

[!include [banner](../includes/banner.md)]

Este tema trata sobre por qué un asiento de reversión introducido en un diario general podría no incluirse en la transacción registrada.  

## <a name="symptom"></a>Síntoma

Un diario general incluye una entrada de reversión y una fecha de reversión en el diario. Al registrar el diario, ninguno de los asientos se revierte. ¿Por qué ocurre esto?

## <a name="resolution"></a>Resolución

Cuando se registra el diario, el proceso de reversión solo se fija en la configuración de **Entrada de reversión** y **Fecha de reversión** de la sección **Líneas** del asiento. Este enfoque permite que un diario incluya algunos asientos marcados para reversión y otros que no lo están.

Los valores del diario solo se utilizan como predeterminados al agregar *nuevas* líneas. El cambio de los valores del diario no afecta las líneas existentes. En este ejemplo, las líneas de asientos se introdujeron primero. Cuando introduzca el detalle de la línea antes de designar el diario como de reversión, la designación como entrada inversa y la fecha no se aplicará a ninguna línea existente.

El cambio de la entrada o la fecha de reversión en una línea existente propaga ese cambio a otras líneas del mismo asiento. Para optimizar el rendimiento, la cuadrícula no se actualiza después de propagar cambios a otras líneas. Puede mostrar los valores actualizados actualizando la cuadrícula.


