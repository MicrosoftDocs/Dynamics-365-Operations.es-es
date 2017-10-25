--- 
title: "Importar una configuración de Lifecycle Services para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una configuración de informe electrónico desde Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
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
ms.openlocfilehash: 9eb4f54897c84b98828c927f0f93613583fd4599
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a>Importar una configuración de Lifecycle Services para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una configuración de informe electrónico desde Microsoft Lifecycle Services (LCS).

En este ejemplo, seleccionará la configuración de la versión deseada del ER y la importará a la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre todas las empresas. Para completar estos pasos, primero debe completar los pasos del procedimiento "Cargar una configuración ER en Lifecycle Services". También se requiere el acceso a LCS para finalizar estos pasos.

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones.

## <a name="delete-a-shared-version-of-data-model-configuration"></a>Eliminar una versión compartida de la configuración del modelo de datos
1. En el árbol, seleccione "Configuración del modelo de ejemplo".
    * Se ha creado la primera versión de la configuración del modelo de datos de muestra y se ha publicado en LCS durante el procedimiento "Cargar una configuración ER en Lifecycle Services". En este procedimiento, eliminará esta versión de la configuración de ER. Esta versión de una configuración de modelo de datos de ejemplo se importará más tarde desde LCS.  
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione la versión de esta configuración que se encuentra en el estado "Compartido". Este estado indica que la configuración se ha publicado en LCS.  
3. Haga clic en Cambiar estado.
4. Haga clic en Interrumpir.
    * Cambie el estado de la versión seleccionada de "Compartido" a "Interrumpido" para que esté disponible para la eliminación.  
5. Haga clic en Aceptar
6. En la lista, busque y seleccione el registro deseado.
    * Seleccione la versión de esta configuración que tiene un estado de "Interrumpido".  
7. Haga clic Eliminar.
8. Haga clic en Sí.
    * Tenga en cuenta que solo la versión de borrador 2 de la configuración del modelo de datos seleccionada está disponible.  
9. Cierre la página.

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a>Importar una versión compartida de la configuración del modelo de datos de LCS
1. En la lista, marque la fila seleccionada.
    * Abra la lista de repositorios para "Litware, Inc.". Litware, Inc.  
2. Haga clic en Repositorios.
3. Haga clic en Abrir.
    * Seleccione el repositorio de LCS y ábralo.  
4. En la lista, marque la fila seleccionada.
    * Seleccionar la primera versión de "Configuración del modelo de ejemplo" en la lista de versiones.  
5. Haga clic en Importar.
6. Haga clic en Sí.
    * Confirme la importación de la versión seleccionada desde LCS.  
    * Tenga en cuenta que el mensaje de información (que se encuentra encima del formulario) confirma la finalización correcta de la importación de la versión seleccionada.  
7. Cierre la página.
8. Cierre la página.
9. Haga clic en Configuraciones.
10. En el árbol, seleccione "Configuración del modelo de ejemplo".
11. En la lista, busque y seleccione el registro deseado.
    * Seleccione la versión de esta configuración que tiene un estado de "Compartido".  
    * Tenga en cuenta que la versión compartida 1 de la configuración del modelo de datos seleccionada está disponible ahora también.  

