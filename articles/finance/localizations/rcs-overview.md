---
title: Regulatory Configuration Service
description: Este tema proporciona una descripción general de las capacidades de Regulatory Configuration Service (RCS) y explica cómo acceder al servicio.
author: JaneA07
manager: AnnBe
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ec7e0fe07d979b85109605949b6ba33ab6d99b51
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890809"
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

![Registro e inicio de sesión en RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

En la página **Regulatory Configuration Service**, revise y acepte los términos y condiciones suplementarios para el uso del servicio, y luego seleccione uno de los siguientes botones:

- **Inscribirse** si es la primera vez que utiliza el servicio y utiliza una dirección de correo electrónico empresarial para proporcionar a su organización un entorno de servicio
- **Iniciar sesión** si se ha registrado anteriormente en el servicio y desea acceder al entorno de su organización

## <a name="regional-availability"></a>Disponibilidad regional

RCS generalmente está disponible en las siguientes regiones:

- Estados Unidos
- India
- Francia
- Europa

Para obtener una lista completa de regiones, consulte [Dynamics 365 y Power Platform: Disponibilidad, ubicación de los datos, idioma y localización](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="related-rcs-documentation"></a>Documentación de RCS relacionada

Para obtener más información acerca componentes relacionados, consulte la siguiente documentación:

- **Repositorio global:**

    - [Cree la configuración de ER y cárguela en el repositorio global](rcs-global-repo-upload.md)
    - [Comparta la configuración en el repositorio global](rcs-global-repo-share-configuration.md)
    - [Filtrado mejorado en el repositorio global](enhanced-filtering-global-repo.md)
    - [Descargar configuraciones de informes electrónicos del repositorio global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Suspender configuraciones en el repositorio global](discontinuing-configurations-rcs-global-repo.md)

- **Característica de globalización**

    - [Regulatory Configuration Service (RCS): característica de globalización](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)