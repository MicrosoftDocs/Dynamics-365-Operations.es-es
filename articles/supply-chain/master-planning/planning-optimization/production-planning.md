---
title: Planificación de producción
description: Este tema describe la planificación de la producción y explica cómo modificar los pedidos de producción planificados mediante Optimización de planificación.
author: ChristianRytt
manager: tfehr
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: eda22aa6f1e8d665d8ef390f24b247a76d4c2956
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992404"
---
# <a name="production-planning"></a>Planificación de producción

Optimización de planificación admite varios escenarios de producción. Si está migrando desde el motor de planificación maestro integrado existente, es importante que esté al tanto de algunos cambios de comportamiento.

<!-- The following video gives a short introduction to some of the current capabilities. 
KFM: Link to video for production functionality, coming soon... -->

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

Cuando ejecuta la planificación maestra, no debe utilizar filtros si se incluyen pedidos de producción planificados. Para obtener más información, consulte la sección [Filtros](#filters) más adelante en este tema.

> [!NOTE]
> Si la fecha de entrega del pedido previsional se cambia a una fecha posterior, la demanda podría estar vinculada a un nuevo pedido planificado. Este comportamiento se produce cuando la nueva fecha de suministro provoca un retraso para la demanda vinculada pero, según la configuración del plazo de entrega, el retraso se puede evitar.

## <a name="explosion-page"></a>Página de expansión

Puede usar la página **Expansión** para analizar la demanda necesaria para un pedido de producción específico o un pedido de producción planificado, la cobertura relacionada y la información de trazabilidad. La información en la página **Expansión** se actualiza durante la planificación maestra. No puede actualizar la información directamente desde la página **Expansión**.

## <a name="filters"></a><a name="filters"></a>Filtros

Para escenarios de planificación que incluyen producción, le recomendamos que evite las ejecuciones de planificación maestra filtradas. Para asegurarse de que la Optimización de planificación tenga la información necesaria para calcular el resultado correcto, debe incluir todos los productos que tengan alguna relación con los productos en toda la estructura de la lista de materiales del pedido planificado.

Aunque los elementos secundarios dependientes se detectan e incluyen automáticamente en las ejecuciones de planificación maestra cuando se utiliza el motor de planificación maestra incorporado, la optimización de planificación no realiza esta acción.

Por ejemplo, si un solo perno de la estructura de la lista de materiales del producto A también se utiliza para producir el producto B, todos los productos de la estructura de la lista de materiales de los productos A y B deben incluirse en el filtro. Debido a que puede ser muy complejo garantizar que todos los productos formen parte del filtro, le recomendamos que evite las ejecuciones de planificación maestra filtradas cuando se trata de pedidos de producción.
