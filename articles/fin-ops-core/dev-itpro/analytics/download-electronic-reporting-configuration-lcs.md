---
title: Descargar configuraciones de informes electrónicos de Lifecycle Services
description: En este tema se explica cómo descargar las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 49785835ee2da911d7b8d1360e1c42f850f1153f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771502"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Descargar configuraciones de informes electrónicos de Lifecycle Services

[!include [banner](../includes/banner.md)]

En este tema se explica cómo descargar las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS).

Este tutorial le guía por el proceso de descarga de la versión más reciente de las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS).

1. Inicie sesión a la aplicación mediante uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

2. Vaya a **Administración de la organización** &gt; **Informes electrónicos**.
3. En la sección **Proveedores de configuración**, seleccione el icono de **Microsoft**.
4. En el icono de **Microsoft**, haga clic en **Repositorios**.

    [![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. En la página **Repositorios de configuración**, en la cuadrícula, seleccione el repositorio existente del tipo **LCS**. Si este repositorio no aparece en la cuadrícula, siga estos pasos:

    1. Haga clic en **Agregar** para agregar un repositorio nuevo.
    2. Seleccione **LCS** como el tipo de repositorio.
    3. Haga clic en **Crear repositorio**.
    4. Si se le solicite, siga las instrucciones de autorización.
    5. Especifique un nombre y una descripción para el repositorio.
    6. Haga clic en **Aceptar** para confirmar la nueva entrada de repositorio.
    7. En la cuadrícula, seleccione el nuevo repositorio del tipo **LCS**.

6. Haga clic en **Abierta** para ver la lista de configuraciones de ER para el repositorio seleccionado.

    [![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

7. En el árbol de configuración del panel izquierdo, seleccione la configuración de ER que necesita.
8. En la ficha desplegable **Versiones**, seleccione la versión necesaria de la configuración de ER seleccionada.
9. Haga clic en **Importar** para descargar la versión seleccionada de LCS en la instancia actual.

    > [!NOTE]
    > El botón **Importar** no está disponible para las versiones de configuración de ER que ya están presentes en la instancia actual.

    [![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> En función de la configuración de ER, se validan las configuraciones después de haberlas importado. Es posible que se le notifique acerca de los problemas de incoherencias que se detecten. Debe resolver esos problemas antes de poder usar la versión de configuración importada. Para obtener más información, consulte la lista de artículos relacionados para este tema.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
