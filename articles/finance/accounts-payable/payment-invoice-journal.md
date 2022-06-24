---
title: Aplicar un programa de pago al diario de facturas
description: Este artículo describe cómo agregar un pago al diario de facturas de proveedores.
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f3ae08ea46be66dd8bf26f7f91bd73f6c5b9192f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863141"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Aplicar un programa de pago al diario de facturas

[!include [banner](../includes/preview-banner.md)]

En Microsoft Dynamics 365 Finance versión 10.0.25, ahora se admite un cronograma de pago en el **Diario de facturas del proveedor**.

Para utilizar esta función, debe habilitar la función **Aplicar programa de pagos al diario de facturas** en Gestión de funciones.

Una vez habilitada la función, se agrega un nuevo campo **Calendario de pago** a la página **Diario de facturas**. Cuando crea una línea de diario de facturas, si las condiciones de pago se mantienen en el proveedor y las condiciones de pago se seleccionan en el programa de pagos, el campo **Calendario de pago** se actualiza en la página **Diario de facturas**.

Puede cambiar el cronograma de pago que se utiliza, de acuerdo con los requisitos de su negocio. Durante la contabilización del diario de facturas de proveedor, se crearán transacciones abiertas de proveedor de acuerdo con la programación de pagos.

 - Para revisar múltiples transacciones abiertas de proveedores que se generaron a partir del cronograma de pagos, vaya a **Cuentas por pagar \> Facturas \> Abrir facturas de proveedor** e introduzca el número de factura o la cuenta de proveedor.
 - Para revisar o configurar el calendario de pagos, vaya a **Cuentas por pagar \> Configuración de pago \> Calendario de pago**.
 - Para configurar las condiciones de pago y asignar un cronograma de pago, vaya a **Cuentas por pagar \> Configuración de pago \> Condiciones de pago**.
 - Para actualizar las condiciones de pago de un proveedor, vaya a **Cuentas por pagar \> Todos los proveedores**, seleccione la cuenta de proveedor y, a continuación, en la pestaña **Pago**, configure el campo **Condiciones de pago**.

La función de programación de pagos también está disponible en el proceso **Registro de facturas de proveedores**. Si se selecciona un programa de pago en el diario de registro de facturas, varias líneas de pago de proveedor **no** generarse cuando se contabiliza el registro de facturas. Las líneas de pago del proveedor se generarán cuando se apruebe la factura.

## <a name="limitation"></a>Limitación

Para una factura de proveedor pendiente, si el programa de pago está en el encabezado de la factura, hay una página avanzada que permite a los usuarios editar las líneas de pago. (Por ejemplo, los usuarios pueden editar la fecha de vencimiento y el valor de cada línea de pago). Las líneas de pago que se generan a partir del diario de facturas tendrán el valor del programa de pagos.

Esta funcionalidad estará disponible para el **Diario de facturas de proveedores** y las **Facturas pendientes** en una versión futura.
