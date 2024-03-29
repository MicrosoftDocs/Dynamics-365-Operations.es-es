---
title: Autorizar previsión de la demanda ajustada
description: No todos los datos de previsión se deben autorizar inmediatamente. Este artículo se explica cómo puede especificar el período para el que una previsión está autorizada. También explica cómo puede autorizar la previsión para empresas y modelos de previsión específicos.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4954b70e56482e419d81485b544cb5d0b4e4a3ce
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740721"
---
# <a name="authorize-an-adjusted-forecast"></a>Autorizar previsión de la demanda ajustada

[!include [banner](../includes/banner.md)]

No todos los datos de previsión se deben autorizar inmediatamente. Este artículo se explica cómo puede especificar el período para el que una previsión está autorizada. También explica cómo puede autorizar la previsión para empresas y modelos de previsión específicos.

No todos los datos de previsión se deben autorizar inmediatamente. Puede especificar las fechas de inicio y fin del período para el que la previsión está autorizada. Esta función le permite congelar los cubos específicos. 

Las fechas de inicio y fin que especifique deben corresponder a las fechas de inicio y fin del depósito en que se genera la previsión. El sistema aplica esta restricción y ajusta automáticamente las fechas, si se requiere el ajuste. 

En la pestaña **Detalles** de la página **Autorización**, puede ver los detalles acerca de la previsión que se generó recientemente. 

Puede seleccionar las empresas y los modelos de previsión para autorizar la programación para el uso. De forma predeterminada, la cuadrícula incluye a todas las empresas para la que la demanda prevista se ha creado. Para cada empresa, se rellena previamente el modelo de previsión que corresponde al plan de previsión actual que está configurado en los parámetros de planificación maestra. Sin embargo, puede cambiar este modelo de previsión a cualquier modelo de previsión que pertenezca a dicha empresa. Si no se han generado datos de la demanda prevista para una empresa seleccionada, recibirá un mensaje de advertencia en el momento de la importación. 

Es muy importante que entienda cómo funciona la casilla **Guardar los ajustes manuales realizados en la previsión de la demanda de la línea base**. Si ha realizado ajustes manuales a la previsión estadística de línea base, los valores ajustados están autorizados para su uso, incluso si esta casilla está desactivada. Sin embargo, los cambios se descartan después de la autorización. Por lo tanto, la próxima vez que se genera una previsión, esa previsión solo es una previsión estadística y no tiene invalidación manual, incluso si selecciona **Transferir ajustes manuales a la previsión de la demanda**. Por lo tanto, puede considerar la casilla **Guardar los ajustes manuales realizados en la previsión de la demanda de la línea base** un mecanismo que le permite conservar o descartar todos los cambios manuales.

## <a name="additional-resources"></a>Recursos adicionales

- [Realización de ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md)
- [Supervisión de la precisión de previsión](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]