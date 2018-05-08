--- 
title: "Crear una orden de domiciliación bancaria para un cliente"
description: "Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d01c7c19925a3c7064ab3f845b92b610b162066c
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Crear una orden de domiciliación bancaria para un cliente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de tarea muestra cómo crear una orden de domiciliación bancaria y cómo usarla en una factura.


## <a name="create-a-bank-account"></a>Creación de una cuenta bancaria
1. Vaya a Clientes > Clientes > Todos los clientes.
2. Por ejemplo, seleccione US-001.
3. En el panel de acciones, haga clic en Clientes.
4. Haga clic en Cuentas bancarias.
5. Haga clic en Nuevo.
6. En el campo Cuenta bancaria, escriba un valor.
7. En el campo Nombre, escriba un valor.
8. Escriba un valor en el campo IBAN.
9. En el campo Divisa, escriba un valor.
10. Haga clic en Guardar.
11. Cierre la página.
12. Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.
13. En la lista, busque y seleccione el registro deseado.
14. En la lista, haga clic en el vínculo de la fila seleccionada.
15. Haga clic en Editar.
16. Expanda la sección Identificación adicional.
17. En el campo Id. de domiciliación bancaria, especifique un valor.
18. Escriba un valor en el campo IBAN.
19. Cierre la página.
20. Cierre la página.

## <a name="define-the-electronic-payment-method"></a>Definición de la forma de pago electrónico
1. Vaya a Clientes > Configuración de pagos > Formas de pago.
2. Haga clic en Nuevo.
3. En el campo Forma de pago, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. El tipo de pago para un método de pago de orden de domiciliación bancaria debe ser Pago electrónico.
6. Seleccione Sí en el campo Requerir orden.
7. Cierre la página.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Agregue una orden de domiciliación bancaria a un cliente.
1. Vaya a Clientes > Clientes > Todos los clientes.
2. Por ejemplo, seleccione US-001.
3. Haga clic en Editar.
4. Expanda la sección Valores predeterminados de pago.
5. En el campo Método de pago, especifique o seleccione un valor.
6. Expanda la sección Valores predeterminados de pago.
7. Expanda la sección Órdenes de domiciliación bancaria.
8. Haga clic en Agregar.
9. En el campo Cuenta bancaria, especifique o seleccione un valor.
10. En el campo Cuenta bancaria de acreedor, especifique o seleccione un valor.
11. Especifique el número de pagos que se prevén para procesar esta orden.
12. Haga clic en Aceptar
13. Haga clic en Imprimir.
14. Haga clic en Informe de orden.
15. Cierre la página.
16. Haga clic en Editar.
17. En el campo Fecha de firma, especifique una fecha.
18. Haga clic en Sí.
19. Especifique la ubicación donde se firmó la orden.
20. Haga clic en Aceptar
21. Cierre la página.

## <a name="create-a-free-text-invoice-with-mandate"></a>Creación de una factura de texto libre con una orden
1. Vaya a Clientes > Facturas > Todas las facturas de servicios.
2. Haga clic en Nuevo.
3. Seleccione el cliente al que haya agregado la orden.
4. En el campo Id. de proyecto, especifique o seleccione un valor.


