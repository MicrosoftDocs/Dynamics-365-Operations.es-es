---
title: Parámetros de producción en ejecución de fabricación
description: Este tema proporciona información sobre cómo configurar los parámetros de producción en la ejecución de fabricación.
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bf1afd18132e92cf081b7bde5067e1be90314467
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565566"
---
# <a name="production-parameters-in-manufacturing-execution"></a>Parámetros de producción en ejecución de fabricación

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre cómo configurar los parámetros de producción en la ejecución de fabricación.

El módulo **Ejecución de fabricación** está concebido principalmente para empresas de fabricación. Puede usarse para registrar la hora y el consumo de artículos en trabajos de producción o proyectos. Antes de comenzar a usar Ejecución de fabricación para registros de trabajos, debe configurar varios parámetros de producción que definen cómo y cuándo se realizan los registros durante el proceso de producción. La configuración de los parámetros de producción afectan a la administración de inventario, la administración de producción y el cálculo de costes.

Considere atentamente las opciones de la página **Parámetros de producción** antes de que los trabajadores comiencen a realizar registros de los trabajos de producción. Haga clic en **Control de producción** &gt; **Configuración** &gt; **Ejecución de fabricación** &gt; **Valores predeterminados de pedido de producción**. Si su empresa utiliza la funcionalidad multisitio, quizá le convendría configurar diferentes parámetros de producción en función del sitio. Los parámetros de integración con el módulo de **Producción** se configuran en las siguientes fichas de la página **Parámetros de producción**:

- **General**: ajustes de parámetros generales para los trabajos de producción en la ejecución de fabricación.
- **Inicio**: parámetros que se usan cuando se inician las operaciones de producción.
- **Operaciones**: parámetros que se aplican a las operaciones de producción y la realimentación en las operaciones durante el proceso de producción.
- **Notificar como terminado**: parámetros que se usan cuando los artículos se informan como terminados en la última operación de un pedido de producción.
- **Validación de cantidades**: parámetros que se usan para validar las cantidades de realimentación y de inicio en pedidos de producción.

## <a name="types-of-production-jobs"></a>Tipos de trabajos de producción
En la ficha **Operaciones** puede seleccionar qué tipos de trabajos de producción requieren registro en la página **Registro del trabajo**.

Normalmente, los trabajadores realizan registros en trabajos de configuración y de proceso. No obstante, si se aplica una programación de trabajos, puede seleccionar otros tipos de trabajos en los que el trabajador debe realizar registros al procesar un pedido de producción. Por ejemplo, puede exigir registros en los trabajos de transporte.

> [!IMPORTANT]
> Asegúrese de seleccionar todos los tipos de trabajo pertinentes. Si no, es posible que los trabajos no aparezcan disponibles para su registro en la página **Registro del trabajo**. Sus selecciones deben coincidir con las selecciones en la columna **Gestión de trabajos** en la ficha **Configuración** de la página **Grupos de rutas** (**Control de producción** &gt; **Configuración** &gt; **Rutas** &gt; **Grupos de rutas**).

Si se selecciona **Gestión de trabajos** en el grupo de rutas, este tipo de trabajo se notifica como terminado en el pedido de producción cuando se notifique como terminado el trabajo en Ejecución de fabricación. Cuando todos los tipos de trabajos para los que se ha seleccionado **Gestión de trabajos** se hayan notificado como terminados en una operación, la ejecución de fabricación también notifica la operación como terminada.

> [!NOTE]
> Algunos tipos de trabajo pueden notificarse manualmente a través de diarios de producción. En este caso, seleccione **Gestión de trabajos** para el tipo de trabajo, pero no seleccione el tipo de trabajo para su registro en la ficha **Operaciones** de la página **Parámetros de producción** en Ejecución de fabricación.

## <a name="bom-consumption-and-picking-list-journals"></a>Consumo de la lista de materiales y diarios de listas de selección
Una configuración coherente para el consumo de lista de materiales (BOM) es importante, ya que ayuda a garantizar que la gestión del inventario es eficiente. Por ejemplo, si los parámetros del consumo de la lista de materiales no están configurados correctamente en Ejecución de fabricación, es posible que se deduzcan materiales del inventario dos veces o ninguna.

En la página **Parámetros de producción**, el consumo automático de la lista de materiales se configura en tres fases:

- Al inicio de un a producción. Configúrelo en esta fase en la ficha **Inicio**.
- Durante el proceso de producción cuando se completa una operación. Configúrelo en esta fase en la ficha **Operaciones**.
- Cuando se notifica un pedido de producción como terminado. Configure esta fase en la ficha **Notificar como terminado**.

Para cada fase, el campo **Consumo automático de L. MAT** permite seleccionar uno de los tres métodos para seleccionar artículos para un pedido de producción:

- **Principio de vaciado**: esta opción se usa en combinación con una opción definida en la lista de materiales en el módulo de **Producción**. Haga clic en **Control de producción** &gt; **Común** &gt; **Pedidos de producción** &gt; **Todos los pedidos de producción**. En la página **Todos los pedidos de producción**, seleccione un pedido de producción de la lista y, a continuación, en el panel de acciones, haga clic en **L. MAT**. En la página **L. MAT**, en la ficha **Configuración**, en el campo **Principio de vaciado**, seleccione una de las siguientes opciones:

  - **Inicio**
  - **Finalizar**
  - **Manual**
  - En blanco (no se ha seleccionado ninguna opción).
  - **Disponible en la ubicación**

    En la ejecución de fabricación, si se selecciona **Principio de vaciado** en el campo **Consumo automático de L. MAT** en la pestaña **Inicio** , todos los materiales que se establecen para **Inicio** en la L. MAT se deducen del inventario cuando se inicia la operación. La opción **Disponible en la ubicación** se usa para los productos que se habilitan para los procesos avanzados del almacén. Si selecciona este principio de vaciado, se vacían los materiales cuando el trabajo del almacén para selección de la materia prima se ha completado. El material también se vacía cuando una línea de la L. MAT que use este principio de vaciado se libera al almacén y el material está disponible en la ubicación de entrada de producción.

    > [!NOTE]
    > Si el campo **Principio de vaciado** se establece en la pestaña **Inicio** en la ejecución de fabricación, debe seleccionar el mismo principio en la pestaña **Operaciones** o la pestaña **Notificar como terminado**. Este requisito le ayuda a garantizar que los materiales se deducen del inventario en listas de materiales que usan **Finalizar** como principio de vaciado en el pedido de producción. Si el mismo principio de vaciado no está seleccionado en la ficha **Operaciones** o la ficha **Notificar como terminado** , los materiales se pueden deducir del inventario dos veces.

- **Siempre**: si selecciona esta opción en una fase, los materiales siempre se deducirán del inventario en esa fase. Por ejemplo, los materiales para la producción se deducen cuando se inicia el pedido de producción. Este valor requiere que **Nunca** esté seleccionado en **Operaciones** y en las fichas **Notificar como terminado** . Este requisito ayuda a impedir que los artículos se deduzcan dos veces del inventario.
- **Nunca**: si selecciona esta opción para una fase, ningún consumo de L. MAT aparece en esa fase. Por ejemplo, si selecciona **Nunca** en las tres fichas (**Inicio**, **Operaciones** y **Notificar como terminado**), los materiales deben deducirse manualmente del inventario.

> [!IMPORTANT]
> Considere atentamente la configuración de los parámetros de producción y asegúrese de que los parámetros seleccionados en las diferentes fichas de la página **Parámetros de producción** no se contradicen entre sí.

En los ejemplos siguientes se muestran algunas configuraciones que admiten varios principios de consumo de L. MAT. Los parámetros se configuran en la página **Parámetros de producción** en la ejecución de fabricación.

### <a name="example-1-backflushing-on-operations"></a>Ejemplo 1: Flujo invertido de las operaciones

Use la configuración siguiente si se deberían generar diarios de listas de selección y el consumo de artículos de la lista de materiales cuando los artículos se notifican como terminados en una operación.

| Ficha                | Campo                          | Configuración                             |
|--------------------|--------------------------------|-------------------------------------|
| Inicio              | Actualizar el inicio en línea           | **Estado** o **Estado + cantidad** |
| Inicio              | Consumo automático de L. MAT      | **Nunca**                           |
| Operations         | Consumo automático de L. MAT      | **Siempre**                          |
| Notificar como terminado | Consumo automático de L. MAT      | **Nunca**                           |
| Notificar como terminado | Actualizar el registro en línea terminado | **Estado + cantidad**               |

### <a name="example-2-backflushing-on-production"></a>Ejemplo 2: Flujo invertido de la producción

Use la configuración siguiente si se deberían generar diarios de listas de selección y el consumo de artículos de la lista de materiales cuando los artículos se notifican como terminados en el pedido de producción.

| Ficha                | Campo                          | Configuración                             |
|--------------------|--------------------------------|-------------------------------------|
| Inicio              | Actualizar el inicio en línea           | **Estado** o **Estado + cantidad** |
| Inicio              | Consumo automático de L. MAT      | **Nunca**                           |
| Operations         | Consumo automático de L. MAT      | **Nunca**                           |
| Notificar como terminado | Consumo automático de L. MAT      | **Siempre**                          |
| Notificar como terminado | Actualizar el registro en línea terminado | **Estado + cantidad**               |

### <a name="example-3-flushing-principle"></a>Ejemplo 3: Principio de vaciado

Use la configuración siguiente si se deberían generar diarios de listas de selección y el consumo de artículos de la lista de materiales según el principio de vaciado configurado para los artículos de la L. MAT.

| Ficha                | Campo                          | Configuración                |
|--------------------|--------------------------------|------------------------|
| Inicio              | Actualizar el inicio en línea           | **Estado + cantidad**  |
| Inicio              | Consumo automático de L. MAT      | **Principio de vaciado** |
| Operations         | Consumo automático de L. MAT      | **Principio de vaciado** |
| Notificar como terminado | Consumo automático de L. MAT      | **Nunca**              |
| Notificar como terminado | Actualizar el registro en línea terminado | **Estado + cantidad**  |

### <a name="example-4-deduction-of-materials-during-startup-of-a-production-order"></a>Ejemplo 4: Deducción de materiales durante el inicio de un pedido de producción

Use la configuración siguiente si se deberían generar diarios de listas de selección y el consumo de artículos de la lista de materiales cuando se inicia la producción.

| Ficha                | Campo                          | Configuración                             |
|--------------------|--------------------------------|-------------------------------------|
| Inicio              | Actualizar el inicio en línea           | **Estado + cantidad**               |
| Inicio              | Consumo automático de L. MAT      | **Siempre**                          |
| Operations         | Consumo automático de L. MAT      | **Nunca**                           |
| Notificar como terminado | Consumo automático de L. MAT      | **Nunca**                           |
| Notificar como terminado | Actualizar el registro en línea terminado | **Estado** o **Estado + cantidad** |

En función de las selecciones descritas anteriormente en esta sección, los diarios de listas de selección se registran en distintas fases del proceso del pedido de producción.

- Cuando se inicia una operación.
- Cuando se notifica una realimentación de cantidad en una operación.
- Cuando los artículos se notifican como terminados en el pedido de producción.

### <a name="example-5-manual-bom-consumption"></a>Ejemplo 5: Consumo manual de la lista de materiales

Puede usar la siguiente configuración si los materiales deberían deducirse siempre manualmente del inventario. En este caso, no se registran los diarios de listas de selección.


|        Ficha         |             Campo              |         Configuración         |
|--------------------|--------------------------------|-------------------------|
|       Inicio        |      Actualizar el inicio en línea      | <strong>Estado</strong> |
|       Inicio        |   Consumo automático de L. MAT    | <strong>Nunca</strong>  |
|     Operations     |   Consumo automático de L. MAT    | <strong>Nunca</strong>  |
| Notificar como terminado |   Consumo automático de L. MAT    | <strong>Nunca</strong>  |
| Notificar como terminado | Actualizar el registro en línea terminado | <strong>Estado</strong> |

