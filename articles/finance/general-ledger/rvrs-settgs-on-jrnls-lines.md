---
title: Configuración de reversiones en diarios y líneas
description: Este artículo trata sobre por qué un asiento de reversión introducido en un diario general podría no incluirse en la transacción registrada.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e36a3ea1736e4d7f60a5a6ce588ad3e66c950c14
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899853"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Configuración de reversiones en diarios y líneas

[!include [banner](../includes/banner.md)]

Este artículo trata sobre por qué un asiento de reversión introducido en un diario general podría no incluirse en la transacción registrada.  

## <a name="symptom"></a>Síntoma

Un diario general incluye una entrada de reversión y una fecha de reversión en el diario. Al registrar el diario, ninguno de los asientos se revierte. ¿Por qué ocurre esto?

## <a name="resolution"></a>Resolución

Cuando se registra el diario, el proceso de reversión solo se fija en la configuración de **Entrada de reversión** y **Fecha de reversión** de la sección **Líneas** del asiento. Este enfoque permite que un diario incluya algunos asientos marcados para reversión y otros que no lo están.

Los valores del diario solo se utilizan como predeterminados al agregar *nuevas* líneas. El cambio de los valores del diario no afecta las líneas existentes. En este ejemplo, las líneas de asientos se introdujeron primero. Cuando introduzca el detalle de la línea antes de designar el diario como de reversión, la designación como entrada inversa y la fecha no se aplicará a ninguna línea existente.

El cambio de la entrada o la fecha de reversión en una línea existente propaga ese cambio a otras líneas del mismo asiento. Para optimizar el rendimiento, la cuadrícula no se actualiza después de propagar cambios a otras líneas. Puede mostrar los valores actualizados actualizando la cuadrícula.


