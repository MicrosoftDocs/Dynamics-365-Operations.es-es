--- 
title: "Creación de un nuevo diseño de almacén"
description: "Este procedimiento le muestra cómo configurar la información sobre las ubicaciones de un almacén."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 15610bc797cf7e7abdec433d0a5cead60da7a555
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-new-warehouse-layout"></a>Creación de un nuevo diseño de almacén

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo configurar la información sobre las ubicaciones de un almacén. Esto solo se aplica a los almacenes creados con el “almacenamiento básico” en el módulo Gestión del inventario, no en los almacenes creados en el módulo Gestión de almacenes. Puede utilizar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.


## <a name="set-the-default-location-capacity"></a>Definir la capacidad de la ubicación predeterminada
1. Vaya a Gestión del inventario > Configurar > Parámetros de la gestión de inventario y almacenes.
2. Haga clic en la ficha Ubicaciones.
3. En el campo Ancho estándar, especifique un número.
4. En el campo Profundidad estándar, especifique un número.
5. En el campo Alto estándar, especifique un número.
6. Haga clic en Guardar.
7. Cierre la página.

## <a name="define-the-location-name-format"></a>Definir el formato del nombre de ubicación
1. Vaya a Gestión del inventario> Configuración > Desglose del inventario > Almacenes
2. Haga clic en Nuevo.
3. En el campo Almacén, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. Alterne la expansión de la sección Nombres de ubicación.
    * Las opciones de esta sección definen el formato predeterminado para los nombres de ubicación. En nuestro ejemplo, incluiremos el número de pasillo, el número de la estantería y el número de balda.  
8. Establezca la opción Incluir pasillo en Sí.
9. Establezca la opción Incluir estantería en Sí. 
10. En el campo Formato, escriba una valor para la estantería.
    * Por ejemplo: -##  
11. Establezca la opción Incluir balda en Sí.
12. En el campo Formato, escriba una valor para la balda.
    * Por ejemplo: -##  

## <a name="define-warehouse-locations"></a>Definir las ubicaciones del almacén
1. En el panel de acciones, haga clic en Almacén.
2. Haga clic en Asistente para ubicación.
3. Haga clic en Siguiente.
4. Anular la selección de la opción Muelle de salida
5. Anular la selección de la opción Ubicaciones de almacenaje
6. Haga clic en Siguiente.
7. Haga clic en Siguiente.
8. Haga clic en Siguiente.
9. Haga clic en Siguiente.
10. Haga clic en Siguiente.
11. Haga clic en Siguiente.
12. Haga clic en Siguiente.
    * Tenga en cuenta que las dimensiones físicas que se muestran en esta página son las que establece al inicio de este procedimiento.  
13. Haga clic en Siguiente.
14. Haga clic en Finalizar.
15. Cierre la página.
16. Actualice la página.


