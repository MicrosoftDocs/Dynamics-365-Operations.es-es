--- 
title: "Configurar las opciones de método de pago que afectan a los extractos comerciales"
description: "Este procedimiento muestra las configuraciones para los métodos de pago comerciales, que afectan a la manera en que se crean y se registran los extractos comerciales."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ba21db9ee97dc4d851c77a906927ef513940b743
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="configure-payment-method-settings-that-affect-retail-statements"></a>Configurar las opciones de método de pago que afectan a los extractos comerciales

[!include [task guide banner](../includes/task-guide-banner.md)]

Este procedimiento muestra las configuraciones para los métodos de pago comerciales, que afectan a la manera en que se crean y se registran los extractos comerciales.

Esta grabación usa la empresa de demostración USRT.

1. Vaya a Venta minorista y comercio > Canales > Tiendas > Todas las tiendas minoristas.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el panel de acciones, haga clic en Configurar.
5. Haga clic en Métodos de pago.
6. Expanda o contraiga la sección Registro.
7. Haga clic en Editar.
    * Seleccione si los importes recibidos para este método de pago se deben registrar en una cuenta contable o en una cuenta bancaria.  
    * Seleccione la cuenta en la que se deben registrar los importes recibidos para este método de pago.  
    * Seleccione una cuenta para registrar posibles diferencias entre el importe total de la transacción recibido y el importe contado para este método de pago.  
    * En este campo puede especificar un importe para controlar cuándo se debe registrar el importe de la diferencia en otra cuenta de diferencia. Puede usar esto para realizar un seguimiento de grandes diferencias.  
    * Seleccione una cuenta para registrar posibles diferencias entre el importe total de la transacción recibido y el importe contado, cuando supera el valor definido en el campo de "Importe máximo de diferencia".  
    * Seleccione "Sí" para registrar importes de ingresos bancarios en una cuenta independiente.  
    * En este campo puede seleccionar si se deben registrar importes de ingresos bancarios en una cuenta contable o en una cuenta bancaria.  
    * Seleccione la cuenta en la que registrar importes de ingresos bancarios.  
    * Seleccione el tipo de transacción bancaria que se usará al registrar importes de ingresos bancarios en la cuenta bancaria.  
    * Seleccione "Sí" para registrar importes seguros en una cuenta independiente.  
    * Seleccione si se deben registrar importes seguros en la cuenta contable o en la cuenta bancaria.  
    * Seleccione la cuenta en la que registrar importes seguros.  
8. Haga clic en Guardar.


