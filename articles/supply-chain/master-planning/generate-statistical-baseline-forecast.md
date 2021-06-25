---
title: Generar previsión estadística de línea base
description: En este tema se proporciona información sobre los parámetros y los filtros que se usan en el cálculo de previsión de demanda.
author: roxanadiaconu
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 780d1e1307b69ec9a31d032039970de454160d6f
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189701"
---
# <a name="generate-a-statistical-baseline-forecast"></a>Generar previsión estadística de línea base

[!include [banner](../includes/banner.md)]

En este tema se proporciona información sobre los parámetros y los filtros que se usan en el cálculo de previsión de demanda. 

Cuando se crea una previsión de línea base, primero debe especificar los parámetros y los filtros que se usan en el cálculo. Por ejemplo, puede crear una previsión de línea base que estime la demanda en función de los datos de transacción desde último año para una empresa específica, para el mes siguiente y para un grupo seleccionado de artículos. 

Para generar una previsión de demanda, vaya a **Planificación maestra &gt; Previsión &gt; Previsión de demanda &gt; Generar previsión estadística de línea base**. 

El cubo de previsión se puede seleccionar en el momento de generar la previsión. Los valores disponibles: Día, Semana y Mes. 

El número de depósitos para los que calcular una previsión está definido en el campo **Horizonte de previsión**. 

Cuando la estrategia de previsión se establece en **Copiar por encima de demanda histórica**, el final del horizonte histórico se ignora. El sistema copia el número de depósitos especificado en el campo **Horizonte de previsión** en la demanda planificada, comenzando desde la fecha establecida en el campo **Desde la fecha** en **Horizonte histórico**. Copiando la demanda histórica a partir de una fecha concreta, los planificadores de producción pueden realizar el plan para el siguiente trimestre de dos maneras:

-   Copiando la demanda del mismo trimestre del año anterior.
-   Copiando la demanda del mismo trimestre del trimestre anterior.

Para evitar confusiones en los planes de producción, algunos depósitos de previsión se pueden congelar. Este número se establece en en campo **Límite de tiempo congelado**. En la página **Previsión de la demanda ajustada**, las celdas para cubos congelados están desactivadas, para dar una indicación visual de que estos valores no se deben cambiar. 

La fecha inicial para la previsión de la demanda de línea basa no tiene que ser la fecha actual o una fecha en el futuro. Para establecer una fecha inicial, use el campo **Fecha de inicio de previsión de línea base: desde fecha**. Por ejemplo, en junio, los usuarios pueden generar una previsión para el año siguiente. Dado que faltan los cubos de previsión entre el final de la demanda histórica y el inicio de la línea base, puede que las predicciones no sean exactas. Si está usando el servicio de previsión de demanda, existen cuatro maneras en las que puede completar los espacios que faltan. Puede elegir el método que desee si configura el parámetro MISSING\_VALUE\_SUBSTITUTION en la página **Parámetros de previsión de demanda**. 

> [!NOTE]
> La sustitución de valores que falta solo funciona para los espacios en datos entre las fechas de inicio y fin para los datos históricos. No rellenará los datos antes o después del último punto de datos físico, solo actúa como extrapolación entre los puntos de datos reales existentes. 

El campo **Fecha inicial de la previsión de línea base** - **Desde la fecha** tiene que estar establecido al principio de un cubo de previsión, por ejemplo, en Estados Unidos, un domingo si el cubo de previsión es la semana. El sistema ajusta automáticamente el campo **Fecha inicial de la previsión de línea base** - **Desde la fecha** para que coincida con el inicio de un cubo de previsión. 

El campo **Fecha de inicio de previsión de línea base** - **Desde la fecha** puede establecerse en una fecha del pasado. Es decir, es posible generar una previsión de demanda en el pasado. Esto resulta útil, ya que permite a los usuarios ajustar los parámetros del servicio de previsión de modo que la previsión estadística generado en el pasado coincide con la demanda histórica real. Los usuarios pueden continuar usando esta configuración de parámetros para generar una previsión estadística de línea base para el futuro. 

Los ajustes manuales realizados en iteraciones anteriores de previsión de demanda se pueden aplicar automáticamente a la nueva previsión de línea base si se activa la casilla **Transferir ajustes manuales a las previsiones de demanda**. Si la casilla está desactivada, los ajustes manuales no se agregan a la previsión de línea base, pero tampoco se eliminan. Los ajustes manuales efectuados a una previsión se pueden eliminar solo en el momento de la importación de previsión, desactivando la casilla **Guardar los ajustes manuales realizados en la previsión de la demanda de línea base**. Los ajustes manuales se guardan en el momento de la autorización. Por lo tanto, si un usuario realiza ajustes manuales a la previsión, pero no autoriza la previsión de nuevo a Supply Chain Management, los cambios se perderán. Para obtener más información acerca de los ajustes manuales y cómo funcionan, consulte [Autorizar una previsión ajustada](authorize-adjusted-forecast.md). 

Una generación de previsión de la demanda puede tener un nombre y comentarios para ayudar a los usuarios a identificar la previsión que se ha generado. Estos valores son visibles en el historial de la generación de previsión en la página **Historial estadística de la generación de previsión de línea base**. 

El grupo de planificación de empresas vinculadas, se pueden aplicar las claves de asignación de artículos y otros filtros en el momento de la generación de la previsión. Esto se pueden usar para mejorar el rendimiento o para dividir los datos en piezas manejables. Sin embargo, tenga en cuenta que no se genera una previsión de la demanda para los miembros de ninguna clave de ninguna clave de asignación de artículos que no está asociada a un grupo de planificación de empresas vinculadas, incluso si la clave de asignación de artículos se selecciona en la consulta. 

> [!TIP]
> Los usuarios pueden recibir a veces mensajes de error mientras se genera una previsión de la demanda, o se completa una generación de previsión sin registro de sesión. Esto puede suceder debido a datos de excedente en la consulta usada anteriormente para la generación de previsión. Para resolver este problema, haga clic en **Seleccionar** para abrir la página **Consulta**, seleccione **Restaurar** y vuelva a generar la previsión de línea base. 

Si la previsión no se genera para un conjunto grande de artículos, sino, por ejemplo, para un artículo o una clave de asignación de artículos a la vez, para obtener un mejor rendimiento, puede activar la casilla **Usar modo de respuesta de la solicitud** en la pestaña **Planificación maestra - configuración - previsión de demanda** - **Parámetros de previsión de demanda - Aprendizaje de Azure Machine**.

> [!NOTE]
> Una previsón potencialmente plana puede deberse a que los datos históricos tienen que ser de un período de tiempo histórico más largo (un mínimo de 3 períodos de tiempo para escoger patrones, como 3 años con previsión mensual). Para obtener un mejor resultado, pruebe a cambiar la granularidad del intervalo temporal o a aumentar el intervalo temporal.

## <a name="additional-resources"></a>Recursos adicionales

- [Configuración de previsión de demanda](demand-forecasting-setup.md)

- [Realización de ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md)

- [Autorizar previsión de la demanda ajustada](authorize-adjusted-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]