---
title: Soporte y renovaciones
description: Este artículo explica cómo configurar y utilizar el proceso de soporte y renovación en pedidos de ventas para crear una programación de facturación para artículos de renovación.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: b40e0136883d909755480a3ce101627297bd9ffb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896532"
---
# <a name="support-and-renewals"></a>Soporte y renovaciones 

Este artículo explica cómo introducir artículos de soporte o artículos de renovación al entrar en los pedidos de ventas. Estos elementos se usan para calcular el importe del cargo del contrato de soporte original y/o el importe de renovación que se usa cuando se crea una programación de facturación en la facturación de suscripción. Por ejemplo, su empresa vende un servidor a un cliente y ofrece una suscripción de respaldo de datos para el primer año y la opción de renovar esa suscripción cada año. El *elemento de soporte* es la suscripción para el primer año, y el *artículo de renovación* es la renovación por cada año sucesivo.

Puede introducir información para el contrato de soporte, el contrato de renovación o ambos. Cuando introduce la información del contrato de soporte, solo se agrega el artículo de soporte al pedido de ventas. Cuando introduce la información del contrato de renovación, el elemento de renovación se usa para crear una programación de facturación.

## <a name="support-and-renewal-setup"></a>Configuración de soporte y renovación

En la página **Niveles de soporte y renovación**, puede configurar diferentes niveles de soporte para elementos de soporte y renovación. El soporte o renovación puede ser un porcentaje del importe del artículo original, o puede ser un importe estándar.

Puede seleccionar los niveles de soporte predeterminados en la página **Parámetros de facturación de contratos periódicos**.

Por ejemplo, una empresa podría ofrecer los siguientes niveles de soporte y renovación.

| Nivel de soporte | Porcentaje de soporte | Porcentaje de renovación |
|---|---|---|
| Ilimitado | 40% | 30% |
| Oro | 25 % | 18 % |
| Plata | 20% | 14 % |
| Bronce | 15 % | 10% |

Para crear un nivel de soporte o renovación, siga estos pasos.

1. En la página **Niveles de soporte y renovación**, seleccione **Nuevo**.
2. En el campo **Nivel de soporte**, especifique un nombre único.
3. En el campo **Descripción**, escriba una descripción.
4. En el campo **Método de cálculo de soporte**, seleccione el método de cálculo de soporte. Si selecciona **Porcentaje**, introduzca un porcentaje de soporte en el campo **Porcentaje de soporte**.
5. En el campo **Método de cálculo de renovación**, seleccione el método de cálculo de renovación. Si selecciona **Porcentaje**, introduzca un porcentaje de renovación en el campo **Porcentaje de renovación**.
6. Seleccione **Guardar**.

### <a name="fields"></a>Campos

La página **Niveles de soporte y renovación** contiene los siguientes campos.

| Campo | Description |
|---|---|
| Nivel de soporte | Un identificador único para el nivel de soporte o renovación (por ejemplo, **Oro** o **Plata**). |
| Description | Una descripción del nivel de soporte o renovación. |
| Método de cálculo de soporte | Seleccione el método de cálculo de soporte para el nivel: **Porcentaje** o **Importe estándar**. |
| Porcentaje de soporte | Si seleccionó **Porcentaje** como método de cálculo de soporte, especifique el porcentaje que se utiliza para calcular el precio del artículo de soporte. Si seleccionó **Importe estándar** como método de cálculo, la cantidad se especifica cuando se crea la transacción. |
| Método de cálculo de renovación | Seleccione el método de cálculo de renovación para el nivel: **Porcentaje** o **Importe estándar**. |
| Porcentaje de renovación | Si seleccionó **Porcentaje** como método de cálculo de renovación, especifique el porcentaje que se utiliza para calcular el precio del artículo de renovación. Si seleccionó **Importe estándar** como método de cálculo, la cantidad se especifica cuando se crea la transacción. |

## <a name="support-and-renewal-process"></a>Proceso de soporte y renovación

La funcionalidad de soporte y renovación puede aplicar diferentes niveles de soporte a los artículos y actualizar la información de renovación en la facturación de suscripción.

Antes de utilizar la funcionalidad de soporte y renovación, se deben completar las siguientes tareas.

1. En la página **Niveles de soporte y renovación**, cree al menos un nivel de soporte o renovación.
2. En la página **Configuración del artículo**, asocie un artículo con los artículos de soporte y renovación. Esta tarea es necesaria solo si desea configurar valores predeterminados para elementos de soporte y/o renovación.
3. En la página **Parámetros de facturación de contratos periódicos**, especifique la configuración predeterminada de soporte y renovación para las nuevas programaciones de facturación.

Para aplicar diferentes niveles de soporte a artículos y actualizar la información de renovación, siga estos pasos.

1. En la página **Todos los pedidos de ventas**, cree un pedido de ventas.
2. En la ficha desplegable **Líneas de pedido de ventas**, agregue un artículo.
3. En la pestaña **Factura**, seleccione **Soporte y renovación \> Agregar soporte y renovación**.
4. En la página **Proceso de soporte y renovación**, la sección de encabezado se actualiza con la configuración de la página **Parámetros de facturación de contratos periódicos**. Estos valores se aplican a todos los artículos de soporte y renovación. (Por ejemplo, si la frecuencia de facturación se establece en **Anualmente**, todas las líneas de ventas que se crean que tienen un artículo de renovación tienen una frecuencia anual). Para asociar el pedido de ventas con una programación de facturación existente, seleccione un valor en el campo **Número de programación de facturación**.
5. Para cambiar la fecha de inicio de la renovación o del soporte, configure la opción **Anular fecha de inicio** en **Sí**.
6. Para agregar o editar el elemento de soporte, seleccione la casilla **Soporte** y, a continuación, introduzca un elemento de soporte en el campo **Artículo de soporte**. El artículo se agrega al pedido de ventas.
7. Para agregar o editar el elemento de renovación, seleccione la casilla **Renovación** y, a continuación, introduzca un elemento de renovación en el campo **Artículo de renovación**. Cuando se facture la orden de venta, se creará una programación de facturación que incluye el artículo.
8. Seleccione **Aceptar**.
9. En la pestaña **General**, seleccione **Factura**. Cuando se contabiliza el pedido de ventas, se crea la programación de facturación. Aparece una notificación que incluye la información de la programación de facturación en los detalles del mensaje.
10. En la página de lista **Programaciones de facturación en su totalidad/activas**, seleccione el número de la programación de facturación para revisar los detalles de la programación de facturación en la página **Programaciones de facturación**.
11. En la ficha desplegable **Líneas de programación de facturación**, seleccione **Soporte y renovación** para revisar los detalles de las líneas que se crearon.

> [!NOTE]
> Si se debe cambiar la fecha de inicio de renovación para una línea de la programación de facturación, puede editar el valor **Fecha de inicio** de la línea en la página **Programaciones de facturación**. Cuando abre la página **Ver detalle de facturación** de la línea, el campo **Fecha de inicio de facturación** se actualiza con la nueva fecha. El valor **Fecha de finalización de facturación** se vuelve a calcular en función de la frecuencia de facturación. La fecha de inicio de la renovación solo se puede actualizar si no se ha creado ni registrado la primera factura de la programación de facturación de renovación. Después de crear y registrar la primera factura, no se puede editar la fecha de inicio.

El proceso de soporte y renovación está disponible solo para el pedido de ventas. Cuando agrega artículos de soporte y renovación a un pedido de ventas, puede crear una nueva programación de facturación o agregar el artículo de renovación a una programación de facturación existente.

## <a name="support-and-renewal-audit"></a>Auditoría de soporte y renovación

En la página **Auditoría de soporte y renovación**, puede revisar los detalles de las líneas de la programación de facturación que se crean a partir del artículo de renovación en un pedido de ventas. Esta opción está disponible solo cuando el elemento de línea de la programación de facturación es un elemento de renovación.

Para editar la información de soporte y renovación para una línea de programación de facturación, siga estos pasos.

1. En la página **Todas las programaciones de facturación**, seleccione el número de programación de facturación.
2. En la sección **Líneas de programación de facturación**, seleccione una línea y luego seleccione **Soporte y renovación**.
3. Revise toda la información del artículo de soporte o renovación.
4. Realice los cambios necesarios en el nivel de soporte, o el porcentaje o importe de renovación, y luego introduzca un valor en el campo **Razón para el cambio**.
5. Seleccione **Procesar**.

### <a name="fields"></a>Campos

La página **Auditoría de soporte y renovación** contiene los siguientes campos.

| Campo | Description |
|-------|-------------|
| Número de artículo | El número de artículo para la línea de programación de facturación. |
| Nombre de producto | Nombre de producto. |
| Nivel de plan de soporte | Vea o cambie el nivel de soporte para el artículo de renovación. |
| Porcentaje de renovación | Introduzca el porcentaje de renovación que se usa cuando se calcula el precio unitario para un artículo de renovación en una programación de facturación. |
| Importe de renovación | Introduzca el importe de renovación que se usa cuando se calcula el precio unitario para un artículo de renovación en una programación de facturación. |
| Razón del cambio | Introduzca su razón para cambiar la información de soporte y renovación. Debe introducir una razón al cambiar el valor del **Porcentaje de renovación**, la **Cantidad de renovación** o el **Nivel de plan de soporte**. |
| Artículo de ventas original | El número de artículo de ventas original del pedido de ventas. |
| Importe neto original | El importe neto original del artículo. |
| Nivel de soporte original | El nivel de soporte original del artículo. |
| Porcentaje de renovación original | El porcentaje de renovación original del artículo. |
| Importe de renovación original | El importe de renovación original del artículo. |
| **Cuadrícula** | |
| Nivel de soporte original | El nivel de soporte anterior. |
| Porcentaje de renovación original | El porcentaje de renovación anterior. |
| Importe de renovación original | El importe de renovación anterior. |
| Modificado por | El nombre del usuario que ha realizado el cambio. |
| Fecha y hora de modificación | La fecha en que se produjo el cambio. |
| Motivo | El motivo del cambio. |
