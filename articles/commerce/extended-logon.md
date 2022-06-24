---
title: Configurar y utilizar la capacidad de inicio de sesión ampliada
description: En este artículo se describe cómo configurar y utilizar capacidad de inicio de sesión ampliada de la aplicación de punto de venta (PDV) Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e27e8d94adccc46559089928b0481442306567ef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884320"
---
# <a name="set-up-and-use-the-extended-logon-capability"></a>Configurar y utilizar la capacidad de inicio de sesión ampliada

[!include [banner](includes/banner.md)]

En este artículo se describe cómo configurar y utilizar capacidad de inicio de sesión ampliada de la aplicación de punto de venta (PDV) Microsoft Dynamics 365 Commerce.

El Cloud POS (CPOS) y el Modern POS (MPOS) brindan una capacidad de inicio de sesión extendida que permite a los trabajadores de tiendas minoristas iniciar sesión en la aplicación de PDV escaneando un código de barras o deslizando una tarjeta usando un lector de bandas magnéticas (MSR).

## <a name="set-up-extended-logon"></a>Configurar el inicio de sesión extendido

Para configurar el inicio de sesión extendido para cajas registradoras en PDV en una tienda minorista, siga estos pasos.

1. En la sede central de Commerce, vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**. 
2. En el panel de navegación izquierdo, seleccione el perfil de funcionalidad asociado con la tienda minorista.
3. En la ficha desplegable **Funciones**, bajo **Opciones adicionales de autenticación en el inicio de sesión**, ponga las siguientes opciones en **Sí** o **No** según corresponda:

    - **Inicio de sesión del personal con código de barras** – Establezca esta opción en **Sí** si desea que sus trabajadores inicien sesión en el PDV escaneando un código de barras. 
    - **Inicio de sesión del personal con contraseña** – Establezca esta opción en **Sí** si desea que sus trabajadores inicien sesión en el PDV introduciendo una contraseña.
    - **Inicio de sesión del personal con tarjeta** – Establezca esta opción en **Sí** si desea que sus trabajadores inicien sesión en el PDV pasando una tarjeta.
    - **Inicio de sesión del personal con tarjeta y contraseña** – Establezca esta opción en **Sí** si desea que sus trabajadores inicien sesión en el PDV introduciendo una contraseña después de pasar una tarjeta.

El código de barras o la tarjeta están asociadas a las credenciales que se pueden asignar a un trabajador. Las credenciales deben tener al menos seis caracteres. La cadena que contiene los primeros cinco caracteres debe ser única y se considera una *ID de credencial* que se utiliza para buscar un trabajador. Los caracteres restantes se utilizan para la verificación de seguridad. Por ejemplo: tiene dos tarjetas, una con las credenciales 12345DGYDEYTDW y otra con las credenciales 12345EWUTBDAJH. Debido a que estas dos tarjetas tienen el mismo ID de credencial (12345), no se pueden asignar ambas correctamente a los trabajadores.

## <a name="assign-extended-logon"></a>Asignar inicio de sesión extendido

De forma predeterminada, solo los directores pueden asignar el inicio de sesión extendido a los trabajadores. Para asignar el inicio de sesión extendido, vaya a **Inicio de sesión extendido** en PDV. A continuación, busque un trabajador introduciendo el Id. de operador del trabajador en el campo de búsqueda. Seleccione el trabajador y, a continuación, haga clic en la pestaña **Asignar**. En la siguiente página, pase o o escanee el inicio de sesión que desee asignar al trabajador. Si se lee correctamente, el botón **Aceptar** estará disponible. Haga clic en **Aceptar** para guardar el inicio de sesión extendido para dicho trabajador.

## <a name="delete-extended-logon"></a>Eliminar inicio de sesión extendido

Para eliminar el inicio de sesión extendido que se asigna a un trabajador, busque el trabajador mediante la operación **Inicio de sesión extendido**. Seleccione el trabajador y, a continuación, haga clic en **Anular asignación**. Se eliminarán todas las credenciales de inicio de sesión extendidas asociadas con dicho trabajador.

## <a name="use-extended-logon"></a>Usar el inicio de sesión extendido

Tras configurar el inicio de sesión extendido y asignar a un trabajador un código de barras o una cinta magnética, el trabajador solo tiene que pasar o escanear su tarjeta mientras se abre la página de inicio de sesión del PDV. Si una contraseña también es necesaria para que el inicio de sesión pueda continuar, se le pedirá al trabajador que especifique su contraseña.

## <a name="extend-extended-logon"></a>Ampliación del inicio de sesión extendido

La implementación lista para usar de la capacidad de inicio de sesión extendido requiere que las credenciales tengan una longitud mínima de seis caracteres y que los primeros cinco caracteres (el ID de la credencial) sean únicos. Originalmente se pensó como una muestra que los desarrolladores pudieran personalizar para cumplir con los requisitos de una implementación específica. (Por ejemplo, podría personalizarse para admitir más caracteres o usar diferentes reglas de verificación de seguridad). Para obtener información detallada sobre cómo crear extensiones para el inicio de sesión extendido, consulte [Ampliación de la funcionalidad de inicio de sesión extendido para MPOS y Cloud POS](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/12/14/extending-the-extended-logon-functionality-for-mpos-and-cloud-pos/).

El servicio del inicio de sesión también puede ser extendido para admitir dispositivos de inicio de sesión extendidos adicionales, como escáneres de la palma de la mano. Para obtener más información, consulte la [documentación de extensibilidad del PDV](dev-itpro/pos-extension/pos-extension-overview.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
