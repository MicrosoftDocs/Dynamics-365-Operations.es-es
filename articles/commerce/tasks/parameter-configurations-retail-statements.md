---
title: Configurar parámetros que afectan a extractos comerciales
description: Este tema muestra las configuraciones para los parámetros de Commerce que afectan la manera en que se crean y se registran los extractos.
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
ms.openlocfilehash: d8cae6d2fa7c469f50fa92141a6cb5a0af1df4b0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023924"
---
# <a name="configure-parameters-that-affect-retail-statements"></a>Configurar parámetros que afectan a extractos comerciales

[!include[task guide banner](../includes/task-guide-banner.md)]

Este tema muestra las configuraciones para los parámetros de Commerce que afectan la manera en que se crean y se registran los extractos. Este procedimiento usa la empresa de prueba USRT.

1. En el panel de navegación, vaya a **Módulos > Retail y Commerce > Configuración de sede central > Parámetros > Parámetros de Commerce**.
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

