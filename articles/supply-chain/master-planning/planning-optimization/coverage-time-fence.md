---
title: Límites de tiempo de cobertura
description: Este tema describe cómo configurar límites de tiempo de cobertura cuando usa la Optimización de planificación. Un límite de tiempo de cobertura indica su horizonte y límite de planificación.
author: t-benebo
ms.date: 01/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2021-01-18
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 12deca22fd6ff3cb4556e0525ab831e1aea0ee33
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468927"
---
# <a name="coverage-time-fences"></a>Límites de tiempo de cobertura

[!include [banner](../../includes/banner.md)]

Este tema describe cómo configurar *límites de tiempo de cobertura* cuando usa la Optimización de planificación. Los planificadores pueden definir el horizonte de planificación (el límite de tiempo de cobertura en días) y excluir la oferta y la demanda que van más allá de ese horizonte. Por lo tanto, los límites de tiempo de cobertura ayudan a prevenir el "ruido" causado por sugerencias de suministro a las que no hace falta que reaccione durante meses. Los ejemplos incluyen el pronóstico del próximo año y los pedidos de los clientes que se realizan mucho más allá del plazo normal.

Un límite de tiempo de cobertura es el número de días después de la fecha de hoy (o, más precisamente, la fecha en la que realiza la ejecución de planificación) en los que se excluye la oferta y la demanda. Para ayudar a evitar retrasos, debe asegurarse de que el límite de tiempo de cobertura sea mayor que el plazo de entrega total. El valor predeterminado del sistema es de 100 días.

Puede especificar un límite de tiempo de cobertura en cada uno de los siguientes niveles:

- **Grupo de cobertura**: puede establecer un límite de tiempo de cobertura predeterminado para cada grupo de cobertura.
- **Cobertura de artículos**: puede reemplazar el límite de tiempo de cobertura heredado del grupo de cobertura asignado a un artículo.
- **Plan maestro**: puede reemplazar los límites de tiempo de cobertura heredados de la configuración del grupo de cobertura y artículo.

Las siguientes secciones explican cómo especificar un grupo de cobertura en cada nivel.

## <a name="set-a-coverage-time-fence-for-a-coverage-group"></a>Establecer un límite de tiempo de cobertura para un grupo de cobertura

Cuando especifica un límite de tiempo de cobertura para un grupo de cobertura, la configuración se aplica a todos los artículos (productos) que pertenecen a ese grupo. Sin embargo, puede reemplazar la configuración para artículos específicos o planes maestros específicos.

Para especificar un límite de tiempo de cobertura para un grupo de cobertura, siga estos pasos.

1. Vaya **Planificación maestra \> Configurar \> Cobertura \> Grupos de cobertura**.
1. Seleccione un grupo de cobertura en la lista o cree un nuevo grupo.
1. En la ficha desplegable **General**, establezca el campo **Límite de tiempo de cobertura (días)** al número de días que desea utilizar como límite de tiempo de cobertura para el grupo de cobertura.

## <a name="set-a-coverage-time-fence-for-a-specific-item"></a>Establecer un límite de tiempo de cobertura para un artículo específico

Cada artículo (producto) pertenece a un grupo de cobertura. Si no se asigna explícitamente ningún grupo de cobertura a un artículo, se aplicará un grupo de cobertura predeterminado. Cada artículo hereda un límite de tiempo de cobertura de su grupo de cobertura. Sin embargo, puede reemplazar este límite de tiempo para artículos específicos que necesite.

Para especificar un límite de tiempo de cobertura para un artículo específico, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione un producto en la cuadrícula.
1. En el panel Acciones, en la pestaña **Plan**, en el grupo **Cobertura**, seleccione **Cobertura de artículos**.
1. En la página **Cobertura de artículos**, en la pestaña **Visión general**, seleccione o cree una fila para el sitio donde desea establecer un límite de tiempo de cobertura.
1. Seleccione la pestaña **General** para abrir la configuración del sitio seleccionado.
1. Seleccione la casilla **Anular configuración de grupo de cobertura**.
1. Establezca el campo **Límite de tiempo de cobertura (días)** al número de días que desea utilizar como límite de tiempo de cobertura para el artículo.

## <a name="set-a-coverage-time-fence-for-a-specific-master-plan"></a>Establecer un límite de tiempo de cobertura para un plan maestro

Puede especificar un límite de tiempo de cobertura al nivel del plan maestro. De esta manera, define el número de días de cobertura del cálculo del plan maestro para un plan maestro. Esta configuración reemplaza cualquier configuración de tiempo de cobertura que se haya definido para cada artículo y grupo de cobertura relevantes.

Para especificar un límite de tiempo de cobertura para un plan maestro, siga estos pasos.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccione un plan maestro existente en la lista o cree un nuevo plan maestro.
1. En la ficha desplegable **Límites de tiempo en días**, establezca la opción **Cobertura** en *Sí*. Después, en el campo de la opción, introduzca el número de días que desea utilizar como límite de tiempo de cobertura para el artículo.

## <a name="considerations-for-coverage-time-fences"></a>Consideraciones sobre límites de tiempo de cobertura

Mientras configura límites de tiempo de cobertura, tenga en cuenta los siguientes puntos:

- Los límites de tiempo de cobertura afectan solo a los datos de entrada para la planificación maestra. Si se producen retrasos, los pedidos planificados resultantes pueden tener una fecha posterior a la fecha de hoy más el límite de tiempo de cobertura.
- Los límites de tiempo de cobertura se especifican en días de calendario. Los calendarios que utilizan días laborables no afectarán al cálculo del límite de tiempo. Por ejemplo, una semana siempre se considera siete días, incluso si los fines de semana están configurados como días no laborables en el calendario laboral.
- No se generarán transacciones de requisitos para ninguna oferta y demanda que se salga del límite de tiempo de cobertura.
- Si cualquier oferta y demanda aprobada cae fuera del límite de tiempo de cobertura, no se cargará en el motor. Por lo tanto, no activará ningún reabastecimiento y no se calcularán los retrasos. Sin embargo, esta oferta y demanda no deben eliminarse del sistema.
- Las variaciones en las cantidades de existencias de seguridad (de las claves mínimas) se ignorarán si quedan fuera del límite de tiempo de cobertura.
- La demanda entre empresas vinculadas se ignorará si la fecha de envío solicitada que se calcula no está dentro del límite de tiempo de cobertura. Tenga en cuenta que, para la planificación maestra integrada, la demanda entre empresas vinculadas no está limitada por el límite de tiempo de cobertura.
- Las previsiones de demanda se ignorarán si la fecha del presupuesto no está dentro del límite de tiempo de cobertura. Tenga en cuenta que, para la planificación maestra integrada, las previsiones de demanda no están limitada por el límite de tiempo de cobertura.
- La Optimización de la planificación tiene en cuenta la zona horaria. Tiene en cuenta la zona horaria en los sitios de oferta y demanda, y la hora de la ejecución de planificación. Por ejemplo, la planificación maestra se activa a las 11 a. m. del 15 de octubre desde un sitio en Dinamarca (zona horaria GMT+1) y se utiliza un límite de tiempo de cobertura de diez días. En este caso, la oferta y la demanda de un sitio en Seattle (zona horaria GMT-8) se incluye hasta las 2 a. m. del 25 de octubre (= diez días de 24 horas después de que se activara la planificación maestra, menos la diferencia de zona horaria de nueve horas). Tenga en cuenta que el motor de planificación maestra integrado solo tiene en cuenta la fecha del límite de tiempo. Por tanto, el resultado puede diferir.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]