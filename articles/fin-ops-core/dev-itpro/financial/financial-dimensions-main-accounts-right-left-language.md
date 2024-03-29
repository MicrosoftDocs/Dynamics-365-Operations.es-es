---
title: Dimensiones financieras y cuentas principales en idiomas de derecha a izquierda
description: Este artículo describe las decisiones que debe realizar cuando use un idioma de derecha a izquierda y debe configurar las dimensiones financieras y las cuentas principales.
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b1e2c0ef5cd405232332847078c70af42f056e17
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8866771"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>Dimensiones financieras y cuentas principales en idiomas de derecha a izquierda

[!include [banner](../includes/banner.md)]

Este artículo describe algunas de las decisiones de implementación que debe tener en cuenta cuando use un idioma de derecha a izquierda y debe configurar las dimensiones financieras y las cuentas principales.

Las dimensiones financieras y las cuentas principales son componentes clave de la fase de planificación para una implementación. Después de crear las dimensiones financieras y cuentas principales en el sistema, se usan en las páginas de **Configuración de estructuras contables**, de **Estructuras de reglas avanzadas**, y de **Configuración de dimensión financiera para las aplicaciones de integración**. El orden que se define en dichas páginas se utiliza en el sistema para la entrada y el consumo de datos. En algunas partes del sistema, las dimensiones financieras y las cuentas principales aparecen en campos diferentes. En otros lugares, como los diarios, las dimensiones financieras y las cuentas principales aparecen como una sola cadena.

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Prácticas recomendadas para configurar dimensiones financieras y cuentas principales en un sistema de derecha a izquierda

- Al seleccionar el delimitador para los planes contables, seleccione una de las opciones de delimitador doble: guion doble (`--`), barra doble (`||`), dos puntos (`..`) o doble subrayado (`\\`).
- Al crear los valores de la dimensión financiera y de la cuenta principal, utilice solo números y caracteres de idioma de derecha a izquierda.
- Evite el uso del delimitador del plan contable seleccionado en los valores de la dimensión financiera y de la cuenta principal.

Siguiendo estas prácticas recomendadas, ayuda a garantizar la representación coherente del orden definido por el usuario en el sistema.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
