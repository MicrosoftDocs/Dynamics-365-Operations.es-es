---
title: "Descargar configuraciones de informes electrónicos de Lifecycle Services"
description: "En este tema se explica cómo descargar las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1e73cd38c33d88feaba825abb64721bc332a4d6e
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Descargar configuraciones de informes electrónicos de Lifecycle Services

[!include[banner](../includes/banner.md)]


En este tema se explica cómo descargar las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS).

Este tutorial le guía por el proceso de descarga de la versión más reciente de las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS).

1.  Inicie sesión en Dynamics 365 for Operations mediante una de las siguientes funciones:
    -   Desarrollador de informes electrónicos
    -   Consultor funcional de informes electrónicos
    -   Administrador del sistema

2.  Vaya a **Administración de la organización** &gt; **Informes electrónicos**.
3.  En la sección **Proveedores de configuración**, seleccione el icono de **Microsoft**.
4.  En el icono de **Microsoft**, haga clic en **Repositorios**. [![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)
5.  En la página **Repositorios de configuración**, en la cuadrícula, seleccione el repositorio existente del tipo **LCS**. Si este repositorio no aparece en la cuadrícula, siga estos pasos:
    1.  Haga clic en **Agregar** para agregar un repositorio nuevo.
    2.  Seleccione **LCS** como el tipo de repositorio.
    3.  Haga clic en **Crear repositorio**.
    4. Si se le solicite, siga las instrucciones de autorización.
    5.  Especifique un nombre y una descripción para el repositorio.
    6.  Haga clic en **Aceptar** para confirmar la nueva entrada de repositorio.
    7.  En la cuadrícula, seleccione el nuevo repositorio del tipo **LCS**.

6.  Haga clic en **Abierta** para ver la lista de configuraciones de ER para el repositorio seleccionado. [![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  En el árbol de configuración del panel izquierdo, seleccione la configuración de ER que necesita.
8.  En la ficha desplegable **Versiones**, seleccione la versión necesaria de la configuración de ER seleccionada.
9.  Haga clic en **Importar** para descargar la versión seleccionada de LCS a la instancia actual de Dynamics 365 for Operations. **Nota:** El botón **Importar** no está disponible para las versiones de configuración de ER que ya están presentes en la instancia actual de Dynamics 365 for Operations. [![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

**Nota:** En función de la configuración de ER, se validan las configuraciones después de haberlas importado. Es posible que se le notifique acerca de los problemas de incoherencias que se detecten. Debe resolver esos problemas antes de poder usar la versión de configuración importada. Para obtener más información, consulte la lista de artículos relacionados para este tema.

<a name="see-also"></a>Consulte también
--------

[Visión general de los informes electrónicos](general-electronic-reporting.md)




