--- 
title: Configurar un trabajador
description: "Este procedimiento demuestra cómo configurar a un trabajador comercial como representante de ventas, que sea apto comisión en ventas en PDV."
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 27b075cf1152f16fc4726b224e877eacb2f2572c
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---
# <a name="configure-a-worker"></a>Configurar un trabajador

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

Este procedimiento demuestra cómo configurar a un trabajador comercial como representante de ventas, que sea apto comisión en ventas en PDV. Este procedimiento usa la empresa de datos de demostración USRT.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Crear un grupo de comisión de ventas para el trabajador
1. Vaya a Ventas y marketing > Comisiones > Grupos de ventas.
    * Se puede asignar trabajadores a uno o más grupos de ventas. En PDV, puede elegir cualquier grupo de ventas que contenga trabajadores de la libreta de direcciones de la tienda.  
2. Haga clic en Nuevo.
3. En el campo Grupo, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. Haga clic en Guardar.
6. En el panel de acciones, haga clic en General.
7. Haga clic en representante de Ventas.
    * Un grupo de ventas puede contener más de un trabajador. Las comisiones pueden dividirse entre los trabajadores en función de cómo defina la proporción de la comisión.  
8. En el campo Nombre, especifique o seleccione un valor.
9. En el campo proporción de la Comisión, especifique un número.
10. Haga clic en Guardar.
11. Cierre la página.
12. Cierre la página.

## <a name="assign-the-workers-default-sales-group"></a>Asignar el grupo de ventas predeterminado de trabajadores
1. Vaya a Venta minorista y comercio > Empleados > Trabajadores.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en la pestaña Comercial.
    * Un trabajador puede asignarse a un grupo de ventas predeterminado. El grupo de ventas predeterminado se añadirá automáticamente a las líneas de ventas en PDV, si la opción está habilitada en el perfil de funcionalidad para la tienda.  
5. Haga clic en Editar.
6. En el campo Grupo predeterminado, especifique o seleccione un valor.
7. Haga clic en Guardar.


