---
title: Configuración de doble escritura desde Lifecycle Services
description: Este tema explica cómo configurar una conexión de doble escritura entre un entorno nuevo de Finance and Operations y un entorno nuevo de Dataverse desde Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 25db9c58c3d09e44dcf11b48cae1a9eda4241c35
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683534"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuración de doble escritura desde Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema explica cómo configurar una conexión de doble escritura entre un entorno nuevo de Finance and Operations y un entorno nuevo de Dataverse desde Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Requisitos previos

Debe ser administrador para configurar una conexión de doble escritura.

+ Debe tener acceso al inquilino.
+ Debes ser administrador tanto en entornos Finance and Operations y entornos Dataverse.

## <a name="set-up-a-dual-write-connection"></a>Configurar una conexión de doble escritura

Siga estos pasos para configurar una conexión de doble escritura.

1. En LCS, vaya a su proyecto.
2. Seleccione **Configurar** para implementar un nuevo entorno.
3. Seleccione la versión. 
4. Seleccione la topología. Si solo hay una topología disponible, se selecciona automáticamente.
5. Complete los primeros pasos en el asistente **Configuraciones de implementación**.
6. En la pestaña **Dataverse**, siga uno de estos pasos:

    - Si un entorno Dataverse ya está aprovisionado para su inquilino, puede seleccionarlo.

        1. Establezca la opción **Configurar Dataverse** a **Sí**.
        2. En el campo **Entornos disponibles**, seleccione el entorno para integrar con sus datos Finance and Operations. La lista incluye todos los entornos donde tiene privilegios de administrador.
        3. Selecciona la casilla de verificación **De acuerdo** para indicar que está de acuerdo con los términos y condiciones.

        ![Pestaña Dataverse cuando un entorno Dataverse ya está aprovisionado para su inquilino](../dual-write/media/lcs_setup_1.png)

    - Si su inquilino aún no tiene un entorno Dataverse, se proporcionará un nuevo entorno.

        1. Establezca la opción **Configurar Dataverse** a **Sí**.
        2. Escriba un nombre para el entorno Dataverse.
        3. Seleccione la región para implementar el entorno.
        4. Seleccione el idioma y la divisa predeterminados para el entorno.

            > [!NOTE]
            > No puede cambiar el idioma y la moneda más tarde.

        5. Selecciona la casilla de verificación **De acuerdo** para indicar que está de acuerdo con los términos y condiciones.

        ![Pestaña Dataverse cuando su inquilino aún no tiene un entorno Dataverse](../dual-write/media/lcs_setup_2.png)

7. Complete los pasos restantes en el asistente **Configuraciones de implementación**.
8. Después de que el entorno tenga un estado de **Implementado**, abra la página de detalles del entorno. La sección **Información del entorno de Dataverse** muestra los nombres de entorno Finance and Operations y el entorno Dataverse que están vinculados.

    ![Sección de información de entorno de Dataverse](../dual-write/media/lcs_setup_3.png)

9. Un administrador del entorno de Finance and Operations debe iniciar sesión en LCS y seleccionar **Enlazar a CDS para aplicaciones** para completar el enlace. La página de detalles del entorno muestra la información de contacto del administrador.

    Una vez que se completa el enlace, el estado se actualiza a **Enlace de entorno completado con éxito**.

10. Para abrir el espacio de trabajo **Integración de datos** en el entorno Finance and Operations y controlar de las plantillas disponibles, seleccione **Enlazar a CDS para aplicaciones**.

    ![Enlace al botón CDS para aplicaciones en la sección de información del entorno de Dataverse](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> No puede desvincular entornos utilizando LCS. Para desvincular un entorno, abra el espacio de trabajo **Integración de datos** en el entorno Finance and Operations, y luego seleccione **Desvincular**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]