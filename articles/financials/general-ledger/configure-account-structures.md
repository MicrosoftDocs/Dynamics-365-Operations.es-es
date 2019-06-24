---
title: Configurar estructuras contables
description: En este tema se proporciona información acerca de las estructuras contables y las dimensiones financieras.
author: aprilolson
manager: AnnBe
ms.date: 06/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fbd4b34d09b4ba8e1d34234c8e32268bba18778
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617305"
---
# <a name="configure-account-structures"></a>Configurar estructuras contables

[!include[banner](../includes/banner.md)]

Las estructuras contables utilizan la cuenta principal y las dimensiones financieras para crear un conjunto de reglas que determinan el pedido y los valores que se utilizaron para introducir el número de cuenta. Puede configurar tantas estructuras contables como necesite para su negocio. Las estructuras contables se asignan a la configuración del libro mayor de una empresa, de manera que se puedan compartir.

Al crear una estructura contable, el número máximo de segmentos es 11. Si necesita más segmentos, evalúe exhaustivamente la configuración y los requisitos, ya que afectará a la experiencia del usuario. Considere si un segmento podría derivar en un escenario de informes a través de una jerarquía en lugar durante la entrada de datos, o mediante un campo definido por el usuario. Por ejemplo, si desea informar sobre la ubicación, pero puede representar la ubicación por departamento o centro de coste, no necesitará la ubicación como una dimensión financiera. Si después de la evaluación decide que son necesarios más de 11 segmentos, puede agregar segmentos adicionales mediante reglas avanzadas.

Las estructuras contables requieren la cuenta principal. La cuenta principal no necesita ser el primer segmento en la estructura, pero identifica qué estructura contable se está utilizando durante la entrada del número de cuenta. Debido a esto, un valor de la cuenta principal solo puede existir en una estructura asignada al libro mayor para que no se superpongan. Después de que se identifique la estructura contable, la lista de valores permitida se filtra para guiar al usuario solo a través de la selección de valores de dimensión válidos, lo que reduce la posibilidad de un movimiento de diario incorrecto.

> [!NOTE] 
> Si planea presupuestar una dimensión financiera, esta deberá formar parte de una estructura contable. La gestión presupuestaria no utiliza actualmente reglas avanzadas.

## <a name="example"></a>Ejemplo
Para ilustrar una práctica recomendada para configurar una estructura contable, supongamos que una empresa desea realizar un seguimiento de sus cuentas de balance de situación (100000..399999) a nivel de cuenta y de dimensión financiera de la unidad de negocio. Para las cuentas de pérdidas y ganancias (400000..999999), realizan un seguimiento de las dimensiones financieras Unidad de negocio, Departamento y Centro de coste. Si realizan una venta, también querrán realizar un seguimiento al Cliente. Mediante este escenario, se recomendaría tener dos estructuras contables asignadas al libro mayor de la empresa (uno para las cuentas de balance de situación y otra para las cuentas de pérdidas y ganancias). Para optimizar la experiencia y la validación del usuario, el Cliente debe ser una regla avanzada que se emplee solo cuando se utilice una cuenta de ventas.

**Estructura de cuenta de balance de situación**

|Cuenta principal          | Unidad de negocio    |
|----------------------|-----------|
|100000..399999 | *;” “|

**Estructura de cuenta de pérdidas y ganancias**

|Cuenta principal          | Unidad de negocio    |Departamento          | Centro de coste    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | *;” “|*;” “|*;” “|*;” “|

**Regla avanzada para agregar un Cliente**

Criterios: Cuando la cuenta principal se encuentra entre 400000 y 499999, se agrega el cliente. No se puede dejar en blanco.

|Cliente          |
|-----------------|
|* |

En este ejemplo simplificado, se permiten todos los valores y en blanco de modo que se utilizan * y “ “.

## <a name="segments-and-allowed-values"></a>Segmentos y valores permitidos
La sección **Segmentos** y **Detalles de valor permitidos** proporciona una cuadrícula como experiencia para introducir las reglas que se siguen en la validación durante el registro. Puede escribir directamente en las celdas de la cuadrícula, importarla de Excel o utilizar la sección **Detalles de valor permitidos** para guiarle a través de ella.

La sección **Detalles de valor permitidos** le guiará por la creación de criterios usando **Operadores** como comienza con, se encuentra entre, incluye, y muchos otros.

[![Permitir valores](./media/account.png)](./media/account.png) 

Los valores permitidos se establecerán como valor predeterminado sobre un diario o una página de la entrada de distribución contable cuando no se necesitan valores posibles para seleccionar en función de la configuración de la estructura contable.

Aquí se indica un ejemplo de la **Estructura de la cuenta de pérdidas y ganancias**.

|Cuenta principal          | Unidad de negocio    |Departamento          | Centro de coste    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | 002 | 022 | 014 |

Cuando se introduzca un diario y la selección de una cuenta del intervalo de pérdidas y ganancias, seleccionando la unidad de negocio "002" hará que los valores 022 y 014 sean el valor predeterminado en el control de la cuenta. Este comportamiento también aparecerá con la página de la distribución contable. 

## <a name="more-than-7-criteria-needed"></a>Se necesitan más de 7 criterios

Si tiene más de 7 criterios que son necesarios, puede continuar agregándolos en la siguiente línea. Observará cuando trabaje en la sección **Detalles de valor permitidos** que los criterios **+Agregar nuevo** ya no están activos después de introducir el séptimo criterio. Esto se debe a muchos factores como: 
 - Ancho de columna 
 - Cómo se almacenan los datos 
 - Rendimiento del control **Detalles de valor permitidos**
 - Facilidad de uso  
 
Para continuar agregando criterios adicionales, haga clic en **Duplicar en el segmento** y **Sección de valores permitidos**. Esto copiará los criterios en una nueva línea. A continuación, puede escribir encima o modificar la sección **Detalles de valor permitidos** .

## <a name="best-practices"></a>Prácticas recomendadas
Al configurar sus estructuras contables existen algunas prácticas recomendadas que puede seguir. Sin embargo, esto es solo una orientación, por lo que debe considerarse una discusión holística sobre su negocio, plan de crecimiento y plan de mantenimiento como parte de esa discusión.

- Haga que la cuenta principal esté la primera o lo más cerca posible de la frente de la estructura contable, por lo que los usuarios obtienen la mejor experiencia dirigida que pueden durante un asiento contable.

- Vuelva a utilizar las estructuras contables tanto como sea posible para reducir mantenimiento en sus entidades jurídicas.

- Para variaciones entre entidades jurídicas, considere usar reglas avanzadas para poder reutilizar estructuras contables.

- Al definir valores permitidos, use intervalos y caracteres comodín tanto como sea posible. Esto no solo le permite crecer y cambiar sin mantenimiento, sino que el sistema también se desempeña más idealmente con esta configuración.

- No ponga solo un asterisco para cada segmento en la estructura contable y confíe únicamente de las reglas avanzadas. Esto puede resultar difícil de gestionar y llevar a menudo a errores del usuario durante el mantenimiento, lo que puede hacer que el sistema no puede registrar.

## <a name="account-structure-activation"></a>Activación de estructura contable
Cuando esté satisfecho con su nueva configuración o con un cambio en una estructura contable, debe activarla. Si una estructura contable se asigna a un libro mayor, esta activación puede ser un proceso de larga ejecución, ya que todas las transacciones sin registrar en el sistema deben sincronizarse en la nueva estructura. Las transacciones registradas no se ven afectadas por los cambios en la estructura contable.

Para obtener más información, consulte [Planificar su plan de cuentas](plan-chart-of-accounts.md), [Dimensiones financieras](financial-dimensions.md) y [Especificar combinaciones de cuentas y dimensiones (control de entrada segmentada)](enter-account-dimension-combinations-segmented-entry-control.md).
