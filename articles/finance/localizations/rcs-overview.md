---
title: Regulatory Configuration Service
description: Este artículo proporciona una descripción general de las capacidades de Regulatory Configuration Service (RCS) y explica cómo acceder al servicio.
author: kfend
ms.date: 06/04/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
ms.openlocfilehash: 01614aec0da097ee5c0c90bcbe9c7e0065f1d4fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277189"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

Regulatory Configuration Service (RCS) es un diseñador independiente y un servicio de gestión del ciclo de vida para la funcionalidad de globalización sin código / código bajo. RCS permite que las partes interesadas de la globalización amplíen y personalicen áreas clave de globalización de impuestos, facturación electrónica, informes regulatorios, banca y documentos comerciales sin tener que involucrar a los desarrolladores. Este enfoque de globalización sin código / bajo código hace que la globalización sea más fácil, rápida y rentable de crear o ampliar.

RCS proporciona las prestaciones siguientes:

- Soporte para todas las funciones que proporciona la generación de informes electrónicos (ER).
- Un requisito previo para configurar nuevos microservicios de globalización.
- Compatibilidad con facturación electrónica. Para más información, vea [Facturación electrónica](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Soportes para el cálculo de impuestos. Para obtener más información, consulte [Servicio de impuestos](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- Compatibilidad con la nueva función de función de globalización que simplifica la gestión del ciclo de vida de funciones de varios componentes y proporciona capacidad adicional para configurar acciones y configurar parámetros de funciones. Para más información, ver [Regulatory Configuration Service: gestión simplificada de funciones de globalización para servicios de globalización](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Soporte para publicación, almacenamiento y uso compartido centralizados de configuraciones personalizadas en el repositorio global para simplificar la administración de la configuración sin requerir el uso de Microsoft Dynamics Lifecycle Services (LCS).

## <a name="access-rcs"></a>Acceder a RCS

Puede registrarse o iniciar sesión en RCS desde la [Página de Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

![Registro e inicio de sesión en RCS.](media/202103_RCS%20Marketing%20page_updated_1.jpg)

En la página **Regulatory Configuration Service**, revise y acepte los términos y condiciones suplementarios para el uso del servicio, y luego seleccione uno de los siguientes botones:

- **Inscribirse** si es la primera vez que utiliza el servicio y utiliza una dirección de correo electrónico empresarial para proporcionar a su organización un entorno de servicio
- **Iniciar sesión** si se ha registrado anteriormente en el servicio y desea acceder al entorno de su organización

> [!NOTE] 
> Después de registrarse, le recomendamos que agregue un usuario de SysAdmin adicional al entorno RCS. Este usuario se asignará como coadministrador del entorno. Esto ayudará a proporcionar estabilidad para el acceso al entorno RCS, ya que el rol de SysAdmin es administrar usuarios para ese entorno. Puede agregar usuarios usando **Espacio de trabajo RCS > Administración del sistema**.

## <a name="regional-availability"></a>Disponibilidad regional

RCS generalmente está disponible en las siguientes regiones:

- Estados Unidos
- India
- Francia
- Europa

Para obtener una lista completa de regiones, consulte [Dynamics 365 y Power Platform: Disponibilidad, ubicación de los datos, idioma y localización](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="rcs-default-company"></a>Empresa predeterminada de RCS

La funcionalidad de tiempo de diseño que se utiliza en RCS se comparte entre todas las empresas. No existe una funcionalidad específica de la empresa. Por lo tanto, le recomendamos que utilice una empresa, **DAT**, con su entorno RCS.

Sin embargo, en algunos escenarios, es posible que desee hacer que los formatos de ER utilicen parámetros relacionados con una entidad jurídica específica. Solo en estos escenarios debe utilizar el conmutador de empresa predeterminado. Para ver un ejemplo, consulte [Configurar formato de ER para usar parámetros especificados por entidad jurídica](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).

## <a name="related-rcs-documentation"></a>Documentación de RCS relacionada

Para obtener más información acerca componentes relacionados, consulte los siguientes temas:

- **RCS:**

    - [Crear configuraciones de informes electrónicos en RCS y cargarlas en el repositorio global](rcs-global-repo-upload.md)

- **Repositorio global:**

    - [Cree la configuración de ER y cárguela en el repositorio global](rcs-global-repo-upload.md)
    - [Comparta la configuración en el repositorio global](rcs-global-repo-share-configuration.md)
    - [Filtrado mejorado en el repositorio global](enhanced-filtering-global-repo.md)
    - [Descargar configuraciones de informes electrónicos del repositorio global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Suspender configuraciones en el repositorio global](discontinuing-configurations-rcs-global-repo.md)
    - [Regulatory Configuration Service (RCS): desactivación del almacenamiento de Lifecycle Services (LCS)](rcs-lcs-repo-dep-faq.md)

- **Característica de globalización**

    - [Regulatory Configuration Service (RCS): característica de globalización](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>Solución de problemas en el registro de RCS

Cuando se registra en RCS desde la página de servicios, puede encontrar un problema relacionado con Azure Active Directory (Azure AD). El mensaje de error que recibe indica que el registro para RCS está actualmente desactivado y debe ser activado antes de que pueda completar el proceso de registro.

![Mensaje de error de registro de RCS.](media/01_RCSSignUpError.jpg)

El problema se produce porque se bloquea la suscripción ad-hoc, y la propiedad `AllowAdHocSubscriptions` debe estar habilitada en su inquilino. 

- Si su departamento de TI gestiona los inquilinos de Azure de su organización, póngase en contacto con ese departamento para informar del problema.
- Si usted es responsable de la gestión de sus inquilinos de Azure, puede solucionar los problemas siguiendo los pasos indicados en [Qué es el registro de autoservicio para Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).
