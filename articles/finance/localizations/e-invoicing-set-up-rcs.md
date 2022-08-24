---
title: Configurar Regulatory Configuration Service (RCS)
description: En este artículo se explica cómo configurar Regulatory Configuration Service (RCS).
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 63a4f77d6e80133947dff678cef3885167ec55be
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285799"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>Configurar Regulatory Configuration Service (RCS)

[!include [banner](../includes/banner.md)]

En este artículo se explica cómo configurar Regulatory Configuration Service (RCS).

## <a name="turn-on-globalization-features"></a>Active las características de globalización

1. Inicie sesión en su cuenta de RCS.
2. Seleccione la ventana **Gestión de funciones**.
3. En el espacio de trabajo **Administración de características**, seleccione **Características de globalización** en la lista y luego seleccione **Habilitar ahora**.

Un mosaico para el espacio de trabajo **Funciones de globalización** debería aparecer ahora en el panel de información de RCS.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Configurar los parámetros para la integración de RCS con la facturación electrónica

1. En el espacio de trabajo **Características de globalización**, en la sección **Configuración relacionada**, seleccione **Parámetros de informes electrónicos**.
2. En la pestaña **Facturación electrónica**, en el campo **URI de punto de conexión de servicio**, introduzca el punto de conexión de servicio apropiado para su geografía de Microsoft Azure, como se muestra en la siguiente tabla.

    | Geografía de centros de datos de Azure | Identificador URI de extremo de servicio |
    |----------------------------|----------------------|
    | Estados Unidos              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Reino Unido             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japón                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Suiza                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brasil                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Emiratos Árabes Unidos       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Australia                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Canadá                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Francia                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | India                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Compruebe que el campo **Id. de aplicación** esté establecido en **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Este valor es un valor fijo. Asegúrese de ingresar solo un identificador único global (GUID) y de que el valor no incluya ningún otro símbolo, como espacios, comas, puntos o comillas.
4. En el campo **Id. de entorno de LCS**, introduzca el id. de su entorno de Microsoft Dynamics Lifecycle Services LCS. Este valor es la referencia al entorno de Finance o Supply Chain Management que utilizará con el servicio de Facturación Electrónica. Para obtener su identificación, inicie sesión en [LCS](https://lcs.dynamics.com/), abra su proyecto y, a continuación, en la pestaña **Administrar entorno**, en la sección **Detalles del entorno**, busque el campo **Identificación del entorno** campo.

    > [!IMPORTANT]
    > Si el complemento de Facturación electrónica está instalado en varios entornos de Supply Chain Management o Finance en LCS, utilice siempre el ID de entorno del entorno instalado más recientemente. Si decide instalar el complemento en un nuevo entorno Después de configurar y trabajar con la funcionalidad de Facturación electrónica, actualice el campo **ID de entorno de LCS** en RCS al último valor.

5. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="configuration-providers"></a>Proveedores de configuración

Puede usar proveedores de configuración para distinguir los propietarios de las configuraciones de informes electrónicos (ER) que se usan en los procesos de facturación electrónica y las características de globalización de los propietarios. Para todas las funciones de globalización proporcionadas por Microsoft y publicadas en el repositorio global, el proveedor de configuración se establece en **Microsoft** (`http://microsoft.com`).

Puede ajustar solo las configuraciones de ER y las funciones de globalización que pertenecen al proveedor de configuración activo. Puede usar estas configuraciones y características como plantillas para crear configuraciones y características que pertenecen al proveedor de configuración activo, para que pueda ajustarlas.

Primero, cree los proveedores de configuración. Luego establezca uno de ellos como activo. No puede configurar el proveedor de configuración **Microsoft** como activo.

### <a name="create-a-configuration-provider"></a>Crear un proveedor de configuración

1. En el espacio de trabajo **Informes electrónicos**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, escriba un nombre único para el proveedor de configuración.
4. En el campo **Dirección de Internet**, escriba la dirección de internet (URL) única del proveedor de configuración.
5. Haga clic en **Guardar** y, a continuación, cierre la página.

### <a name="select-a-configuration-provider-as-active"></a>Seleccione un proveedor de configuración como activo

1. En la lista de proveedores de configuración, seleccione el proveedor de configuración que desea establecer como activo.
2. Seleccione **Definir como activo**.

## <a name="import-er-configurations-from-the-global-repository"></a>Importar configuraciones de informes electrónicos del repositorio global

1. En el espacio de trabajo **Informes electrónicos**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
2. En la lista de proveedores de configuración seleccione **Microsoft** y luego **Repositorios**.
3. Seleccione **Global** y después, en el Panel de acciones, seleccione **Abrir**.
4. Importe los siguientes modelos de ER:

    - **Modelo de contexto de factura de cliente**
    - **Modelo de factura**
    - **Documentos fiscales** (para escenarios brasileños, si es necesario)
    - **Modelo de mensaje de respuesta**

5. Si **Asignación del modelo de factura** no se importó automáticamente, impórtelo.
6. Cierre la página.
