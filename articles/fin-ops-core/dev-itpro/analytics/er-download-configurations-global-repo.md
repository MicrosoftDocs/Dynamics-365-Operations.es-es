---
title: Descargue las configuraciones de ER del repositorio global del servicio de configuración
description: Este tema explica cómo descargar configuraciones de informes electrónicos (ER) desde el repositorio global del servicio de configuración.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a96e78a64fe0559ae5f3bfddabf3fe1cad8a3dcb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679567"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>Descargue las configuraciones de ER del repositorio global del servicio de configuración

[!include [banner](../includes/banner.md)]

Este tema explica cómo descargar [configuraciones de informes electrónicos (ER)](general-electronic-reporting.md#Configuration) desde el repositorio global del servicio de configuración. Para más información, consulte [Microsoft Dynamics 365 for Finance and Operations: Regulatory services, servicio de configuración](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="open-configurations-repository"></a>Abrir el repositorio de configuraciones

1. Inicie sesión en la aplicación Dynamics 365 Finance mediante uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

2. Vaya a **Administración de la organización > Espacios de trabajo > Informes electrónicos**.
3. En la sección **Proveedores de configuración**, seleccione el icono de **Microsoft**.
3. En el icono **Microsoft**, seleccione **Repositorios**.

    ![Espacio de trabajo de los informes electrónicos](./media/er-download-configurations-global-repo-er-workspace.png)

4. En la página **Repositorios de configuración**, en la cuadrícula, seleccione el repositorio existente del tipo **Global**. Si este repositorio no aparece en la cuadrícula, siga estos pasos:

    1. Seleccione **Agregar** para agregar un repositorio nuevo.
    2. Seleccione **Global** como tipo de repositorio y luego seleccione **Crear repositorio**.
    3. Si se le solicite, siga las instrucciones de autorización.
    4. introduzca un nombre y una descripción para el repositorio y luego seleccione **Aceptar** para confirmar la nueva entrada del repositorio.
    5. En la cuadrícula, seleccione el nuevo repositorio del tipo **Global**.

5. Seleccione **Abrir** para ver la lista de configuraciones de ER para el repositorio seleccionado.

    ![Página de repositorios de configuración](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>Importar una única configuración

1. En la página **Repositorios de configuración**, en el árbol de configuraciones, seleccione la configuración de ER que desee.
2. En la ficha desplegable **Versiones**, seleccione la versión necesaria de la configuración de ER seleccionada.
3. Seleccione **Importar** para descargar la versión seleccionada del repositorio Global a a la instancia actual de Finance.

    > [!NOTE]
    > El botón **Importar** no está disponible para las versiones de configuración de ER que ya están presentes en la instancia de Finance actual.

    ![Página de configuración del repositorio](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>Importar configuraciones filtradas

1. En la página **Repositorios de configuración**, en el árbol de configuraciones, expanda la ficha desplegable **Filtrar**.
2. En la cuadrícula **Etiquetas**, agregue las etiquetas que sean necesarias.
3. En el campo **Aplicabilidad por país/región**, seleccione los códigos de país/región apropiados y luego seleccione **Aplicar filtro**.

    > [!NOTE]
    > La ficha desplegable **Configuraciones** muestra todas las configuraciones que satisfacen las condiciones de selección especificadas.

4. En la ficha desplegable **Configuraciones**, seleccione **Importar** para descargar las configuraciones filtradas del repositorio Global a la instancia actual.
5. En la ficha desplegable **Configuraciones**, seleccione **Restablecer filtro** para limpiar las condiciones de selección especificadas.

    ![Página de configuración del repositorio](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> En característica de la configuración de ER, se validan las configuraciones después de haberlas importado. Es posible que se le notifique acerca de los problemas de incoherencias que se detecten. Debe resolver los problemas para poder usar la versión de configuración importada. Para obtener más información, consulte la lista de recursos relacionados para este tema.

> [!NOTE]
> Las configuraciones de ER se pueden configurar como dependientes de otras configuraciones. Por lo tanto, junto con una configuración seleccionada, pueden importarse automáticamente otras configuraciones. Para obtener más información sobre las dependencias de configuración, consulte [Definir la dependencia de las configuraciones de ER en otros componentes](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
