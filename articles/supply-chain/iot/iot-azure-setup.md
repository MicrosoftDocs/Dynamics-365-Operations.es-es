---
title: Configurar recursos de Azure para Inteligencia IoT
description: Este tema explica cómo crear y configurar los recursos Microsoft Azure que necesita para Inteligencia IoT.
author: ''
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ea1083a65efb25699b9237c72c081f50e1fb476c
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802782"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>Configurar recursos de Azure para Inteligencia IoT

[!include [banner](../../includes/banner.md)]

Este tema explica cómo crear y configurar los recursos Microsoft Azure que necesita para Inteligencia IoT.

## <a name="create-azure-resources"></a>Crear recursos de Azure

Siga estos pasos para crear un centro de IoT, una caché Redis y un almacén de claves al que se pueda acceder mediante Microsoft Dynamics 365 Supply Chain Management.

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>Verifique que el id. de la aplicación de primera entidad Microsoft Dynamics ERP Microservices está en su inquilino

Para verificar que el id. de la aplicación de primera entidad Microsoft Dynamics ERP Microservices está en su inquilino, siga estos pasos.

1. Inicie sesión en el portal Azure en <https://portal.azure.com>.
2. Ir a **Azure Active Directory**.
3. Vaya a **Aplicaciones empresariales**.
4. En el campo **Tipo de aplicacion**, seleccione **Aplicaciones de Microsoft**.
5. En el campo de búsqueda, introduzca **Microsoft Dynamics Microservicios ERP**.
6. Verifique que **Microsoft Dynamics ERP Microservices** está en la lista. Otras aplicaciones tienen nombres similares. Por lo tanto, debe asegurarse de encontrar la aplicación correcta. El id. de la aplicación es **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Si la aplicación no está en la lista, debe agregarla a su inquilino:

    1. En Azure Portal, en la barra de herramientas, seleccione el botón para abrir Azure Cloud Shell.
    2. Ejecute el comando **Install-Module AzureAD**. Introduzca **Y** para instalar el módulo.
    3. Ejecute el comando **Get-InstalledModule -Name "AzureAD"** para verificar que el módulo esté instalado.
    4. Ejecute el comando **Connect-AzureAD -Confirm** para ejecutar la autenticación.
    5. Ejecute el comando **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Ahora puede repetir los pasos 1 a 6 para verificar que el id. de la aplicación esté en su inquilino.

### <a name="create-a-key-vault-resource"></a>Crear un recurso de almacén de claves

Para crear un recurso de almacén de claves, siga estos pasos.

1. En Azure Portal, cree o vaya a un grupo de recursos.
2. Seleccione **Agregar**.
3. En la página **Nuevo**, en el campo de búsqueda, introduzca **Almacén de claves**. Después seleccione **Crear**.
4. En la página **Crear almacén de claves**, en el campo **Nombre de almacén de claves**, introduzca un nombre.
5. Revise los valores predeterminados y luego seleccione **Revisar + crear**.
6. Seleccione **Crear**.

El almacén de claves se crea en segundo plano.

### <a name="create-an-iot-hub-resource"></a>Crear un recurso de centro de IoT

Para crear un recurso de centro de IoT, siga estos pasos.

1. Cree un grupo de recursos o vaya a él.
2. Seleccione **Agregar**.
3. En la página **Nuevo**, en el campo de búsqueda, introduzca **Centro de IoT**. Después seleccione **Crear**.
4. En el campo **Nombre de centro de IoT**, introduzca un nombre.
5. Revise los valores predeterminados y luego seleccione **Revisar + crear**.
6. Seleccione **Crear**.

El centro de IoT se crea en segundo plano.

> [!NOTE]
> Se recomienda crear solo un recurso de centro de IoT por entorno.

### <a name="create-a-redis-cache-resource"></a>Crear un recurso de caché Redis

Para crear un recurso de caché Redis, siga estos pasos.

1. Cree un grupo de recursos o vaya a él.
2. Seleccione **Agregar**.
3. En la página **Nuevo**, en el campo de búsqueda, introduzca **Azure Cache para Redis**. Después seleccione **Crear**.
4. Introduzca un nombre en el campo **Nombre DNS**.
5. Revise los valores predeterminados y luego seleccione **Crear**.

La caché Redis se crea en segundo plano.

> [!NOTE]
> Se recomienda crear solo una sola caché Redis por entorno.

Todos los recursos se han creado ya.

## <a name="configure-the-azure-resources"></a>Configurar los recursos de Azure

### <a name="configure-the-iot-hub"></a>Configurar el centro de IoT

Para configurar el centro de IoT, siga estos pasos.

1. En sus recursos, seleccione el recurso del centro de IoT.
2. En el panel de navegación izquierdo, seleccione **Puntos finales incorporados**.
3. En **Grupos de consumidores**, pegue los siguientes grupos de consumidores. Estos grupos de consumidores corresponden a los escenarios listos para usar.

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>Configurar el almacén de claves

Para configurar el almacén de claves, siga estos pasos.

1. En sus recursos, seleccione el recurso del almacén de claves.
2. En el panel de navegación izquierdo, seleccione **Directivas de acceso**.
3. Seleccione **Agregar una directiva de acceso**.
4. En la página **Agregar directiva de acceso**, en el campo **Permisos secretos**, seleccione **Obtener** y **Lista**.
5. Haga clic en **Seleccionar principal**.
6. En el cuadro de diálogo **Principal**, busque y seleccione **Microsoft Dynamics ERP Microservices**. Luego, seleccione **Seleccionar**.
7. Seleccione **Agregar**.
8. Seleccione **Guardar**.

La aplicación ya tiene acceso a los secretos del almacén de claves.

### <a name="save-the-iot-hub-connection-string-secret"></a>Guardar el secreto de cadena de conexión del centro de IoT

Para guardar el secreto de la cadena de conexión del centro de IoT, siga estos pasos.

1. En sus recursos, seleccione el recurso del centro de IoT.
2. En el panel de navegación izquierdo, seleccione **Puntos finales incorporados**.
3. Copie el valor en el campo **Punto final compatible con Event Hub**.
4. Vaya al recurso del almacén de claves.
5. En el panel de navegación izquierdo, seleccione **Secretos**.
6. Seleccione **Generar/Importar**.
7. Escriba un nombre en el campo **Nombre**.
8. En el campo **Valor**, pegue el valor del punto final que copió anteriormente.
9. Seleccione **Crear**.

### <a name="save-the-redis-cache-connection-string-secret"></a>Guardar el secreto de cadena de conexión de la caché Redis

Para guardar el secreto de la cadena de conexión de la caché Redis, siga estos pasos.

1. En sus recursos, seleccione el recurso de caché Redis.
2. Seleccione **Claves de acceso**.
3. Copie el valor en el campo **Cadena de conexión primaria**.
4. Vaya al recurso del almacén de claves.
5. En el panel de navegación izquierdo, seleccione **Secretos**.
6. Seleccione **Generar/Importar**.
7. Escriba un nombre en el campo **Nombre**.
8. En el campo **Valor**, pegue la cadena de conexión que copió anteriormente.
9. Seleccione **Crear**.

> [!NOTE]
> Siempre que actualice una de las cadenas de conexión, también debe actualizar los valores secretos.

Ya ha terminado de aprovisionar los recursos de Azure necesarios. El siguiente paso es [instalar el complemento Inteligencia IoT en Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).
