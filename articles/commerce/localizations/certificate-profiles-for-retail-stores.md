---
title: Perfiles de certificado definidos por el usuario para tiendas
description: Este artículo proporciona una visión general de los perfiles de certificados disponibles en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: v-chgriffin
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.search.industry: Retail
ms.search.form: RetailFormLayout, RetailParameters
ms.openlocfilehash: 5baf043a43210d819b605546089e981c86922ca9
ms.sourcegitcommit: 4f28f262cfb8f047cb5c0070261aa0748835e74b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2022
ms.locfileid: "9558447"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Perfiles de certificado definidos por el usuario para tiendas

[!include [banner](../includes/banner.md)]

Este artículo proporciona una visión general de los perfiles de certificados disponibles en Microsoft Dynamics 365 Commerce. Esta funcionalidad extiende la característica [Gestionar secretos para canales minoristas](../dev-itpro/manage-secrets.md) agregando soporte para certificados locales.

Mientras el punto de venta (POS) se ejecuta en modo sin conexión, no puede acceder a los certificados que están almacenados en el Key Vault Microsoft Azure. En su lugar, debería utilizarse el certificado local. Se admiten las siguientes funcionalidades:

- Uso de certificados locales en escenarios de reserva de Key Vault
- Usar certificados locales sin Key Vault (por ejemplo, en una instalación local)
- Actualización gradual de certificados, donde algunas tiendas y terminales usan una nueva versión del certificado, pero otras tiendas y terminales continúan usando la versión anterior

La funcionalidad de perfiles de certificado le permite especificar un certificado predeterminado y establecer el orden en que se buscan los certificados del mismo perfil de certificado. Esta funcionalidad también proporciona un enfoque de configuración similar para certificados locales y certificados de Key Vault. Puede agregar configuraciones específicas de la empresa para los certificados, pero el identificador único entre empresas para cada certificado se puede utilizar en los canales de comercio.

### <a name="scenarios"></a>Situaciones

La funcionalidad de perfiles de certificado admite los siguientes escenarios en los canales de comercio:

- Uso de certificado local en escenarios de reserva de Key Vault. Algunos ejemplos estos escenarios de reserva son:

    - No se puede acceder al almacenamiento del almacén de claves.
    - No se encuentra un certificado en el almacenamiento del almacén de claves.
    - El PDV se ejecuta en modo fuera de línea.

- Uso de certificados locales, pero sin almacenarlos en Key Vault (por ejemplo, en una instalación local)
- Realice una actualización gradual de certificados, donde se utilice una nueva versión del certificado solo en tiendas o en terminales donde la nueva versión ya esté disponible.
- Utilice el mismo certificado en varias empresas.

## <a name="set-up-certificate-profiles"></a>Configuración de perfiles de certificado

El siguiente procedimiento explica cómo configurar perfiles de certificado.

### <a name="set-up-key-vault"></a>Configuración de Key Vault

Antes de poder utilizar un certificado digital almacenado en el almacenamiento de Key Vault, se deben completar los siguientes pasos.

1. Crear una cuenta de almacenamiento Key Vault. Le recomendamos que implemente la cuenta de almacenamiento en la misma región geográfica que Commerce Scale Unit.
1. Cargue el certificado digital en la cuenta de almacenamiento de Key Vault.
1. Autorice a la aplicación del Servidor de Objetos de Aplicación (AOS) a leer los secretos de la cuenta de almacenamiento de Key Vault.

Para obtener más información sobre cómo trabajar con Key Vault, consulte [Empezar a utilizar Azure Key Vault](/azure/key-vault/key-vault-get-started).

### <a name="set-up-system-parameters"></a>Configurar parámetros del sistema

Antes de configurar los perfiles de certificado en los canales de Commerce, debe permitir que Commerce use los certificados almacenados en Key Vault y los perfiles de certificado.

Para configurar los parámetros del sistema en Commerce headquarters, siga estos pasos.

1. En la página **Parámetros del sistema**, configure la opción **Usar almacén de certificados avanzado** como **Sí**.
1. En el espacio de trabajo **Gestión de funciones**, active la característica **Perfiles de certificado definidos por el usuario para tiendas minoristas**.

### <a name="set-up-key-vault-parameters"></a>Configurar parámetros de Key Vault

En la página **Parámetros de Key Vault**, debe especificar los siguientes parámetros para acceder al almacenamiento de Key Vault:

- **Nombre** y **Descripción** - El nombre y la descripción de la cuenta de almacenamiento de Key Vault.
- **URL de Key Vault** - La URL de la cuenta de almacenamiento de Key Vault.
- **Cliente de Key Vault** - Un Id. de cliente interactivo de la aplicación Azure Active Directory (Azure AD) que está asociada con la cuenta de almacenamiento de Key Vault para autenticación. Este cliente debe tener acceso para leer secretos de la cuenta de almacenamiento.
- **Clave secreta de Key Vault** - Una clave secreta que está asociada con la aplicación Azure AD que se utiliza para la autenticación en la cuenta de almacenamiento de Key Vault.
- **Nombre**, **Descripción** y **Referencia secreta** - El nombre, descripción y referencia secreta del certificado.

Para más información, vea [Configurar el cliente de Azure Key Vault](../../finance/localizations/setting-up-azure-key-vault-client.md).

### <a name="configure-a-certificate-profile"></a>Configurar un perfil de certificado

Para configurar un perfil de certificado en Commerce headquarters, siga estos pasos.

1. Vaya a **Administración del sistema \> Configuración \> Perfiles de certificado**.
1. En el Panel de acciones, seleccione **Nuevo** para crear un registro.
1. Escriba valores en los campos **Perfil de certificado**, **Nombre** y **Descripción**.

    > [!NOTE]
    > El perfil del certificado es un identificador único de un certificado en todas las empresas y componentes comerciales.

1. En la ficha desplegable **Entidades jurídicas**, seleccione **Agregar** para agregar una línea.
1. En la pestaña **Entidad jurídica**, seleccione la entidad jurídica (empresa) para la que se debe usar el perfil de certificado actual.

    Si el perfil de certificado debe usarse para varias entidades legales, repita los pasos 4 y 5 para agregar una línea para cada entidad jurídica adicional.

1. Seleccione **Configuraciones** para abrir la página **Configuración de perfil de certificado**, donde puede ingresar la configuración específica de la empresa para el perfil del certificado. Especifique qué certificados se pueden usar cuando se llama al perfil de certificado actual en los canales de Commerce. Agregue tantos certificados como necesite y establezca prioridades para ellos. Si un certificado que tiene una prioridad más alta no está disponible, se utilizará el siguiente certificado, según la prioridad. Para obtener más información, consulte la seccion [Flujo de trabajo: búsqueda de certificados en el tiempo de ejecución de Commerce](#workflow-searching-certificates-in-the-commerce-runtime).

    > [!NOTE]
    > El campo **Prioridad** se establece automáticamente. Un valor de **1** representa la máxima prioridad. Cuando se agrega una nueva línea en la página **Configuración de perfil de certificado**, su prioridad se establece en un número que es uno más que la prioridad de la línea anterior. Para cambiar la prioridad de una línea específica, seleccione la línea y luego seleccione **Subir** para aumentar la prioridad o **Bajar** para disminuirla.

1. Cuando agrega una nueva línea en la página **Configuración de perfil de certificado**, configure los siguientes campos:

    - **Tipo de ubicacion** - Seleccione la ubicación donde se almacena el certificado. Este campo tiene dos valores posibles: **Certificado local** y **Almacén de claves**.
    - **Certificado de Key Vault** - Este campo es obligatorio si configura el campo **Tipo de ubicación** como **Almacén de claves**. Úselo para especificar un certificado secreto de Key Vault.
    - **Nombre de la tienda** - Este campo es opcional y está disponible solo si configura el campo **Tipo de ubicación** como **Certificado local**. Úselo para especificar un nombre de tienda predeterminado que debe usarse para buscar certificados locales.
    - **Ubicación de la tienda** - Este campo es opcional y está disponible solo si configura el campo **Tipo de ubicacion** como **Certificado local**. Úselo para especificar una ubicación de tienda predeterminado que debe usarse para buscar certificados locales.

        > [!NOTE]
        > El nombre y la ubicación de la tienda predeterminados se agregan para simplificar el proceso de búsqueda de certificados locales en Commerce Runtime. X509StoreProvider tiene una lista de carpetas donde se almacenan los certificados. Si no se especifican el nombre y la ubicación de la tienda predeterminados, X509StoreProvider intenta encontrar un certificado en las otras carpetas en su lista. Para obtener más información sobre los valores disponibles para el nombre de la tienda y la ubicación de la tienda, consulte [StoreName Enum](/dotnet/api/system.security.cryptography.x509certificates.storename) y [StoreLocation Enum](//dotnet/api/system.security.cryptography.x509certificates.storelocation).

    - **Huella digital** - Este campo es obligatorio y está disponible solo si configura el campo **Tipo de ubicacion** como **Certificado local**. Úselo para especificar la huella digital del certificado.

        > [!IMPORTANT]
        > Debe asegurarse de que el usuario que ejecuta la aplicación que tiene que usar el certificado local (por ejemplo, Modern POS en el modo fuera de línea) tiene al menos acceso de solo lectura a la clave privada del certificado.

    - **Comentarios** - Este campo es opcional y permite a los usuarios ingresar notas.

## <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Flujo de trabajo: búsqueda de certificados en Commerce Runtime

Este es el flujo de trabajo básico que se utiliza para buscar un certificado cuando se llama a un perfil de certificado en Commerce Runtime.

1. El sistema identifica si el perfil de certificado tiene una configuración específica de la empresa para la entidad jurídica actual.
1. El sistema intenta encontrar el certificado utilizando los valores en la página **Configuración de perfil de certificado** de la línea donde el campo **Prioridad** está configurado en **1**.

    - Si el campo **Tipo de ubicacion** está configurado como **Almacén de claves**, el valor del campo **Secreto del certificado de Key Vault** se utiliza para buscar el certificado en la página **Parámetros de almacén de claves**. A continuación, se busca el certificado en el almacén de claves.
    - Si el campo **Tipo de ubicacion** está configurado en **Certificado local**, X509StoreProvider busca primero el certificado utilizando el nombre y la ubicación de la tienda predeterminados, si se especifican estos parámetros. Luego busca en todas las demás carpetas de su lista de carpetas.

1. Si no se encuentra el certificado, el proceso se repite para la línea donde el campo **Prioridad** está configurado en **2**, y así sucesivamente.

> [!NOTE]
> Si el perfil del certificado no tiene configuraciones para la entidad legal actual, o si la búsqueda del certificado no tiene éxito para todas las líneas en la página **Configuración de perfil de certificado**, no se encuentra el certificado.

### <a name="caching-the-results-of-certificate-searches"></a>Almacenamiento en caché de los resultados de las búsquedas de certificados

Los resultados de las búsquedas de certificados se almacenan en caché. El tiempo de caducidad predeterminado para un caché es una hora. Sin embargo, este tiempo se puede personalizar y se puede establecer en un valor máximo de 24 horas.

## <a name="gradual-update"></a>Actualización gradual

Si se introduce una nueva versión del certificado, pero no se puede actualizar en todas las tiendas al mismo tiempo, la funcionalidad de perfiles de certificado permite que el certificado se actualice gradualmente.

1. Busque un perfil de certificado y la línea que debe actualizarse, y luego seleccione **Configuraciones**.
1. Agregue una línea y especifique la configuración relacionada con la última versión del certificado.
1. Aumente el valor de **Prioridad** de la nueva línea. Utilice el botón **Subir** para mover la línea de modo que esté por encima de la línea de la versión anterior del mismo certificado.
> [!NOTE]
> En Commerce Runtime, se llamará primero a la nueva versión del certificado. Si el certificado aún no se ha actualizado en una tienda específica o en un terminal específico, se llamará a la versión anterior.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
