---
title: Crear facturas de pago
description: Este artículo explica cómo crear facturas de arrendamiento mensual. Puede crear facturas para arrendamientos individuales o puede utilizar un proceso por lotes para crearlas para arrendamientos múltiples.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymentSchedule
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0ac9efaf6d068377053ae36951f4ad808fcb2438
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886431"
---
# <a name="create-payment-invoices"></a>Crear facturas de pago

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Puede crear facturas mensuales para arrendamientos individuales o puede utilizar un proceso por lotes para crearlas para arrendamientos múltiples. El siguiente procedimiento muestra cómo crear un asiento de pago de arrendamiento individual cuando el parámetro **Pagar al proveedor** de la página **Configuración del libro de arrendamiento** está activado.

1. En la página **Resumen de arrendamiento**, seleccione un arrendamiento y luego seleccione **Libros \> Programación de pagos**.
2. Seleccione el pago que se debe realizar y luego seleccione **Crear diario**. Recibe un mensaje que indica que se ha creado un diario con el pago seleccionado.
3. Seleccione **Diarios de facturas** y luego seleccione la factura que debe pagarse.
4. En la pestaña **Líneas**, revise la entrada del diario antes de registrarla en contabilidad.

    > [!NOTE]
    > De forma predeterminada, las líneas de factura de proveedor que se crean utilizan el perfil de contabilización de proveedor de la página **Parámetros de proveedores**.

5. Seleccione el diario correcto y luego seleccione la factura que debe pagarse.

    Para este ejemplo, el parámetro **Pagar al proveedor** del libro de arrendamiento está activado. Por lo tanto, la factura estará en el diario de facturas. La sección **Visión de conjunto** muestra un resumen de la entrada de diario y la sección **Líneas** muestra detalles de las líneas de diario reales.
    
   El sistema bloquea la edición de ciertos campos financieros para evitar variaciones entre las transacciones y los programas. Algunos campos que están bloqueados incluyen: **Cuenta**, **Cantidades**, **Dimensiones financieras**, **Divisa** y **Tipo de transacción**. Además, no podrá agregar o eliminar líneas de asientos de diario en los asientos de diario de arrendamiento de activos, ya que esto podría causar variaciones entre los horarios y las transacciones.

    > [!NOTE]
    > Si el parámetro **Pagar al proveedor** está desactivado, las entradas del diario de pagos se enumerarán en la página **Arrendamiento de activos** del libro de arrendamiento, y el sistema creará una entrada de arrendamiento de activos en lugar de una factura. La entrada de pago de arrendamiento se publicará en el nombre del diario que se especifica en el campo **Diario de arrendamiento mensual**.

6. Una vez que se registra la transacción, puede ver la información de la transacción y el valor en libros del pasivo por arrendamiento seleccionando **Transacciones de pasivo** en el libro de arrendamiento.

    En la programación de pagos, estará seleccionada la casilla **Diario publicado** y la línea mostrará el número de diario de facturas. Después de crear un diario de pagos y una entrada para ese diario, debe revertir la entrada antes de que pueda volver a crearse.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
