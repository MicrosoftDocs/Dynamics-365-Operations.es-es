---
title: Configurar parámetros para la automatización del proceso de cobro
description: Este tema describe los parámetros que afectan los procesos de cobro automatizados y proporciona una guía para configurarlos de modo que el proceso automatizado refleje sus intenciones y expectativas.
author: JodiChristiansen
ms.date: 08/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3055e10375f1b0be936e3ed0344cdf33dc7bc7e9
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "7487083"
---
# <a name="configure-parameters-for-collection-process-automation"></a>Configurar parámetros para la automatización del proceso de cobro

[!include [banner](../includes/banner.md)]

Este tema describe los parámetros que afectan los procesos de cobro automatizados y proporciona una guía para configurarlos de modo que el proceso automatizado refleje sus intenciones y expectativas. Para obtener información sobre cómo automatizar los procesos de cobro, consulte [Automatización del proceso de cobro](collections-process-automate.md).

## <a name="general"></a>General
Ingrese un número en el **Porcentaje de clientes por tarea por lotes** para determinar el número de tareas por lotes por proceso de automatización. Configure **Registrar cartas de cobro automáticamente** en **Sí**, de forma que el tipo de acción registre la carta de cobro durante la automatización. Establezca **Crear actividades para automatizaciones** en **Sí** para crear y cerrar actividades para tipos de acciones que no son actividades para ver todos los pasos automatizados tomados en una cuenta. Defina el número de días que el historial de cobros se almacena en el **Días en que se debe mantener el historial de automatización del proceso de cobro**. Cuando una factura llega al último paso del proceso de cobro, no se utilizará para crear tipos de acciones de automatización de procesos futuros si **Excluir factura después de activar el último paso del proceso** se establece en **Sí**. La siguiente factura más antigua determina el siguiente paso de automatización del proceso, para garantizar que continúen las acciones de automatización del proceso de cobro. 

## <a name="payment-predictions"></a>Previsiones de pago
A partir de la versión 10.0.21, las predicciones de pago de clientes, que se encuentran en Finance insights, proyectan si una factura se pagará puntualmente, tarde o muy tarde. Puede configurar cada una de esas categorías en Finance insights. Si se prevé que las facturas se pagarán tarde, es importante comenzar el proceso de cobros antes de que venza la factura. Esas predicciones se pueden utilizar para crear actividades de cobros cuando se ejecutan automatizaciones de procesos de cobro. Establezca **Habilitar predicciones de pago** en **Sí** para utilizar las predicciones de pago de los clientes para crear actividades de cobro basadas en la probabilidad de que la factura se pague tarde. 

Para obtener más información sobre las predicciones de pago de los clientes y Finance insights, consulte [Predicciones de pagos de clientes](payment-insights-overview.md).

Cuando se ejecuta el modelo de predicciones de pago del cliente, este asigna un porcentaje a la predicción de que la factura se pague puntualmente, tarde o muy tarde. Puede utilizar esa información para iniciar automáticamente las actividades de cobro mediante la automatización del proceso de cobro en los casos en los que se espera un pago tardío. Puede ver estos porcentajes en las páginas **Predicciones de pago por cliente** o **Predicciones de pago por transacción**, en **Créditos y cobros > Cobros**. 

Si la predicción de pago promedio para una factura de cliente es menor que el porcentaje de referencia, no se crea ninguna actividad. Si la predicción de la factura es mayor o igual que el porcentaje de referencia, se crea una actividad por cliente. Para **Predicción: tarde**, introduzca el **Porcentaje de referencia** de cuándo la automatización del proceso de cobro debe crear actividades de cobro. Este es un valor agregado tanto para tarde como para muy tarde. Seleccione una **Plantilla de documento empresarial** para utilizarla para la actividad creada o crear una nueva. Esto identifica el **Tipo**, el **Objetivo** y los **Días hasta el cierre de la actividad**. Ingrese cualquier **Nota** que será la descripción predeterminada cuando se cree la actividad. Para **Predicción: muy tarde**, introduzca el **Porcentaje de referencia** de cuándo la automatización del proceso de cobro debe crear actividades de cobro para un cliente que se espera que pague sus facturas muy tarde. Seleccione una **Plantilla de documento empresarial** para utilizarla para la actividad creada. Esto identifica el **Tipo**, el **Objetivo** y los **Días hasta el cierre de la actividad**. Ingrese cualquier **Nota** que será la descripción predeterminada cuando se cree la actividad. 

### <a name="example"></a>Ejemplo
Si el porcentaje de referencia tardío se establece en el 60 %. Cuando se ejecuta el modelo de predicciones de pago del cliente para cada factura, el sistema asigna un porcentaje a la predicción de que la factura se pague puntualmente, tarde o muy tarde. Si la predicción de pago de que la factura se pagará con retraso es del 59 % o menos, el proceso de cobro automatizado no creará ninguna actividad de cobro para la factura. Si la predicción de pago del cliente para una factura es mayor o igual al 60 %, entonces se crea una actividad de cobro durante la automatización del proceso de cobro. 

> [!NOTE]
> La predicción de muy tardía se evalúa antes que la predicción de tardía porque las muy tardías incluyen las facturas que se prevé que se pagarán tarde. El proceso de cobro solo genera una actividad si la factura cae entre los puntos de referencia de tarde y muy tarde. En ese caso, el sistema utiliza la actividad de muy tarde y el documento empresarial, ya que las de muy tarde reciben mayor prioridad. Cualquier otra acción que ya se haya generado no se generará por segunda vez.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
