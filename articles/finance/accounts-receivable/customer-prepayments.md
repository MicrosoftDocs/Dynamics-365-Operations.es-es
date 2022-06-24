---
title: Anticipos del cliente
description: Este artículo explica cómo configurar y procesar los anticipos del cliente (también llamados depósitos del cliente).
author: twheeloc
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88773067c472471fb75167712268d1076c1738a5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861571"
---
# <a name="customer-prepayments"></a>Anticipos del cliente

[!include [banner](../includes/banner.md)]

Los anticipos del cliente se utilizan cuando recibe un pago de un cliente, pero no hay ninguna factura con la que se pueda liquidar el pago. Estos tipos de pagos también se conocen como depósitos del cliente.

El proceso de configuración y trabajo con anticipos de clientes consta de los siguientes pasos básicos.

1. Cree un perfil de registro de cliente para anticipos.
2. Elija el parámetro **Perfil de registro con asiento del diario de anticipos**.
3. Cree un diario de pagos del cliente y seleccione la casilla **Asiento del diario de anticipos** en cada línea.
4. Registre el diario de pagos del cliente.
5. Una vez generada una factura, liquide el anticipo con ella mediante la página **Liquidar transacciones abiertas**.

## <a name="create-a-customer-posting-profile-for-prepayments"></a>Crear un perfil de registro de cliente para anticipos

Por lo general, cuando acepta anticipos o depósitos de sus clientes antes de que se entreguen los bienes o servicios o antes de que exista una factura en su sistema, querrá registrar el efectivo como un pasivo en lugar de un activo en su plan de cuentas. Sin embargo, los requisitos para registrar estos importes en su contabilidad general pueden diferir según su país o región. Por lo tanto, asegúrese de consultar a sus contables sobre las regulaciones locales que se apliquen.

En general, el proceso para crear un perfil de contabilización que se puede utilizar para anticipos es el mismo que el proceso para crear otros perfiles de contabilización. La principal diferencia es la cuenta principal que selecciona en el campo **Extracto de cuenta**. Para obtener más información, consulte [Perfiles de contabilización del cliente (formulario)](customer-posting-profiles.md).

## <a name="define-parameters-for-customer-prepayments"></a>Definir parámetros para anticipos de clientes

Hay dos parámetros principales de clientes que debe tener en cuenta al configurar el sistema para anticipos de clientes. Siga estos pasos para configurar los parámetros.

1. Vaya a **Clientes \> Configuración \> Parámetros de clientes**.
2. Opcional: en la pestaña **Impuestos y contabilidad**, en la ficha desplegable **Pago**, establezca la opción **Impuestos sobre el asiento del diario de anticipos** en **Sí**.
3. En el campo **Perfil de registro con asiento del diario de anticipos**, seleccione el perfil de contabilización del cliente que se utilizará cuando se registren los anticipos del cliente.
4. Cierre la página.

## <a name="create-customer-prepayment-vouchers"></a>Crear asientos de anticipos de clientes

Cuando crea el diario de pagos del cliente, para cada anticipo debe establecer la opción **Asiento del diario de anticipos** a **Sí** en la página **Diario de pagos de clientes**. Para crear un anticipo de cliente, siga estos pasos.

1. Vaya a **Clientes \> Pagos \> Diario de pagos de clientes**.
2. Seleccione **Nuevo** para crear un diario.
3. En el campo **Nombre**, seleccione el nombre de diario que usar.

    > [!IMPORTANT]
    > Si estableció la opción **Impuestos sobre el asiento del diario de anticipos** a **Sí** en el procedimiento anterior, debe seleccionar un nombre de diario donde el parámetro **Importe incluye impuesto de venta** esté seleccionado. 

4. Opcional: puede introducir una descripción detallada en el campo **Descripción**.
5. Seleccionar **Líneas**.
6. Si no existe una línea en blanco, seleccione **Nuevo** para crear una línea.
7. En el campo **Fecha**, introduzca la fecha en la que se debe publicar la entrada de anticipo.
8. En el campo **Cuenta**, seleccione el cliente para el anticipo.
9. Opcional: puede introducir una descripción detallada de la transacción en el campo **Descripción**.
10. En el campo **Crédito**, especifique el importe del anticipo.
11. En el campo **Cuenta de contrapartida**, seleccione la cuenta de contrapartida del pago. Por ejemplo, seleccione el banco o la cuenta principal para registrar el pago.
12. En el campo **Método de pago**, seleccione el método de pago del cliente.
13. En la pestaña **Pago** , establezca la opción **Asiento del diario de anticipos** a **Sí**.
14. Repita los pasos del 7 al 13 para cada anticipo adicional que deba registrarse.
15. Seleccione **Registrar** para terminar el diario.

## <a name="settle-prepayments-with-invoices"></a>Liquidar anticipos con facturas

Puedes usar el espacio de trabajo **Pagos de clientes** para encontrar y liquidar fácilmente los pagos que no se han liquidado por completo.

1. En el panel **Inicio**, seleccione el icono **Pagos de clientes**.
2. En la sección **Transacciones de clientes**, en la pestaña **Pagos no liquidados**, busque y seleccione el pago a liquidar.
3. Seleccione **Liquidar transacciones**.
4. Selecciona la casilla **Marcar** para la factura y el pago que se liquidarán.
5. Seleccione **Registrar**.

Para obtener más información sobre cómo liquidar transacciones abiertas, consulte [Descripción de la liquidación](/dynamics365/finance/cash-bank-management/settlement-overview).
