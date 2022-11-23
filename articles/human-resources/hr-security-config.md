---
title: Conceptos de configuración de seguridad para integraciones basadas en tablas virtuales
description: Este artículo explica una arquitectura para crear una integración entre Microsoft Dynamics 365 Human Resources y otros sistemas.
author: twheeloc
ms.date: 11/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 219ceb0adae0cee5f74a39140ab74af9fdac1eb6
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759660"
---
# <a name="security-configuration-concepts-for-virtual-table-based-integrations"></a>Conceptos de configuración de seguridad para integraciones basadas en tablas virtuales

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe una arquitectura para usar [tablas virtuales (entidades) de Microsoft Dataverse](/dev-itpro/power-platform/virtual-entities-overview) para construir una integración entre Dynamics 365 Human Resources y un sistema de terceros. El enfoque del artículo está en la configuración de seguridad y en los aspectos de autenticación y autorización que se requieren entre los límites del sistema para construir un sistema seguro y funcional.

## <a name="prerequisite-reference-articles"></a>Artículos de referencia de requisitos previos

En los artículos siguientes se proporciona más información acerca de los conceptos en este artículo:

- [Información general sobre entidades virtuales](/dev-itpro/power-platform/virtual-entities-overview)
- [Comenzar con tablas virtuales (entidades)](/developer/data-platform/virtual-entities/get-started-ve)
- [Utilizar la autenticación de servidor a servidor de varios inquilinos (Microsoft Dataverse)](/developer/data-platform/use-multi-tenant-server-server-authentication)
- [Usar la autenticación de OAuth con Microsoft Dataverse (Dataverse)](/developer/data-platform/authenticate-oauth)
- [Flujo de credenciales de cliente de OAuth 2.0 en la plataforma de identidad de Microsoft](/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)
- [Autenticación y autorización](/dev-itpro/power-platform/authentication-and-authorization)

## <a name="architecture"></a>Arquitectura 

El siguiente diagrama arquitectónico muestra los conceptos principales que están involucrados en una integración que usa tablas virtuales (entidades).

![Integración basada en tablas virtuales.](./media/Hosts.jpg)

A continuación, se ofrece una explicación de algunos de los elementos del diagrama anterior:

- **microsoft** – Microsoft aloja y opera los diferentes productos de Dynamics 365 en nombre de los clientes.

    - **Inquilino de Azure Active Directory (Azure AD) C** - Un inquilino de Azure AD que es propiedad de Microsoft. Es el arrendatario en el que están registradas las aplicaciones de Dynamics 365.

- **Socio integrador**

    - **Sistema integrador** – El sistema que se está integrando con Dynamics 365. Puede ser un sistema de nómina o cualquier sistema que se base en datos almacenados en Dynamics 365.
    - **Adaptador** – El software o servicio que es responsable de interactuar tanto con Dynamics 365 como con el sistema de integración.

        > [!NOTE]
        > Si un adaptador está destinado a ser utilizado por varios clientes de Dynamics 365, la expectativa es que se registrará como una aplicación multiusuario en Azure AD.

    - **Inquilino de Azure AD A** - Un arrendatario de Azure AD que es propiedad del socio integrador. Es el arrendatario en el que está registrado el ID de aplicación del adaptador.

- **Cliente mutuo** – Un cliente que implementa Dynamics 365 Human Resources y la solución del socio integrador.

    - **Dynamics 365 Finanzas o Recursos Humanos** – La instancia específica del cliente de Dynamics 365 Finance o Human Resources que contiene los datos del cliente que requiere el sistema de integración.
    - **Dataverse** – El entorno de Dataverse específico del cliente que está conectado a Finance o Human Resources. Dataverse proporciona una API web para la interacción con los datos de Dynamics 365.
    - **Inquilino de Azure AD B** - El cliente de Azure AD del cliente. Funciona como proveedor de identidad (servidor de autorización) y emite tokens que autorizan a las personas que llaman a llamar a la instancia de Dataverse del cliente.

## <a name="basic-request-flow"></a>Flujo de solicitudes básico

Esta sección describe el flujo básico de una solicitud típica que está involucrada en una integración. Hace referencia al diagrama arquitectónico anterior en este artículo.

Una solicitud típica requiere que el adaptador consulte los datos de Dynamics 365 y luego guarde y sincronice esos datos con el sistema de integración.

1. El adaptador llama a la API web de Dataverse para consultar datos relevantes.

    > [!NOTE]
    > La autenticación es un requisito previo y la adquisición de tokens es una parte importante del proceso. La autenticación se describirá en la sección [Autenticación y autorización en los límites del sistema](#authentication-and-authorization-at-system-boundaries).

    Esta llamada se hace contra la API web de Dataverse para consultar los datos de la aplicación que se exponen a través de una tabla virtual. (Vea "2. Sincronización inicial" y "3. Sincronización delta" en el diagrama).

2. Dataverse maneja la solicitud consultando la tabla virtual a través del complemento de entidad virtual ("Proxy de tabla virtual" en el diagrama). La solicitud de Dataverse se reenvía al servicio de entidad virtual de Finanzas o Recursos Humanos para consultar los datos almacenados físicamente en la base de datos de Finanzas o Recursos Humanos.
3. El servicio de Entidad Virtual Financiera o de Recursos Humanos traduce la solicitud contra la entidad virtual en una consulta contra la Entidad Financiera o de Recursos Humanos que respalda la entidad virtual de Dataverse. Los datos se recuperan de la base de datos, se vuelven a traducir a la representación de la entidad de Dataverse y se devuelve a la persona que llama.
4. El adaptador completa cualquier mapeo y traducción de datos requeridos, y realiza una llamada al sistema de integración para conservar los datos en la base de datos del sistema de integración. (Vea "4. Guardar datos" en el diagrama).

## <a name="authentication-and-authorization-at-system-boundaries"></a>Autenticación y autorización en los límites del sistema

*Autenticación* valida que se ha probado la identidad de un usuario o de una aplicación, y confirma que el usuario o la aplicación es quien dice ser. *Autorización* otorga al usuario o aplicación el derecho de acceder a permisos específicos a nivel de aplicación. Para más información, ver [Autenticación frente a autorización](/azure/active-directory/develop/authentication-vs-authorization).

La mayoría de las llamadas entre sistemas del diagrama arquitectónico anterior en este artículo involucran al adaptador. El adaptador debe autenticarse para realizar las siguientes llamadas:

- La llamada a Dataverse
- La llamada al sistema integrador

Mire los límites del sistema en el diagrama. Cada solicitud web entre sistemas debe autenticarse y se deben pasar verificaciones de autorización a nivel de aplicación antes de que los datos se devuelvan a la persona que llama. Para una solicitud en una tabla virtual de Dynamics 365 respaldada por Finanzas o Recursos humanos, las verificaciones de autenticación y autorización se aplican en los siguientes límites del sistema:

- La llamada entre el adaptador y el punto final de la API web de Dataverse (OData)
- La llamada entre el complemento de entidad virtual de Dataverse y el servicio de entidad virtual de Finance o Human Resources

En ambos casos, las comprobaciones de autenticación se realizan primero. Luego, se realizan verificaciones de autorización a nivel de aplicación para garantizar que el usuario o la aplicación autenticados tengan los privilegios de nivel de aplicación correctos para recuperar los datos solicitados.

La autenticación para llamar a Dataverse se maneja a través de un token de portador que debe incluirse como un encabezado HTTP en la solicitud web para Dataverse. El adaptador debe obtener un token de la instancia de Azure AD del inquilino B. (Vea "1. Obtener Token" en el diagrama). Azure AD actúa como proveedor de identidad en el flujo de autenticación.

El adaptador se autentica proporcionando su identidad de aplicación (no secreta, tal como está registrada en el inquilino A de Azure AD) y un secreto de aplicación o certificado que solo tiene la aplicación del adaptador.

Después de que el usuario o la aplicación se haya autenticado para realizar llamadas a Dataverse, las comprobaciones de autorización de nivel de Dataverse se realizan en cada solicitud. Estas comprobaciones aseguran que la persona que llama (la identidad de la aplicación del adaptador, que se designa "\<guid A\>" en el diagrama) tiene los permisos de aplicación apropiados. La autorización a nivel de aplicación se gestiona en Dataverse a través de un usuario de la aplicación que representa el ID de la aplicación del adaptador. Los permisos a nivel de aplicación se administran otorgando acceso a roles de aplicación específicos definidos por Dataverse. Esos roles proporcionan privilegios granulares a la aplicación.

Para obtener orientación más detallada, consulte [Utilice la autenticación de servidor a servidor de multiinquilino](/power-apps/developer/data-platform/use-multi-tenant-server-server-authentication)

Si se pasan las comprobaciones de permisos de la aplicación de nivel de Dataverse, el complemento de la entidad virtual realiza una llamada al extremo del servicio de la entidad virtual en el entorno de finanzas o recursos humanos. La autenticación de servidor a servidor (S2S) se utiliza para realizar esta llamada. Utiliza la identidad y el secreto que están configurados en el registro de configuración del origen de datos virtual de Finanzas y operaciones.

![Registro de configuración de fuentes de datos virtuales de Finanzas y operaciones en el entorno de pruebas.](./media/sandbox.jpg)

Para obtener más información, [Configurar entidades virtuales de Dataverse](/dev-itpro/power-platform/admin-reference).

La llamada del complemento de entidad virtual de Dataverse para Finance o Human Resources incluye la identidad del adaptador de la llamada original a Dataverse del adaptador (la identidad designada "\<guid A\>" en el diagrama de la arquitectura). Si el origen de datos de la entidad virtual está configurado correctamente y se pasan las comprobaciones de autenticación S2S, el servicio de entidad virtual en Finanzas o Recursos humanos ejecutará la consulta en el contexto de la persona que llama original (el adaptador, \<guid A\>). Se realizarán verificaciones de permisos de aplicaciones (autorización) a nivel de Finanzas o Recursos Humanos para garantizar que el adaptador tenga los privilegios necesarios para acceder a las entidades de datos que se solicitan a través de la consulta.

La seguridad de Finanzas y Recursos Humanos se gestiona de las siguientes maneras:

1. Al mapear la identidad del adaptador (\<guid A\>) a un usuario específico de Finance o Human Resources. Esta asignación se raliza en la página **Aplicaciones de Azure Active Directory**. Para obtener más información, consulte [Registrar la aplicación externa](/dev-itpro/data-entities/services-home-page.md#register-your-external-application).
2. Otorgando al usuario de Finance o Human Resources los roles, derechos y privilegios apropiados a nivel de aplicación. Para obtener más información, consulte [Seguridad basada en roles](/dev-itpro/sysadmin/role-based-security).

Si a la aplicación del adaptador (\<guid A\>) se le otorgan los privilegios que se requieren para acceder a los datos solicitados, ocurren los siguientes eventos:

1. Se ejecuta la consulta.
2. Los datos se traducen de nuevo a la página de la entidad de Dataverse.
3. Los datos se devuelven al adaptador.

> [!IMPORTANT]
> Durante el desarrollo, el adaptador se puede ejecutar mediante un usuario de finanzas o recursos humanos que tenga la función de administrador. Sin embargo, en un entorno de producción, el adaptador nunca debe ejecutarse con privilegios de administrador.

## <a name="key-takeaways"></a>Conclusiones clave

Aquí hay algunas implicaciones importantes de la tabla virtual o la arquitectura de la entidad:

- La configuración de seguridad para las tablas virtuales respaldadas por Human Resources se administra en Human Resources.
- El cliente ("Cliente mutuo" en el diagrama arquitectónico anterior en este artículo) tiene control total sobre los privilegios que se otorgan a la identidad del adaptador de integración (designada como "\<guid A\>" en el diagrama).
- El cliente es responsable de la correcta configuración de seguridad de su entorno de Human Resources. El socio de integración que crea el adaptador debe brindar orientación sobre los privilegios que requiere el adaptador.
