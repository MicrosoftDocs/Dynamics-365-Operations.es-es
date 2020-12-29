---
title: Establecer cuotas de pago de cliente
description: Creación de cuotas de pago para pagos de clientes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b6475671002379d84519df05a0198a17ac000677
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447596"
---
# <a name="establish-customer-payment-fees"></a>Establecer cuotas de pago de cliente

[!include [banner](../../includes/banner.md)]

Creación de cuotas de pago para pagos de clientes.

Esta tarea usa la empresa de demostración USMF.

1. En el **Panel de exploración**, vaya a **Módulos > Clientes > Configuración de pagos > Cuota de pago**.
2. Haga clic en **Nuevo**.
3. En el campo **Id. de cuota**, especifique un identificador para la cuota. El Id. de cuota se muestra en los diarios de pagos, por lo que debe hacerlo descriptivo para comprender qué cuota se está aplicando.  
4. Escriba un nombre para la cuota en el campo **Nombre**.
5. En el campo **Descripción de cuota**, especifique una descripción para la cuota.
6. En el campo **Cargo**, seleccione si la cuota se cobrará al cliente o a una cuenta contable. Si la cuota se aplica al cliente, seleccione Cliente. Si la cuota se aplica a su organización como gasto, seleccione Libro mayor. Para esta tarea, seleccione Cliente.  
7. En el campo **Tipo de diario**, seleccione el tipo de diario que puede usar esta cuota de pago. Si estas cuotas se usan para los pagos de cliente, el tipo de diario será probablemente Cobros.  
8. Haga clic en **Guardar**.
9. Haga clic en **Configuración de cuota de pago**. La configuración de la cuota de pago se usa para definir los criterios para cuando se aplique la cuota de pago.  Por ejemplo, puede definir que la cuota se calculará si la cuenta bancaria es USMF OPER, y el método de pago es cheque.  
10. En el campo **Agrupaciones**, seleccione Tabla, Grupo o Todo para definir en qué cuentas bancarias se aplicará esta cuota. Si selecciona Todo, se podría aplicar esta cuota en todas las cuentas bancarias.  Si selecciona Tabla, solo se podría aplicar esta cuota a la cuenta bancaria que seleccione. Si selecciona Grupo, solo se podría aplicar esta cuota a las cuentas bancarias en el grupo de bancos seleccionado.  
11. En el campo **Relación del banco**, seleccione un grupo de bancos o una cuenta bancaria. Si ha seleccionado Tabla, las búsquedas mostrarán cuentas bancarias. Si ha seleccionado Grupo, las búsquedas mostrarán grupos de bancos.  
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. En el campo **Método de pago**, seleccione el método de pago para la cuota que se va a evaluar. Por ejemplo, puede aplicar una cuota para sus clientes si envían los pagos como cheques, en lugar de como pago electrónico.  
14. En la lista, busque y seleccione el registro deseado.
15. Si es relevante, en el campo **Divisa de pago**, especifique una divisa de pago. La divisa de pago se usa como criterio adicional para saber si se aplicará la cuota.  Por ejemplo, su banco puede cobrar una cuota adicional para los pagos recibidos en divisa USD, ya que normalmente solo tramitan la divisa EUR.  
16. Seleccione si la cuota será un porcentaje, un importe o un intervalo.
17. En el campo **Porcentaje/Importe**, especifique el porcentaje o el importe de la cuota. Si el campo Porcentaje / Importe es Porcentaje, el valor especificado aquí será un porcentaje. Si el campo Porcentaje / Importe es Importe, el valor especificado aquí será un importe. Si el campo Porcentaje / Importe es Intervalo, use la ficha Intervalo para definir los niveles.  
18. En el campo **Divisa de cuota**, seleccione la divisa de la cuota. Esta es la divisa en la que se creará la cuota.  
19. Haga clic en **Guardar**.

