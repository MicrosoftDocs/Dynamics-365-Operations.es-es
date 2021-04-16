---
title: Crear una orden de domiciliación bancaria para un cliente
description: Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3bbf3703941255dfd82b8fb501ba8a9d1f3a2ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835085"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Crear una orden de domiciliación bancaria para un cliente

[!include [banner](../../includes/banner.md)]

Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura.


## <a name="create-a-bank-account"></a>Creación de una cuenta bancaria
1. En el **Panel de exploración**, vaya a **Módulos > Clientes > Clientes > Todos los clientes**.
2. En la lista, seleccione un registro. Por ejemplo, seleccione US-001.
3. En el panel de acciones, haga clic en **Clientes**.
4. Haga clic en **Cuentas bancarias**.
5. Haga clic en **Nuevo**.
6. En el campo **Cuenta bancaria**, escriba un valor.
7. En el campo **Nombre**, escriba un valor.
8. Escriba un valor en el campo **IBAN**.
9. En el campo **Divisa**, escriba un valor.
10. Haga clic en **Guardar**.
11. Cierre la página.
12. En el **Panel de exploración**, vaya a **Módulos > Gestión de efectivo y bancos > Cuentas bancarias > Cuentas bancarias**.
13. En la lista, busque y seleccione el registro deseado.
14. En la lista, haga clic en el vínculo de la fila seleccionada.
15. Haga clic en **Editar**.
16. Expanda la ficha desplegable **Identificación adicional**.
17. En el campo **Id. de domiciliación bancaria**, especifique un valor.
18. Escriba un valor en el campo **IBAN**.
19. Cierre la página.
20. Cierre la página.

## <a name="define-the-electronic-payment-method"></a>Definición de la forma de pago electrónico
1. En el **Panel de exploración**, vaya a **Módulos > Clientes > Configuración de pagos > Métodos de pago**.
2. Haga clic en **Nuevo**.
3. En el campo **Método de pago**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Tipo de pago**, seleccione "Pago electrónico". El tipo de pago para un método de pago de orden de domiciliación bancaria debe ser Pago electrónico.
6. Seleccione Sí en el campo **Requerir orden**.
7. Cierre la página.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Agregue una orden de domiciliación bancaria a un cliente.
1. En el **Panel de exploración**, vaya a **Módulos > Clientes > Clientes > Todos los clientes**.
2. En la lista, seleccione un registro. Por ejemplo, seleccione US-001.
3. Haga clic en **Editar**.
4. Expanda la ficha desplegable **Valores predeterminados de pago**.
5. En el campo **Método de pago**, especifique o seleccione un valor.
6. Expanda la ficha desplegable **Valores predeterminados de pago**.
7. Expanda la ficha desplegable **Órdenes de domiciliación bancaria**.
8. Haga clic en **Agregar**.
9. En el campo **Cuenta bancaria**, especifique o seleccione un valor.
10. En el campo **Cuenta bancaria de acreedor**, especifique o seleccione un valor.
11. En el campo **Frecuencia de pago**, especifique el número de pagos que se prevén para procesar esta orden.
12. Haga clic en **Aceptar**.
13. Haga clic en **Imprimir**.
14. Haga clic en **Informe de orden**.
15. Cierre la página.
16. Haga clic en **Editar**.
17. En el campo **Fecha de firma**, especifique una fecha.
18. Haga clic en **Sí**.
19. Especifique la ubicación donde se firmó la orden.
20. Haga clic en **Aceptar**.
21. Cierre la página.

## <a name="create-a-free-text-invoice-with-mandate"></a>Creación de una factura de texto libre con una orden
1. En el **Panel de exploración**, vaya a **Módulos > Clientes > Facturas > Todas las facturas de servicios**.
2. Haga clic en **Nuevo**.
3. Seleccione el cliente al que haya agregado la orden.
4. En el campo **Id. de orden de domiciliación bancaria**, especifique o seleccione un valor.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]