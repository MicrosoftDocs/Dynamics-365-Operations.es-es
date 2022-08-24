---
title: Descargar configuraciones de informes electrónicos de Lifecycle Services
description: En este artículo se explica cómo descargar las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.form: ERSolutionImport, ERWorkspace
ms.openlocfilehash: f48dd14bc3009550d78bd71db030c172d2ef6450
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277828"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Descargar configuraciones de informes electrónicos de Lifecycle Services

[!include [banner](../includes/banner.md)]

Este artículo explica cómo descargar la versión más reciente de [Configuraciones de informes electrónicos (ER)](general-electronic-reporting.md#Configuration) desde la [Biblioteca de activos compartidos](../lifecycle-services/asset-library.md) en Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> El uso de (LCS) como repositorio de almacenamiento para las configuraciones de ER se está poniendo [en desuso](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Para más ifnormación, vea: [Regulatory Configuration Service (RCS): desactivación del almacenamiento de Lifecycle Services (LCS)](../../../finance/localizations/rcs-lcs-repo-dep-faq.md)

1. Inicie sesión a la aplicación mediante uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

2. Vaya a **Administración de la organización** &gt; **Espacios de trabajo** &gt; **Informes electrónicos**.
3. En la sección **Proveedores de configuración**, seleccione el icono de **Microsoft**.
4. En el icono **Microsoft**, seleccione **Repositorios**.

    [![Icono de Microsoft en la página de configuraciones de localización.](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. En la página **Repositorios de configuración**, en la cuadrícula, seleccione el repositorio existente del tipo **LCS**. Si este repositorio no aparece en la cuadrícula, siga estos pasos:

    1. Seleccione **Agregar** para agregar un repositorio.
    2. Seleccione **LCS** como el tipo de repositorio.
    3. Seleccione **Crear repositorio**.
    4. Si se le solicita la autorización, siga las instrucciones en pantalla.
    5. Especifique un nombre y una descripción para el repositorio.
    6. Seleccione **Aceptar** para confirmar la nueva entrada de repositorio.
    7. En la cuadrícula, seleccione el nuevo repositorio del tipo **LCS**.

6. Seleccione **Abrir** para ver la lista de configuraciones de ER para el repositorio seleccionado.

    [![Página de repositorios de configuración.](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > Si tiene problemas para acceder al repositorio LCS para descargar configuraciones de la biblioteca de activos compartidos en LCS, puede descargar configuraciones desde el [Repositorio global](er-download-configurations-global-repo.md) en lugar.

7. En el árbol de configuración del panel izquierdo, seleccione la configuración de ER que necesita.
8. En la ficha desplegable **Versiones**, seleccione la versión necesaria de la configuración de ER seleccionada.
9. Seleccione **Importar** para descargar la versión seleccionada de LCS en la instancia actual.

    > [!NOTE]
    > El botón **Importar** no está disponible para las versiones de configuración de ER que ya están presentes en la instancia actual.

    [![Página de configuración del repositorio.](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> En característica de la configuración de ER, se validan las configuraciones después de haberlas importado. Es posible que se le notifique acerca de los problemas de incoherencias que se detecten. Debe resolver esos problemas antes de poder usar la versión de configuración importada. Para obtener más información, consulte la lista de temas relacionados para este artículo.

## <a name="additional-resources"></a>Recursos adicionales

[Información general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Descargue las configuraciones de ER del repositorio global del servicio de configuración](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
