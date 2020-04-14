---
title: Configuración de clientes y cuentas bancarias de cliente para domiciliaciones bancarias ISO20022
description: Esta tarea le guía por el procedimiento de configuración de una cuenta bancaria de cliente y una orden de domiciliación bancaria de cliente, necesarias para generar el archivo de pago de cliente como la domiciliación bancaria ISO20022.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0b09d7d203f1bb58fad26a109962005affa6d307
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144916"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>Configuración de clientes y cuentas bancarias de cliente para domiciliaciones bancarias ISO20022

[!include [banner](../../includes/banner.md)]

Esta tarea le guía por el procedimiento de configuración de una cuenta bancaria de cliente y una orden de domiciliación bancaria de cliente, necesarias para generar el archivo de pago de cliente como la domiciliación bancaria ISO20022. En función de los formatos de pago del cliente configurados, la información adicional, que no se cubren en este procedimiento, puede ser necesaria para un cliente o una cuenta bancaria de cliente. 

Esta tarea se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal de entidad jurídica en Alemania.



Este es el cuarto de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.


## <a name="set-up-a-customer-bank-account"></a>Configuración de una cuenta bancaria de cliente
1. Vaya a Clientes > Clientes > Todos los clientes.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Cuenta, por el valor "DE-010".
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el panel de acciones, haga clic en Clientes.
5. Haga clic en Cuentas bancarias.
6. Haga clic en Nuevo.
7. En el campo Cuenta bancaria, escriba un valor.
8. En el campo Nombre, escriba un valor.
    * Por ejemplo, especifique "Banco EUR".  
9. En el campo Grupos de bancos, especifique o seleccione un valor.
10. Escriba un valor en el campo IBAN.
    * Por ejemplo, escriba "DE36200400000628808808".  
11. En el campo Código SWIFT, escriba un valor.
    * Por ejemplo, especifique "COBADEFFXXX".  Tenga en cuenta que no requiere SWIFT\BIC para muchos formatos de pago, aunque se recomienda tenerlos registrados para una cuenta bancaria.  
12. Haga clic en Guardar.
13. Cierre la página.
14. Haga clic en Editar.
15. Expanda la sección Valores predeterminados de pago.
16. En el campo Cuenta bancaria, especifique o seleccione un valor.

## <a name="add-a-direct-debit-mandate"></a>Adición de una orden de domiciliación bancaria
1. Expanda la sección Órdenes de domiciliación bancaria.
2. Haga clic en Agregar.
3. En el campo Cuenta bancaria de acreedor, especifique o seleccione un valor.
    * Por ejemplo, seleccione DEMF OPER.  
4. En el campo Fecha de firma, especifique una fecha.
5. Haga clic en Sí para confirmar la actualización de la fecha.
6. En el campo Ubicación de firma, especifique o seleccione un valor.
7. En el campo Número esperado de pagos, especifique un número.
8. Haga clic en Aceptar
9. Haga clic en Guardar.

