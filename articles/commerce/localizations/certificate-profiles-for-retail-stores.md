---
title: Perfiles de certificado definidos por el usuario para tiendas
description: Este tema proporciona una descripción general sobre cómo se utilizan los certificados en las tiendas minoristas.
author: josaw
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0b8bf49a8eb78d0557ef105b40dd4cb5f0d24ce4
ms.sourcegitcommit: 83ec80382bfeb693d5c5949b6f65296bd50eed12
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973942"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Perfiles de certificado definidos por el usuario para tiendas

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

## <a name="overview"></a>Información general

Este tema proporciona una visión general de los perfiles de certificados disponibles en Microsoft Dynamics 365 Commerce. Esta funcionalidad extiende la característica [Gestionar secretos para canales minoristas](../dev-itpro/manage-secrets.md) agregando soporte para certificados locales.

Mientras el punto de venta (POS) se ejecuta en modo fuera de línea, no puede acceder a los certificados que están almacenados en el almacén de claves. En su lugar, debería utilizarse el certificado local. Se admiten las siguientes funcionalidades:

- Uso de certificados locales en escenarios de reserva de Key Vault
- Usar certificados locales sin un almacén de claves (por ejemplo, en una instalación local)
- Actualización gradual de certificados, donde algunas tiendas y terminales usan una nueva versión del certificado, pero otras tiendas y terminales continúan usando la versión anterior

La funcionalidad de perfiles de certificado le permite especificar un certificado predeterminado y establecer el orden en que se buscan los certificados del mismo perfil de certificado. Esta funcionalidad también proporciona un enfoque de configuración similar para certificados locales y certificados de Key Vault. Puede agregar configuraciones específicas de la empresa para los certificados, pero el identificador único entre empresas para cada certificado se puede utilizar en los canales de comercio.

### <a name="scenarios"></a>Situaciones

La funcionalidad de perfiles de certificado admite los siguientes escenarios en los canales de comercio:

- Uso de certificado local en escenarios de reserva de Key Vault. Algunos ejemplos estos escenarios de reserva son:

    - No se puede acceder al almacenamiento del almacén de claves.
    - No se encuentra un certificado en el almacenamiento del almacén de claves.
    - El PDV se ejecuta en modo fuera de línea.

- Uso de certificados locales, pero sin almacenarlos en el almacén de claves (por ejemplo, en una instalación local)
- Realice una actualización gradual de certificados, donde se utilice una nueva versión del certificado solo en tiendas o en terminales donde la nueva versión ya esté disponible.
- Utilice el mismo certificado en varias empresas.

## <a name="set-up-certificate-profiles"></a>Configuración de perfiles de certificado

El siguiente procedimiento explica cómo configurar perfiles de certificado. Antes de utilizar perfiles de certificado en los canales comerciales, siga estos pasos para configurar los ajustes.

1. En el espacio de trabajo **Gestión de funciones**, active la característica **Perfiles de certificado definidos por el usuario para tiendas minoristas**.
2. Vaya a **Administración del sistema \> Configuración \> Perfiles de certificado**.
3. Cree un registro y establezca los campos **Perfil de certificado**, **Nombre** y **Descripción** de este.

    > [!NOTE]
    > El perfil del certificado es un identificador único de un certificado en todas las empresas y componentes comerciales.

3. En la pestaña **Entidades legales**, agregue una línea y seleccione la entidad legal (empresa) para la que se debe usar el perfil de certificado actual. Si el perfil de certificado debe usarse para varias entidades legales, repita este paso para agregar una línea para cada entidad legal adicional.
4. Seleccione **Configuraciones** para abrir la página **Configuración de perfil de certificado**, donde puede ingresar la configuración específica de la empresa para el perfil del certificado.

### <a name="certificate-profile-settings"></a>Configuración de perfil de certificado

Cuando selecciona **Configuraciones** para las líneas de perfil de certificado, aparece la página **Configuración de perfil de certificado**. Esta página le permite especificar qué certificados se pueden usar cuando se llama al perfil de certificado actual en los canales de comercio. También puede especificar el orden en el que se deben buscar los certificados.

> [!NOTE]
> El campo **Prioridad** se establece automáticamente. Un valor de **1** representa la máxima prioridad. Cuando se agrega una nueva línea en la página**Configuración de perfil de certificado**, su prioridad se establece en un número que es uno más que la prioridad de la línea anterior. Para cambiar la prioridad de una línea específica, seleccione la línea y luego seleccione **Subir** para aumentar la prioridad o **Bajar** para disminuirla.

Cuando agrega una nueva línea a la página **Configuración de perfil de certificado**, configure los siguientes campos:

- **Tipo de ubicacion** - Seleccione la ubicación donde se almacena el certificado. Este campo tiene dos valores posibles: **Certificado local** y **Almacén de claves**.
- **Certificado de Key Vault** - Este campo es obligatorio si configura el campo **Tipo de ubicación** como **Almacén de claves**. Úselo para especificar un certificado secreto de Key Vault.

    > [!NOTE]
    > Antes de usar un certificado de Key Vault en perfiles de certificado, asegúrese de cargar un certificado en el almacenamiento de Key Vault y siga las instrucciones en [Configurar el cliente de Azure Key Vault](https://docs.microsoft.com/dynamics365/finance/localizations/setting-up-azure-key-vault-client).

- **Nombre de la tienda** - Este campo es opcional y está disponible solo si configura el campo **Tipo de ubicación** como **Certificado local**. Úselo para especificar un nombre de tienda predeterminado que debe usarse para buscar certificados locales.
- **Ubicación de la tienda** - Este campo es opcional y está disponible solo si configura el campo **Tipo de ubicacion** como **Certificado local**. Úselo para especificar una ubicación de tienda predeterminado que debe usarse para buscar certificados locales.

    > [!NOTE]
    > El nombre y la ubicación de la tienda predeterminados se agregan para simplificar el proceso de búsqueda de certificados locales en Commerce Runtime. X509StoreProvider tiene una lista de carpetas donde se almacenan los certificados. Si no se especifican el nombre y la ubicación de la tienda predeterminados, X509StoreProvider intenta encontrar un certificado en las otras carpetas de su lista.

- **Huella digital** - Este campo es obligatorio y está disponible solo si configura el campo **Tipo de ubicacion** como **Certificado local**. Úselo para especificar la huella digital del certificado.
- **Comentarios** - Este campo es opcional y permite a los usuarios ingresar notas.

### <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Flujo de trabajo: búsqueda de certificados en Commerce Runtime

Este es el flujo de trabajo básico que se utiliza para buscar un certificado cuando se llama a un perfil de certificado en Commerce Runtime.

1. El sistema identifica si el perfil de certificado tiene una configuración específica de la empresa para la entidad jurídica actual.
1. El sistema intenta encontrar el certificado utilizando los valores en la página **Configuración de perfil de certificado** de la línea donde el campo **Prioridad** está configurado en **1**.

    - Si el campo **Tipo de ubicacion** está configurado como **Almacén de claves**, el valor del campo **Secreto del certificado de Key Vault** se utiliza para buscar el certificado en la página **Parámetros de almacén de claves**. A continuación, se busca el certificado en el almacén de claves.
    - Si el campo **Tipo de ubicacion** está configurado en **Certificado local**, X509StoreProvider busca primero el certificado utilizando el nombre y la ubicación de la tienda predeterminados, si se especifican estos parámetros. Luego busca en todas las demás carpetas de su lista de carpetas.

1. Si no se encuentra el certificado, el proceso se repite para la línea donde el campo **Prioridad** está configurado en **2**, y así sucesivamente.

> [!NOTE]
> Si el perfil del certificado no tiene configuraciones para la entidad legal actual, o si la búsqueda del certificado no tiene éxito para todas las líneas en la página **Configuración de perfil de certificado**, no se encuentra el certificado.

#### <a name="caching-the-results-of-certificate-searches"></a>Almacenamiento en caché de los resultados de las búsquedas de certificados

Los resultados de las búsquedas de certificados se almacenan en caché. El tiempo de caducidad predeterminado para un caché es una hora. Sin embargo, este tiempo se puede personalizar y se puede establecer en un valor máximo de 24 horas.

### <a name="gradual-update"></a>Actualización gradual

Si se introduce una nueva versión del certificado, pero no se puede actualizar en todas las tiendas al mismo tiempo, la funcionalidad de perfiles de certificado permite que el certificado se actualice gradualmente.

1. Busque un perfil de certificado y la línea que debe actualizarse, y luego seleccione **Configuraciones**.
1. Agregue una línea y especifique la configuración relacionada con la última versión del certificado.
1. Aumente el valor de **Prioridad** de la nueva línea. Utilice el botón **Subir** para mover la línea de modo que esté por encima de la línea de la versión anterior del mismo certificado.

> [!NOTE]
> En Commerce Runtime, se llamará primero a la nueva versión del certificado. Si el certificado aún no se ha actualizado en una tienda específica o en un terminal específico, se llamará a la versión anterior.
