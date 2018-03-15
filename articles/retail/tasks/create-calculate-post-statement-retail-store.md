--- 
title: Crear, calcular y registrar un extracto para una tienda
description: "Este procedimiento le guía por los pasos manuales para crear, calcular y registrar un extracto para un almacén."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
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
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 33ebb28196baa9ae944dbd124274b05cb587fea4
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a>Crear, calcular y registrar un extracto para una tienda

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimiento le guía por los pasos manuales para crear, calcular y registrar un extracto para un almacén. También hay trabajos por lotes que se pueden configurar para las mismas tareas. Los pasos para configurar y ejecutar los trabajos por lotes se pueden encontrar en otros temas. Para completar este procedimiento, debe tener transacciones que se completaron en PDV y después se incluyeron en Dynamics AX. Este registro usa la empresa USRT en los datos de demostración. Este procedimiento puede remitir a Microsoft Dynamics AX. Tenga en cuenta que Dynamics AX ahora se denomina Microsoft Dynamics 365 for Operations.

1. Vaya a Todos los espacios de trabajo > .. > Operaciones financieras de tienda.
2. Haga clic en Nuevo extracto.
3. En el campo Número de tienda, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Haga clic en Aceptar
    * El grupo Configuración tiene la configuración que controla qué transacciones se incluyen en el extracto y cómo se agrupan en las líneas de extracto. Puede abrir el grupo de configuración y cambiar estos ajustes, o puede usar los valores predeterminados.  
    * El campo Método de extracto define cómo se agruparán las líneas de extracto.  
    * Seleccione un miembro del personal o un registro si desea calcular un extracto solo para el registro o el miembros del personal específico.  
6. En el campo Método de cierre, seleccione una opción.
7. Haga clic en Calcular extracto.
8. Haga clic en Sí.
    * Tras calcular el extracto, debe haber líneas creadas con importes totales para cada método de pago y el método de extracto que se usó.  
    * Especifique un importe contado en cada línea si se necesita especificar o actualizar. El campo contado se rellena con importes de las declaraciones por forma de pago realizadas en PDV.  
9. Haga clic en Registrar extracto.
10. Haga clic en Cerrar.
11. Vaya a Venta minorista y comercio > Canales > Operaciones financieras de tienda.
12. Haga clic en la ficha Extractos registrados.


