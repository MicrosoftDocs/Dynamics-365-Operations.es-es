---
title: Planificación de producción
description: Este artículo describe la planificación de la producción y explica cómo modificar los pedidos de producción planificados mediante Optimización de planificación.
author: t-benebo
ms.date: 06/01/2021
ms.topic: article
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 151aa3688c570ea6ec282c297ed18288dd886131
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873793"
---
# <a name="production-planning"></a>Planificación de producción

[!include [banner](../../includes/banner.md)]

Optimización de planificación admite varios escenarios de producción. Si está migrando desde el motor de planificación maestro integrado existente, es importante estar al tanto de algunos cambios de comportamiento.

El siguiente video ofrece una breve introducción a algunos de los conceptos discutidos en este artículo: [Dynamics 365 Supply Chain Management: mejoras en la optimización de la planificación](https://youtu.be/u1pcmZuZBTw).

## <a name="turn-on-this-feature-for-your-system"></a>Activar esta función para su sistema

Si su sistema aún no incluye las funciones descritas en este artículo, vaya a [Gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la característica *Pedidos de producción planificados para Planning Optimization*.

## <a name="planned-production-orders"></a>Pedidos de producción planificados

Cuando la planificación maestra crea pedidos planificados para cumplir con los requisitos, el tipo de pedido se determina por el valor del campo **Tipo de pedido planificado**. Si el campo **Tipo de pedido planificado** está configurado en *Producción*, se crean los pedidos de producción planificados. Estos pedidos de producción planificados incluyen información sobre la lista de materiales (L.MAT) activa y el ID de ruta de la configuración de producción relacionada.

## <a name="requirements-from-boms"></a>Requisitos de listas de materiales

La información de la lista de materiales se respeta durante la planificación maestra. La salida del plan incluye el suministro de material para cubrir la demanda de material relacionado para la producción.

Durante la planificación maestra, la lista de materiales activa actual se utiliza para determinar los materiales necesarios para la producción. Este paso se realiza en todos los niveles de la estructura de la lista de materiales relacionada con el pedido de producción requerido. Los requisitos de material se cumplen mediante el uso del inventario disponible disponible, el suministro existente bajo pedido y los pedidos planificados aprobados. Si se requiere material adicional en algún lugar, se crea un pedido planificado para cubrir la demanda.

## <a name="scheduling-during-firming"></a>Programación durante la puesta en firme

Los pedidos de producción planificados incluyen el ID de ruta que se requiere para la programación de producción. Sin embargo, el soporte de programación durante el proceso de planificación para pedidos previsionales está pendiente. El ID de ruta se utiliza para programar pedidos de producción planificados durante la puesta en firme. Por lo tanto, el tiempo de entrega de los pedidos de producción planificados puede diferir del tiempo de entrega de los pedidos de producción programados y puestos en firme relacionados que se generan a partir de ellos, como se describe aquí:

- **Pedido de producción planificado** - El tiempo de entrega se basa en el tiempo de entrega estático del producto liberado.
- **Pedido de producción de puesta en firme** - El tiempo de espera se basa en la programación que utiliza la información de la ruta y las limitaciones de recursos relacionadas.

Para obtener más información sobre la disponibilidad esperada de las funciones, consulte [Análisis de ajuste de optimización de planificación](planning-optimization-fit-analysis.md).

Si depende de la funcionalidad de producción que aún no está disponible para Optimización de la planificación, puede continuar utilizando el motor de planificación maestro integrado. No se requiere ninguna excepción.

## <a name="delays"></a>Retrasos

Si el tiempo de entrega del material requerido es mayor que el período entre la fecha de hoy y la fecha de requerimiento de material, el pedido planificado para el material requerido y el pedido de producción relacionado se retrasarán. Para los pedidos planificados, el retraso (en días) se calcula en función del tiempo de entrega del producto liberado. Luego, la información de demora se propaga a todos los niveles de la estructura de la lista de materiales. Por lo tanto, puede seguir el impacto de la materia prima retrasada hasta el pedido de ventas del cliente.

## <a name="modifying-planned-orders"></a>Modificar pedidos planificados

Cuando cambia la información de un pedido planificado, recibe el siguiente mensaje: "Tenga en cuenta que el impacto de los cambios manuales en los pedidos planificados no se reflejará en el resto del plan hasta la siguiente ejecución de planificación maestra".

Si desea cambiar la información de un pedido planificado y ver el impacto en los requisitos de material relacionados, siga estos pasos.

1. Actualice el pedido planificado.
2. Apruebe el pedido planificado.
3. Ejecute la planificación maestra.

Cuando ejecuta la planificación maestra, no debe utilizar filtros si se incluyen pedidos de producción planificados. Para obtener más información, consulte la sección [Filtros](#filters) más adelante en este artículo.

> [!NOTE]
> Si la fecha de entrega del pedido previsional se cambia a una fecha posterior, la demanda podría estar vinculada a un nuevo pedido planificado. Este comportamiento se produce cuando la nueva fecha de suministro provoca un retraso para la demanda vinculada pero, según la configuración del plazo de entrega, el retraso se puede evitar.

## <a name="explosion-page"></a>Página de expansión

Puede usar la página **Expansión** para analizar la demanda necesaria para un pedido de producción específico o un pedido de producción planificado, la cobertura relacionada y la información de trazabilidad. La información en la página **Expansión** se actualiza durante la planificación maestra. No puede actualizar la información directamente desde la página **Expansión**.

## <a name="filters"></a><a name="filters"></a>Filtros

Para asegurarse de que la Optimización de planificación tenga la información necesaria para calcular el resultado correcto, debe incluir todos los productos que tengan alguna relación con los productos en toda la estructura de la lista de materiales del pedido planificado. Para escenarios de planificación que incluyen producción, le recomendamos que evite las ejecuciones de planificación maestra filtradas.

Aunque los elementos secundarios dependientes se detectan e incluyen automáticamente en las ejecuciones de planificación maestra cuando se utiliza el motor de planificación maestra incorporado, actualmente la optimización de planificación no realiza esta acción.

Por ejemplo, si un solo perno de la estructura de la lista de materiales del producto A también se utiliza para producir el producto B, todos los productos de la estructura de la lista de materiales de los productos A y B deben incluirse en el filtro. Debido a que puede resultar complejo garantizar que todos los productos formen parte del filtro, le recomendamos que evite las ejecuciones de planificación maestra filtradas cuando se trata de pedidos de producción. De lo contrario, la planificación maestra proporcionará resultados no deseados.

### <a name="reasons-to-avoid-filtered-master-planning-runs"></a>Razones para evitar ejecuciones de planificación maestra filtradas

Cuando ejecuta una planificación maestra filtrada para un producto, la optimización de la planificación (a diferencia del motor de planificación maestra incorporado) no detecta todos los subproductos y las materias primas en la estructura de la lista de materiales de ese producto y, por lo tanto, no los incluye en la ejecución de planificación maestra. Aunque la optimización de planificación identifica el primer nivel en la estructura de la lista de materiales del producto, no carga ninguna configuración del producto (como el tipo de pedido predeterminado o la cobertura del artículo) de la base de datos.

En la optimización de la planificación, los datos de la ejecución se cargan de antemano y se aplican los filtros. Esto significa que si un subproducto o materia prima incluida en un producto específico no forma parte del filtro, la información sobre él no se extraerá para la ejecución. Además, si el subproducto o la materia prima también se incluye en otro producto, una ejecución filtrada que incluya solo el producto original y sus componentes eliminaría la demanda planificada existente que se creó para ese otro producto.

Esta lógica puede hacer que las ejecuciones de planificación maestra filtradas produzcan resultados inesperados. Las siguientes secciones proporcionan ejemplos que ilustran los resultados inesperados que podrían ocurrir.

### <a name="example-1"></a>Ejemplo 1

Bien terminado *FG* consta de los siguientes componentes:

- Materia prima *R*
- Subproducto *S1*, que consta de subproducto *S2*

Hay inventario disponible para la materia prima *R*, mientras que el subproducto *S1* no está presente en el inventario.

Cuando realiza una ejecución de planificación maestra filtrada para productos terminados *FG*, obtendrá un pedido de producción planificado para el bien terminado *FG*, un pedido de compra planificado para la materia prima *R* y un pedido de compra planificado para el subproducto *S1*. Este es un resultado indeseable porque la optimización de la planificación ha ignorado el suministro existente de materia prima *R* y el subproducto *S1* necesita ser producido usando *S2* en lugar de ser pedido directamente. Esto sucedió porque la optimización de planificación solo tiene la lista de componentes para el bien terminado *FG* sin ninguna información relacionada, como el suministro existente de sus componentes o su configuración de pedido predeterminada.

### <a name="example-2"></a>Ejemplo 2

Sobre la base del ejemplo anterior, un bien terminado adicional, *FG2* también usa un subproducto *S1*. Existe un pedido planificado para el bien terminado *FG2* y existe demanda planificada para todos sus componentes, incluyendo *S1*.

Decide superar los resultados no deseados de la ejecución de planificación maestra filtrada del ejemplo anterior agregando todos los subproductos y materias primas de la estructura de la lista de materiales del bien terminado *FG* al filtro y luego ejecutando la regeneración completa.

Cuando ejecuta la regeneración completa, el sistema elimina todos los resultados existentes para todos los productos incluidos y luego vuelve a crear los resultados en función de los nuevos cálculos. Esto significa que la demanda planificada existente de producto *S1* se elimina y luego se vuelve a crear teniendo en cuenta solamente los requisitos del bien terminado *FG*, mientras que se ignoran los requisitos del bien terminado *FG2*. Esto sucede porque cuando ejecuta la optimización de planificación, no incluye la demanda planificada de otros pedidos de producción planificados &mdash; solo se utiliza la demanda planificada generada durante la ejecución.

> [!NOTE]
> Si el pedido previsional existente para el bien terminado *FG2* está en estado *Aprobado*, entonces se incluirá la demanda planificada aprobada, incluso cuando el producto principal no se haya agregado al filtro.

Por lo tanto, a menos que agregue todos los componentes del bien terminado *FG*, el bien terminado *FG2* y todos los demás productos de los que forman parte estos componentes (junto con sus componentes), la ejecución de planificación maestra filtrada proporcionará resultados no deseados.

Debido a que puede resultar complejo garantizar que todos los productos formen parte del filtro, le recomendamos que evite las ejecuciones de planificación maestra filtradas cuando se trata de pedidos de producción.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
