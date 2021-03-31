---
title: Configuración de la administración de crédito
description: En este tema se describe la configuración necesaria para la administración de crédito.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5cd6d2f23a68ad3d7308d40a2638866dde7a7a81
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224774"
---
# <a name="credit-management-setup"></a>Configuración de la administración de crédito 

[!include [banner](../includes/banner.md)]

## <a name="credit-management-workflows"></a>Flujos de trabajo de gestión de créditos

Vaya **Créditos y cobros \> Configurar \> Flujos de trabajo de administración de crédito** para definir los flujos de trabajo que se utilizan para administrar los ajustes del límite de crédito.

- Puede crear un flujo de trabajo que le permita aprobar un lote de ajustes de límites de crédito a través de una sola aprobación.
- Puede agregar un flujo de trabajo a nivel de línea, de modo que los ajustes del límite de crédito se puedan aprobar individualmente.
- Puede crear un flujo de trabajo de lanzamiento que enrute automáticamente las retenciones a un proceso de flujo de trabajo.

## <a name="blocking-rules"></a>Reglas de bloqueo

### <a name="ranking-payment-terms"></a>Clasificación de condiciones de pago

Puede poner un pedido de ventas en espera si las condiciones de pago del pedido no coinciden con las condiciones de pago predeterminadas para el cliente. Sin embargo, a veces las condiciones de pago difieren pero son lo suficientemente similares como para que no desee poner el pedido en espera. Puede clasificar los términos de pago para que algunos de ellos tengan el mismo rango, y otros tengan un rango más alto o más bajo.

Si las clasificaciones de las condiciones de pago están activas y si las condiciones de pago del pedido tienen una clasificación más alta que las condiciones de pago predeterminadas para el cliente, el pedido de ventas se pondrá en espera.

Para configurar la clasificación de condiciones de pago vaya a **Crédito y cobros \> Configuración \> Configuración de administración de crédito \> Clasificar condiciones de pago**  

### <a name="ranking-settlement-discounts"></a>Clasificación de descuentos de liquidación

Puede poner un pedido de ventas en espera si el descuento por pronto pago del pedido no coincide con el descuento por pronto pago predeterminado para el cliente. Sin embargo, a veces los descuentos por pronto pago difieren pero son lo suficientemente similares como para que no desee poner el pedido en espera. Puede clasificar los descuentos por pronto pago para que algunos de ellos tengan el mismo rango, y otros tengan un rango más alto o más bajo.

Si las clasificaciones de descuentos de liquidación están activas y si el descuento por pronto pago del pedido tiene una clasificación más alta que el descuento por pronto pago predeterminado para el cliente, el pedido de ventas se pondrá en espera.

Para configurar la clasificación de condiciones de pago vaya a **Crédito y cobros \> Configuración \> Configuración de administración de crédito \> Clasificar liquidación de descuentos**  

## <a name="reasons"></a>Motivos

Se utilizan varios tipos de razones en la administración de crédito:

- Los motivos de retención indican por qué se puso en espera un pedido de ventas.
- Los motivos de liberación se asignan a un pedido cuando se libera de la retención.
- Las razones de estado indican por qué se asignó el estado de una cuenta a un cliente.

Puede configurar razones en la página **Razones de la administración de crédito** (**Crédito y cobros \> Configuración \> Configuración de administración de crédito \> Razones de la administración de crédito**).

1. En el campo **Tipo de razón**, seleccione el tipo de razón: **Retener**, **Liberar** o **Estado**.
2. En el campo **Razón**, especifique un nombre para la razón.
3. En el campo **Descripción**, especifique una descripción para el código de razón.

## <a name="credit-management-groups"></a>Grupos de gestión de créditos

Los grupos de administración de crédito se utilizan para identificar clientes o grupos de clientes que tienen las mismas propiedades de administración de crédito. Por ejemplo, los grupos de administración de crédito pueden usarse para determinar las reglas de administración de crédito de bloqueo y exclusión para los clientes.

Puede crear grupos de administración de crédito en la página **Grupos de administración de crédito** (**Crédito y cobros \> Configuración > Configuración de administración de crédito \> Grupos de administración de crédito**).

1. Seleccione **Nuevo** para crear una línea.
2. Especifique un id. para el grupo. El id. puede tener hasta 10 caracteres.
3. En el campo **Descripción**, especifique un nombre para el grupo. El nombre puede tener hasta 60 caracteres.

El grupo de administración de crédito se asigna a un cliente en la ficha desplegable **Créditos y cobros** de la página **Todos los clientes** (**Clientes \> Clientes \> Todos los clientes**).

## <a name="account-statuses"></a>Estados de cuenta

Puede crear estados de cuenta para identificar la solvencia de una cuenta de cliente. Puede definir un estado y su efecto en los procesos de facturación y entrega en espera. Los estados de cuenta también se pueden usar para determinar las reglas de bloqueo para un cliente.

Puede crear estados de cuenta en la página **Estados de cuenta** (**Crédito y cobros \> Configuración > Configuración de administración de crédito \> Estados de cuenta**).

1. Agregue un estado de cuenta y escriba una descripción que represente la solvencia de un cliente. Por ejemplo, use **Normal** para indicar que un cliente está al día y los pedidos abiertos están sujetos al procesamiento estándar de administración de crédito.
2. En los campos **Facturación** y **Entrega en espera**, seleccione el tipo de retención que debe producirse para los clientes que tienen este estado de cuenta. Puede retener todo el procesamiento, retener solo el procesamiento de facturas o no retener ningún procesamiento cuando se aplican las reglas de límite de crédito.

## <a name="scoring-groups"></a>Grupos de clasificación

Puede configurar grupos de puntuación para definir los factores de riesgo y los criterios que se utilizan para medirlos. Cuando la información sobre un cliente se aplica a un grupo de puntuación, se calcula una puntuación para cada factor de riesgo y se utiliza para colocar al cliente en un grupo de riesgo. El grupo de riesgo se puede utilizar para identificar la solvencia y calcular los límites de crédito automáticos.

Puede crear grupos de puntuación en la página **Grupos de puntuación** (**Crédito y cobros \> Configuración \> Configuración de administraciónde crédito \> Riesgo \> Grupos de puntuación**).

1. Cree un grupo de puntuación y asígnele un nombre.
2. Escriba una descripción para describir mejor el grupo de puntuación.
3. Seleccione un tipo de grupo. Hay ocho tipos predefinidos. También puede seleccionar **Definido por el usuario** para definir un tipo de grupo que se adapte mejor a su organización.
4. Seleccione un tipo de puntuación para definir la forma de calcular la puntuación de riesgo en el grupo de puntuación. Las siguientes opciones están disponibles:

    - **Rango**: use esta opción para definir un rango de valores que se deben usar para calcular una puntuación.
    - **Definido por el usuario**: use esta opción para definir manualmente una lista de valores que se deben usar para la puntuación.

5. Si seleccionó **Rango** como tipo de puntuación, agregue líneas para definir el rango de valores y las puntuaciones correspondientes.

    1. En el campo **Valor inicial**, especifique el valor más bajo del rango.
    2. En el campo **Valor final**, especifique el valor más alto del rango.
    3. En el campo **Puntuación**, introduzca la puntuación que se debe asignar cuando el valor proporcionado está en el rango "inicial"/"final".

    Si seleccionó **Definido por el usuario** como tipo de puntuación, agregue líneas para definir los valores definidos por el usuario y las puntuaciones correspondientes.

    1. En el campo **Valor**, introduzca el valor definido por el usuario que se debe proporcionar a partir de la información del cliente.
    2. En el campo **Puntuación**, introduzca la puntuación que se debe asignar cuando el valor proporcionado está en el rango "inicial"/"final".

## <a name="risk-classification"></a>Clasificación del riesgo

Puede definir valoraciones de riesgos que se pueden asignar a los clientes, en función de su puntuación de riesgo. Una puntuación de riesgo se calcula comparando la información del cliente con cada grupo de puntuación. Las puntuaciones se suman y la puntuación total se compara con los valores de la configuración del grupo de riesgo para identificar el grupo de riesgo al que pertenece el cliente. La puntuación del grupo de riesgo se usa para definir reglas de bloqueo y exclusión de administración de crédito para el cliente.

Puede configurar grupos de riesgo en la página **Valoraciones de riesgo** (**Crédito y cobros \> Configuración \> Configuración de administración de crédito \> Riesgo \> Clasificación de riesgo**).

1. Introduzca un id. de grupo de riesgo.
2. Escriba una descripción para explicar mejor el grupo de riesgo.
3. Introduzca un rango de puntuaciones que se utilizará para determinar qué clientes pertenecen al grupo de riesgo.
4. Seleccione un indicador de grupo de riesgo para especificar el símbolo que representa al grupo de riesgo.

## <a name="guaranteeinsurance-types"></a>Tipos de garantía/seguro

Puede configurar tipos de garantía/seguro en la página **Tipos de garantía/seguro** (**Crédito y cobros \> Configuración \> Configuración de administración de crédito \> Seguro y garantías \> Tipos de seguro y garantías**).

1. Introduzca un tipo de garantía o de seguro que identifique el nombre del garante o del corredor de seguros.
2. Introduzca una descripción para describir al garante/corredor de seguros.

## <a name="coverage-types"></a>Tipos de cobertura

Los tipos de cobertura se pueden usar para clasificar mejor las pólizas de seguro. No se pueden usar con garantías.

Puede agregar tipos de cobertura en la página **Tipos de cobertura** (**Crédito y cobros \> Configuración \> Configuración de administración de crédito \> Seguro y garantías \> Tipos de cobertura**).

1. Introduzca un tipo de cobertura para identificar el tipo de cobertura que se debe agregar como seguro o garantía.
2. Especifique una descripción del tipo de cobertura.

## <a name="automatic-credit-limits"></a>Límites de crédito automáticos

Puede crear criterios para límites de crédito automáticos en la página **Límites de crédito automáticos** (**Crédito y cobros \> Configuración \> Configuración de administración de crédito \> Riesgo \> Límites automáticos de crédito**).

1. Seleccione un grupo de riesgo al que se debe asignar el límite automático de crédito.
2. Seleccione la divisa para el límite automático de crédito. Puede crear múltiples límites de crédito automáticos en diferentes divisas para un mismo grupo de riesgo.
3. Introduzca el importe de ingresos que representa los ingresos máximos de la empresa y que se puede usar para este límite automático de crédito. Cuando se crean límites de crédito, el importe de los ingresos se compara con un valor de ingresos que se encuentra en la página **Finanzas** (**Clientes \> Todos los clientes \> Seleccionar un cliente \> General \> Estadísticas \> Financiero**). El sistema utiliza el valor más reciente en la sección **Visión general**.

Siga estos pasos para agregar líneas que representen el límite de crédito que se generará según los criterios seleccionados.

1. Seleccione el grupo de puntuación que define la información del cliente que se debe utilizar para calcular el límite de crédito.
2. Seleccione el operador de comparación que define cómo se debe evaluar la información del grupo de puntuación.
3. Especifique el valor que se debe comparar con el valor especificado para el grupo de puntuación.
4. Especifique el límite de crédito que se debe asignar si la información del cliente coincide con el valor especificado para el grupo de puntuación. Por ejemplo, crea un límite de crédito automático para el grupo de puntuación **Bajo**. Si los años en el negocio representa uno de los grupos de puntuación, puede definir una línea que asigne un límite de crédito de 100 000 si el cliente lleva cinco años en el negocio y otra línea que asigna un límite de crédito de 200 000 si el cliente lleva 10 años en el negocio.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]