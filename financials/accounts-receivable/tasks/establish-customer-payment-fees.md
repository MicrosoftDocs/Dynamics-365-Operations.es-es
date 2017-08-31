--- 
title: Establecer cuotas de pago de cliente
description: "Creación de cuotas de pago para pagos de clientes."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 220b33fe81a63aad83bc045ca4a7c74971e7c7bd
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="establish-customer-payment-fees"></a>Establecer cuotas de pago de cliente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Creación de cuotas de pago para pagos de clientes.

Esta tarea usa la empresa de demostración USMF.

1. Vaya a Clientes > Configuración de pagos > Cuota de pago.
2. Haga clic en Nuevo.
3. En el campo Id. de cuota, especifique un identificador para la cuota.
    * El Id. de cuota se muestra en los diarios de pagos, por lo que debe hacerlo descriptivo para comprender qué cuota se está aplicando.  
4. Escriba un nombre para la cuota en el campo Nombre.
5. En el campo Descripción de cuota, especifique una descripción para la cuota.
6. Seleccione si la cuota se cobrará al cliente o a una cuenta contable.
    * Si la cuota se aplica al cliente, seleccione Cliente. Si la cuota se aplica a su organización como gasto, seleccione Libro mayor. Para esta tarea, seleccione Cliente.  
7. Seleccione el tipo de diario que puede usar esta cuota de pago.
    * Si estas cuotas se usan para los pagos de cliente, el tipo de diario será probablemente Cobros.  
8. Haga clic en Guardar.
9. Haga clic en Configuración de cuota de pago.
    * La configuración de la cuota de pago se usa para definir los criterios para cuando se aplique la cuota de pago.  Por ejemplo, puede definir que la cuota se calculará si la cuenta bancaria es USMF OPER, y el método de pago es cheque.  
10. Seleccione Tabla, Grupo o Todo para definir en qué cuentas bancarias se aplicará esta cuota.
    * Si selecciona Todo, se podría aplicar esta cuota en todas las cuentas bancarias.  Si selecciona Tabla, solo se podría aplicar esta cuota a la cuenta bancaria que seleccione. Si selecciona Grupo, solo se podría aplicar esta cuota a las cuentas bancarias en el grupo de bancos seleccionado.  
11. Seleccione un grupo de bancos o una cuenta bancaria.
    * Si ha seleccionado Tabla, las búsquedas mostrarán cuentas bancarias. Si ha seleccionado Grupo, las búsquedas mostrarán grupos de bancos.  
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. Seleccione la forma de pago para la que se aplicará esta cuota.
    * Por ejemplo, puede aplicar una cuota para sus clientes si envían los pagos como cheques, en lugar de como pago electrónico.  
14. En la lista, busque y seleccione el registro deseado.
15. Si procede, especifique una divisa de pago.
    * La divisa de pago se usa como criterio adicional para saber si se aplicará la cuota.  Por ejemplo, su banco puede cobrar una cuota adicional para los pagos recibidos en divisa USD, ya que normalmente solo tramitan la divisa EUR.  
16. Seleccione si la cuota será un porcentaje, un importe o un intervalo.
17. Especifique el porcentaje o el importe de la cuota.
    * Si el campo Porcentaje / Importe es Porcentaje, el valor especificado aquí será un porcentaje. Si el campo Porcentaje / Importe es Importe, el valor especificado aquí será un importe. Si el campo Porcentaje / Importe es Intervalo, use la ficha Intervalo para definir los niveles.  
18. En el campo Divisa de cuota, seleccione la divisa de la cuota.
    * Esta es la divisa en la que se creará la cuota.  
19. Haga clic en Guardar.


