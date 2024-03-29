---
title: Configuraciones de pago para los extractos de Retail
description: Este procedimiento muestra las configuraciones para los métodos de pago de tienda Commerce, que afectan a la manera en que se crean y se registran los extractos.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3c8c7678d88b3c01138aa098b8830336885e6445fb41931b19bcda2b95b86b5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712366"
---
# <a name="payment-configurations-for-retail-statements"></a>Configuraciones de pago para los extractos de Retail

[!include [banner](../includes/banner.md)]

Este procedimiento muestra las configuraciones para los métodos de pago de tienda Commerce, que afectan a la manera en que se crean y se registran los extractos.

Esta grabación usa la empresa de demostración USRT.

1. Vaya a Retail y Commerce > Canales > Tiendas > Todas las tiendas.
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]