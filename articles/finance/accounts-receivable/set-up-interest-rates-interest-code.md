---
title: Establecer tipos de interés para un código de interés
description: Los códigos de interés contienen la configuración que determina si se carga el interés y cómo se calcula en las cuentas vencidas.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1169a397dfdd32f728a09e2ad279842edc289c19
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971640"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a>Establecer tipos de interés para un código de interés

[!include [banner](../includes/banner.md)]

Los códigos de interés contienen la configuración que determina si se carga el interés y cómo se calcula en las cuentas vencidas.

Puede configurar un único código de interés y aplicarlo a varios perfiles de registro de cliente, códigos de facturación o líneas de factura concretas. Cuando se cambian los detalles del código de interés, todas las funciones que usan el código implementarán automáticamente los cambios en las nuevas transacciones. Puede configurar dos tipos de índices para cada código de interés:
-   Índices para las ganancias por intereses: representan los ingresos obtenidos por cargar un interés en las facturas o notas de interés.
-   Índices para los pagos de interés: representan el coste pagado por el interés de las notas de abono.

Ambos tipos de índices pueden existir al mismo tiempo y en el mismo código de interés. Los tipos de interés pueden basarse en tres tipos de cálculo:
-   Interés por porcentaje.
-   Interés por importe.
-   Interés por intervalo, lo que genera un único porcentaje o importe.

Si utiliza un código de interés para calcular el interés, se creará una nota de interés independiente para cada tipo de interés vigente durante el tiempo que el pago ha superado la fecha de vencimiento de la transacción. Se usa la ficha **Ganancias** de la página **Código de Interés** para configurar los tipos de interés para la ganancia que se obtiene al cargar el interés. Use la ficha **Pagos** para configurar los tipos de interés para el interés que usted paga.

## <a name="interest-rates-based-on-a-percentage"></a>Tipos de interés basados en porcentajes
Puede configurar los tipos de interés que calculan un porcentaje concreto.

- El importe del interés se aplica a todas las divisas.
- Se pueden especificar límites de interés opcionales.
- <strong>Porcentaje</strong> se selecciona** en el campo <strong>**Calcular el interés en función de</strong> en la página <strong>Configurar códigos de interés</strong>.

Por ejemplo, para configurar un código de interés que evalúe el 5 por ciento de interés por cada dos meses que el pago de la factura supere la fecha de vencimiento de la transacción, escriba 2 en el campo **Calcular interés cada** y seleccione **Mes**.

## <a name="interest-rates-based-on-amounts"></a>Tipos de interés basados en importes
Puede configurar los tipos de interés que calculan un importe concreto por divisa.
- Se especifica un importe de interés para cada divisa en el código de interés.
- Se pueden especificar límites de interés opcionales.
- **Porcentaje** se selecciona en el campo **Calcular el interés en función de** en la página **Configurar códigos de interés**.

Por ejemplo, para configurar un código de interés que evalúe el interés de 25,00 por cada 20 días que el pago de la factura supere la fecha de vencimiento de la transacción, escriba 20 en el campo **Calcular interés cada** y seleccione **Día**.

## <a name="interest-rates-based-on-ranges"></a>Tipos de interés basados en intervalos
Puede configurar los tipos de interés que varían en función del importe vencido o el número de días o de meses que se retrasa el importe.
-   Puede usar la ficha **Ganancias por divisa** para definir los parámetros específicos del interés para cada divisa. Aquí es también donde se define el intervalo.
-   Use el botón **Intervalos** para agregar las líneas que representan los intervalos que desea configurar. El valor **De** representa el principio del intervalo y el número **Valor de interés** representa un porcentaje o un importe, en función de la selección en el campo **Calcular el interés en función de** de la página **Configurar códigos de interés** .

## <a name="example-1-interest-by-range--amount"></a>Ejemplo 1: interés por intervalo = importe
Establezca el código de interés que evalúa el interés una vez por cada tres meses que el pago de la factura supere la fecha de vencimiento de la transacción. Deberá basar el cálculo en un valor de interés de porcentaje, de acuerdo con los intervalos del importe escalonado. El valor de interés será del 1 por ciento para los importes de factura de hasta 1.000,00, del 2 por ciento para los importes entre 1.001,00 y 5.000,00, y del 3 por ciento para los importes superiores a 5.000,00. Configure los valores del campo del código de interés de la siguiente manera:

| **Nombre del campo**                  | **Valor de campo** |
|---------------------------------|-----------------|
| **Código del interés**               | 3M%PorCant        |
| **Calcular interés cada**    | 3/Mes         |
| **Interés por intervalo**           | Importe          |
| **Calcular el interés en función de** | Porcentaje      |

Configure la información del intervalo de la siguiente manera:

| **Valor inicial** | **Valor del interés** |
|----------------|--------------------|
| 0              | 1                  |
| 1,001          | 2                  |
| 5,001          | 3                  |


## <a name="example-2-interest-by-range--days"></a>Ejemplo 2: interés por intervalo = días
--------------------------------------------------

Establezca el código de interés que evalúa el interés una vez por cada 15 días que el pago de la factura supere la fecha de vencimiento de la transacción. Deberá basar el cálculo en un valor de interés del importe, de acuerdo con los intervalos escalonados del día. El valor del interés será de 10,00 por 15 días durante los primeros 60 días, de 15,00 por 15 días durante los días 61 a 90, y de 20,00 por 15 días a partir del día 91. Configure los valores del campo del código de interés de la siguiente manera:

| **Nombre del campo**                  | **Valor de campo** |
|---------------------------------|-----------------|
| **Código del interés**               | 15DCantXDía      |
| **Calcular interés cada**    | 15/Día          |
| **Interés por intervalo**           | Días            |
| **Calcular el interés en función de** | Importe          |

Configure la información del intervalo de la siguiente manera:

| **Valor inicial** | **Valor del interés** |
|----------------|--------------------|
| 0              | 10                 |
| 61             | 15                 |
| 91             | 20                 |


## <a name="example-3-interest-by-range--months"></a>Ejemplo 3: interés por intervalo = meses
----------------------------------------------------

Establezca el código de interés que evalúa el interés una vez por cada mes que el pago de la factura supere la fecha de vencimiento de la transacción. Deberá basar el cálculo en un valor de interés de porcentaje, de acuerdo con los intervalos escalonados del mes. El valor del interés será del 1,5 por ciento por mes para los primeros tres meses vencidos, del 2,0 por ciento por mes para los segundos tres meses y del 2,5 por ciento por mes para cada mes pasados los primeros seis meses. Configure los valores del campo del código de interés de la siguiente manera:

| **Nombre del campo**                  | **Valor de campo** |
|---------------------------------|-----------------|
| **Código del interés**               | 1M%PorMes        |
| **Calcular interés cada**    | 1/Mes         |
| **Interés por intervalo**           | Meses          |
| **Calcular el interés en función de** | Porcentaje      |

Configure la información del intervalo de la siguiente manera:

| **Valor inicial** | **Valor del interés** |
|----------------|--------------------|
| 0              | 1.5                |
| 4              | 2                  |
| 7              | 2,5                |

## <a name="new-versions"></a>Versiones nuevas
Los códigos de interés tienen fecha de vigencia. Si desea modificar el tipo de interés, puede crear una **nueva versión** que estará vigente a partir de una fecha futura.

Para ver diferentes versiones, puede usar la opción de menú **Desde fecha** para seleccionar la fecha final. También puede seleccionar **Mostrar todos los registros** para ver todos los códigos de interés en la página.



