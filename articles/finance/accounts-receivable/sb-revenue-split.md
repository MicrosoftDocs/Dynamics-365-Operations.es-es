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
ms.openlocfilehash: 5c2eb6c8e18770eb149c445f662ab7a90aad81a7
ms.sourcegitcommit: 367e323bfcfe41976e5d8aa5f5e24a279909d8ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "8660462"
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
