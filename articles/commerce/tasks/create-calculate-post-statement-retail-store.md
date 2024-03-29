---
title: Crear, calcular y registrar extractos para una tienda
description: En este artículo se describen los pasos manuales para crear, calcular y registrar un extracto para un almacén.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 740857e6a902e21588855eef5e36cac68e560898
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873287"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Crear, calcular y registrar extractos para una tienda

[!include [banner](../includes/banner.md)]

En este artículo se describen los pasos manuales para crear, calcular y registrar un extracto para un almacén. También hay trabajos por lotes que se pueden configurar para las mismas tareas. Los pasos para configurar y ejecutar los trabajos por lotes se pueden encontrar en otros artículos. Para completar este procedimiento, debe tener transacciones que se completaron en PDV y después se incluyeron en Dynamics 365 Commerce. Este registro usa la empresa USRT en los datos de demostración.

1. Seleccione **Operaciones financieras de tienda** en la página principal.
2. Seleccione **Nuevo extracto**.
3. En el campo **Número de tienda**, seleccione una opción en la lista desplegable.
4. Seleccione **Aceptar**.
5. El grupo **Configuración** contiene la configuración que controla qué transacciones se incluyen en el extracto y cómo se agrupan en las líneas de extracto. Puede abrir el grupo **Configuración** y cambiar estos ajustes, o puede usar los valores predeterminados.  
    - El campo **Método de extracto** define cómo se agruparán las líneas de extracto.  
    - Seleccione un miembro del personal o un registro en el campo **Personal/registro** si desea calcular un extracto solo para el registro o el miembro del personal concretos.  
6. En el campo **Método de cierre**, seleccione una opción.
7. Seleccione **Calcular extracto** en el panel de acciones.
8. Seleccione **Sí**.
    - Tras calcular el extracto, debe haber líneas creadas con importes totales para cada método de pago y el método de extracto que se usó.  
    - Especifique un importe contado en cada línea si se necesita especificar o actualizar. El campo contado se rellena con importes de las declaraciones por forma de pago realizadas en PDV.  
9. Seleccione **Registrar extracto** en el panel de acciones.
10. Seleccione **Cerrar**.
11. Cierre el panel.
12. En la página principal, seleccione **Operaciones financieras de tienda**.
13. Seleccione la pestaña **Extractos registrados**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]