---
title: Facturación electrónica para Egipto
description: Este artículo proporciona información que le ayudará a comenzar con la Facturación electrónica para Egipto en Microsoft en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c2a46ef938c5dee62c0d0acd1648584df344c81a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904423"
---
# <a name="electronic-invoicing-for-egypt"></a>Facturación electrónica para Egipto

[!include [banner](../includes/banner.md)]

Este artículo proporciona información que le ayudará a comenzar con la facturación electrónica para Egipto. Le guía a través de los pasos de configuración que dependen del país en Regulatory Configuration Service (RCS). Estos pasos complementan los pasos que se describen en [Configurar la facturación electrónica](e-invoicing-set-up-overview.md).

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda comenzar los procedimientos de este artículo, complete los siguientes requisitos previos:

- Familiarícese con la Facturación electrónica tal como se describe en [Descripción general de la facturación electrónica](e-invoicing-service-overview.md).
- Regístrese para RCS y configure la Facturación electrónica Para obtener más información, consulte los siguientes temas:

    - [Alta e instalación del servicio de Factura Electrónica](e-invoicing-sign-up-install.md)
    - [Configurar los recursos de Azure para la facturación electrónica](e-invoicing-set-up-azure-resources.md)
    - [Instalar el complemento para microservicios en Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    
- Active la integración entre su aplicación Microsoft Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management y el servicio de Facturación Electrónica como se describe en [Activar y configurar la integración con Facturación Electrónica](e-invoicing-activate-setup-integration.md).
- Cree un secreto de certificado digital en Azure Key Vault y configúrelo como se describe en [Certificados y secretos de clientes](e-invoicing-customer-certificates-secrets.md). Para fines de prueba, la autoridad fiscal egipcia proporciona certificados digitales de prueba específicos que deben usarse solo durante las fases de prueba y validación de la solución. Para obtener más información, vaya al sitio web de la autoridad fiscal egipcia utilizando el vínculo que se proporciona en el [SDK de facturación electrónica egipcia](https://sdk.invoicing.eta.gov.eg/faq/).

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>Configuración específica del país para la característica de factura electrónica egipcia (EG)

Algunos de los parámetros de la **Característica de facturación electrónica egipcia (EG)** se publican con valores predeterminados. Para implementar la característica de facturación electrónica en el entorno del servicio, revise los valores predeterminados y actualícelos según sea necesario para que reflejen mejor la operación comercial.

1. Importe la última versión de la característica de globalización **Factura electrónica egipcia (EG)** como se describe en [Importar características del repositorio global](e-invoicing-import-feature-global-repository.md).
2. Cree una copia de la característica de Globalización importada y seleccione su proveedor de configuración, como se describe en [Crear una característica de globalización](e-invoicing-create-new-globalization-feature.md).
3. En la pestaña **Versiones**, verifique que esté seleccionada la versión **Borrador**.
4. En la pestaña **Configuraciones**, en la cuadrícula, seleccione la configuración de la característica **Factura de ventas derivada**.
5. Seleccione **Editar**.
6. En la pestaña **Canalización de procesamiento**, en la sección **Canalización de procesamiento**, seleccione **Firmar el documento json para la autoridad fiscal egipcia**.
7. En la sección **Parámetros**, seleccione **Nombre del certificado** y luego seleccione el nombre del certificado digital que creó.
8. En la sección **Canalización de procesamiento**, seleccione **Integrarse con el servicio ETA egipcio**. Repita este paso para las dos apariciones de esta acción.
9. En la sección **Parámetros**, seleccione **URL de servicio web** y **URL de inicio de sesión de servicio**. A continuación, revise los parámetros de URL. Para obtener la URL de pruebas y producción, vaya al sitio web de la autoridad fiscal egipcia utilizando el vínculo proporcionado en el [SDK de facturación electrónica egipcia](https://sdk.invoicing.eta.gov.eg/faq/).
10. Seleccione **Guardar** y cierre la página.
11. Repita los pasos del 4 al 10 para la configuración de características **Factura de proyecto derivada**.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>Configuración específica del país para la configuración de la aplicación de factura electrónica egipcia (EG)

Hay parámetros que deben configurarse en su entorno de Finance o Supply Chain Management. Puede completar esta configuración en estos dos lugares:

- Directamente en su entorno de Finance o Supply Chain Management. Para obtener más información, consulte [Configurar los parámetros de facturación electrónica](e-invoicing-set-up-parameters.md).
- En RCS. En el ámbito de la configuración de característica de facturación electrónica, puede definir todos los parámetros y luego implementarlos directamente en su entorno de Finance o Supply Chain Management cuando implemente la característica de facturación electrónica.

Para ambas opciones, los parámetros son los mismos. Si está configurando su primera característica en el servicio de Facturación electrónica, le recomendamos que siga estos pasos para configurar los parámetros en RCS y luego implementarlos en su aplicación conectada.

> [!NOTE]
> Algunas versiones de características de facturación electrónica pueden contener un conjunto predefinido de parámetros específicos de la aplicación para Finance o Supply Chain Management. En este caso, debe comprobar que los datos sean correctos. De lo contrario, establezca manualmente los parámetros.

1. Encuentre la copia de la característica de globalización **Factura electrónica egipcia (EG)** que creó.
2. En la pestaña **Versiones**, verifique que esté seleccionada la versión **Borrador**.
3. En la pestaña **Configuraciones**, seleccione **Configuración de la aplicación**.
4. En el campo **Aplicaciones conectadas**, seleccione la aplicación donde desea implementar los parámetros.
5. En la página **Tipos de documentos electrónicos**, seleccione **Agregar** para crear un registro.
6. En el campo **Nombre de la tabla**, agregue **CustInvoiceJour**.
7. En el campo **Contexto**, agregue una referencia al nombre de asignación **Contexto de la factura del cliente**. La configuración es **Modelo de contexto de factura de cliente**.
8. En el campo **Asignación de documentos electrónicos**, agregue una referencia al nombre de asignación **Contexto de la factura del cliente**. La configuración es **Asignación de modelos de factura**.
9. Seleccione **Guardar**.
10. En la página **Tipos de respuestas**, seleccione **Agregar**.
11. En el campo **Tipo de respuesta** , especifique **Respuesta**.
12. En el campo **Descripción**, escriba **Respuesta de proceso**.
13. En el campo **Estado de envío**, seleccione **Pendiente**.
14. En el campo **Asignación de modelos**, seleccione **Importación de mensaje de respuesta**. La configuración es **Importación de mensaje de respuesta de Egipto (EG)**.
15. Seleccione **Guardar**.
16. Seleccione **Agregar**.
17. En el campo **Tipo de respuesta** , especifique **ResponseData**.
18. En el campo **Descripción**, escriba **Datos de respuesta de proceso**.
19. En el campo **Estado de envío**, seleccione **Pendiente**.
20. En el campo **Nombre de la entidad de datos**, seleccione **SalesInvoiceHeaderV2Entity**.
21. En el campo **Asignación de modelos**, seleccione **Importación de datos de respuesta**. La configuración es **Formato de importación de datos de respuesta de Egipto (EG)**.
22. Seleccione **Guardar** y cierre la página.
23. Cierre la página.

Para implementar una característica en el entorno de servicio y una configuración de aplicación en la aplicación conectada de Finance o Supply Chain Management, consulte [Completar, publicar e implementar una característica de globalización](e-invoicing-complete-publish-deploy-globalization-feature.md)

## <a name="privacy-notice"></a>Aviso de privacidad

Habilitar la función **Factura electrónica egipcia (EG)** puede requerir que se envíen datos limitados. Estos datos incluyen el número de identificación fiscal de la organización. Los datos se transmitirán a agencias de terceros autorizadas por la autoridad tributaria para enviar facturas electrónicas a esa autoridad tributaria en el formato predefinido requerido para la integración con el servicio web del gobierno. Un administrador puede habilitar y deshabilitar la característica yendo a **Administración de la organización** \> **Configuración** \> **Parámetros de documentos electrónicos**. En la pestaña **Características**, seleccione las fila que contiene la característica **Factura electrónica egipcia (EG)** y luego haga la selección apropiada. Los datos que se importan de sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Para más información, vea la sección "Aviso de privacidad" en la documentación de características específicas de cada país.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general sobre facturación electrónica](e-invoicing-service-overview.md)
- [Comenzar con la administración de servicios de facturación electrónica](e-invoicing-get-started-service-administration.md)
- [Comenzar con la facturación electrónica](e-invoicing-get-started.md)
- [Facturas electrónicas de clientes en Egipto](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
