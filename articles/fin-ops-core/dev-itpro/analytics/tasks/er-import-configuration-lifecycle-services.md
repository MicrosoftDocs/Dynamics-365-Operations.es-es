---
title: Importar una configuración de Lifecycle Services
description: Este artículo describe cómo importar una nueva versión de una configuración de informes electrónicos (ER) desde Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
ms.openlocfilehash: 92c5d010430b38cb6c11a87283a2f7d4c29484f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290376"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>Importar una configuración de Lifecycle Services

[!include [banner](../../includes/banner.md)]

En este artículo se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una [configuración de informe electrónico](../general-electronic-reporting.md#Configuration) desde la [biblioteca de activos de proyectos](../../lifecycle-services/asset-library.md) en Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> El uso de (LCS) como repositorio de almacenamiento para las configuraciones de ER se está poniendo [en desuso](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Para más ifnormación, vea: [Regulatory Configuration Service (RCS): desactivación del almacenamiento de Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).

En este ejemplo, seleccionará la configuración de la versión deseada del ER y la importará a la empresa de ejemplo que se llama Litware, Inc. Estos pasos se pueden realizar en cualquier empresa porque las configuraciones de ER se comparten entre todas las empresas. Para completar estos pasos, primero debe completar los pasos del procedimiento [Cargar una configuración ER en Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). También se requiere acceso a LCS.

1. Inicie sesión a la aplicación mediante uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Administrador del sistema

2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. Seleccione **Configuraciones**.

<a name="accessconditions"></a>
> [!NOTE]
> Asegúrese de que el usuario actual de Dynamics 365 Finance es miembro del proyecto LCS que contiene la biblioteca de activos al que el usuario desea [acceder](../../lifecycle-services/asset-library.md#asset-library-support) para importar configuraciones de ER.
>
> No puede acceder a un proyecto LCS desde un repositorio de ER que representa un dominio diferente al dominio que se usa en Finance. Si lo intenta, se mostrará una lista vacía de proyectos LCS y no podrá importar configuraciones de ER desde la biblioteca de activos en el nivel de proyecto en LCS. Para acceder a las bibliotecas de activos en el nivel de proyecto desde un repositorio de ER que se utiliza para importar configuraciones de ER, inicie sesión en Finance utilizando las credenciales de un usuario que pertenezca al inquilino (dominio) para el que se ha aprovisionado la instancia de Finance actual.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>Eliminar una versión compartida de la configuración del modelo de datos

1. En la página **Configuraciones**, en el árbol de configuraciones, seleccione **Configuración del modelo de ejemplo**.

    Se ha creado la primera versión de la configuración del modelo de datos de muestra y se ha publicado en LCS cuando completó los pasos en [Cargar una configuración ER en Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). En este procedimiento, eliminará esta versión de la configuración de ER. Luego, importará esa versión de LCS más adelante en este artículo.

2. En la lista, busque y seleccione el registro deseado.

    Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Compartido**. Este estado indica que la configuración se ha publicado en LCS.

3. Seleccione **Cambiar estado**.
4. Seleccione **Interrumpir**.

    Al cambiar el estado de la versión seleccionada de **Compartido** a **Interrumpido**, hace que la versión esté disponible para la eliminación.

5. Seleccione **Aceptar**.
6. En la lista, busque y seleccione el registro deseado.

    Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Interrumpido**.

7. Seleccione **Eliminar**.
8. Seleccione **Sí**.

    Tenga en cuenta que solo la versión de borrador 2 de la configuración del modelo de datos seleccionada está ahora disponible.

9. Cierre la página.

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>Importar una versión compartida de la configuración del modelo de datos de LCS

1. Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.

2. En la sección **Proveedores de configuración**, seleccione el icono de **Litware, Inc.**.

3. En el icono **Litware, Inc.**, seleccione **Repositorios**.

    Ahora puede abrir la lista de repositorios para el proveedor de configuración Litware, Inc.

4. Seleccione **Abrir**.

    Para este ejemplo, seleccione el repositorio **LCS** y ábralo. Debe tener [acceso](#accessconditions) al proyecto LCS y a la biblioteca de activos a la que accede el repositorio ER seleccionado.

5. En la lista, marque la fila seleccionada.

    Para este ejemplo, seleccione la primera versión de **Configuración del modelo de ejemplo** en la lista de versiones.

6. Seleccione **Importar**.
7. Seleccione **Sí** para confirmar la importación de la versión seleccionada de LCS.

    Un mensaje informativo confirma que la versión seleccionada se importó correctamente.

8. Cierre la página.
9. Cierre la página.
10. Seleccione **Configuraciones**.
11. En el árbol, seleccione **Configuración del modelo de ejemplo**.
12. En la lista, busque y seleccione el registro deseado.

    Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Compartido**.

    Tenga en cuenta que la versión compartida 1 de la configuración del modelo de datos seleccionada está disponible ahora también.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
