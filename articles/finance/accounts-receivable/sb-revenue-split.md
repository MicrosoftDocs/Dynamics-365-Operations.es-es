---
title: Plantillas de división de ingresos en facturación de suscripción
description: Este tema explica cómo configurar plantillas de división de ingresos para artículos que se venden como paquetes.
author: JodiChristiansen
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 73dbc2242639a54d687506e7c325fec4b9a95d12
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770165"
---
# <a name="revenue-split-templates-in-subscription-billing"></a>Plantillas de división de ingresos en facturación de suscripción

Utilice la página **Plantilla de división de ingresos** para configurar plantillas para la división de ingresos. La división de ingresos consiste en un artículo principal que tiene artículos secundarios. Este tipo de artículos se vende a menudo a los clientes como un solo artículo o paquete.

Por ejemplo, se puede crear un artículo de equipo informático de la siguiente manera:

- **Artículo principal:** Suscripción Plata
- **Artículos de línea (secundarios):**

    - Soporte
    - Mantenimiento
    - Licencia

Cuando cree un artículo principal, tenga en cuenta las siguientes restricciones:

- Se puede especificar un artículo como elemento principal solo una vez.
- El artículo principal se puede seleccionar como artículo secundario en la misma plantilla.
- Una plantilla válida requiere al menos un artículo secundario.
- Un artículo se puede especificar como artículo secundario para varios artículos de agrupación.
- Cada relación principal-secundario debe ser única.

## <a name="create-a-parent-item-that-has-child-items"></a>Crear un elemento principal que tenga elementos secundarios

Siga estos pasos para crear un artículo principal que tenga artículos secundarios.

1. En la página **Plantilla de división de ingresos**, seleccione **Nuevo**.
1. En el campo **Artículo principal**, seleccione un artículo principal. El campo **Número de variante** se actualiza automáticamente. Puede cambiar el valor si es necesario.
1. En el campo **Método de asignación**, seleccione un método de asignación.
1. En la lista **Artículos componentes**, seleccione **Agregar** para agregar artículos secundarios.
1. Si seleccionó **Porcentaje** en el campo **Método de asignación**, especifique un porcentaje en el campo **Porcentaje**.

    - Si seleccionó **Igual importe** en el campo **Método de asignación**, el campo **Porcentaje** se actualiza automáticamente para que cada artículo tenga un porcentaje igual.
    - Si seleccionó **Importe variable**, **Importe principal cero** o **Cantidad cero** en el campo **Método de asignación**, el valor del campo **Porcentaje** sigue siendo **0** (cero) y no se puede cambiar.

1. Seleccione **Guardar**.

## <a name="fields"></a>Campos

La página **Plantilla de división de ingresos** contiene los siguientes campos.

| Campo | Description |
|-------|-------------|
| Artículo primario | Seleccione un número de artículo. Este artículo se convierte en el artículo principal del artículo de agrupación que crea. |
| Nombre de producto | Nombre de producto. |
| Método de asignación | <p>Seleccione el método de asignación:</p><ul><li>**Importe igual** – Los porcentajes de asignación se calculan automáticamente y se dividen por igual entre todos los elementos de la plantilla.</li><li>**Porcentaje** – Puede especificar un importe en porcentaje para la asignación. La suma de todos los porcentajes debe ser igual a 100.</li><li>**Importe variable** – Los artículos secundarios que se agregan tienen un importe neto de 0 (cero). El precio de los artículos secundarios debe especificarse en el nivel de transacción.</li><li>**Importe cero** – El artículo principal conserva su precio unitario y su importe neto. Todos los artículos secundarios tienen un importe neto de 0 (cero).</li><li>**Importe principal cero** – El artículo principal tiene un importe neto fijo de 0 (cero). Todos los artículos secundarios se tratan como artículos estándar. No se realiza ninguna validación para verificar que la suma de los importes de los artículos secundarios sea igual al importe de los artículos principales.</li></ul> |
| **Artículos componentes** | |
| Artículo componente | Seleccione un número de artículo. Este artículo es un artículo secundario. |
| Número de variante | Seleccione el número de variante del artículo. |
| Nombre de producto | Nombre de producto. |
| Porcentaje | <p>Porcentaje de asignación para el hito:</p><ul><li>Si el campo **Método de asignación** se establece en **Porcentaje**, puede especificar el porcentaje.</li><li>Si el campo **Método de asignación** se establece en **Importe igual**, el porcentaje se calcula automáticamente para que cada artículo de la plantilla tenga un porcentaje igual.</li><li>Si el campo **Método de asignación** se establece en **Importe variable**, **Importe principal cero** o **Importe cero**, el porcentaje es 0 (cero) y no se puede editar.</li></ul><p>El valor de este campo puede ser cualquier número positivo entre 0 (cero) y 100. La suma de todos los porcentajes debe ser igual a 100.</p> |
| Porcentaje total | <p>La suma de los valores de la columna **Porcentaje**.</p><ul><li>Si el campo **Método de asignación** se establece en **Igual importe** o **Porcentaje**, la suma de todos los porcentajes debe sumar 100.</li><li>Si el campo **Método de asignación** se establece en **Importe variable**, **Importe principal cero** o **Importe cero**, el porcentaje total es 0 (cero).</li></ul> |

## <a name="revenue-split-on-a-sales-order"></a>División de ingresos en un pedido de ventas

Para crear un pedido de ventas que tenga un artículo configurado para división de ingresos, siga estos pasos.

1. En la página **Pedido de ventas**, cree un pedido de ventas.
2. En la línea de cada artículo configurado para división de ingresos, seleccione la casilla **División de ingresos**. Ese artículo se convierte en el artículo principal. Si la plantilla ya está configurada, los artículos secundarios aparecen automáticamente en la lista.
3. Para agregar más artículos secundarios, seleccione **Agregar elemento secundario de división de ingresos** y seleccione el artículo secundario que desea agregar.
4. Guarde el pedido.

## <a name="revenue-split-with-billing-schedules"></a>División de ingresos con programaciones de facturación

Para crear una programación de facturación que tenga un artículo configurado para división de ingresos, siga estos pasos.

1. En la página **Programas de facturación (todas/activas)**, cree una programación de facturación.
2. En la línea de cada artículo configurado para división de ingresos, seleccione la casilla **División de ingresos**. Ese artículo se convierte en el artículo principal. Si la plantilla ya está configurada, los artículos secundarios aparecen automáticamente en la lista.
3. Para agregar más artículos secundarios, seleccione **Agregar elemento secundario de división de ingresos** y seleccione el artículo secundario que desea agregar.
4. Continúe con los pasos para trabajar con la programación de facturación.

> [!NOTE]
> Si la opción **Crear automáticamente división de ingresos** está configurada como **Sí** en la página **Parámetros de facturación periódica del contrato**, se realizarán las siguientes acciones:
>
> - Si el artículo de línea está configurado como artículo principal en una plantilla de división de ingresos, la casilla **División de ingresos** se seleccionará automáticamente.
> - Los artículos secundarios se ingresan automáticamente en el pedido de ventas o en la línea del programa de facturación.
>
> Si la opción **Crear automáticamente división de ingresos** está configurada como **No**, el comportamiento es el que se explicó anteriormente.

## <a name="additional-revenue-split-information"></a>Información adicional de división de ingresos

Cuando agrega un artículo que forma parte de una división de ingresos, tenga en cuenta la siguiente información: 

- El importe primario no puede ser diferido.
- Los valores de fecha de inicio, fecha de finalización, cantidad, unidad, sitio y almacén de los artículos secundarios se basan en el artículo principal. Estos valores no se pueden cambiar para los elementos secundarios. Todos los cambios deben realizarse en el elemento principal. 
- El método de fijación de precios es **Simple** y no se puede cambiar.
- Los elementos secundarios se pueden agregar o eliminar.
- Los elementos primarios y secundarios deben usar el mismo grupo de elementos. 
- Los elementos secundarios pueden tener una de las siguientes configuraciones:

    - Los campos **Frecuencia de facturación** e **Intervalos de facturación** se establecen en el mismo valor que el elemento principal. 
    - El campo **Frecuencia de facturación** es **Una vez**. En este caso, el campo **Intervalos de facturación** se establece automáticamente en **1**. 

- La suma de los importes netos de los artículos secundarios es igual al importe principal. Si el método de asignación es **Cantidades cero**, tanto la suma de los importes de los elementos secundarios como el importe principal son 0 (cero). 

    > [!NOTE]
    > Si el método de asignación es **Monto principal cero**, la suma (distinta de cero) de los elementos secundarios no es igual a la cantidad principal, que es 0 (cero). Este método de asignación se utiliza con fines internos, de modo que los empleados puedan ver los elementos secundarios. Sin embargo, los clientes solo pueden ver el artículo principal.

- Si el tipo de arreglo de elementos múltiples (MEA) de la orden de venta es **Único**, la línea de transacción de asignación de ingresos de elementos múltiples correspondiente se crea cuando se agregan los artículos principal y secundario. 
- Si el método de asignación para una división de ingresos es **Cantidades iguales** y se modifica el importe principal, se vuelven a calcular los importes para todas las líneas secundarias. 
- Para una división de ingresos donde el método de asignación es **Importe variable**, se produce el siguiente comportamiento:

    - El importe neto del artículo primario aparece en la columna **Importe primario**. Este valor se puede editar. Sin embargo, el precio unitario, el monto neto y el descuento son 0 (cero) y no se pueden editar.
    - El precio unitario de los artículos secundarios es 0 (cero). Puede editar el precio unitario o la cantidad neta. Cuando edita un valor, el otro valor se actualiza automáticamente.

- Para una división de ingresos donde el método de asignación es **Porcentaje**, se produce el siguiente comportamiento:

    - El importe neto del artículo primario aparece en la columna **Importe primario**. Este valor se puede editar. Sin embargo, el precio unitario, el monto neto y el descuento son 0 (cero) y no se pueden editar. 
    - La cantidad neta de elementos secundarios se calcula como *Porcentaje* &times; *Importe principal*.

- Para una división de ingresos donde el método de asignación es **Importe igual**, se produce el siguiente comportamiento:

    - El importe neto del artículo primario aparece en la columna **Importe primario**. Este valor se puede editar. Sin embargo, el precio unitario, el monto neto y el descuento son 0 (cero) y no se pueden editar. 
    - El importe neto de los elementos secundarios se calcula dividiendo el importe principal en partes iguales entre todos los elementos secundarios. 
    - Si se eliminan o agregan artículos secundarios, la cantidad neta y los precios unitarios se vuelven a calcular para que todas las líneas secundarias tengan cantidades iguales. 
    - Si el monto primario no se puede dividir en partes iguales, el monto neto y el precio unitario del último artículo secundario pueden ser un poco más o menos que el monto neto y el precio unitario de los otros artículos secundarios. 

- Para una división de ingresos donde el método de asignación es **Importe cero**, se produce el siguiente comportamiento:

    - El precio unitario, la cantidad neta y el descuento se pueden editar. El monto principal es 0 (cero) y no se puede editar. 
    - Los valores de cantidad, unidad, sitio y almacén de los artículos secundarios se basan en el artículo principal. Estos valores no se pueden cambiar para los elementos secundarios. Todos los cambios deben realizarse en el elemento principal. 
    - El precio unitario y el precio neto de los artículos secundarios es 0 (cero) y no se pueden editar. 

- Para una división de ingresos donde el método de asignación es **Importe primario cero**, se produce el siguiente comportamiento:

    - El precio de unidad, importe primario e importe neto del artículo primario son 0 (cero).
    - En un programa de facturación, las líneas secundarias aparecen como si se hubieran agregado manualmente y todos los valores se actualizan según el grupo de programación de facturación seleccionado. Estos valores se pueden editar. Para elementos secundarios, puede acceder a las opciones **Escalación y descuento** y **Precios avanzados** usando los campos **Cantidad ingresada**, **Precio unitario**, **Descuento** e **Importe neto** en **Ver detalles de facturación**. 
    - En un pedido de ventas, las líneas secundarias tienen un descuento y un porcentaje de descuento de 0 (cero). 
    - La frecuencia de facturación de los artículos principal y secundario se puede cambiar, y cada línea puede tener una frecuencia diferente. Sin embargo, el elemento primario se actualiza automáticamente para que use la frecuencia más corta entre sus líneas secundarias. Por ejemplo, una división de ingresos tiene dos elementos secundarios, uno de los cuales utiliza la frecuencia de facturación **Mensual** y el otro utiliza la frecuencia de facturación **Anual** frecuencia de facturación. En este caso, la frecuencia de facturación del artículo principal se actualiza a **Mensual**.
