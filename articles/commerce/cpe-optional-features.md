---
title: Configurar características opcionales para un entorno de vista previa de Commerce
description: Este tema explica cómo configurar características opcionales para una vista previa del entorno de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2c4872cdebc414eaa865af025237bd9e1d14bfd2
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906125"
---
# <a name="configure-optional-features-for-a-commerce-preview-environment"></a>Configurar características opcionales para un entorno de vista previa de Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema explica cómo configurar características opcionales para una vista previa del entorno de Microsoft Dynamics 365 Commerce.

## <a name="prerequisites"></a>Requisitos previos

Si desea evaluar las características transaccionales de correo electrónico, se deben cumplir los requisitos previos siguientes:

- Tiene un servidor de correo electrónico disponible (Protocolo de transferencia de correo simple \[SMTP\]), que se puede usar desde la suscripción de Microsoft Azure donde aprovisiona el entorno de la versión preliminar.
- Tiene el nombre completamente cualificado del dominio (FQDN)/dirección IP del servidor, el número de puerto de SMTP y detalles de autenticación disponibles.

Si desea evaluar las características de la Gestión de activos digitales ingiriendo nuevas imágenes omnicanal, debe tener disponible el nombre del inquilino de su sistema de gestión de contenido (CMS). Las instrucciones para encontrar este nombre se proporcionan más adelante en este tema. >>> (P: ¿dónde están las instrucciones?)

## <a name="configure-the-image-back-end"></a>Configurar el back-end de la imagen

### <a name="find-your-media-base-url"></a>Encuentre su URL de base de medios

> [!NOTE]
> Antes de poder completar este procedimiento, debe completar los pasos en [Configure su sitio en Commerce ](cpe-post-provisioning.md#set-up-your-site-in-commerce).

1. Inicie sesión en la herramienta de administración del sitio de Commerce utilizando la URL de la que tomó nota cuando inició el comercio electrónico durante el aprovisionamiento (consulte [Inicializar comercio electrónico ](provisioning-guide.md#initialize-e-commerce)).
1. Abra el sitio de **Fabrikam**.
1. Elija **Activos** en el menú de la izquierda.
1. Seleccione cualquier activo de imagen único.
1. En el inspector de propiedades a la derecha, busque la propiedad **URL pública**. El valor es una URL. Este es un ejemplo:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.

1. Reemplazar el último identificador en la dirección URL (**MA1nQC** en el ejemplo anterior) por la cadena **search?fileName=**. Así es como se ve la URL de ejemplo después de realizar este cambio:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    Esta URL es la URL de su base de medios. Anótela.

### <a name="update-the-media-base-url"></a>Actualizar la URL base multimedia

1. Inicie sesión en Dynamics 365 Retail.
1. Use el menú de la izquierda, para ir a **Módulos \> Retail \> Configuración de canal \> Perfiles del canal**.
1. Seleccione **Editar**.
1. En **Propiedades del perfil**, reemplace el valor de propiedad para **Dirección URL base del servidor multimedia** por la URL base de medios que creó anteriormente.
1. En la lista de la izquierda, en el canal **Predeterminado** seleccione el otro canal.
1. En **Propiedades del perfil**, seleccione **Agregar**.
1. Para la propiedad que se agregó, seleccione **URL base del servidor de medios** como la clave de propiedad Como valor de la propiedad, introduzca la URL de la base de medios que creó anteriormente.
1. Seleccione **Guardar**.

## <a name="configure-the-email-server"></a>Configurar el servidor de correo electrónico

> [!NOTE]
> El servidor SMTP o servicio de correo electrónico que especifica aquí debe ser accesible dentro de la suscripción de Azure que está usando para el entorno.

1. Inicie sesión en Retail.
1. Use el menú de la izquierda, para ir a **Módulos \> Administración del sistema \> Configuración \> Correo electrónico \> Parámetros de correo electrónico**.
1. En la pestaña **Configuraciones SMTP**, en el campo **Servidor de correo saliente**, introduzca el FQDN o la dirección IP de su servidor SMTP o servicio de correo electrónico.
1. En el campo **Número de puerto SMTP**, especifique el número de puerto. (Si no está utilizando la Capa de sockets seguros \[SSL \], el número de puerto predeterminado es **25**).
1. Si se requiere autenticación, introduzca valores en los campos **Nombre de usuario** y **Contraseña**.
1. Seleccione **Guardar**.
1. Seleccione **Actualizar**.
1. En la pestaña **Correo electrónico de prueba**, en el campo **Proveedor de correo electrónico**, seleccione **SMTP**.
1. En el campo **Enviar a**, escriba la dirección de correo electrónico donde desea que se entregue el correo electrónico de prueba.
1. Seleccione **Enviar correo electrónico de prueba**.

## <a name="configure-email-templates"></a>Configurar plantillas de correo electrónico

Para cada evento transaccional para el que desea enviar mensajes de correo electrónico se tiene que actualizar la plantilla de correo electrónico con una dirección de correo electrónico de remitente válida.

1. Inicie sesión en Retail.
1. Use el menú de la izquierda, para ir a **Módulos \> Administración de la organización \> Configuración \> Plantillas de correo electrónico de organización**.
1. Seleccione **Mostrar lista**.
1. Para cada plantilla en la lista, siga estos pasos:

    1. A continuación, en el campo **Correo electrónico del remitente**, escriba la dirección de correo electrónico del remitente.
    1. Opcional: en el campo **Nombre del remitente**, introduzca el nombre que debe usarse como el nombre del remitente.

1. Seleccione **Guardar**.

## <a name="customize-email-templates"></a>Personalizar plantillas de correo electrónico

Es posible que desee personalizar las plantillas de correo electrónico para que utilicen imágenes diferentes. O puede que desee actualizar los enlaces en las plantillas para que vayan a su entorno de vista previa. Este procedimiento explica cómo descargar plantillas predeterminadas, personalizarlas y actualizar las plantillas en el sistema.

1. En un explorador web, descargue [el archivo .zip de correo electrónico predeterminado de la versión preliminar de Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) en su equipo local. Este archivo contiene los siguientes documentos HTML:

    - Plantilla de confirmación de pedido
    - Emitir plantilla de tarjeta regalo
    - Nueva plantilla de pedido
    - Empaquetar plantilla de pedido
    - Recoger plantilla de pedido

1. Personalice las plantillas mediante un editor HTML o de texto. Vea la lista de [tokens compatibles ](#supported-tokens-in-the-email-template) más adelante en este tema.
1. Inicie sesión en Retail.
1. Use el menú de la izquierda, para ir a **Módulos \> Administración de la organización \> Configuración \> Plantillas de correo electrónico de organización**.
1. Expanda la lista de la izquierda para ver todas las plantillas.
1. Para cada plantilla que desee personalizar, siga estos pasos:

    1. Seleccione la plantilla en la lista.
    1. En **Contenido del mensaje de correo electrónico**, seleccione la versión de idioma adecuada en la lista. (El valor de plantilla predeterminado es **en-us**).
    1. En **Contenido del mensaje de correo electrónico**, seleccione **Editar**. Aparecerá el panel **Subir plantilla de correo electrónico**.
    1. Seleccione **Explorar** y busque el archivo HTML que tiene el contenido personalizado.
    1. Seleccione **Cargar**. La plantilla se carga en el sistema y se muestra una vista previa.
    1. Seleccione **Aceptar**.
    1. Opcional: personalizar la propiedad **Asunto** de la plantilla.
    1. Seleccione **Guardar**.

### <a name="supported-tokens-in-the-email-template"></a>Tokens compatibles en la plantilla de correo electrónico

Estos tokens se reemplazarán en el momento de la representación de correo electrónico con los valores reales que se aplican al cliente y su pedido.

#### <a name="sales-order"></a>Pedido de ventas

Los siguientes tokens se aplican al pedido de ventas general.

| Nombre del token | Token de  |
|-------------------|-------|
| Número de pedido      | %salesid% |
| Nombre del cliente   | %customername% |
| Dirección de entrega  | %deliveryaddress% |
| Dirección de facturación   | %customeraddress% |
| Fecha del pedido        | %shipdate% |
| Modo de entrega     | %modeofdelivery% |
| Descuento          | %discount% |
| Impuestos         | %tax% |
| Total del pedido       | %total% |

#### <a name="sales-line"></a>Línea de ventas

Los siguientes tokens se sustituyen con valores para cada producto del pedido.

> [!NOTE]
> Ponga el token **Lista de productos - inicio** al comienzo del bloque HTML que se repite para cada producto y coloque el token **Lista de productos - final** al final del bloque.

| Nombre del token      | Token de  |
|------------------------|-------|
| Lista de productos: inicio   | \<!--%tablebegin.salesline% --\> |
| Lista de productos: final     | \<!--%tableend.salesline%--\> |
| Nombre de producto           | %lineproductname% |
| Descripción            | %lineproductdescription% |
| Cantidad               | %linequantity% |
| Unidad de precio de línea        | %lineprice% (comprobar) |
| total de artículo de línea        | %linenetamount% |
| descuento de línea          | %linediscount% |
| Fecha de envío              | %lineshipdate% |
| Método de compras     | %linedeliverymode% |
| dirección de entrega       | %linedeliveryaddress% |
| Unidad de ventas de la línea | %lineunit% |

## <a name="additional-resources"></a>Recursos adicionales

[Resumen del entorno de vista previa de Commerce](cpe-overview.md)

[Aprovisionar un entorno de vista previa de Commerce](provisioning-guide.md)

[Configurar un entorno de vista previa de Commerce](cpe-post-provisioning.md)

[Preguntas más frecuentes del entorno de vista previa de Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal de Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Recursos de ayuda para Dynamics 365 Retail](../retail/index.md)
