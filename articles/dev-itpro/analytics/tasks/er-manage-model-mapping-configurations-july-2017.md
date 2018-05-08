--- 
title: "Administrar las configuraciones de asignación de modelo para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con el rol de Administrador del sistema o con el rol de Desarrollador de informes electrónicos puede administrar asignaciones de modelo de informe electrónico (ER) en configuraciones de ER independientes."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 35fdc1e98897d449ce18fe38cc6b7896ca5c5278
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="manage-model-mapping-configurations-for-electronic-reporting-er"></a>Administrar las configuraciones de asignación de modelo para informes electrónicos (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con el rol de Administrador del sistema o con el rol de Desarrollador de informes electrónicos puede administrar asignaciones de modelo de informe electrónico (ER) en configuraciones de ER independientes. En este manual de la tarea, creará las configuraciones necesarias de ER para la empresa del ejemplo, Litware, Inc. Para completar esta guía de la tarea, primero debe completar los pasos de la guía de la tarea,  "ER crea un proveedor de la configuración” y lo marca como activo. 

Dado que las configuraciones de ER se comparten entre las empresas, puede completar esta guía de tareas mediante el conjunto de datos de la empresa de su elección. La funcionalidad para esta guía de tareas está disponible si ha instalado una de las revisiones siguientes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 para Dynamics AX 7.0 o https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 para la versión de Dynamics 365 for Operations.

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Compruebe que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como activo. Si no ve a este proveedor de configuración, primero debe completar los pasos de la guía de tareas Creación de un proveedor de configuración y marcarlo como activo.   

## <a name="add-a-new-er-model-configuration"></a>Añada una nueva configuración para el modelo ER
1. Haga clic en Configuraciones de informes.
    * Agregue una nueva configuración para el modelo. El nombre debe ser exclusivo en el árbol de configuraciones.  
2. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
3. En el campo Nombre, escriba "Modelo de datos de ejemplo".
    * Modelo de datos de ejemplo  
4. Haga clic en Crear configuración.
5. Haga clic en Diseñador.
6. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
7. Escriba "Raíz" en el campo Nombre.
    * Raíz  
8. Haga clic en Agregar.
9. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
10. Escriba "Empresa" en el campo Nombre.
    * Compañía  
11. Haga clic en Agregar.
12. En el campo Descripción, escriba el texto, Descripción de la entidad jurídica o empresa en que un usuario se registra en tiempo de ejecución. 
    * Descripción de la entidad jurídica o de la empresa en la que un usuario se registró en el tiempo de ejecución.  
13. Haga clic en Referencia raíz.
14. Haga clic en Aceptar
15. Haga clic en Guardar.
16. Cierre la página.
17. Haga clic en Cambiar estado.
18. Haga clic en Completar.
19. Haga clic en Aceptar

## <a name="add-a-new-er-model-mapping-configuration"></a>Agregar una nueva configuración de asignación al modelo de ER
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
2. En el campo Nuevo, especifique "Asignación de modelo basado en el modelo Modelo de datos de ejemplo".
3. En el campo Nombre, escriba "Asignación de ejemplo".
    * Asignación de ejemplo  
4. Haga clic en Crear configuración.
5. Expanda la sección Requisitos previos.
    * Tenga en cuenta el grupo de los requisitos previos de implementaciones se ha agregado automáticamente. El grupo contiene el componente de requisitos previos necesario que se refiere a la configuración principal del modelo de datos y se marca como Implementación. Esto significa que esta configuración de asignación del Modelo de asignación de ejemplo se considerada la implementación del modelo de datos, Modelo de datos de ejemplo. Por lo tanto, este componente forzará al ER que descargue la configuración de asignación del modelo, Asignación de ejemplo de un repositorio de ER cuando se descarga la configuración del modelo, Modelo de datos de ejemplo.   
6. Haga clic en Diseñador.
    * Tenga en cuenta que la configuración creada de asignación de modelo contiene una nueva asignación en blanco con el mismo nombre que la configuración creada. Tenga en cuenta que cuando una configuración de modelo de elemento principal seleccionada contiene asignaciones de modelo, se copiarán en una configuración de modelo nueva.   
7. Haga clic en Diseñador.
8. En el árbol, seleccione "Dynamics 365 for Operations\Tabla".
9. Haga clic en Agregar raíz.
10. Escriba "Empresa" en el campo Nombre.
    * Compañía  
11. En el campo Tabla, escriba "CompanyInfo".
    * CompanyInfo  
12. Haga clic en Aceptar
13. En el árbol, expanda "Empresa".
14. En el árbol, expanda "Empresa\buscar()".
15. En el árbol, seleccione "Empresa\buscar()\Nombre".
16. Haga clic en Enlazar.
17. Haga clic en Guardar.
18. Cierre la página.
19. Cierre la página.
20. En el panel de acciones, haga clic en Configuraciones.
21. Haga clic en Parámetros de usuario.
22. Seleccione Sí en el campo Parámetros de ejecución.
23. Haga clic en Aceptar
24. Haga clic en Editar.
25. Seleccione Sí en el campo Borrador de ejecución.

## <a name="add-a-new-er-format-configuration"></a>Añada una nueva configuración para el formato de ER
1. En el árbol, seleccione "Modelo de datos de ejemplo".
2. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
3. En el campo Nuevo, especifique "Formato basado en el modelo Modelo de datos de ejemplo".
4. En el campo Nombre, escriba "Formato de ejemplo".
    * Formato de ejemplo  
5. Haga clic en Crear configuración.
6. Haga clic en Diseñador.
7. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
8. En el árbol, seleccione "Texto\Cadena".
9. Haga clic en Aceptar
10. Haga clic en la ficha Asignación.
11. En el árbol , expanda "modelo".
12. En el árbol, seleccione "modelo\Empresa".
13. Haga clic en Enlazar.
14. Haga clic en Guardar.
15. Cierre la página.
    * Ejecute la versión de borrador del formato creado para probar.  
16. Haga clic en Ejecutar.
    * En las versiones de ficha desplegable, haga clic en Ejecutar.  
17. Haga clic en Aceptar
    * Revise la salida que contiene el nombre de la empresa en la que el usuario que está ejecutando esta configuración del formato se ha registrado. Tenga en cuenta que la configuración creada de asignación del modelo se usa por esta configuración del formato ya que solo hay una configuración disponible que contiene asignaciones de modelo necesarias.   

## <a name="add-alternative-er-model-mapping-configuration"></a>Agregar una configuración alternativa de asignación al modelo de ER
1. En el árbol, seleccione "Modelo de datos de ejemplo".
2. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
3. En el campo Nuevo, especifique "Asignación de modelo basado en el modelo Modelo de datos de ejemplo".
4. En el campo Nombre, escriba "Asignación ejemplo (alternativa)".
    * Asignación de ejemplo (alternativa)  
5. Haga clic en Crear configuración.
6. Haga clic en Diseñador.
7. Haga clic en Diseñador.
8. En el árbol, seleccione "Dynamics 365 for Operations\Tabla".
9. Haga clic en Agregar raíz.
10. Escriba "Empresa" en el campo Nombre.
    * Compañía  
11. En el campo Tabla, escriba "CompanyInfo".
    * CompanyInfo  
12. Haga clic en Aceptar
13. Haga clic en Editar.
14. En el árbol, seleccione String\CONCATENATE.
15. Haga clic en Agregar función.
16. En el árbol, expanda "Empresa".
17. En el árbol, expanda "Empresa\buscar()".
18. En el árbol, seleccione "Empresa\buscar()\Nombre".
19. Haga clic en Agregar origen de datos.
20. En el campo Fórmula, escriba un valor.
    * CONCATENAR(Empresa.'buscar()'.Nombre, ";",  
21. En el árbol, seleccione "Empresa\buscar()\Empresa(ÁreaDatos)".
22. Haga clic en Agregar origen de datos.
23. En el campo Fórmula, escriba un valor.
    * CONCATENAR(Empresa.'buscar()'.Nombre, “; ”, Empresa.'buscar().ÁreaDatos)  
24. Haga clic en Guardar.
25. Cierre la página.
26. Haga clic en Guardar.
27. Cierre la página.
28. Cierre la página.
29. Seleccione Sí en el campo Borrador de ejecución.

## <a name="use-an-existing-er-model-mapping-configuration"></a>Use una configuración de asignación existente del modelo de ER
1. En el árbol, seleccione "Muestra modelo de datos\Muestra formato".
2. Haga clic en Ejecutar.
    * Tenga en cuenta que la versión de borrador de la configuración del formato de ER no se puede ejecutar porque hay más de una configuración de asignación de modelo disponible para el modelo de datos sin definir que se ha seleccionado como el origen de datos de formato de ER en ejecución.   
    * A continuación, se definirá la configuración de la asignación de modelo alternativa como aquella desde la que las asignaciones de modelo se usarán como orígenes de datos para ejecutar el formato de ER.   
3. En el árbol, seleccione "Muestra modelo de datos\Asignación de Muestra (alternativa)".
4. Seleccione Sí en el campo Valor predeterminado de la asignación de modelo.
5. En el árbol, seleccione "Muestra modelo de datos\Muestra formato".
6. Haga clic en Ejecutar.
7. Haga clic en Aceptar
    * Tenga en cuenta que la configuración de la asignación de modelo predeterminada se usa por esta configuración de formato para generar el documento electrónico (la salida creada contiene el código de empresa).  


