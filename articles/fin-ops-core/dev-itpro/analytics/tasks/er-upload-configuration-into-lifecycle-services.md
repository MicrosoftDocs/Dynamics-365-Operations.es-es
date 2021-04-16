---
title: Cargar una configuración en Lifecycle Services
description: En este tema se explica cómo crear una nueva configuración de Informes electrónicos (ER) y subirla a Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0211fea7af303fe1dd7dce26f887bed4ed3b0f1e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744924"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>Cargar una configuración en Lifecycle Services

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede cargar una nueva versión de una [configuración de informe electrónico](../general-electronic-reporting.md#Configuration) y cargarla en la [biblioteca de activos de proyectos](../../lifecycle-services/asset-library.md) en Microsoft Dynamics Lifecycle Services (LCS).

En este ejemplo, creará una configuración y la cargará a LCS para la empresa de demostración que se llama Litware, Inc. Estos pasos se pueden completarse en cualquier empresa porque las configuraciones de ER se comparten entre las empresas. Para completar estos pasos, primero debe completar los pasos en [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md). También se requiere acceso a LCS.

1. Inicie sesión a la aplicación mediante uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Administrador del sistema

2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. Seleccione **Litware, Inc.** y márquela como **Activa**.
4. Seleccione **Configuraciones**.

<a name="accessconditions"></a>
> [!NOTE]
> Asegúrese de que el usuario actual de Dynamics 365 Finance es miembro del proyecto LCS que contiene la [biblioteca de activos](../../lifecycle-services/asset-library.md#asset-library-support) que se usa para importar configuraciones de ER.
>
> No puede acceder a un proyecto LCS desde un repositorio de ER que representa un dominio diferente al dominio que se usa en Finance. Si lo intenta, se mostrará una lista vacía de proyectos LCS y no podrá importar configuraciones de ER desde la biblioteca de activos a nivel de proyecto en LCS. Para acceder a las bibliotecas de activos a nivel de proyecto desde un repositorio de ER que se utiliza para importar configuraciones de ER, inicie sesión en Finance utilizando las credenciales de un usuario que pertenezca al inquilino (dominio) para el que se ha aprovisionado la instancia de Finance actual.

## <a name="create-a-new-data-model-configuration"></a>Creación de un nuevo modelo de configuración de datos

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. En la página **Configuraciones**, seleccione **Crear configuración** para abrir el cuadro de diálogo desplegable.

    En este ejemplo, creará una configuración que contenga un modelo de datos de muestra para los documentos electrónicos. Esta configuración del modelo de datos se cargará en LCS más adelante.

3. En el campo **Nombre**, escriba **Configuración del modelo de ejemplo**.
4. En el campo **Descripción**, escriba **Configuración del modelo de ejemplo**.
5. Seleccionar **Crear configuración**.
6. Seleccione **Diseñador de modelos**.
7. Seleccione **Nuevo**.
8. En el campo **Nombre**, escriba **Punto de entrada**.
9. Seleccione **Agregar**.
10. Seleccione **Guardar**.
11. Cierre la página.
12. Seleccione **Cambiar estado**.
13. Seleccione **Completar**.
14. Seleccione **Aceptar**.
15. Cierre la página.

## <a name="register-a-new-repository"></a>Registrar uno nuevo repositorio

1. Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.

2. En la sección **Proveedores de configuración**, seleccione el icono de **Litware, Inc.**.

3. En el icono **Litware, Inc.**, seleccione **Repositorios**.

    Ahora puede abrir la lista de repositorios para el proveedor de configuración Litware, Inc.

4. Seleccione **Agregar** para abrir el cuadro de diálogo desplegable.

    Ahora puede agregar un nuevo repositorio.

5. En el campo para especificar el **Repositorio de configuración**, escriba **LCS**.
6. Seleccione **Crear repositorio**.
7. En el campo **Proyecto**, especifique o seleccione un valor.

    Para este ejemplo, seleccione el proyecto LCS deseado. Debe tener [acceso](#accessconditions) al proyecto.

8. Seleccione **Aceptar**.

    Complete una nueva entrada de repositorio.

9. En la lista, marque la fila seleccionada.

    Para este ejemplo, seleccione el registro del repositorio **LCS**.

    Tenga en cuenta que un repositorio registrado está marcado por el proveedor actual. En otras palabras, solo las configuraciones que son propiedad de ese proveedor pueden colocarse en este repositorio y, por lo tanto, cargarse en el proyecto LCS seleccionado.

10. Seleccione **Abrir**.

    Abre el repositorio para ver la lista de configuraciones de ER. Si seleccione un proyecto que no ha usado para compartir las configuraciones de ER, la lista estará vacía.

11. Cierre la página.
12. Cierre la página.

## <a name="upload-a-configuration-into-lcs"></a>Cargar una configuración en LCS

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones, seleccione **Configuración del modelo de ejemplo**.

    Debe seleccionar una configuración creada que ya se ha completado.

3. En la lista, busque y seleccione el registro deseado.

    Para este ejemplo, seleccione la versión de la configuración seleccionada que tiene un estado de **Completado**.

4. Seleccione **Cambiar estado**.
5. Seleccione **Compartir**.

    El estado de la configuración cambia de **Completado** a **Compartido** cuando la configuración se publica en LCS.

6. Seleccione **Aceptar**.
7. En la lista, busque y seleccione el registro deseado.

    Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Compartido**.

    Tenga en cuenta que el estado de la versión seleccionada se cambió de **Completado** a **Compartido**.

8. Cierre la página.
9. Seleccione **Repositorios**.

    Ahora puede abrir la lista de repositorios para el proveedor de configuración Litware, Inc.

10. Seleccione **Abrir**.

    Para este ejemplo, seleccione el repositorio **LCS** y ábralo.

    Tenga en cuenta que la configuración seleccionada se muestra como activo del proyecto de LCS seleccionado.

11. Abra LCS yendo a <https://lcs.dynamics.com>.
12. Abra un proyecto que se utilizó anteriormente para el registro del repositorio.
13. Abra la biblioteca de activos del proyecto.
14. Seleccione el tipo de activo **Configuración GER**.

    La configuración de ER que cargó debe aparecer en la lista.

    Tenga en cuenta que la configuración de LCS cargada se puede importar a otra instancia si los proveedores tienen acceso a este proyecto de LCS.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]