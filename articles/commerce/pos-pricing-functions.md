---
title: Funciones de precios en PDV
description: Este artículo describe varias funciones de precio y descuento en la aplicación de punto de venta (POS) de Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-14
ms.openlocfilehash: 210798ac192ee251594ec8ff9d23dab31ec2043e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473738"
---
# <a name="pricing-functions-in-pos"></a>Funciones de precios en PDV

[!include [banner](includes/banner.md)]

Este artículo describe varias funciones de precio y descuento en la aplicación de punto de venta (POS) de Microsoft Dynamics 365 Commerce.

La aplicación PDV de Dynamics 365 Commerce proporciona capacidades ricas que permiten a los trabajadores de primera línea realizar operaciones comerciales en tiendas. La siguiente tabla muestra las funciones de precio y descuento que están actualmente disponibles en la aplicación.

| Función                       | Operaciones de PDV |
|--------------------------------|----------------|
| Ver precios                    | [Comprobación de precio](#price-check) |
| Ver descuentos                 | [Ver todos los descuentos](#view-all-discounts)<br>[Ver descuentos disponibles](#view-available-discounts) |
| Anular precios                | [Anulación del precio](#price-override) |
| Aplicar o eliminar descuentos      | [Importe de descuento de línea](#line-discount-amount)<br>[Porcentaje de descuento de línea](#line-discount-percent)<br>[Importe de descuento total](#total-discount-amount)<br>[Porcentaje de descuento total](#total-discount-percent)<br>[Quitar descuentos del sistema de la transacción](#remove-system-discounts-from-transaction)<br>[Volver a aplicar descuentos del sistema](#reapply-system-discounts) |
| Aplicar o eliminar vales        | [Agregar código de vale](#add-coupon-code)<br>[Quitar código de vale](#remove-coupon-code) |
| Calcular precios y descuentos | [Volver a calcular](#recalculate) |

Para obtener información sobre cómo se pueden configurar las operaciones anteriores en la aplicación PDV y si admiten el modo fuera de línea, consulte [Operaciones de punto de venta (POS) en línea y fuera de línea](pos-operations.md).

## <a name="price-check"></a>Comprobación de precio

La operación **Comprobación de precio** permite a los usuarios de PDV buscar precios preconfigurados para un producto específico.

## <a name="view-all-discounts"></a>Ver todos los descuentos

La operación **Ver todos los descuentos** permite a los usuarios de POS buscar todas las promociones efectivas que se están ejecutando actualmente en el canal de la tienda. En concreto, esta operación enumera todos los descuentos que cumplen alguna de las siguientes condiciones:

- El grupo de precios del descuento coincide con el grupo de precios de la tienda.
- El grupo de precios del descuento se asigna a un programa de fidelización o afiliación.
- El grupo de precios del descuento se asigna a un catálogo asociado con la tienda.

La operación **Ver todos los descuentos** muestra solo descuentos que no compiten con ninguno de los descuentos ya aplicados. Este comportamiento ayuda a garantizar que, si un asociado de ventas informa a un cliente sobre un descuento, y el cliente toma la acción requerida (por ejemplo, el cliente compra un artículo más para obtener un 10 por ciento de descuento), el descuento se aplica a la transacción. Los descuentos basados en cupones se muestran solo si el parámetro **Aplicar sin un código de cupón** está activado.

Dentro de la operación **Ver todos los descuentos**, los usuarios de POS pueden buscar descuentos por nombre y descripción, y pueden filtrar los descuentos en función de si requieren un cupón.

## <a name="view-available-discounts"></a>Ver descuentos disponibles

La operación **Ver descuentos disponibles** permite a los usuarios de POS ver todos los descuentos que se aplican a una línea seleccionada en una transacción oa toda la transacción. Los descuentos que se aplican a una línea seleccionada incluyen descuentos que ya se aplicaron y descuentos que aún no se han aplicado pero que se pueden aplicar (por ejemplo, descuentos combinados que requieren artículos adicionales). Si un descuento aplicable está vinculado a un cupón donde el parámetro **Aplicar sin código de cupón** está activado, el usuario de POS también puede utilizar la función **Aplicar cupón** dentro de esta operación para canjear el cupón directamente, sin tener que ingresar o escanear ningún código de cupón o código de barra de cupón.

## <a name="price-override"></a>Anulación del precio

La operación **Anulación de precio** permite a los usuarios de POS anular el precio de venta de un producto en una transacción. Esta operación solo funciona para productos que están configurados para permitir anulaciones de precios.

## <a name="line-discount-amount"></a>Importe de descuento de línea

La operación **Cantidad de descuento de línea** permite a los usuarios de PDV ingresar un monto de descuento para un artículo de línea en una transacción. Esta operación se aplica sólo a artículos con descuento y respeta el valor **Importe máximo de descuento de línea** que se especifica en el grupo de permisos de PDV para el usuario.

## <a name="line-discount-percent"></a>Porcentaje de descuento de línea

La operación **Porcentaje de descuento de línea** permite a los usuarios de PDV ingresar un porcentaje de descuento para un artículo de línea en una transacción. Esta operación se aplica sólo a artículos con descuento y respeta el valor **Porcentaje máximo de descuento de línea** que se especifica en el grupo de permisos de PDV para el usuario.

## <a name="total-discount-amount"></a>Importe de descuento total

La operación **Cantidad de descuento total** permite a los usuarios de PDV ingresar un monto de descuento para una transacción. Esta operación se aplica sólo a artículos con descuento y respeta el valor **Importe máximo de descuento total** que se especifica en el grupo de permisos de PDV para el usuario. Si el monto del descuento que se ingresa excede el monto total máximo del descuento, la operación se bloquea y no se activa ningún flujo de anulación de permisos. Actualmente, no se puede aplicar un monto de descuento total a un carrito que tiene una combinación de artículos de venta y artículos devueltos.

## <a name="total-discount-percent"></a>Porcentaje de descuento total

La operación **Porcentaje de descuento total** permite a los usuarios de PDV ingresar un porcentaje de descuento para una transacción. Esta operación se aplica sólo a artículos con descuento y respeta el valor **Porcentaje máximo de descuento total** que se especifica en el grupo de permisos de PDV para el usuario. Si el porcentaje del descuento que se ingresa excede el porcentaje total máximo del descuento, la operación se bloquea y no se activa ningún flujo de anulación de permisos. Actualmente, no se puede aplicar un porcentaje de descuento total a un carrito que tiene una combinación de artículos de venta y artículos devueltos.

## <a name="remove-system-discounts-from-transaction"></a>Quitar descuentos del sistema de la transacción

La operación **Eliminar descuentos del sistema de la transacción** permite a los usuarios de POS borrar todos los descuentos del sistema aplicados (incluidos los descuentos basados en cupones) de una transacción. Después de realizar esta operación, el motor de precios comienza a excluir los descuentos del sistema del alcance del cálculo de descuentos. La operación **Eliminar descuentos del sistema de la transacción** no elimina los descuentos manuales.

## <a name="reapply-system-discounts"></a>Volver a aplicar descuentos del sistema

La operación **Reaplicar descuentos del sistema** permite a los usuarios de POS volver a aplicar descuentos calculados por el sistema a una transacción si los descuentos se eliminaron mediante la operación **Eliminar descuentos del sistema de la transacción**. Después de realizar esta operación, el motor de precios comienza a incluir todos los descuentos del sistema en el alcance del cálculo de descuentos.

## <a name="add-coupon-code"></a>Agregar código de vale

La operación **Añadir código de cupón** permite a los usuarios de POS agregar un cupón a una transacción ingresando un código de cupón. Alternativamente, los usuarios de PDV pueden escanear el código de barras de un vale o introducirlo usando el teclado numérico en la pantalla **Transacción**.

## <a name="remove-coupon-code"></a>Quitar código de vale

La operación **Eliminar código de cupón** permite a los usuarios de POS seleccionar y eliminar uno o más cupones que se aplican actualmente a una transacción.

## <a name="recalculate"></a>Volver a calcular

La operación **Recalcular** permite a los usuarios de PDV activar el cálculo de precios a pedido. Esta operación es necesaria cuando está habilitado el bloqueo de precio y/o el cálculo de precio retrasado, y el usuario de POS desea volver a calcular precios y descuentos después de cambios en el carrito o en el pedido. La operación **Recalcular** siempre recalcula todo el pedido. No se puede utilizar para volver a calcular las líneas de ventas seleccionadas. Para aplicar descuentos manuales a una línea de ventas bloqueada en POS, los usuarios de POS primero deben usar la operación **Recalcular** para desbloquear todas las líneas de venta.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
