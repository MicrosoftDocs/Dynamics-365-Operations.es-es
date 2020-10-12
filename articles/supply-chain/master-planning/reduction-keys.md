---
title: Previsión de las claves de reducción
description: Este tema proporciona ejemplos que muestran cómo configurar una clave de reducción. Incluye información sobre los distintos ajustes de la clave de reducción y los resultados de cada uno. Puede usar una clave de reducción para definir cómo reducir los requisitos de previsión.
author: roxanadiaconu
manager: tfehr
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqPlanSched, ReqReduceKeyDefaultDataWizard, ReqReduceKey
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76105cad18047d58a835b6c325575c58451a7c1a
ms.sourcegitcommit: cde71bc7d14ea6cdff2c4e991057d39a6a0473d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "3887073"
---
# <a name="forecast-reduction-keys"></a>Previsión de las claves de reducción

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre los distintos métodos que se usan para reducir los requisitos de previsión. Incluye los ejemplos de los resultados de cada método. También se explica cómo crear, configurar, y usar una previsión de clave de reducción. Algunos métodos usan una previsión de clave de reducción para reducir los requisitos de previsión.

## <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Los métodos que se usan para reducir los requisitos de previsión

Cuando incluye una previsión en un plan maestro, puede seleccionar cómo se reducen los requisitos de previsión cuando la demanda real es incluida. Tenga en cuenta que la planificación maestra excluye los requisitos de pronóstico del pasado, lo que significa todos los requisitos de pronóstico antes de la fecha de hoy.

Para incluir una previsión en un plan maestro y seleccionar el método que se usa para reducir los requisitos de previsión, vaya a **Planificación maestra \> Configuración \> Planes \> Planes maestros**. En el campo **Modelo de previsión** seleccione un modelo de previsión. En el campo **Método utilizado para reducir los requisitos de previsión**, seleccione un método. Las opciones siguientes están disponibles:

- Ninguno
- Porcentaje - clave de reducción
- Transacciones – clave de reducción
- Transacciones – período dinámico

En las secciones siguientes se ofrece más información acerca de cada opción.

### <a name="none"></a>Ninguno

Si elige **Ninguno** los requisitos de previsión no se reducen durante la programación maestra. En este caso, la planificación maestra crea pedidos planificados para suministrar la demanda prevista (requisitos de previsión). Estos pedidos planificados mantienen la cantidad propuesta, independientemente de otros tipos de demanda. Por ejemplo, si se colocan los pedidos de ventas, la planificación maestra crea pedidos planificados adicionales de suministrar los pedidos de ventas. La cantidad de los requisitos de previsión no se reduce.

### <a name="percent--reduction-key"></a>Porcentaje - clave de reducción

Si seleccionó **Porcentaje - clave de reducción**, los requisitos de previsión se reducen en función de los porcentajes y los períodos definidos por la clave de reducción. En este caso, la planificación maestra crea los pedidos planificados en los que la cantidad se calcula como clave de reducción de la cantidad × la clave de reducción de cada período. Si hay otros tipos de demanda, la planificación maestra también crea pedidos planificados de suministrar esa demanda.

#### <a name="example-percent--reduction-key"></a>Ejemplo: Porcentaje – clave de reducción

Este ejemplo muestra cómo reduce una clave de reducción los requisitos de previsión de la demanda en función de los porcentajes y los períodos definidos por la clave de reducción.

Para este ejemplo, se incluye la previsión de la demanda siguiente en un plan maestro.

| Mes    | Previsión de la demanda |
|----------|-----------------|
| Enero  | 1.000           |
| Febrero | 1.000           |
| Marzo    | 1.000           |
| Abril    | 1.000           |

En la página **Claves de reducción**, configure las siguientes líneas.

| Cambio | Unidad  | Porcentaje |
|--------|-------|---------|
| 1      | Mes | 100     |
| 2      | Mes | 75      |
| 3      | Mes | 50      |
| 4      | Mes | 25      |

Asigne la clave de reducción al grupo de cobertura del artículo. A continuación, en la página **Planes maestros** , en el campo **Método utilizado para reducir los requisitos de previsión** , se selecciona **Porcentaje - clave de reducción**.

En este caso, si ejecuta la programación de previsión el 1 de enero, los requisitos de previsión de la demanda se consumen de acuerdo con los porcentajes configurados en la página **Claves de reducción**. las siguientes cantidades de requisitos se transfieren al plan maestro.

| Mes                | Cantidad de pedido planificado | Cálculo    |
|----------------------|------------------------|----------------|
| Enero              | 0                      | = 0% × 1000   |
| Febrero             | 250                    | = 25% × 1000  |
| Marzo                | 500                    | = 50% × 1000  |
| Abril                | 750                    | = 75% × 1000  |
| De mayo a diciembre | 1.000                  | = 100% × 1000 |

### <a name="transactions--reduction-key"></a>Transacciones – clave de reducción

Si seleccionó **Transacciones - clave de reducción**, los requisitos de previsión se reducen mediante las transacciones que se producen durante los períodos definidos por la clave de reducción.

#### <a name="example-transactions--reduction-key"></a>Ejemplo: Transacciones - clave de reducción

Este ejemplo muestra cómo los pedidos reales, que se producen en períodos definidos por la clave de reducción, reducen los requisitos de previsión de la demanda.

Para este ejemplo seleccione **Transacciones - clave de reducción** , en el campo **Método utilizado para reducir los requisitos de previsión** , de la página **Planes maestros**.

Los siguientes pedidos de ventas existen el 1 de enero.

| Mes    | Número de piezas solicitadas |
|----------|--------------------------|
| Enero  | 956                      |
| Febrero | 1.176                    |
| Marzo    | 451                      |
| Abril    | 119                      |

Si utiliza la misma previsión de la demanda de 1000 piezas por mes que se usó en el ejemplo anterior, las siguientes cantidades de requisitos se transfieren al plan maestro.

| Mes                | Número de piezas requeridas |
|----------------------|---------------------------|
| Enero              | 44                        |
| Febrero             | 0                         |
| Marzo                | 549                       |
| Abril                | 881                       |
| De mayo a diciembre | 1.000                     |

### <a name="transactions--dynamic-period"></a>Transacciones – período dinámico

Si se selecciona **- Transacciones - período dinámico**, los requisitos de previsión se reducen por las transacciones de pedidos reales que tienen lugar durante el período dinámico. El período dinámico cubre las fechas de previsión actuales y finaliza con el inicio de la próxima previsión. En este caso, la planificación maestra crea pedidos planificados para suministrar la demanda prevista (requisitos de previsión). Sin embargo, cuando se colocan las transacciones de pedidos reales, se reducen los requisitos de previsión. Las transacciones reales consumen parte de los requisitos previstos.

Cuando se utiliza esta opción, el comportamiento es el siguiente:

- Las claves de reducción no se requieren ni se usan. 
- Si la previsión se reduce por completo, los requisitos de previsión para la previsión actual se convierten en 0 (cero).
- Si no hay previsión futura, se reducen los requisitos de previsión de la última previsión que se introdujo.
- Se incluyen límites de tiempo en el cálculo de la reducción de previsión.
- Se incluyen días positivos en el cálculo de la reducción de previsión.
- Si las transacciones de pedidos reales sobrepasan a los requisitos previstos, las transacciones restantes no se reenvían al próximo período de previsión.

#### <a name="example-1-transactions--dynamic-period"></a>Ejemplo 1: Transacciones - período dinámico

Aquí un ejemplo sencillo que muestra cómo funciona el método **- Transacciones período dinámico**.

Para este ejemplo, se incluye la previsión de la demanda siguiente en un plan maestro.

| Fecha       | Previsión de la demanda |
|------------|-----------------|
| 1 de enero  | 1.000           |
| 1 de febrero | 1.000             |

También puede crear los siguientes pedidos de ventas.

| Fecha        | Cantidad de pedido de ventas |
|-------------|----------------------|
| 15 de enero  | 200                  |
| 15 de febrero | 400                  |

En este caso, se crean los siguientes pedidos planificados.

| Fecha de previsión de la demanda | Cantidad | Explicación                           |
|--------------------- |----------|---------------------------------------|
| 1 de enero            | 800      | Requisitos de previsión (= 1000 - 200) |
| 15 de enero           | 200      | Requisitos de pedidos de ventas             |
| 1 de febrero           | 600      | Requisitos de previsión (= 1000 - 400) |
| 15 de febrero          | 400      | Requisitos de pedidos de ventas             |

#### <a name="example-2-transactions--dynamic-period"></a>Ejemplo 2: Transacciones - período dinámico

En la mayoría de los casos, se configuran los sistemas de modo que las transacciones reduzcan la previsión de la demanda en de períodos específicos de previsión: semanas, meses, y así sucesivamente. Estos períodos se definen en la clave de reducción. No obstante, el tiempo entre dos líneas de previsión de la demanda también puede *implicar* a un período.

Para este ejemplo cree una previsión de la demanda para las fechas y las cantidades siguientes.

| Fecha       | Previsión de la demanda |
|------------|-----------------|
| 1 de enero  | 1.000           |
| 5 de enero  | 500             |
| 12 de enero | 1.000           |

Observe que, en este previsión, no hay un período compensación entre las fechas de la previsión. Entre las primeras y segundas fechas hay un período de cuatro días, y entre las segundas y terceras fechas, hay un período de siete días. Estos lapsos son períodos dinámicos.

También puede crear las siguientes líneas de pedidos de ventas.

| Fecha                             | Cantidad de pedido de ventas |
|----------------------------------|----------------------|
| 15 de diciembre en el año anterior | 500                  |
| 3 de enero                        | 100                  |
| 10 de enero                       | 200                  |

En este caso, la previsión se reduce de la siguiente forma:

- Como el primer pedido de ventas no se encuentra en de ningún período, no se reducirá ninguna previsión.
- Como el segundo pedido de ventas es para entre el 1 de enero y el 5 de enero, reducirá la previsión para el 1 de enero por 100.
- Como el tercer pedido de ventas es para entre el 5 de enero y el 12 de enero, reducirá la previsión para el 5 de enero por 200.

Por lo tanto, se crean los siguientes pedidos planificados.

| Fecha de previsión de la demanda             | Cantidad | Explicación                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 15 de diciembre en el año anterior | 500      | Requisitos de pedido de ventas                                            |
| 1 de enero                        | 900      | Período de los requisitos de previsión del 1 de enero al 5 de enero (= 1000 – 100) |
| 3 de enero                        | 100      | Requisitos de pedido de ventas                                            |
| 5 de enero                        | 300      | Período de los requisitos de previsión del 5 de enero al 10 de enero (= 500 – 200)  |
| 12 de enero                       | 1.000    | Período de los requisitos de previsión del 12 de enero al final                      |

## <a name="create-and-set-up-a-forecast-reduction-key"></a>Crear y establecer una clave de reducción de previsión

Una clave de reducción de previsión se usa en **Transacciones - clave de reducción** y los métodos **Porcentaje - clave de reducción** para reducir los requisitos previstos de previsión. Siga estos pasos para crear y configurar una clave de reducción.

1. Vaya a **Planificación maestra \> Configuración \> Cobertura \> Claves de reducción**.
2. Seleccione **Nueva** o pulse **CTRL+N** para crear una clave de reducción.
3. En el campo **Clave de reducción** , especifique un identificador único para la clave de reducción de previsión. Después escriba un nombre en el campo **Nombre**. 
4. Definir períodos y el porcentaje de la clave de reducción en cada período:

    - El campo **Fecha de vigencia** indica la fecha en que la configuración de los períodos comienza. Cuando el campo **Usar la fecha de vigencia** se establece en **Sí**, los períodos comienzan en la fecha de vigencia. Cuando se establece en **No**, los períodos empiezan en la fecha en que se ejecute la planificación maestra.
    - Definir períodos durante los que la reducción de previsión debe aparecer.
    - Para un período específico, especifique los porcentajes en los que los requisitos de previsión se deben reducir. Puede especificar valores positivos para reducir los requisitos o valores negativos, para aumentar los requisitos.

## <a name="use-a-reduction-key"></a>Usar una clave de reducción

Una clave de reducción de previsión debe asignarse al grupo de cobertura del artículo. Siga estos pasos para asignar una clave de reducción al grupo de cobertura del artículo.

1. Vaya **Planificación maestra \> Configurar \> Cobertura \> Grupos de cobertura**.
2. En la ficha desplegable **Otro**, en el campo **Clave de reducción** seleccione la clave de reducción que se asignará al grupo de cobertura. La clave de reducción se aplicará a todos los artículos que pertenezcan al grupo de cobertura.
3. Para usar una clave de reducción para calcular la reducción de previsión durante la programación maestra, debe definir esta configuración en el plan de previsión o el plan maestro. Vaya a una de las páginas ubicaciones:

    - Planificación maestra \> Configuración \> Planes \> Planes de previsión
    - Planificación maestra \> Configurar \> Planes \> Planes maestros

4. En la página **Planes de previsión** o **Planes maestros** , en la ficha desplegable **General** , en el campo **Método utilizado para reducir los requisitos de previsión** , seleccione **Porcentaje - clave de reducción** o **Transacciones - clave de reducción**.

## <a name="reduce-a-forecast-by-transactions"></a>Reducir una previsión por transacciones

Cuando selecciona **Transacciones - clave de reducción** o **Transacciones - período dinámico** como método para reducir los requisitos previstos, puede especificar qué transacciones reducen la previsión. En la página **Grupos de cobertura** , en la ficha desplegable **Otro** , en el campo **Reducir la previsión por** , seleccione **Todas las transacciones** si todas las transacciones deben reducir la previsión o **Pedidos** si sólo los pedidos de ventas reducen la previsión.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los planes maestros](master-plans.md)
