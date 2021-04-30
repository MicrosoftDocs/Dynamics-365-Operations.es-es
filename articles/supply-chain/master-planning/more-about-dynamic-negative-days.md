---
title: Días negativos y días negativos dinámicos
description: En este tema se proporciona información acerca de los días negativos y los días negativos dinámicos, y cómo puede utilizarlos para ayudar a su negocio.
author: t-benebo
ms.date: 06/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2019-06-07
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7440a6a0b9093664a0d717b3bfa011ee3100639f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907750"
---
# <a name="negative-days-and-dynamic-negative-days"></a>Días negativos y días negativos dinámicos

[!include [banner](../includes/banner.md)]

En este tema se proporciona información acerca de los días negativos y los días negativos dinámicos, y cómo puede utilizarlos para ayudar a su negocio. El *límite de tiempo de días negativos* representa el número de días que está dispuesto a esperar antes de que pida un nuevo reabastecimiento cuando tenga un inventario negativo.

En este tema obtendrá información acerca de lo siguiente:

- Cómo se crean pedidos planificados
- La correlación entre el límite de tiempo de días negativos y el plazo del artículo
- Cómo se calcula el límite de tiempo de días negativos dinámicos, y cómo se descompone el plazo del artículo en el cálculo
- Cómo interpretar las [sugerencias para mejorar el tiempo de ejecución para la planificación de requisitos de material (MRP) (planificación maestra)](https://blogs.msdn.com/b/axmfg/archive/2015/01/02/checklist-for-improving-mrp-performance-part-2-how-to-setup-planning-parameters.aspx) relacionadas con los días negativos

En este tema se utilizan tres escenarios hipotéticos para ayudarle a comprender esta información. La diferencia entre los escenarios es el punto en el que obtiene la demanda: antes, durante o después del plazo del artículo.

## <a name="scenario-1-you-get-demand-before-the-items-lead-time-period"></a>Escenario 1: obtiene la demanda antes del plazo del artículo

Es posible que obtenga la demanda relativamente pronto en el plazo del artículo o justo antes de que comience el plazo. A continuación se muestra un ejemplo de este escenario:

- El artículo DemoProduct tiene un plazo de compra de seis días.
- El día cero (1 de enero), el nivel de inventario para el artículo DemoProduct es 0 (cero).
- El día cero (1 de enero), obtiene un pedido de ventas para una cantidad de 10 del artículo DemoProduct.
- El día siete (7 de enero), hay un pedido de compra existente para una cantidad de 10 del artículo DemoProduct.

En la ilustración siguiente se muestra una vista gráfica de este escenario.

![Vista gráfica del escenario 1](./media/negative-days-1.jpg)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: los días negativos son menos que el plazo del artículo

Si establece los días negativos en un número que es inferior al plazo del artículo, MRP busca recepciones para el artículo DemoProduct dentro del límite de tiempo de días negativos. Puesto que no encuentra ninguna recepción, MRP crea un nuevo pedido de compra planificado. Este pedido planificado se retrasa inmediatamente seis días (el plazo). Por lo tanto, pasará al 7 de enero. El pedido de compra existente obtiene un mensaje de acción **Cancelar**, ya que la creación del nuevo pedido de compra planificado lo ha hecho redundante.

En la ilustración siguiente se muestra una captura de pantalla de este caso.

![Captura de pantalla del caso A para el escenario 1](./media/negative-days-2.png)

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre en este caso.

![Vista gráfica del caso A para el escenario 1](./media/negative-days-3.png)

Si se considera el rendimiento de MRP y se planifica el nerviosismo, este caso no funciona bien. MRP debe crear un nuevo pedido planificado, y debe calcular retrasos y acciones. Estas tareas requieren mucho tiempo. Este caso también agrega dos transacciones más a su plan. Por otro lado, el pedido de ventas solo se retrasa seis días, no siete.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: los días negativos son más que el plazo del artículo

Para ayudar a mejorar el rendimiento de MRP, puede establecer los días negativos en un número que sea mayor que el plazo del artículo. Puesto que no puede obtener el suministro dentro del plazo en este escenario, puede buscar recepciones mientras esta búsqueda tenga sentido. Aunque el tiempo de ejecución para MRP sea más corto, debe estar atento a los retrasos adicionales en los pedidos.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Caso C: correlacionar automáticamente el plazo del artículo con el límite de tiempo de días negativos

Para correlacionar automáticamente el plazo del artículo con el límite de tiempo de días negativos, utilice días negativos dinámicos. Para usar días negativos dinámicos, vaya a **Planificación maestra \> Configuración \> Parámetros de planificación maestra** y, a continuación, en la pestaña **General**, en la sección **Cobertura**, establezca la opción **Utilizar días negativos dinámicos** en **Sí**. Posteriormente, MRP busca recepciones dentro del límite de tiempo de días negativos dinámicos. Este límite de tiempo se calcula mediante la fórmula siguiente:

Límite de tiempo de días negativos dinámicos = Plazo de compra + Límite de tiempo de días negativos (+ Fecha actual – Fecha de requisito)

(Si el tipo de pedido predeterminado del artículo DemoProduct es **Producción** o **Transferencia**, el plazo es el plazo de **inventario**.)

Cuando se utilizan días negativos dinámicos, el límite de tiempo que MRP busca para las recepciones es ahora 6 + 2 + 0 = 8 días. MRP encuentra el pedido de compra existente y fija el pedido de ventas en este. No se crean nuevos pedidos planificados. Por lo tanto, el tiempo de ejecución para MRP es más corto. En la ilustración siguiente se muestran los requisitos netos para el artículo DemoProduct.

![Requisitos netos del caso C para el escenario 1](./media/negative-days-4.png)

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre en este caso.

![Vista gráfica del caso C para el escenario 1](./media/negative-days-5.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: utilizar solo días negativos dinámicos

Si establece los días negativos en **0** (cero) y utiliza solo el límite de tiempo de días negativos dinámicos, el límite de tiempo de días negativos dinámicos es 6 + 0 + 0 = 6 días. En este caso, el resultado es el mismo que el resultado del caso A para este escenario. MRP debe crear un nuevo pedido planificado, y debe calcular retrasos y acciones. Estas tareas requieren mucho tiempo y también pueden ser frustrantes. También tiene dos transacciones más para procesar. Puesto que la demanda no se puede cumplir a tiempo para que el artículo llegue, este caso agrega complicaciones innecesarias a su plan.

En la ilustración siguiente se muestra una captura de pantalla para este caso.

![Captura de pantalla del caso D para el escenario 1](./media/negative-days-6.png)

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre en este caso.

![Vista gráfica del caso D para el escenario 1](./media/negative-days-7.png)

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: utilizar tanto los días negativos mayores que el plazo del artículo como el límite de tiempo de días negativos dinámicos

Si establece los días negativos en un número mayor que el plazo del artículo, y si también puede utilizar el límite de tiempo de días negativos dinámicos, el límite de tiempo de días negativos dinámicos es 6 + 6 + 0 = 12 días. Este enfoque puede producir un límite de tiempo muy largo en el que MRP debe buscar resultados. Para obtener más información acerca de cómo el caso E se relaciona con una situación en la que establece los días negativos en un límite de tiempo largo, consulte la sección [Conclusión](#conclusion) de este tema.

## <a name="scenario-2-you-get-demand-during-the-items-lead-time-period"></a>Escenario 2: obtiene la demanda durante el plazo del artículo

Es posible que obtenga demanda alguna vez durante el plazo de su artículo. A continuación se muestra un ejemplo de este escenario:

- El artículo DemoProduct tiene un plazo de compra de seis días. 
- El día cero (1 de enero), el nivel de inventario para el artículo DemoProduct es 0 (cero).
- El día cuatro (5 de enero), que se encuentra dentro del plazo del artículo, obtiene un pedido de ventas para una cantidad de 10 del artículo DemoProduct.
- El día siete (8 de enero), hay un pedido de compra para una cantidad de 10 del artículo DemoProduct.

En la ilustración siguiente se muestra una vista gráfica de este escenario.

![Vista gráfica del escenario 1](./media/negative-days-8.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: los días negativos son menos que el plazo del artículo

Si establece los días negativos en un número que es inferior al plazo del artículo, MRP busca recepciones para el artículo DemoProduct dentro del límite de tiempo de días negativos. Puesto que no se encuentra ninguna recepción, MRP crea un nuevo pedido de compra planificado que utiliza la fecha actual como la fecha del pedido. Este pedido planificado se retrasa inmediatamente seis días (el plazo). Por lo tanto, pasará al 7 de enero. El pedido de compra existente obtiene un mensaje de acción **Cancelar**, ya que la creación del nuevo pedido de compra planificado lo ha hecho redundante.

En la ilustración siguiente se muestra una captura de pantalla para este caso.

![Captura de pantalla del caso A para el escenario 2](./media/negative-days-9.png)

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre en este caso.

![Vista gráfica del caso A para el escenario 2](./media/negative-days-10.png)

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: los días negativos son más que el plazo del artículo

Este caso es similar al caso B para el escenario 1. Si establece los días negativos en un número mayor que el plazo del artículo, no obtiene un nuevo pedido planificado. El pedido de ventas está vinculado al pedido de compra existente.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Caso C: correlacionar automáticamente el plazo del artículo con el límite de tiempo de días negativos

Este caso se asemeja al caso C para el escenario 1, ya que los días negativos dinámicos funcionan del mismo modo que en ese caso. El límite de tiempo de días negativos dinámicos es ahora 6 + 2 – 4 = 4 días. Si utiliza este enfoque, MRP encuentra el pedido de compra existente y lo vincula al pedido de ventas. Puesto que no se crea nuevos pedidos planificados, el tiempo de ejecución para MRP es inferior.

En la ilustración siguiente se muestra una captura de pantalla de este caso.

![Captura de pantalla del caso C para el escenario 2](./media/negative-days-11.png)

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre en este caso.

![Vista gráfica del caso C para el escenario 2](./media/negative-days-12.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: utilizar solo días negativos dinámicos

Si establece los días negativos en **0** (cero) y utiliza solo el límite de tiempo de días negativos dinámicos, el límite de tiempo de días negativos dinámicos es ahora 6 + 0 – 4 = 2 días. En este caso, el resultado es el mismo que el resultado del caso A para este escenario. Para ver una vista gráfica de lo que ocurre, consulte el caso A para este escenario.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: utilizar tanto los días negativos mayores que el plazo del artículo como el límite de tiempo de días negativos dinámicos

Si establece los días negativos en un número mayor que el plazo del artículo, y si también puede utilizar el límite de tiempo de días negativos dinámicos, el límite de tiempo de días negativos dinámicos es 6 + 6 – 4 = 8 días. Este enfoque puede producir un límite de tiempo muy largo en el que MRP debe buscar resultados. Para obtener más información acerca de cómo el caso E se relaciona con una situación en la que establece los días negativos en un límite de tiempo largo, consulte la sección [Conclusión](#conclusion) de este tema.

## <a name="scenario-3-you-get-demand-after-the-items-lead-time-period"></a>Escenario 3: obtiene la demanda después del plazo del artículo

Puede que obtenga la demanda después del plazo del artículo. A continuación se muestra un ejemplo de este escenario:

- El artículo DemoProduct tiene un plazo de compra de seis días.
- El día cero (1 de enero), el inventario para el artículo DemoProduct es 0 (cero).
- El día siete (8 de enero), que se encuentra fuera del plazo del artículo, obtiene un pedido de ventas para una cantidad de 10 del artículo DemoProduct.
- El día 10 (11 de enero), hay un pedido de compra para una cantidad de 10 del artículo DemoProduct.

En la ilustración siguiente se muestra una vista gráfica de este escenario.

![Vista gráfica del escenario 3](./media/negative-days-13.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: los días negativos son menos que el plazo del artículo

Si establece los días negativos en un número inferior al plazo del artículo, MRP busca dos días antes de la fecha de requisito del pedido de ventas. Puesto que no encuentra nada, MRP crea un pedido de compra planificado el 2 de enero. Este pedido de compra planificado se enviará justo a tiempo para satisfacer la demanda del pedido de ventas. El pedido de compra existente obtiene un mensaje de acción **Cancelar**, puesto que no se requiere.

En la ilustración siguiente se muestra una captura de pantalla de este caso.

![Captura de pantalla del caso A para el escenario 3](./media/negative-days-14.png)

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre en este caso.

![Vista gráfica del caso A para el escenario 3](./media/negative-days-15.png)

> [!NOTE]
> En el captura de pantalla anterior, la fecha de requisito del pedido de compra es el 12 de enero. Puesto que la captura de pantalla se tomó en 2015, cuando el 11 de enero era domingo, MRP movió la fecha de requisito al siguiente día laborable, que era lunes 12 de enero. Sin embargo, el pedido de compra tiene una fecha de entrega de 11 de enero.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: los días negativos son más que el plazo del artículo

Si establece los días negativos en un número mayor que el plazo del artículo, no obtiene un nuevo pedido planificado. El pedido de ventas se fija al pedido de compra existente. Por tanto, se retrasa el pedido de ventas. Si crea un pedido planificado, puede enviar el pedido de ventas a tiempo.

En la ilustración siguiente se muestra una captura de pantalla de este caso.

![Captura de pantalla del caso B para el escenario 3](./media/negative-days-16.png)

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre en este caso.

![Vista gráfica del caso B para el escenario 3](./media/negative-days-17.png)

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Caso C: correlacionar automáticamente el plazo del artículo con el límite de tiempo de días negativos

Este caso se asemeja al caso C para el escenario 1, ya que los días negativos dinámicos funcionan del mismo modo, si no mejor, en el caso B para este escenario.

El límite de tiempo de días negativos dinámicos es ahora 6 + 2 – 7 = 1 día. Sin embargo, en este caso, el sistema aún considera el plazo de días negativos (2), ya que MRP considera el valor máximo entre el plazo de días negativos y el plazo de días negativos dinámicos. Por lo tanto, el resultado de este caso es el mismo que el resultado del caso A para este escenario.

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre en este caso.

![Vista gráfica del caso C para el escenario 3](./media/negative-days-18.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: utilizar solo días negativos dinámicos

Si establece los días negativos en **0** (cero) y utiliza solo el límite de tiempo de días negativos dinámicos, el límite de tiempo de días negativos dinámicos es ahora 6 + 0 – 7 = -1 día. En este caso, el sistema aún considera el plazo de días negativos (2). Por lo tanto, el resultado de este caso es el mismo que el resultado del caso A para este escenario y tiene las mismas desventajas. Para ver una vista gráfica de lo que ocurre, consulte el caso A para el escenario 2.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: utilizar tanto los días negativos mayores que el plazo del artículo como el límite de tiempo de días negativos dinámicos

Este caso es el mismo que el caso E para los escenarios 1 y 2. Tiene básicamente las mismas ventajas y desventajas.

## <a name="conclusion"></a>Conclusión

Como muestran los tres escenarios de este tema, una buena idea es establecer los días negativos en un número que sea mayor que el plazo de los artículos del grupo de cobertura. También se recomienda usar solamente días negativos dinámicos, y establecer los días negativos en el número de días que está dispuesto a esperar antes de pedir un nuevo reabastecimiento cuando tenga inventario negativo (es decir, el número de días que está dispuesto a retrasar más la demanda). Además, los artículos en el mismo grupo de cobertura deben tener plazos similares.

Si establece los días negativos en **0** (cero) y no utiliza días negativos dinámicos, MRP crea siempre un nuevo pedido planificado para satisfacer la demanda. En esta situación, es importante que trabaje con los mensajes de acción para asegurarse de que no se acumula el inventario.

Es posible que desee establecer los días negativos en un límite de tiempo mayor y, seguidamente, trabajar con mensajes de acción. Este enfoque produce buenos resultados de planificación, aunque también es un poco más lento. Puede que también sea difícil de analizar, ya que debe analizar y aplicar los mensajes de acción. Este es un ejemplo:

- El artículo DemoProduct tiene un plazo de compra de seis días.
- El día cero (1 de enero), el inventario para el artículo DemoProduct es 0 (cero).
- El día cero (1 de enero), obtiene un pedido de ventas para una cantidad de 10 del artículo DemoProduct.
- El día 10 (10 de enero), obtiene un pedido de ventas para una cantidad de 10 del artículo DemoProduct.
- El día 12 (12 de enero), hay un pedido de compra para una cantidad de 10 del artículo DemoProduct.
- Los días negativos se establecen en **20**, que es mucho más que el plazo del artículo.

En la ilustración siguiente se muestra una vista gráfica de lo que ocurre.

![Revisión gráfica del ejemplo](./media/negative-days-19.png)

MRP produce los siguientes resultados.

![Resultados](./media/negative-days-20.png)

En el captura de pantalla anterior, la fecha de requisito del pedido de ventas es el 9 de enero, en lugar del 10 de enero. Puesto que la captura de pantalla se tomó en 2015, cuando el 10 de enero era sábado, la fecha de requisito del pedido debería ser el día laborable anterior, que era viernes 9 de enero.

MRP crea un pedido de compra planificado para satisfacer la demanda solicitada por el primer pedido de ventas, pero también recomienda que cancele el pedido planificado, ya que puede avanzar el pedido de compra existente y aumentar la cantidad en este.

Los resultados no son incorrectos, pero el tiempo de ejecución para MRP puede ser superior, ya que MRP debe crear todos los retrasos y sugerencias. Además, el planificador puede requerir más tiempo para entender los resultados de MRP. Lo que es más importante, en este caso, es fundamental que el planificador entienda y utilice los mensajes de acción.

Si reduce los días negativos a un número que es más cercano al plazo del artículo, y utiliza días negativos dinámicos, MRP produce los siguientes resultados.

![Resultados](./media/negative-days-21.png)

MRP crea un pedido planificado que se vincula al primer pedido de ventas. A continuación, como se espera, el segundo pedido de ventas se fija al pedido de compra existente, según la configuración de días negativos. Este resultado de planificación también es correcto, y el tiempo de ejecución para MRP puede ser más breve. En este caso, no es fundamental que entienda y sepa cómo trabajar con los mensajes de acción.

Para ayudar a garantizar que se introducen los valores correctos para su negocio, debe pensar en los términos de funcionalidad y tiempo de ejecución de MRP. Por lo tanto, puede realizar un pequeño proceso de prueba y error para determinar los valores óptimos.

## <a name="see-also"></a>Consulte también

Para una mayor discusión, consulte la entrada de blog original [Más acerca de los días negativos (dinámicos)](/archive/blogs/axmfg/more-about-dynamic-negative-days) original del blog.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]