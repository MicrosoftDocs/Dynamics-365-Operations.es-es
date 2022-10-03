---
title: Introducción al complemento de facturación electrónica para Francia
description: Este artículo proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Francia.
author: dkalyuzh
ms.date: 07/07/2022
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-00-02
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: 3ac4af8c131e35d9a499d0d558c7cce1d4872b37
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573288"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-france"></a>Introducción al complemento de facturación electrónica para Francia

[!include [banner](../includes/banner.md)]

Este artículo proporciona información que le ayudará a comenzar con la facturación electrónica para Francia. Le guía a través de los pasos de configuración que dependen del país en Regulatory Configuration Service (RCS). Estos pasos complementan los pasos que se describen en [Empezar a utilizar el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Configuración específica del país para la función de facturación electrónica de la presentación French Chorus Pro (FR)

Se requieren algunos pasos para configurar la función de facturación electrónica **Presentación de French Chorus Pro (FR)**. Algunos de los parámetros de la configuración se publican con valores predeterminados. Estos valores deben revisarse y actualizarse para que reflejen mejor sus operaciones comerciales.

### <a name="prerequisites"></a>Requisitos previos

Antes de que pueda comenzar los procedimientos de este artículo, complete los siguientes requisitos previos:

- Familiarízate con la Facturación Electrónica. Para más información, vea [Información general de la facturación electrónica](e-invoicing-service-overview.md).
- Regístrese para RCS y configure la Facturación electrónica Para obtener más información, consulte los siguientes artículos:

    - [Alta e instalación del servicio de Factura Electrónica](e-invoicing-sign-up-install.md)
    - [Configurar los recursos de Azure para la facturación electrónica](e-invoicing-set-up-azure-resources.md)
    - [Instalar el complemento para microservicios en Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    - [Activar y configurar la integración con la Facturación Electrónica](e-invoicing-activate-setup-integration.md): use la información de este artículo para activar la integración entre la aplicación Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management y el servicio de Facturación Electrónica.
    - [Códigos NAF y números siret](emea-fra-naf-codes-siret-numbers.md) y [Configurar códigos NAF y números Siret](tasks/fr-00003-naf-codes-siret-numbers.md) – Utilice la información de estos artículos para configurar códigos NAF y números Siret en sus entidades legales. 

- Su organización debe estar registrada para operar con Chorus Pro. Microsoft proporciona integración con Chorus pro en modo OAuth2 a través de una interfaz de programación de aplicaciones (API). Para obtener información detallada sobre el registro de Chorus Pro y la activación de la aplicación, consulte la [documentación oficial](https://communaute.chorus-pro.gouv.fr/documentation/help-for-api-developers-in-oauth2-mode/).

    Siga estos pasos para registrarse con Chorus Pro.

    1. Vaya al [portal PISTE](https://piste.gouv.fr/en/component/apiportal/registration) para iniciar su registro. 
    2. Registre una aplicación y active las credenciales de Open Authorization (OAuth).
    3. Copie y guarde el ID de cliente de las credenciales de OAuth y la clave secreta. Utilizará esta información en pasos posteriores.
    4. Vaya al [portal ChorusPro](https://portail.chorus-pro.gouv.fr/aife_csm/?id=aife_enrollment) para registrarse. 
    5. Cree una cuenta técnica para acceder a la API. Para más información, vea [Creación de una cuenta técnica para el acceso a la API en producción](https://communaute.chorus-pro.gouv.fr/documentation/creation-of-a-technical-account-for-an-api-access-in-production/).
    6. Copie el ID de usuario de la cuenta técnica y la contraseña. Utilizará esta información en pasos posteriores.

## <a name="country-specific-configuration-of-the-application-setup-for-the-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Configuración específica del país de la configuración de la aplicación para la función de facturación electrónica de presentación de Chorus Pro para Francia (FR)

Algunos de los parámetros de la característica de facturación electrónica **Presentación de Chorus Pro para Francia (FR)** se publican con valores predeterminados. Para implementar la característica de facturación electrónica en el entorno del servicio, revise y actualice los valores predeterminados según sea necesario para que reflejen mejor las operaciones comerciales.

1. En Azure key vault, cree secretos y la referencia a ellos correspondiente. Para más información, consulte [Certificados y secretos de clientes](e-invoicing-customer-certificates-secrets.md).
2. Importe la última versión de la característica de globalización **Presentación Chorus Pro para Francia (FR)** como se describe en [Importar características del repositorio global](e-invoicing-import-feature-global-repository.md).
3. Cree una copia de la función de globalización importada y seleccione su proveedor de configuración. Para obtener más información, consulte [Crear una característica de globalización](e-invoicing-create-new-globalization-feature.md).
4. En la pestaña **Versiones**, verifique que esté seleccionada la versión **Borrador**.
5. En la pestaña **Configuraciones**, en la cuadrícula, seleccione la configuración de la característica **Factura de ventas derivada UBL**.
6. Seleccione **Editar** y, luego, en la pestaña **Tubería de procesamiento**, en la sección **Tubería de procesamiento**, seleccione **(Vista previa) Integrar con French Chorus Pro** con el nombre de la acción **Presentar Chorus Pro para Francia**.
7. En la sección **Parámetros**, en el campo **Nombre secreto de ID de cliente**, seleccione el nombre secreto que creó para el ID de cliente en el almacén de claves.
8. En el campo **Nombre secreto de secreto de cliente**, seleccione el nombre secreto que creó para el secreto de cliente en el almacén de claves.
9. En el campo **Nombre secreto de inicio de sesión técnico**, seleccione el nombre secreto que creó para el inicio de sesión de la cuenta técnica en el almacén de claves.
10. En el campo **Nombre secreto de contraseña técnica**, seleccione el nombre secreto que creó para la contraseña de la cuenta técnica en el almacén de claves.
11. En la pestaña **Tubería de procesamiento**, en la sección **Tubería de procesamiento**, seleccione **Integrar con French Chorus Pro** con el nombre de la acción **Estado de solicitud de Chorus Pro para Francia**.
12. En la sección **Parámetros**, en el campo **Nombre secreto de ID de cliente**, seleccione el nombre secreto que creó para el ID de cliente en el almacén de claves.
13. En el campo **Nombre secreto de secreto de cliente**, seleccione el nombre secreto que creó para el secreto de cliente en el almacén de claves.
14. En el campo **Nombre secreto de inicio de sesión técnico**, seleccione el nombre secreto que creó para el inicio de sesión de la cuenta técnica en el almacén de claves.
15. En el campo **Nombre secreto de contraseña técnica**, seleccione el nombre secreto que creó para la contraseña de la cuenta técnica en el almacén de claves.
16. Haga clic en **Guardar** y, a continuación, cierre la página.
17. Repita los pasos 6 a 16 para la configuración de funciones **Factura de proyecto UBL derivada**, **Nota de crédito de ventas UBL derivada** y **Nota de crédito del proyecto UBL derivada**.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general del complemento de facturación electrónica](e-invoicing-service-overview.md)
- [Comenzar con la administración de servicios de complemento de facturación electrónica](e-invoicing-get-started-service-administration.md)
- [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md)
