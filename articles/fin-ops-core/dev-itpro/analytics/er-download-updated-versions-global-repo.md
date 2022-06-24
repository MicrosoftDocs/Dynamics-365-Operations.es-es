---
title: Importar versiones actualizadas de configuraciones ER
description: Este artículo explica cómo importar versiones actualizadas de informes electrónicos (ER) desde el repositorio global del servicio de configuración.
author: NickSelin
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 69eaa3e2ecfbd1e92f23725d97d7fa9f0abe1cea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847557"
---
# <a name="import-updated-versions-of-er-configurations"></a>Importar versiones actualizadas de configuraciones ER

[!include [banner](../includes/banner.md)]

Los [repositorios](general-electronic-reporting.md#Repository) de informes electrónicos (ER) se usan para compartir [configuraciones ER](general-electronic-reporting.md#Configuration). Puede [importar](download-electronic-reporting-configuration-lcs.md) configuraciones de ER desde diferentes repositorios en su instancia de Microsoft Dynamics 365 Finance. Cuando importa configuraciones de ER, los [proveedores de configuración](general-electronic-reporting.md#Provider) puede publicar [versiones](general-electronic-reporting.md#component-versioning) nuevas de repositorios para que puedan ser compartidos.

Este artículo explica cómo importar versiones actualizadas de ER desde el repositorio global del servicio de configuración. Para más información, consulte [Microsoft Dynamics 365 for Finance and Operations: Regulatory services, servicio de configuración](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="review-the-available-updated-versions"></a>Revise las versiones actualizadas disponibles

1. Inicie sesión en Finance mediante con uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Importar versiones actualizadas de configuraciones**.

    ![Página de ubicación de configuraciones.](./media/er-download-updated-versions-global-repo1.png)

4. En el cuadro de diálogo **Importar actualizaciones de versiones de configuraciones de informes electrónicos**, en el campo **Modo de ejecución**, seleccione **Mostrar solo las actualizaciones disponibles**. A continuación seleccione **Aceptar**. 

    ![El campo Modo de ejecución está configurado para mostrar solo las actualizaciones disponibles.](./media/er-download-updated-versions-global-repo2.png)

5. Revise los mensajes que recibe. Estos mensajes proporcionan la siguiente información sobre las configuraciones de ER en la instancia actual de Finance y cómo se comparan con el contenido del repositorio global:

    - El número total de configuraciones de ER
    - Configuraciones de ER que no están presentes en el repositorio global
    - Configuraciones de ER para las cuales la última versión ya está disponible en la instancia actual de Finance (para ver la lista completa de estas configuraciones de ER, seleccione el enlace **Detalles del mensaje**).

        ![Mensaje y detalles del mensaje "Las últimas versiones de las siguientes configuraciones ya están importadas"](./media/er-download-updated-versions-global-repo3.png)

    - Configuraciones de ER para las cuales la última versión está disponible en el repositorio global y pueden importarse en la instancia actual de Finance (para ver la lista completa de estas configuraciones de ER, seleccione el enlace **Detalles del mensaje**).

        ![Mensaje "Actualizaciones disponibles" y detalles del mensaje](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>Importar versiones actualizadas disponibles

1. Inicie sesión en Finance mediante con uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Importar versiones actualizadas de configuraciones**.
4. En el cuadro de diálogo **Importar actualizaciones de versiones de configuraciones de informes electrónicos**, en el campo **Modo de ejecución**, seleccione **Importar las últimas actualizaciones** para importar las últimas versiones de configuraciones ER desde el repositorio global a la instancia actual de Finance.
5. Para programar un trabajo por lotes para la importación, en la ficha desplegable **Correr en segundo plano**, configure la opción **Procesamiento por lotes** **Sí**. Si desea repetir la importación periódicamente, configure la recurrencia requerida.

    ![Campo de modo de ejecución configurado para importar las últimas actualizaciones.](./media/er-download-updated-versions-global-repo5.png)

6. Seleccione **Aceptar**.
7. Para saber qué versiones de configuración se han importado, siga uno de estos pasos:

    - Si ejecuta la importación de forma interactiva en lugar de utilizar un trabajo por lotes, revise los mensajes que recibe.

        ![Mensajes recibidos durante una ejecución de importación interactiva.](./media/er-download-updated-versions-global-repo6.png)

    - Si ejecuta la importación en modo por lotes, siga estos pasos:

        1. Vaya **Común** \> **Consultas** \> **Trabajos por lotes** \> **Mis trabajos por lotes**.
        2. Encuentre y seleccione el trabajo **Importar actualizaciones de versiones de configuraciones de informes electrónicos** y luego, en el Panel de acciones, en la pestaña **Trabajo por lotes**, seleccione **Historial de trabajo por lotes** para ver el historial de trabajos.
        3. En la página **Historial de trabajo por lotes**, seleccione **Registro**. Luego, en el mensaje que recibe, seleccione el vínculo **Detalles del mensaje** para ver el registro de trabajo.

        ![Registro de trabajo.](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> No recomendamos que programe un trabajo por lotes recurrente para importar versiones actualizadas de configuraciones de ER directamente desde el repositorio global a un entorno de producción, porque las versiones importadas estarán disponibles de inmediato para su uso. En su lugar, utilice este enfoque para implementar versiones de configuraciones de ER en un entorno de espacio aislado. Luego pueden evaluarse en el entorno de espacio aislado antes de implementarse en un entorno de producción.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Descargue las configuraciones de ER del repositorio global del servicio de configuración](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]