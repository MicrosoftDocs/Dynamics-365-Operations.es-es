---
title: Las dimensiones financieras y cuentas principales en un idioma de derecha a izquierda
description: "Este tema describe algunas de las decisiones de implementación que debe tener en cuenta cuando use un idioma de derecha a izquierda en Microsoft Dynamics 365 for Operations, y debe configurar las dimensiones financieras y las cuentas principales."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0a2fcbbc91960e0602f42d89ca5e46b8d51f98d6
ms.openlocfilehash: da5c53ddf113daf19a9832cf59f7a231a00b3367
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions-and-main-accounts-in-a-right-to-left-language"></a>Las dimensiones financieras y cuentas principales en un idioma de derecha a izquierda

[!include[banner](../includes/banner.md)]


Este tema describe algunas de las decisiones de implementación que debe tener en cuenta cuando use un idioma de derecha a izquierda en Microsoft Dynamics 365 for Operations, y debe configurar las dimensiones financieras y las cuentas principales.

Las dimensiones financieras y las cuentas principales son componentes clave de la fase de planificación para una implementación. Después de crear las dimensiones financieras y cuentas principales en el sistema, se usan en las páginas de **Configuración de estructuras contables**, de **Estructuras de reglas avanzadas**, y de **Configuración de dimensión financiera para las aplicaciones de integración**. El orden que se define en dichas páginas se utiliza en el sistema para la entrada y el consumo de datos. En algunas partes del sistema, las dimensiones financieras y las cuentas principales aparecen en campos diferentes. Sin embargo, en otros lugares, como los diarios, las dimensiones financieras y las cuentas principales aparecen como una sola cadena.

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Prácticas recomendadas para configurar dimensiones financieras y cuentas principales en un sistema de derecha a izquierda

-   Al seleccionar el delimitador para los planes contables, seleccione una de las opciones de delimitador doble: guión doble (--), barra doble (||), dos puntos (..) o doble subrayado (\_\_).
-   Al crear los valores de la dimensión financiera y de la cuenta principal, utilice solo números y caracteres de idioma de derecha a izquierda.
-   Evite el uso del delimitador del plan contable seleccionado en los valores de la dimensión financiera y de la cuenta principal.

Siguiendo estas prácticas recomendadas, ayuda a garantizar la representación coherente del orden definido por el usuario en el sistema.




