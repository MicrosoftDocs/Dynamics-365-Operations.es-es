---
title: Definir la dependencia de las configuraciones de ER en otros componentes
description: 'Para completar estos pasos, primero debe completar los pasos de la guía de tareas, "ER: Administrar las configuraciones de asignación de modelos" y debe tener acceso a Microsoft Dynamics Lifecycle Services (LCS).'
author: NickSelin
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18eb8de7c851e5477d93a00f744fe56929c43ca2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544849"
---
# <a name="define-the-dependency-of-er-configurations-on-other-components"></a>Definir la dependencia de las configuraciones de ER en otros componentes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para completar estos pasos, primero debe completar los pasos de la guía de tareas, "ER: Administrar las configuraciones de asignación de modelos" y debe tener acceso a Microsoft Dynamics Lifecycle Services (LCS).

Este procedimiento muestra cómo diseñar una configuración de informes electrónicos (ER) y especificar su dependencia desde otros componentes de software, de modo que pueda ayudar a garantizar que la configuración se a descargado correctamente a una versión específica de Microsoft Dynamics 365 for Finance and Operations. En este ejemplo, usted creará las configuraciones de ER necesarias para la empresa de ejemplo, Litware, Inc. 

Este procedimiento se ha creado para los usuarios con los roles de Administrador del sistema o Desarrollador de informes electrónicos asignados. Los pasos se pueden realizar con cualquier empresa, porque las configuraciones de informes electrónicos se comparten entre todas las empresas. 

1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
    * Asegúrese de que el árbol de las configuraciones contenga la configuración "Modelo de datos de ejemplo" y los elementos subordinados. De lo contrario, siga los pasos de la guía de tareas, "ER: Administrar las configuraciones de asignación de modelos" y después vuelva a empezar esta guía.   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a>Definir la dependencia de las configuraciones de ER a partir de otros componentes
1. En el árbol, expanda "Modelo de datos de ejemplo".
2. En el árbol, seleccione "Muestra modelo de datos\Muestra asingación".
    * Seleccionamos la versión de borrador de la configuración de la asignación del modelo "Asignación de ejemplo". Ahora definiremos la dependencia de otros componentes de software. Este paso se considera un requisito previo para controlar la descarga desde la versión de esta configuración de un repositorio de ER y cualquier uso futuro de esta versión.   
3. Expanda la sección Requisitos previos.
    * Tenga en cuenta que el grupo de los requisitos previos "Implementaciones" se ha agregado automáticamente a esta página. Este grupo contiene el componente de requisitos previos necesario para la configuración del modelo de datos y tiene activado el indicador de Implementación. Este indicador indica que la configuración "Asignación de ejemplo" se considerada la implementación del modelo de datos "Modelo de datos de ejemplo". Este componente forzará al ER que descargue la configuración de asignación "Asignación de ejemplo" desde un repositorio de ER cada vez que descargue la configuración del modelo "Modelo de datos de ejemplo".   
4. Haga clic en Editar.
    * Una única dependencia de la versión actual de una configuración de un componente de software se puede especificar mediante la definición del tipo de componente, y bien la versión del componente o un intervalo de versiones de componentes.  
    * Las dependencias deseadas se pueden agrupar juntas. Cuando se selecciona el tipo de agrupación "Todos de", la condición de la dependencia de este grupo se considera satisfecha cuando se satisfaga cada condición de la dependencia de este grupo y grupo subordinado. Cuando se selecciona el tipo de agrupación "Uno de", la condición de la dependencia de este grupo se considera satisfecha cuando se satisfaga al menso una condición de la dependencia de este grupo y grupo subordinado.   
5. Haga clic en Nuevo.
6. Seleccionar el componente de requisito previo de producto.
7. Seleccione Microsoft Dynamics 365 for Operations (1611).
8. En el campo versión, escriba "[7.1.1541.3036,8)".
    * [7.1.1541.3036,8)  
    * Las dependencias que introduzca serán evaluadas cuando esta configuración se descargue de cualquier ER almacenada. Esta versión de configuración se descargará del ER almacenado cuando la versión 1 de la configuración "Muestra modelo de datos” esté ya en el lugar o se haya descargado por adelantado. Si ha descargado por adelantado, debe completarse en Finance and Operations, cuya versión debe ser 7.1.1541.3036 o posterior, pero no debe superar la versión 8.   
9. Haga clic en Guardar.
10. Cierre la página.
11. Haga clic en Cambiar estado.
12. Haga clic en Completar.
13. Haga clic en Aceptar
14. En el árbol, seleccione "Muestra modelo de datos\Asignación de Muestra (alternativa)".
15. Haga clic en Editar.
16. Haga clic en Nuevo.
17. Seleccionar el componente de requisito previo de producto.
18. Seleccionar Microsoft Dynamics AX 7.0 RTW:
19. En el campo versión, escriba "[7.0.1265.3015,7.1)".
    * [7.0.1265.3015,7.1)  
    * Las dependencias que introduzca serán evaluadas cuando la configuración se descargue de cualquier ER almacenado. Esta versión de configuración se descargará del ER almacenado cuando la versión 1 de la configuración "Muestra modelo de datos” esté ya en el lugar o se haya descargado por adelantado. Si ha descargado por adelantado, debe completarse en Microsoft Dynamics 365 for Finance and Operations Enterprise edition, cuya versión debe ser 7.0.1265.3015 o posterior, pero no ser inferior a la versión 1.   
20. Haga clic en Guardar.
21. Cierre la página.
22. Haga clic en Cambiar estado.
23. Haga clic en Completar.
24. Haga clic en Aceptar

## <a name="configure-the-er-repository"></a>Configurar el repositorio de ER
1. Cierre la página.
2. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Abra la lista de repositorios de ER para el proveedor de ER actual, Litware, Inc.  
3. En la lista, marque la fila seleccionada.
4. Haga clic en Repositorios.
5. Haga clic en Mostrar filtros.
6. Introduzca un valor de filtro de "LCS" en el campo "Nombre de tipo" mediante el operador de filtro "contiene".
    * Si el repositorio de LCS ya está registrado para el proveedor de ER actual, puede omitir los pasos restantes en esta subtarea. Si el repositorio de LCS no está ya registrado, complete los pasos restantes.   
7. Haga clic en Agregar para abrir el cuadro desplegable.
8. En el campo Repositorio de configuración, escriba "LCS".
9. Haga clic en Crear repositorio.
10. En el campo Proyecto, especifique o seleccione un valor.
    * Seleccione el proyecto deseado de LCS en la búsqueda del campo “Proyecto”.  
11. Haga clic en Aceptar
12. Cierre la página.

## <a name="upload-configurations-to-lcs"></a>Cargar las configuraciones en LCS
1. Haga clic en Configuraciones de informes.
2. En el árbol, seleccione "Modelo de datos de ejemplo".
3. Seleccione la versión completada de esta configuración.
4. Haga clic en Cambiar estado.
5. Haga clic en Compartir.
6. Haga clic en Aceptar
    * La versión 1 de esta configuración de modelo se ha cargado en LCS mediante el proyecto de LCS para el repositorio de ER que se ha configurado previamente.   
7. En el árbol, expanda "Modelo de datos de ejemplo".
8. En el árbol, seleccione "Muestra modelo de datos\Muestra asingación".
9. Seleccione la versión completada de esta configuración.
10. Haga clic en Cambiar estado.
11. Haga clic en Compartir.
12. Haga clic en Aceptar
    * La versión 1.1 de esta configuración de asignación de modelo se ha cargado en LCS mediante el proyecto de LCS para el repositorio de ER que se ha configurado previamente.   
13. En el árbol, seleccione "Muestra modelo de datos\Asignación de Muestra (alternativa)".
14. Seleccione la versión completada de esta configuración.
15. Haga clic en Cambiar estado.
16. Haga clic en Compartir.
17. Haga clic en Aceptar
    * La versión 1.1 de esta configuración de asignación de modelo se ha cargado en LCS mediante el proyecto de LCS para el repositorio de ER que se ha configurado previamente.   

## <a name="evaluate-er-configuration-dependencies"></a>Evaluar las dependencias de la configuración del ER
    * Eliminaremos las configuraciones creadas del sistema y las descargaremos de nuevo en el repositorio de LCS.  
1. En el árbol, seleccione "Muestra modelo de datos\Muestra asingación".
2. Haga clic Eliminar.
3. Haga clic en Sí.
4. En el árbol, seleccione "Muestra modelo de datos\Asignación de Muestra (alternativa)".
5. Haga clic Eliminar.
6. Haga clic en Sí.
7. En el árbol, seleccione "Muestra modelo de datos\Muestra formato".
8. Haga clic Eliminar.
9. Haga clic en Sí.
10. En el árbol, seleccione "Modelo de datos de ejemplo".
11. Haga clic Eliminar.
12. Haga clic en Sí.
13. Cierre la página.
    * Abra la lista de repositorios de ER para el proveedor de ER actual, Litware, Inc.  
14. Haga clic en Repositorios.
15. Haga clic en Mostrar filtros.
16. Introduzca un valor de filtro de "LCS" en el campo "Nombre de tipo" mediante el operador de filtro "contiene".
17. Haga clic en Abrir.
18. En el árbol, seleccione "Modelo de datos de ejemplo".
    * Tenga en cuenta que puede ver una evaluación de si las condiciones necesarias de requisitos previos se han satisfecho para cada versión de la configuración de ER para el repositorio actual. Para ver esta evaluación, haga clic en Comprobar requisitos previos.   
19. Haga clic en comprobar requisitos previos.
20. Haga clic en Importar.
21. Haga clic en Sí.
22. Cierre la página.
23. Cierre la página.
24. Cierre la página.
25. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
26. En el árbol, expanda "Modelo de datos de ejemplo".
    * Tenga en cuenta que la configuración de asignación "Asignación de ejemplo” se ha descargado junto con la configuración seleccionada del modelo de datos. Los dos archivos se descargan conjuntamente porque la asignación “Asignación de ejemplo” se ha definido como implementación del modelo de datos seleccionado, y es aplicable para Finance and Operations. La configuración de "Asignación de ejemplo (alternativa)” no se ha descargado porque la condición para la versión de la aplicación requerida no se cumplió.   
    * Si inicia sesión en Dynamics 365 for Finance and Operations, Enterprise Edition, registra el mismo proveedor, accede al mismo proyecto de LCS y descarga la misma configuración del modelo de datos, la configuración "Asignación de ejemplo (alternativa)” se descargará, mientras que la configuración "Asignación de ejemplo” se omitirá.  

