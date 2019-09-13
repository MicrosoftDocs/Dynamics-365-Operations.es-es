---
title: Configurar parámetros de Retail que afectan a extractos comerciales
description: Este tema muestra las configuraciones para los Parámetros comerciales que afectan la manera en que se crean y se registran los extractos comerciales.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867280"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a>Configurar parámetros de Retail que afectan a extractos comerciales

[!include[task guide banner](../includes/task-guide-banner.md)]

Este tema muestra las configuraciones para los Parámetros comerciales que afectan la manera en que se crean y se registran los extractos comerciales. Este procedimiento usa la empresa de prueba USRT.

1. En el panel de navegación, vaya a **Módulos > Venta minorista y comercio > Configuración de sede central > Parámetros > Parámetros comerciales**.
2. Seleccione la pestaña **Registro**.
    - Seleccione **Sí** si desea registrar los importes de descuento periódicos de manera específica.  
    - Seleccione **Estándar** para usar cuentas predeterminadas, o seleccione **Periódico** si desea definir qué cuenta se usará para cada descuento periódico.  
      - Seleccione **Resumen** si se deben agregar las líneas de inventario siempre que sea posible.  
      - Seleccione **Sí** si Facturas y pagos se deben liquidar automáticamente como parte del proceso de contabilización de extractos.  
      - Seleccione **Sí** si se deben agregar transacciones de ingresos seguros.  
      - Seleccione **Sí** si se deben agregar transacciones de ingreso bancario.  
      - Seleccione **Sí** para activar la agregación para la contabilización de extractos.  
      - Seleccione **Sí** para crear y procesar pedidos en paralelo cuando se registran extractos.  
      - Especifique los pedidos máximos que se procesarán en cada tarea de trabajo por lotes.  
3. Seleccione **Guardar**.

