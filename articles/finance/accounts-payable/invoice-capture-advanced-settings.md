---
title: Configuración avanzada de la solución Invoice Capture
description: Este artículo proporciona información sobre la configuración avanzada de la solución Invoice Capture.
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
ms.openlocfilehash: a1e24b700d0f30fd90f2619dd6e6687736a86774
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691203"
---
# <a name="invoice-capture-solution-advanced-settings"></a>Configuración avanzada de la solución Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artículo proporciona información sobre la configuración avanzada de la solución Invoice Capture.

## <a name="create-additional-connections-for-channels"></a>Crear conexiones adicionales para canales

Debe crear conexiones con el correo electrónico o el almacenamiento de archivos para permitir el seguimiento de las facturas entrantes desde diferentes canales. Debe registrar las conexiones al principio para otorgar acceso a los flujos automatizados que se utilizan en la solución.

Los siguientes tipos de conexión se utilizan para importar facturas:

- Office 365 Outlook
- Outlook.com
- OneDrive
- SharePoint

El canal para la importación de facturas utilizará las conexiones en otros pasos de configuración. Antes de que los usuarios puedan crear un canal de una conexión específica, se les debe otorgar un rol de seguridad **Administrador** y deben crear conexiones.

Para crear una conexión con Microsoft Dataverse, siga estos pasos.

1. Vaya a **Sistema de administración \> Solución predeterminada**.
2. Seleccione **Nuevo** y después **Referencia de conexión**.
3. Escriba un nombre en el campo **Nombre para mostrar**.
4. Seleccione **Microsoft Dataverse** como conector.
5. Si está configurando la conexión por primera vez, seleccione **Nueva conexión**.
6. En el cuadro de diálogo que aparece, cree una conexión de Dataverse y luego seleccione **Crear**.
7. Introduzca la cuenta y contraseña de Dataverse.
8. Después de pasar la validación, vaya a la página de conexión, seleccione **Actualizar**, seleccione la cuenta y luego seleccione **Crear**.

Para crear un correo electrónico o conexión de almacenamiento de archivo, siga estos pasos.

1. Sobre la página **Creación de conexión**, en el campo **Tipo de conección**, seleccione **Office 365 Outlook**.
2. Para una conexión de correo electrónico, puede seleccionar **Outlook.com** u **Office 365 Outlook** como el conector. Para una conexión de almacenamiento de archivos, puede seleccionar **OneDrive** o **SharePoint**.

Para revisar las conexiones existentes, vaya a **Solución por defecto \> Objetos \> Referencias de conexión**. El usuario que crea canales debe tener al menos una conexión de Dataverse además de correo electrónico específico o conexiones de almacenamiento de archivos. El creador del nuevo canal debe ser el propietario de la conexión.
