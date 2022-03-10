---
title: Creación de un nuevo diseño de almacén
description: En este tema se describe cómo configurar la información sobre las ubicaciones en un almacén.
author: yufeihuang
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf5c5203aa0a4c8522b8f9d04fc6a8cd306a64a3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580897"
---
# <a name="create-a-new-warehouse-layout"></a>Creación de un nuevo diseño de almacén

[!include [banner](../../includes/banner.md)]

En este tema se describe cómo configurar la información sobre las ubicaciones en un almacén. Esto solo se aplica a los almacenes creados con el “almacenamiento básico” en el módulo Gestión del inventario, no en los almacenes creados en el módulo Gestión de almacenes. Puede utilizar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.


## <a name="set-the-default-location-capacity"></a>Definir la capacidad de la ubicación predeterminada
1. En el panel de exploración, vaya a **Módulos > Gestión del inventario > Configurar > Inventario y parámetros de gestión de inventario y almacenes**.
2. Seleccione la pestaña **Ubicaciones**.
3. En el campo **Ancho estándar**, especifique un número.
4. En el campo **Profundidad estándar**, especifique un número.
5. En el campo **Alto estándar**, especifique un número.
6. Seleccione **Guardar**.
7. Cierre la página.

## <a name="define-the-location-name-format"></a>Definir el formato del nombre de ubicación
1. En el Panel de exploración, vaya a **Módulos > Gestión de inventario > Configuración > Desglose del inventario > Almacenes**.
2. Seleccione **Nuevo**.
3. En el campo **Almacén**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Sitio**, seleccione el registro deseado en la búsqueda.
6. Alterne la expansión de la sección **Nombres de ubicación**. Las opciones de esta sección definen el formato predeterminado para los nombres de ubicación. En nuestro ejemplo, incluiremos el número de pasillo, el número de la estantería y el número de balda.  
7. Establezca la opción **Incluir pasillo** en **Sí**.
8. Establezca la opción **Incluir estantería** en **Sí**. 
9. En el campo **Formato**, escriba una valor para la estantería.
10. Establezca la opción **Incluir balda** en **Sí**.
11. En el campo **Formato**, escriba una valor para la balda.

## <a name="define-warehouse-locations"></a>Definir las ubicaciones del almacén
1. En el panel de acciones, haga clic en **Almacén**.
2. Seleccione **Asistente para ubicación**.
3. Seleccione **Siguiente**.
4. Anular la selección de la opción **Muelle de salida**
5. Anular la selección de la opción **Ubicaciones de almacenaje**
6. Seleccione **Siguiente** hasta llegar a la opción donde se puede seleccionar **Fin**.
7. Cierre la página.
8. Actualice la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]