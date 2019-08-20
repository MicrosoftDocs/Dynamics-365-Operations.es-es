---
title: Establecer método de pago de cliente
description: Creación de una forma de pago para pagos de clientes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 477f1ff72fd8012c3403d22aa128d97e45d5559f
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842914"
---
# <a name="establish-customer-method-of-payment"></a>Establecer método de pago de cliente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Creación de una forma de pago para pagos de clientes. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Clientes > Configuración de pagos > Formas de pago.
2. Haga clic en Nuevo.
3. En el campo Forma de pago, especifique un Id. para la forma de pago.
    * El id. de método de pago se muestra en las facturas y los pagos, por lo que debe escribir uno bastante descriptivo para comprender qué tipo de pago se registra y para qué cuenta bancaria.  
4. En el campo Descripción, escriba una descripción.
5. Seleccione qué estado de pago es necesario para que los pagos se registren.
    * Al crear un pago de cliente, solo se puede registrar cuando el estado de pago coincide con el estado de pago que se define aquí.  
6. Seleccione cómo se deben crear los pagos de los clientes para las facturas.
    * Esta opción solo se usa al ejecutar una propuesta de pago. Se podría usar una propuesta de pago para los pagos del cliente al realizar débitos directos y si se retiran los fondos de las cuentas bancarias de los clientes.  
7. Seleccione el tipo de pago.
    * El tipo de pago ayudará a determinar si se producirá o no alguna validación en el pago.  
8. Seleccione en qué tipo de cuenta se registrarán los pagos.
    * Normalmente, el banco se seleccionará para esta opción.  
9. Seleccione la cuenta bancaria en la que se registrará este pago.
10. Especifique el tipo de transacción bancaria para identificar el tipo de pago usado por su banco.
    * El tipo de transacción bancaria se usa durante el proceso de conciliación bancaria y puede hacer más fácil la conciliación.  
11. Seleccione si este pago se registrará temporalmente en una cuenta puente.
    * Si desea intentar la hora flotante para que un pago desactive el banco, use la funcionalidad de puente. El pago se registrará temporalmente en una cuenta contable hasta se compense en el banco, en cuyo momento el pago se moverá a la cuenta bancaria que ha definido aquí.  
12. Escriba la cuenta principal utilizada para la contabilización puente.
    * Esta es la cuenta principal en la que el pago se registrará temporalmente si usa el puente.  
13. Use la ficha Formato de archivo para definir la configuración de los pagos electrónicos.
14. Use la ficha Control de pagos para definir los campos que son obligatorios.
    * Por ejemplo, si necesita que se depositen todos los pagos con este método de pago, puede elegir esta opción en esta ficha.  
15. Use la ficha Atributos de pago para definir qué atributos de pago usar para esta forma de pago.
16. Haga clic en Guardar.

