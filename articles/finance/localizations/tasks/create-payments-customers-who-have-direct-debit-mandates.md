---
title: Crear pagos para un cliente con órdenes de domiciliación bancaria
description: Este procedimiento muestra cómo generar un archivo de pago por domiciliación bancaria ISO20022 para un cliente que tiene la domiciliación bancaria configurada y una factura que debe pagarse.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a4714f1f1b24554684219fc1d766b4b87cff7bb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447703"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a>Crear pagos para un cliente con órdenes de domiciliación bancaria

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo generar un archivo de pago por domiciliación bancaria ISO20022 para un cliente que tiene la domiciliación bancaria configurada y una factura que debe pagarse. Crear y enviar una factura es opcional. En lugar de tener una factura a pagar puede seleccionar una orden en un diario antes de generar un archivo de pago para admitir una situación de pago por adelantado del cliente.



La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.



Este es el quinto de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos. Debe completar todas las tareas previas antes de poder completar esta tarea. Primero debe importar las configuraciones de informes electrónicos de pagos de cliente, configurar el método de pago y la información de su empresa y de los clientes. 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a>Registrar una factura de servicios con información de orden de domiciliación bancaria
1. Vaya a Clientes > Facturas > Todas las facturas de servicios.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, especifique o seleccione un valor.
    * Por ejemplo, seleccione DE-010.  
4. En el campo Método de pago, especifique o seleccione un valor.
    * Por ejemplo: seleccione Electrónico.  
5. En el campo Id. de proyecto, especifique o seleccione un valor.
6. Haga clic en Agregar línea.
7. En el campo Descripción, escriba un valor.
8. En el campo Cuenta principal, especifique los valores deseados.
9. En el campo Precio unitario, escriba un número.
10. Haga clic en Registrar.
11. Haga clic en Aceptar

## <a name="create-a-payment"></a>Crear un pago
1. Vaya a Clientes > Pagos > Diario de pagos.
2. Haga clic en Nuevo.
3. En el campo Nombre, especifique o seleccione un valor.
4. Haga clic en Líneas.
5. Haga clic en Propuesta de pago.
6. Haga clic en Crear propuesta de pago.
7. Expanda la sección Registros que incluir.
8. Haga clic en Filtro.
9. En la lista, seleccione la fila para la tabla Transacciones de cliente y el campo Forma de pago.
    * Puede aplicar cualquier criterio para seleccionar transacciones de cliente para pagar. Para este ejemplo, utilice Electrónico como método de pago para filtrar transacciones.  
10. En el campo Criterios, especifique o seleccione un valor.
11. Haga clic en Aceptar.
12. Haga clic en Aceptar.
13. Haga clic en Crear pagos.
