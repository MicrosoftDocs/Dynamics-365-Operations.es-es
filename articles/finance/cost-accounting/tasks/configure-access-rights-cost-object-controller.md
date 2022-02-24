---
title: Configurar los derechos de acceso para un controlador de objeto de coste
description: Use este procedimiento para configurar los derechos de acceso para el controlador de objeto de coste.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88d6208e867bd322ddfc4e599856b1905fa8e19b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969387"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>Configurar los derechos de acceso para un controlador de objeto de coste

[!include [banner](../../includes/banner.md)]

Use este procedimiento para configurar los derechos de acceso para el controlador de objeto de coste. Este registro usa la empresa USP2 con los datos para demostración.


## <a name="assign-the-cost-object-controller-role"></a>Asignar el rol del controlador del objeto de coste
1. Vaya a Administración del sistema > Usuarios > Usuarios.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre según el campo Nombre de usuario con un valor de “alicia”.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en Asignar roles.
5. En la lista, busque y seleccione el registro deseado.
6. Haga clic en Aceptar

## <a name="enable-access-list-security"></a>Habilitar la seguridad de lista de acceso
1. Vaya a Contabilidad de costes > Dimensiones > Jerarquías de dimensiones.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione Organización.  
3. Haga clic en Editar.
4. Seleccione Sí en el campo de la jerarquía de la lista de acceso.
5. Haga clic en Ver jerarquía.

## <a name="assign-access-rights-to-user"></a>Asignar derechos de acceso al usuario
1. Haga clic en Nuevo.
2. En la lista, marque la fila seleccionada.
3. En el campo Id. de usuario, especifique o seleccione un valor.
    * Seleccione Administración.  
4. En el árbol, seleccione "Organización\Director general\Director financiero\FIM".
5. Haga clic en Nuevo.
6. En la lista, marque la fila seleccionada.
7. En el campo Id. de usuario, especifique o seleccione un valor.
    * Seleccione Alicia.  
8. Haga clic en Guardar.

## <a name="enable-access-rights-in-cost-accounting"></a>Habilitar derechos de acceso en la contabilidad de costes
1. Vaya a Contabilidad de costes > Configuración > Parámetros.
2. Haga clic en la pestaña General.
3. Seleccione Sí en el parámetro Habilitar acceso de visualización para el campo de miembros de dimensión de objeto de coste.
4. Haga clic en Guardar.
5. Cierre la página.
6. Vaya a Contabilidad de costes > Configuración > Configuración del espacio de trabajo de control de costes.
7. Haga clic en Editar.
8. Seleccione Sí en el campo Publicado.
    * Si selecciona Sí, un usuario al que se asigna uno de los cuatro roles siguientes puede ver los informes del área de trabajo de control de costes: administrador de contabilidad de costes, contable de costes, funcionario contable de costes y controlador de objetos de coste. Si selecciona No, solo un usuario al que se asigna uno de los cuatro roles siguientes puede ver los informes del área de trabajo de control de costes: administrador de contabilidad de costes, contable de costes y funcionario contable de costes.    
9. Haga clic en Guardar.

