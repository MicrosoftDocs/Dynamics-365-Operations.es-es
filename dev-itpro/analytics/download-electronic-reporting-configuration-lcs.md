---
title: "Descargar configuraciones de informes electrónicos de Lifecycle Services"
description: "Este tema explica cómo descargar las configuraciones de electrónicas (ER) que informan de servicios (LCS) del ciclo de vida de Microsoft Dynamics."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 9dca5dec846670da25926826f59d7bce0fa0dcea
ms.lasthandoff: 03/31/2017


---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Descargar configuraciones de informes electrónicos de Lifecycle Services

Este tema explica cómo descargar las configuraciones de electrónicas (ER) que informan de servicios (LCS) del ciclo de vida de Microsoft Dynamics.

Este tutorial le guía por el proceso de descarga de la versión más reciente de las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS).

1.  Inicie sesión en Dynamics 365 for Operations mediante una de las siguientes funciones:
    -   Desarrollador de informes electrónicos
    -   Consultor funcional de informes electrónicos
    -   Administrador del sistema

2.  Retroceda ** Administración de organización ** &gt; ** el informe de errores ** electrónico.
3.  En la sección **Proveedores de configuración**, seleccione el icono de **Microsoft**.
4.  En el icono de **Microsoft**, haga clic en **Repositorios**. [actualización-er-de-LCS-para-MS-Abrir-MS-repositorio-lista de![] (. /media/update-er-from-lcs-for-ms-open-ms-repositories-list.png])(. /media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)
5.  En la página **Repositorios de configuración**, en la cuadrícula, seleccione el repositorio existente del tipo **LCS**. Si este repositorio no aparece en la cuadrícula, siga estos pasos:
    1.  Haga clic en **Agregar** para agregar un repositorio nuevo.
    2.  Seleccione **LCS** como el tipo de repositorio.
    3.  Haga clic en **Crear repositorio**.
    4.  Especifique un nombre y una descripción para el repositorio.
    5.  Haga clic en **Aceptar** para confirmar la nueva entrada de repositorio.
    6.  En la cuadrícula, seleccione el nuevo repositorio del tipo **LCS**.

6.  Haga clic en **Abierta** para ver la lista de configuraciones de ER para el repositorio seleccionado. [actualización-er-de-LCS-para-MS-crear-LCS-repositorio de![] (. /media/update-er-from-lcs-for-ms-make-lcs-repository.png])(. /media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  En el árbol de configuración del panel izquierdo, seleccione la configuración de ER que necesita.
8.  En la ficha desplegable **Versiones**, seleccione la versión necesaria de la configuración de ER seleccionada.
9.  Haga clic en **Importar** para descargar la versión seleccionada de LCS a la instancia actual de Dynamics 365 for Operations. **Nota:** El botón **Importar** no está disponible para las versiones de configuración de ER que ya están presentes en la instancia actual de Dynamics 365 for Operations. [actualización-er-de-LCS-para-MS-descarga-configuración de![] (. /media/update-er-from-lcs-for-ms-download-configuration.png])(. /media/update-er-from-lcs-for-ms-download-configuration.png)

**Nota:** En función de la configuración de ER, se validan las configuraciones después de haberlas importado. Es posible que se le notifique acerca de los problemas de incoherencias que se detecten. Debe resolver esos problemas antes de poder usar la versión de configuración importada. Para obtener más información, consulte la lista de artículos relacionados para este tema.

<a name="see-also"></a>Consulte también
--------

[Visión general de los informes electrónicos](general-electronic-reporting.md)


