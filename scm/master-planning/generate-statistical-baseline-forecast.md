---
title: "Generar una previsión estadístico de la línea de base"
description: "Este artículo proporciona información sobre los parámetros y los filtros que se usan en el cálculo de previsión de demanda."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c0c918b94fe96d123bb6c25c42fe168a026cd8a9
ms.lasthandoff: 03/31/2017


---

# <a name="generate-a-statistical-baseline-forecast"></a>Generar una previsión estadístico de la línea de base

Este artículo proporciona información sobre los parámetros y los filtros que se usan en el cálculo de previsión de demanda. 

Cuando se crea una previsión de línea base, primero debe especificar los parámetros y los filtros que se usan en el cálculo. Por ejemplo, puede crear una previsión de línea base que estime la demanda en función de los datos de transacción desde último año para una empresa específica, para el mes siguiente y para un grupo seleccionado de artículos. 

Para generar una previsión de la demanda, vaya ** la previsión &gt; de la &gt; demanda prevista de la planificación &gt; maestra genera la línea de base estadística pronosticada **. 

El cubo de previsión se puede seleccionar en el momento de generar la previsión. Los valores disponibles: Día, Semana y Mes. 

El número de depósitos para los que calcular una previsión está definido en el campo** Horizonte de previsión**. 

Cuando la estrategia de previsión se establece en **Copiar por encima de demanda histórica**, el final del horizonte histórico se ignora. El sistema copia el número de depósitos especificados en ** horizonte de previsión ** los campos a la demanda de previsión, desde el conjunto de la fecha en ** a partir de la fecha ** el campo en ** horizonte histórico **. Copiando la demanda histórica a partir de una fecha concreta, los planificadores de producción pueden realizar el plan para el siguiente trimestre de dos maneras:

-   Copiando la demanda del mismo trimestre del año anterior.
-   Copiando la demanda del mismo trimestre del trimestre anterior.

Para evitar confusiones en los planes de producción, algunos depósitos de previsión se pueden congelar. Este número se establece en en campo **Límite de tiempo congelado**. En la página **Previsión de la demanda ajustada **, las celdas para cubos congelados están desactivadas, para dar una indicación visual de que estos valores no se deben cambiar. 

La fecha inicial para la previsión de la demanda de línea basa no tiene que ser la fecha actual o una fecha en el futuro. Para establecer una fecha inicial, use el campo **Fecha de inicio de previsión de línea base: desde fecha**. Por ejemplo, en junio, los usuarios pueden generar una previsión para el año siguiente. Dado que faltan los cubos de previsión entre el final de la demanda histórica y el inicio de la línea base, puede que las predicciones no sean exactas. Si está usando el Microsoft Dynamics 365 para el servicio de previsión de demanda de operaciones, existen cuatro formas las que puede completar en espacios que falta. Puede elegir el método que desea configura el parámetro QUE FALTA de la SUBSTITUCIÓN\_del VALOR\_en ** los parámetros de la previsión de demanda ** la página. 

** La línea de base seleccione la fecha inicial ** - ** a partir de la fecha ** campo tiene que ser establecido al comienzo de un depósito de previsión, por ejemplo, en los Estados Unidos, un domingo si el depósito de previsión es la semana. El sistema ajusta automáticamente ** fecha inicial de previsión de línea base ** - ** a partir de la fecha ** campos para que coincida con el principio de un depósito de previsión. 

** La línea de base seleccione la fecha inicial ** - ** a partir de la fecha ** campo se puede establecer en una fecha en el pasado. Es decir, es posible generar una previsión de demanda en el pasado. Esto resulta útil, ya que permite a los usuarios retocar los parámetros del servicio de previsión de modo que la previsión estadística generado en el pasado coincide con la demanda histórica real. Los usuarios pueden continuar usando esta configuración de parámetros para generar una previsión estadística de línea base para el futuro. 

Los ajustes manuales realizados en iteraciones anteriores de previsión de demanda se pueden aplicar automáticamente a la nueva previsión de línea base si se activa la casilla **Transferir ajustes manuales a las previsiones de demanda**. Si la casilla está desactivada, los ajustes manuales no se agregan a la previsión de línea base, pero tampoco se eliminan. Los ajustes manuales efectuados a una previsión se pueden eliminar solo en el momento de la importación de previsión, desactivando la casilla **Guardar los ajustes manuales realizados en la previsión de la demanda de línea base**. Los ajustes manuales se guardan en el momento de la autorización. Por lo tanto, si un usuario crea los ajustes manuales a la previsión, pero no autoriza la previsión de nuevo a Dynamics 365 para las operaciones, los cambios se perderán. Para obtener más información acerca de los ajustes manuales y cómo funcionan, consulte [autorizando el pronóstico ajustado authorize-adjusted-forecast.md] (). 

Una generación de previsión de la demanda puede tener un nombre y comentarios para ayudar a los usuarios a identificar la previsión que se ha generado. Estos valores son visibles en el historial de la generación de previsión en la página **Historial estadística de la generación de previsión de línea base**. 

El grupo de planificación de empresas vinculadas, se pueden aplicar las claves de asignación de artículos y otros filtros en el momento de la generación de la previsión. Esto se pueden usar para mejorar el rendimiento o para dividir los datos en piezas manejables. Sin embargo, tenga en cuenta que no se genera una previsión de la demanda para los miembros de ninguna clave de ninguna clave de asignación de artículos que no está asociada a un grupo de planificación de empresas vinculadas, incluso si la clave de asignación de artículos se selecciona en la consulta. 

**Sugerencia**: los usuarios pueden recibir a veces mensajes de error mientras se genera una previsión de la demanda, o se completa una generación de previsión sin registro de sesión. Esto puede suceder debido a datos de excedente en la consulta usada anteriormente para la generación de previsión. Para corregir este problema, haga clic en **Seleccionar** para abrir la página **Consulta**, haga clic en **Restaurar** y vuelva a generar la previsión de línea base. 

Si la previsión no se genera para grande un conjunto de artículos, pero, por ejemplo, para un artículo o una clave de asignación de artículos al mismo tiempo, entonces para obtener mejor rendimiento, puede seleccionar ** modo de la respuesta de la solicitud de uso ** la casilla en ** planificación maestra - la configuración - previsión de demanda ** - ** parámetros de la previsión de demanda - Azure Machine Learning ** ficha.

<a name="see-also"></a>Consulte también
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)


