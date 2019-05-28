---
title: Principios de vaciado
description: Este tema describe los cuatro principios de vaciado que se usan para el consumo de materias primas.
author: johanhoffmann
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e4b9cd918bec9a094744b208821285c57f01798a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547454"
---
# <a name="controlling-raw-material-consumption-by-using-flushing-principles"></a>Controlar el consumo de materias primas mediante principios de vaciado

[!include [banner](../includes/banner.md)]

Los principios de vaciado reflejan las distintas estrategias de consumo de materias primas que se usan en los procesos de producción. El consumo es el proceso que deduce el material del inventario disponible y establece el valor de los materiales consumidos a **Trabajo en curso** para los pedidos de producción y los pedidos de lote. Las materias primas se consumen normalmente desde una ubicación configurada para el proceso que consume el material. Esta ubicación se conoce como la ubicación de entrada de producción.

Antes del consumo de materiales, los materiales se mueven a la ubicación de entrada. En la ilustración siguiente se muestra el proceso.

[![escenario4a](./media/scenario4a.png)](./media/scenario4a.png)

1. Almacén de material
2. Picking de materia prima
3. Ubicación de entrada de producción
4. Consumo de materias primas
5. Proceso de producción

El consumo de material se controla mediante los siguientes cuatro principios de vaciado:

- Manual
- Inicio
- Finalizar
- Disponible en la ubicación

Los principios de vaciado se configuran en una jerarquía de valores predeterminados. La jerarquía comienza en el producto liberado, donde el principio de vaciado tiene el valor **Inicio**. El principio de vaciado desde el producto se puede anular en la lista de materiales (L. MAT) o la línea de fórmula. El principio de vaciado predeterminado en las líneas de L. MAT de producción o las líneas de fórmula de pedido de lote se toma del producto o del valor anulado en la L. MAT o fórmulas.

## <a name="description-of-the-flushing-principles"></a>Descripción de los principios de vaciado

### <a name="manual"></a>Manual
El principio de vaciado manual indica que el registro de consumo de material es una operación manual. Este principio es relevante si, por ejemplo, desea realizar el seguimiento del tiempo, y debe contabilizarse la cantidad de números de lote o números de serie consumidos para fines de seguimiento. El consumo manual se registra en un diario de lista de selección de producción. Para los artículos que se habilitan para procesos de almacén avanzados, se puede aplicar un flujo manual.

### <a name="start"></a>Inicio
El principio de vaciado Inicio indica que el material se consumirá automáticamente cuando se inicie un pedido de producción. El importe de material que se consume es proporcional a la cantidad iniciada. Si el principio de vaciado Inicio se usa junto con el sistema de ejecución de fabricación, también se pueden usar para vaciar materiales cuando se inicie una operación o un trabajo de proceso. Este principio es relevante si, por ejemplo, la desviación en el consumo es baja, los materiales son materiales de valor reducido, no hay requisitos de seguimiento o hay un tiempo de ejecución breve en las operaciones. 

### <a name="finish"></a>Finalizar
El principio de vaciado Finalizar indica que el material se consumirá automáticamente cuando el pedido de producción se notifique como finalizado, o cuando una operación que se configura para consumir los materiales se registra como completada. El importe de material que se consume es proporcional a la cantidad que se notifica como finalizada. Si el principio de vaciado Finalizar se usa junto con el sistema de ejecución de fabricación, también se pueden usar para vaciar materiales cuando se complete una operación o un trabajo de proceso. Este principio es relevante en las mismas situaciones que el principio Inicio. Sin embargo, el principio Finalizar es para operaciones que tienen un tiempo de ejecución más largo, donde los materiales no se deben definir como trabajo en curso antes de que se complete la operación. 

### <a name="available-at-location"></a>Disponible en la ubicación
El principio de vaciado Disponible en la ubicación indica que el material se consumirá automáticamente cuando se registre como seleccionado para producción. El material se registra como seleccionado de la ubicación cuando se complete el trabajo para la selección de materia prima, o cuando el material está disponible en la ubicación de entrada de producción y la línea de materiales se libera al almacén. La lista de selección que se genera durante el proceso se registra en un trabajo por lotes. Este principio es relevante si, por ejemplo, tiene muchas actividades de selección en un pedido de producción. En este caso, no es necesario actualizar manualmente la lista de selección y puede obtener una vista actual del saldo de trabajo en curso.
