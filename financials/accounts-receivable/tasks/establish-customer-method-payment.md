--- 
title: "Establecer método de pago de cliente"
description: "Creación de una forma de pago para pagos de clientes."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/15/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: bfafcccb12112ca7cceefb65be3f942bfc307751
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="establish-customer-method-of-payment"></a>Establecer método de pago de cliente

[!include[task guide banner](../../includes/task-guide-banner.md)]

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

