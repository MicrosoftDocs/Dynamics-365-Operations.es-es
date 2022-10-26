---
title: Instalar la solución Invoice Capture
description: Este artículo proporciona información sobre cómo instalar la solución de Invoice Capture  e integrarla con Microsoft Dynamics 365 Finance.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: d853e347c833345f34b65760fd7ee35cbb38c9a3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691226"
---
# <a name="install-the-invoice-capture-solution"></a>Instalar la solución Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Si instaló la solución en versión preliminar privada, debe desinstalar la solución anterior antes de continuar.

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda instalar la solución Invoice Capture, debe completar los siguientes requisitos previos:

1. Registre una solicitud y agregue un secreto de cliente a Microsoft Azure Active Directory (Azure AD) en su suscripción de Azure. Para obtener más información, consulte [Registrar una aplicación web con AAD](../../dev-itpro/data-entities/services-home-page.md#register-a-web-application-with-aad).

    > [!NOTE]
    > Tome nota de los valores de **Id. de la aplicación (cliente)**, **Secreto del cliente** e **Id. de inquilino**, porque los necesitará más adelante.

2. Registre la aplicación de Azure en un entorno de Dynamics 365 Finance. Para obtener más información, consulte [Registrar la aplicación externa](../../dev-itpro/data-entities/services-home-page.md#register-your-external-application).

## <a name="install-and-set-up-the-solution"></a>Instalar y configurar la solución

Para instalar la solución de Invoice Capture , vaya a AppSource y seleccione el vínculo para la versión preliminar de [Dynamics 365 Invoice Capture](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics365-invoice-capture-preview?flightCodes=invoicecapture). Una vez completada la instalación, verá la solución instalada en el entorno seleccionado en Power Apps.

Para completar la configuración de almacén, siga estos pasos.

1. Descargue la [solución asistente](https://github.com/InvoiceCapture/InstallationTools/releases/download/latest/msdyn_InvoiceCaptureIntallationTools.zip) para configurar los siguientes detalles:

    - La comunicación entre Microsoft Power Platform y el entorno financiero
    - La referencia de conexión para Dataverse y Office 365 Outlook que utilizará el canal

2. En Power Apps, vaya a su entorno y seleccione **Importar solución**.
3. Seleccione **Navegar**, seleccione el paquete de solución del asistente que descargó y luego seleccione **Siguiente**.
4. Seleccione **Siguiente**.
5. Asigne una conexión existente o cree una nueva seleccionando **Nueva conexión**.
6. Una vez que el paquete se haya importado correctamente, abra **Dynamics 365 Invoice Capture: herramientas de instalación**.
7. Ejecute el flujo de nube para configurar la conexión entre la solución de Invoice Capture  en Microsoft Power Platform y Finance.
8. Seleccione **Ejecutar** y especifique los siguientes parámetros:

    - **URL de Dynamics 365 Finance** – La URL del entorno de Finance con el que desea integrarse.
    - **Id. de inquilino** - Id. de inquilino del entorno de Finance.
    - **Identificación del cliente** – El ID de la aplicación de Azure que se registró.
    - **Secreto de cliente** - Secreto de cliente que se generó para la aplicación de Azure.
