--- 
title: "Configuración de parámetros para los extractos de Retail"
description: "Este procedimiento muestra las configuraciones para los Parámetros comerciales que afectan la manera en que se crean y se registran los extractos comerciales."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 731a3ec06efa103ba663df83240c77dfe78bb7cd
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="parameter-configurations-for-retail-statements"></a>Configuración de parámetros para los extractos de Retail

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimiento muestra las configuraciones para los Parámetros comerciales que afectan la manera en que se crean y se registran los extractos comerciales. Este procedimiento usa la empresa de prueba USRT.

1. Vaya a Venta minorista y comercio > Configuración de sede minorista > Parámetros > Parámetros comerciales.
2. Haga clic en la ficha Registro.
    * Seleccione "Sí" si desea registrar los importes de descuento periódicos de manera específica.  
    * Seleccione “Estándar” para usar cuentas predeterminadas, o seleccione “Periódico” si desea definir qué cuenta se usará para cada descuento periódico.  
    * Seleccione “Resumen” si se deben agregar las líneas de inventario siempre que sea posible.  
    * Seleccione “Sí” si Facturas y pagos se deben liquidar automáticamente como parte del proceso de contabilización de extractos.  
    * Seleccione “Sí” si se deben agregar transacciones de ingresos seguros.  
    * Seleccione “Sí” si se deben agregar transacciones de ingreso bancario.  
    * Seleccione "Sí" para activar la agregación para la contabilización de extractos.  
    * Seleccione "Sí" para crear y procesar pedidos en paralelo cuando se registran extractos.  
    * Especifique los pedidos máximos que se procesarán en cada tarea de trabajo por lotes.  
3. Haga clic en Guardar.


