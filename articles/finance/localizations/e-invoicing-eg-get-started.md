---
title: Comenzar con el complemento de facturación electrónica para Egipto
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Egipto en Finance y Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 68ee08226f440e850a080600dbf5e16768b45e43
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592607"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-egypt"></a>Comenzar con el complemento de facturación electrónica para Egipto

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Egipto. El tema le guía a través de los pasos de configuración que dependen del país en Regulatory Configuration Services (RCS) y complementa los pasos descritos en [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configuración específica del país para la función de facturación electrónica de la factura electrónica egipcia (EG)

Para configurar la función de facturación electrónica de la factura electrónica egipcia (EG), hay que completar algunos pasos. Algunos de los parámetros de las configuraciones se publican con valores predeterminados, por lo que deben revisarse y actualizarse para adaptarse mejor a su operación comercial.

### <a name="prerequisites"></a>Requisitos previos

Para completar el procedimiento, en esta sección, debe:

- Cree un secreto de certificado digital, como se describe en la sección **Crear secreto de certificado digital** en [Comenzar con la administración del servicio de complemento de facturación electrónica](e-invoicing-get-started-service-administration.md). Para fines de prueba, la autoridad fiscal egipcia proporciona certificados digitales de prueba específicos que deben usarse solo durante las fases de prueba y validación de la solución. Para obtener más información, consulte el sitio web de la autoridad fiscal egipcia utilizando el enlace proporcionado en el [SDK de facturación electrónica egipcia](https://sdk.sit.invoicing.eta.gov.eg/faq/).
- Cree una función de facturación electrónica de factura electrónica egipcia (EG) para su organización, como se describe en la sección **Crear una función de facturación electrónica en el proveedor de su organización**, en [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características**, del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Complemento de facturación electrónica**.
2. En la página **Características del complemento de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Factura electrónica egipcia (EG)**.
3. En la pestaña **Versiones**, verifique que se selecciona la versión **Borrador**.
4. En la pestaña **Configuraciones**, en la cuadrícula, seleccione la configuración de la característica **Factura de ventas**.
5. Seleccione **Editar** y, en la pestaña **Acciones** pestaña del grupo de campos **Comportamiento**, seleccione **Firmar el documento json para la autoridad fiscal egipcia**.
6. En el grupo de campos **Parámetros** , seleccione el parámetro **Nombre del certificado** y seleccione el nombre del certificado digital creado para usarlo con la función de facturación electrónica.
7. En el grupo de campos **Acciones**, seleccione **Integrarse con el servicio ETA egipcio**. Repita este paso para las dos apariciones de esta acción.
8. En el grupo de campos **Parámetros** , seleccione **URL del servicio web** y **URL del servicio de inicio de sesión** y, si es necesario, revise los parámetros de URL. Consulte el sitio web de la autoridad fiscal egipcia para obtener la URL de pruebas y producción, utilizando el enlace proporcionado en el [SDK de facturación electrónica egipcia](https://sdk.sit.invoicing.eta.gov.eg/faq/).
9. Seleccione **Guardar** y cierre la página.
10. Para configurar la instalación de la aplicación, consulte [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configuración específica del país de la configuración de la aplicación para la función de facturación electrónica de factura electrónica egipcia (EG)

La configuración de la aplicación para la característica de facturación electrónica **factura electrónica egipcia (EG)** requiere seguir unos pasos específicos. Debe realizar esos pasos antes de implementar su función de facturación electrónica en su entorno de servicio de complemento de facturación electrónica.

### <a name="prerequisites"></a>Requisitos previos

Antes de completar el procedimiento de esta sección, cree e inicie una característica de facturación electrónica **Factura electrónica egipcia (EG)** para configurar la instalación de la aplicación para la característica de facturación electrónica **Factura electrónica egipcia (EG)** como se describe en la sección **Configurar la instalación de la aplicación** en el tema [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características**, del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Complemento de facturación electrónica**.
2. En la página **Características del complemento de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Factura electrónica egipcia (EG)**.
3. En la pestaña **Versiones**, verifique que esté seleccionada la versión **Borrador**.
4. En la pestaña **Configuraciones**, seleccione **Configuración de la aplicación** y, en el campo **Aplicación conectada**, seleccione la aplicación donde desea implementar.
5. En el campo **Nombre de la tabla**, verifique que el diario de facturas del cliente esté seleccionado.
6. Seleccione **Tipos de respuesta** y luego seleccione **Nuevo**.
7. En el campo **Tipo de respuesta**, introduzca "Respuesta" y, en el campo **Descripción**, introduzca "Descripción".
8. En el campo **Estado de envío**, seleccione **Pendiente**.
9. En el campo **Asignación de modelos**, seleccione **Asignación de modelos desde mensaje de respuesta**, con **(Versión preliminar) Formato de importación de mensaje de respuesta** y luego seleccione **Guardar**.
10. Seleccione **Nuevo** y, en el campo **Tipo de respuesta**, introduzca "ResponseData" como valor fijo. En el campo **Descripción**, escriba "Descripción".
11. En el campo **Estado de envío**, seleccione **Pendiente**.
12. En el campo **Nombre de la entidad de datos**, seleccione **Encabezados de facturas de venta V2**.
13. En el campo **Asignación de modelos**, seleccione **Importación de datos de respuesta egipcia**, con **(Versión preliminar) Importación de datos de respuesta egipcia** y luego seleccione **Guardar**.
14. Para implementar la función de facturación electrónica, consulte [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Aviso de privacidad

Habilitar la característica **Factura electrónica egipcia (EG)** puede requerir el envío de datos limitados, que incluyen el id. de registro fiscal de la organización. Este dato se transmitirá a agencias de terceros autorizadas por la autoridad tributaria con el fin de enviar facturas electrónicas a esta autoridad tributaria en el formato predefinido requerido para la integración con el servicio web del gobierno. Un administrador puede habilitar y deshabilitar la característica yendo a **Administración de la organización** > **Configuración** > **Parámetros de documentos electrónicos**. En la pestaña **Características**, seleccione las fila que contiene la característica **Factura electrónica egipcia (EG)** y luego haga la selección apropiada. Los datos importados de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte las secciones de Aviso de privacidad en la documentación de funciones específicas de cada país o región para obtener más información.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general del complemento de facturación electrónica](e-invoicing-service-overview.md)
- [Comenzar con la administración de servicios de complemento de facturación electrónica](e-invoicing-get-started-service-administration.md)
- [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md)
- [Facturas electrónicas de clientes en Egipto](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
