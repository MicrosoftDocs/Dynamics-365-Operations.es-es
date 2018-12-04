--- 
title: "ER Cargar una configuración en Lifecycle Services"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración nueva de informes electrónicos y cargarla en Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 19ae8820e5d4a798a5789e9632edb431fe9fede4
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="er-upload-a-configuration-into-lifecycle-services"></a>ER Cargar una configuración en Lifecycle Services

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración nueva de informes electrónicos y cargarla en Microsoft Lifecycle Services (LCS).

En este ejemplo, creará una configuración y la subira a LCS para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre las empresas. Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones. También se requiere el acceso a LCS para finalizar estos pasos.

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Seleccione "Litware, Inc." y establézcala como activa.
3. Haga clic en Configuraciones.

## <a name="create-a-new-data-model-configuration"></a>Creación de un nuevo modelo de configuración de datos
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
    * Creará una configuración que contenga un modelo de datos de muestra para los documentos electrónicos. Esta configuración del modelo de datos se cargará en LCS más adelante.  
2. En el campo Nombre, escriba "Configuración del modelo de ejemplo".
    * Configuración del modelo de ejemplo  
3. En el campo Descripción, escriba "Configuración del modelo de ejemplo".
    * Configuración del modelo de ejemplo  
4. Haga clic en Crear configuración.
5. Haga clic en Diseñador de modelo.
6. Haga clic en Nuevo.
7. En el campo Nombre, escriba "Punto de entrada".
    * Punto de entrada  
8. Haga clic en Agregar.
9. Haga clic en Guardar.
10. Cierre la página.
11. Haga clic en Cambiar estado.
12. Haga clic en Completar.
13. Haga clic en Aceptar

## <a name="register-a-new--repository"></a>Registrar uno nuevo repositorio
1. Cierre la página.
2. Haga clic en Repositorios.
    * Esto le permite abrir la lista de repositorios para el proveedor de configuración Litware, Inc.  
3. Haga clic en Agregar para abrir el cuadro desplegable.
    * Esto le permite agregar un nuevo repositorio.  
4. En el campo Repositorio de configuración, seleccione LCS.
5. Haga clic en Crear repositorio.
6. En el campo Proyecto, especifique o seleccione un valor.
    * Seleccione el proyecto de LCS que desee. Debe tener acceso al proyecto.  
7. Haga clic en Aceptar
    * Complete una nueva entrada de repositorio.  
8. En la lista, marque la fila seleccionada.
    * Seleccione el registro de repositorio LCS.  
    * Tenga en cuenta que un repositorio registrado está marcado por el proveedor actual, lo que significa que solo las configuraciones propiedad del proveedor se pueden colocar en este repositorio y, por tanto, cargar en el proyecto de LCS seleccionado.  
9. Haga clic en Abrir.
    * Abra el repositorio para ver la lista de configuraciones de ER. Estará vacío si este proyecto no se ha usado todavía para la distribución de las configuraciones de ER.  
10. Cierre la página.
11. Cierre la página.

## <a name="upload-configuration-into-lcs"></a>Cargar configuración en LCS
1. Haga clic en Configuraciones.
2. En el árbol, seleccione "Configuración del modelo de ejemplo".
    * Seleccione una configuración creada que ya se ha completado.  
3. En la lista, busque y seleccione el registro deseado.
    * Seleccione la versión de la configuración seleccionada con el estado de “Completado”.  
4. Haga clic en Cambiar estado.
5. Haga clic en Compartir.
    * El estado de la configuración cambiará de "Completado" a "Compartido" cuando se publique en LCS.  
6. Haga clic en Aceptar
7. En la lista, busque y seleccione el registro deseado.
    * Seleccione la versión de configuración con el estado de "Compartido".  
    * Tenga en cuenta que el estado de la versión seleccionada ha cambiado de "Completado" a "Compartido".  
8. Cierre la página.
9. Haga clic en Repositorios.
    * Esto le permite abrir la lista de repositorios para el proveedor de configuración Litware, Inc.  
10. Haga clic en Abrir.
    * Seleccione el repositorio de LCS y ábralo.  
    * Tenga en cuenta que la configuración seleccionada se muestra como activo del proyecto de LCS seleccionado.  
    * Abra LCS con https://lcs.dynamics.com. Abra un proyecto que se usó anteriormente para el registro de repositorio, abra "Biblioteca de activos" de este proyecto y expanda el contenido del tipo de activo "Configuración de GER"; la configuración de ER cargada estará disponible. Tenga en cuenta que la configuración de LCS cargada se puede importar a otra instancia de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition si los proveedores tienen acceso a este proyecto de LCS.  


