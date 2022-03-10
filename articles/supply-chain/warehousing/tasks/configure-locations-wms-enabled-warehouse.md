---
title: Configurar ubicaciones en un almacén con WMS
description: Este procedimiento le muestra cómo configurar la ubicación para un nuevo almacén con WMS (un almacén que usa procesos avanzados de gestión de almacenes).
author: perlynne
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, WHSLocationFormat, WHSLocationType, WHSLocationProfile, WHSParameters, WHSZoneGroup, WHSZone, WHSLocationBuild, WHSLocation, WHSPackSizeCategory, WHSLocationLimit, WHSInventFixedLocation, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5273a388b30a41b75bd76c92fa4b9ff05c8f8d6
ms.sourcegitcommit: db80edbe0c32e3a5f22aae6154781f3ff8a2ab2a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2021
ms.locfileid: "7599357"
---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a>Configurar ubicaciones en un almacén con WMS

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra cómo configurar la ubicación para un nuevo almacén con WMS (un almacén que usa procesos avanzados de gestión de almacenes). El proceso normalmente lo realiza el director del almacén. Puede realizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Una condición previa es que tenga al menos un sitio configurado.


## <a name="create-a-new-warehouse"></a>Creación de un nuevo almacén
1. Vaya a **Panel de exploración > Módulos > Gestión de inventario > Configuración > Desglose del inventario > Almacenes**.
2. Haga clic en **Nuevo**.
3. En el campo **Almacén**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Sitio**, seleccione o escriba un valor de sitio existente.
6. Expanda la sección **Almacén**.
7. Establezca **Usar procesos de gestión de almacenes** en Sí. Esta configuración permite ejecutar procesos de almacenamiento avanzados mediante trabajos de almacén y dispositivos móviles.
8. Cierre la página.

## <a name="define-a-location-format"></a>Definición de un formato de ubicación
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén > Formatos de ubicación**. Los formatos de ubicación son sistemas de nombres para crear nombres únicos y coherentes para distintos huecos de ubicación dentro de un almacén. Puede resultar útil usar separadores como parte del formato de ubicación para facilitar la identificación de los componentes de la ubicación, como el número de pasillo. En este ejemplo, crearemos un nombre con cuatro componentes. Por ejemplo, pasillo, estantería, balda y hueco.
2. Haga clic en **Nuevo**.
3. En el campo **Formato de ubicación**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Descripción del segmento**, escriba un valor. Esto describe lo que representa el primer componente del nombre de la ubicación. Por ejemplo, podría ser Pasillo.
6. En el campo **Longitud**, especifique un número. Esto determina cuántos caracteres debe tener esta parte del nombre de la ubicación. Tenga en cuenta que el total de todos los componentes en el nombre, incluidos separadores, no puede superar los 10 caracteres.    
7. En el campo **Separador**, escriba un valor. Esto determina el carácter o símbolo que se usa entre el primer y el segundo componente del nombre.  
8. En la sección **Detalles** , haga clic en **Nuevo**.
9. En el campo **Descripción del segmento**, escriba un valor.
10. En el campo **Longitud**, especifique un número.
11. En el campo **Separador**, escriba un valor.
12. En la sección **Detalles** , haga clic en **Nuevo**.
13. En el campo **Descripción del segmento**, escriba un valor.
14. En el campo **Longitud**, especifique un número.
15. En el campo **Separador**, escriba un valor.
16. En la sección **Detalles** , haga clic en **Nuevo**.
17. En el campo **Descripción del segmento**, escriba un valor.
18. En el campo **Longitud**, especifique un número.
19. Haga clic en **Guardar**.
20. Cierre la página.

## <a name="define-location-types"></a>Definición de tipos de ubicaciones
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén > Tipos de ubicación**. Los tipos de ubicación se pueden usar como opciones de filtrado para controlar los distintos procesos de gestión de almacenes. Como mínimo, necesita crear tipos de ubicación de envío intermedio y final para definir el proceso de gestión de los almacenes de salida. 
2. Haga clic en **Nuevo**.
3. En el campo de tipo de **Ubicación**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. Cierre la página.

## <a name="define-location-profile"></a>Definición de un perfil de ubicación
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén > Perfiles de ubicación**. La definición de los perfiles de ubicación es muy importante. Aquí se puede controlar la capacidad de las ubicaciones agrupadas, así como las directivas relacionadas con qué inventario se incluye en el almacén y cómo. Los perfiles de ubicación se pueden usar como opciones de filtrado para controlar los distintos procesos de gestión de almacenes. Como mínimo, debe crear un perfil de ubicación de usuario para habilitar los procesos de gestión de almacenes.
2. Haga clic en **Nuevo**.
3. En el campo **Id. de perfil de ubicación**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Formato de ubicación**, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo **Tipo de ubicación**, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. Active o desactive la casilla **Permitir estados de inventario combinados**. Habilite esta opción si desea permitir valores mixtos de estado de inventario en las ubicaciones que se van a agrupar mediante este perfil de ubicación. 
12. Active o desactive la casilla **Anular reglas para días de lote**. Habilite esta opción para anular la regla sobre cuántos días pueden variar las fechas de vencimiento del lote de inventario con objeto de permitir combinar lotes de inventario que no cumplen con esta regla.  
13. Active o desactive la casilla de verificación **Permitir recuento cíclico**. Habilite esta opción para permitir procesar mediante recuento cíclico todas las ubicaciones que se van a agrupar mediante este perfil de ubicación. 
14. Expanda o contraiga la sección **Dimensiones**. La ficha Dimensiones permite definir parámetros y métodos para habilitar los cálculos precisos de la capacidad de carga dentro de cada una de las ubicaciones.  
15. Cierre la página.

## <a name="enable-warehouse-management-parameters"></a>Activación de parámetros de gestión de almacenes
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén >Parámetros de gestión de almacenes**. Para poder procesar el trabajo de almacén, es necesario configurar parámetros para el perfil de ubicación de usuario, el tipo de ubicación provisional y el tipo de ubicación de envío final. Tan pronto como el proceso de salida termine en el tipo de ubicación de envío final definido, las transacciones de salida relacionadas se actualizarán a "Seleccionado".
2. Expanda o contraiga la sección **Perfiles de ubicación**.
3. En el campo **Ubicación de usuario**, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Expanda o contraiga la sección **Tipos de ubicación**.
6. En el campo **Tipo de ubicación provisional**, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo **Tipo de ubicación de envío final**, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. Cierre la página.

## <a name="define-warehouse-zone-groups"></a>Definición de zonas de almacén
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén >Grupos de zonas de almacén**. Las zonas de almacén se pueden usar como filtros para opciones para controlar los distintos procesos de gestión de almacenes. Necesita crear un grupo de zonas antes de poder definir una zona.   
2. Haga clic en **Nuevo**.
3. En el campo **Id. de grupo de zonas**, escriba un valor.
4. En el campo **Nombre de grupo de zonas**, escriba un valor.
5. Cierre la página.

## <a name="define-warehouse-zones"></a>Definición de zonas de almacén
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén > Zonas**.
2. Haga clic en **Nuevo**.
3. En el campo **Id. de zona**, escriba un valor.
4. En el campo **Nombre de zona**, escriba un valor.
5. En el campo **Id. de grupo de zonas**, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Cierre la página.

## <a name="create-locations-using-the-location-setup-wizard"></a>Creación de ubicaciones mediante el asistente para la configuración de ubicaciones
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén > Asistente para la configuración de ubicaciones**.
2. En el campo **Almacén**, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo **Id. de zona**, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo **Id. de perfil de ubicación**, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. En la lista, marque la fila seleccionada.
12. En el campo **Desde el número**, escriba un número. Los campos Desde el número y Hasta el número definen cuántas ubicaciones se crearán. Por ejemplo, si establece Desde el número en 1 y Hasta el número en 3 para las cuatro líneas en el formato de ubicación, se crearán 81 ubicaciones (3x3x3x3).   
13. En el campo **Hasta el número**, escriba un número.
14. En la lista, busque y seleccione el registro deseado.
15. En el campo **Desde el número**, escriba un número.
16. En el campo **Hasta el número**, escriba un número.
17. En la lista, busque y seleccione el registro deseado.
18. En el campo **Desde el número**, escriba un número.
19. En el campo **Hasta el número**, escriba un número.
20. En la lista, busque y seleccione el registro deseado.
21. En el campo **Desde el número**, escriba un número.
22. En el campo **Hasta el número**, escriba un número.
23. Haga clic en Crear.

## <a name="create-locations-manually"></a>Creación manual de ubicaciones
1. Vaya a **Gestión de almacenes > Configurar > Almacén > Ubicaciones**. Crear manualmente ubicaciones dentro de un almacén es fácil. El nombre de la ubicación y la identificación del perfil de ubicación son valores necesarios. 
2. Haga clic en **Nuevo**.
3. En el campo **Almacén**, escriba un valor.
4. En el campo **Ubicación**, escriba un valor. Tenga en cuenta que aquí está creando una nueva ubicación, por lo que necesita escribir un nuevo nombre único, en lugar seleccionar uno existente.
5. En el campo **Id. de perfil de ubicación**, escriba un valor.
6. Cierre la página.

## <a name="define-pack-size-categories"></a>Definición de categorías de tamaño de paquete
1. Vaya a **Gestión de almacenes > Configurar > Almacén > Categorías de tamaño de paquete**. Se pueden usar categorías de tamaño de paquete para agrupar artículos que tienen tamaños físicos de embalaje similares. En este ejemplo, la categoría de tamaño de paquete se usará para controlar la capacidad en las ubicaciones de picking dentro de una zona específica del almacén. Tenga en cuenta que la identificación de la categoría de tamaño de paquete debe asignarse a la entidad de producto emitido para poder usarla como parte del procesamiento de los límites de existencias.  
2. Haga clic en **Nuevo**.
3. En el campo **Id. de categoría de tamaño de paquete**, especifique un valor.
4. En el campo **Nombre de categoría de tamaño de paquete**, especifique un valor.
5. Cierre la página.

## <a name="define-location-stocking-limits"></a>Definir límites de existencias de la ubicación
1. Vaya a **Gestión de almacenes > Configurar > Almacén > Límites de existencias de la ubicación**. Los límites de existencias en la ubicación ayudan a garantizar que no se cree trabajo para solicitar colocar inventario en una ubicación que no tiene capacidad física para incluir el inventario.  
2. Haga clic en **Nuevo**.
3. En el campo **Almacén**, escriba un valor.
4. En el campo **Id. de perfil de ubicación**, escriba un valor.
5. En el campo **Id. de categoría de tamaño de paquete**, especifique un valor.
6. En el campo **Cantidad**, especifique un número.
7. Haga clic en **Guardar**.
8. Cierre la página.

## <a name="define-fixed-picking-locations"></a>Definición de ubicaciones de picking fijas
1. Vaya a **Gestión de almacenes > Configurar > Almacén > Ubicaciones fijas**. Puede definir las ubicaciones que se usarán por producto o por variante de producto. Es posible crear varias ubicaciones fijas para el mismo producto dentro del mismo almacén.     
2. Haga clic en **Nuevo**.
3. En el campo **Código de artículo**, escriba un valor.
4. En el campo **Almacén**, escriba un valor.
5. En el campo **Ubicación**, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
