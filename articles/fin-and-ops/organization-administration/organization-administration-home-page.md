---
title: "Página principal de administración de la organización"
description: "En este tema se indican recursos que le ayudarán a usar Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, en una organización."
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: eb8674a6401b11e8e33d3cba54add1fb4bca1cd3
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="organization-administration-home-page"></a>Página principal de administración de la organización

[!include[banner](../includes/banner.md)]


En este tema se detalla contenido que ayudará a los usuarios avanzados y a los administradores a configurar Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Gracias a este contenido será posible configurar el sistema de su organización y negocio para que funcione de forma rápida y efectiva.

La mayor parte del contenido que se detalla aquí se aplica a características del módulo **Administración de organización** . Sin embargo, existen un par de tareas, como la creación y el uso de una plantilla de registro, que se pueden realizar en cualquier módulo y así permitirle perfeccionar el funcionamiento de su organización. 

<a name="number-sequences"></a>Secuencias numéricas
----------------
Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que necesitan identificadores. El registro de datos maestros o de transacciones que necesita un identificador se denomina *referencia*. Antes de poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia.

-   [Información general de secuencias numéricas](number-sequence-overview.md)
-   [Configurar secuencias numéricas mediante asistente](tasks/set-up-number-sequences-wizard.md) (Guía de tareas)
-   [Configurar secuencias numéricas de manera individual](tasks/set-up-number-sequences-individual-basis.md) (Guía de tareas)

## <a name="organizations"></a>Organizaciones
Una organización es un grupo de personas que trabajan juntas para llevar a cabo un proceso empresarial o lograr un objetivo. Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio.

Antes de configurar las organizaciones y las jerarquías organizativas en Finance and Operations, asegúrese de tener previsto cómo se modelará la empresa. El modelo organizativo tiene un importante efecto en la implementación de Finance and Operations y en los procesos empresariales.

-   [Organizaciones y jerarquías organizativas](organizations-organizational-hierarchies.md)
-   [Planificación de su jerarquía organizativa](plan-organizational-hierarchy.md)
-   [Creación o modificación de una jerarquía organizativa](tasks/create-organization-hierarchy.md) (Guía de tareas)
-   [Creación de una entidad jurídica](tasks/create-legal-entity.md) (Guía de tareas)
-   [Creación o modificación de una unidad operativa](tasks/create-operating-unit.md) (Guía de tareas)

## <a name="address-books"></a>Libretas de direcciones
La libreta de direcciones global es un repositorio centralizado de datos maestros que se deben almacenar para todas las personas y organizaciones internas y externas con los que la empresa interactúe. En los datos que se asocian a los registros de parte se incluyen el nombre, la dirección y la información de contacto. 

Después de crear la libreta de direcciones global, puede crear libretas de direcciones adicionales como sea necesario, como una libreta de direcciones independiente para cada empresa de su organización o para cada línea de negocio. 

-   [Libreta de direcciones global](overview-global-address-book.md)
-   [Plan para saber cómo configurar la libreta de direcciones global y las libretas de direcciones adicionales](plan-configuration-global-address-book-additional-address-books.md)
- [Configurar la libreta de direcciones global](tasks/configure-global-address-book.md)
-   [Preguntas frecuentes sobre libretas de direcciones](qa-address-books.md)


## <a name="workflow"></a>Flujo de trabajo
El flujo de trabajo es un sistema que está instalado en Finance and Operations que puede usar para crear flujos de trabajo individuales, o procesos empresariales. Al crear un flujo de trabajo, debe especificar cómo fluye o se mueve un documento en el sistema; para ello, debe mostrar quién debe completar una tarea, tomar una decisión o aprobar un documento. 

-   [Visión general del flujo de trabajo](overview-workflow-system.md)
-   [Elementos del flujo de trabajo](workflow-elements.md)
-   [Acciones de flujo de trabajo](workflow-actions.md)
-   [Crear un flujo de trabajo](create-workflow.md)

## <a name="electronic-signatures"></a>Firmas electrónicas
Una firma electrónica confirma la identidad de una persona que va a comenzar o aprobar un proceso informático. En algunos sectores, una firma electrónica es tan vinculante legalmente como una firma escrita. Las firmas electrónicas son un requisito de cumplimiento de directivas para determinados sectores regulados, como el farmacéutico, alimentación, aeroespacial y defensa.

En Finance and Operations, puede usar firmas electrónicas para procesos empresariales críticos. Algunos procesos llevan integrada la capacidad de firma electrónica. También puede crear requisitos de firma personalizados para cualquier tabla o campo de la base de datos.

-   [Visión general de la firma electrónica](electronic-signature-overview.md)
-   [Configuración de firmas electrónicas](tasks/set-up-electronic-signatures.md) (Guía de tareas)

## <a name="case-management"></a>Gestión de casos
Al planificar, seguir y analizar casos, puede desarrollar resoluciones eficaces que se pueden usar para emisiones similares. Por ejemplo, si un representante de servicio al cliente o un generalista de recursos humanos crean casos, pueden encontrar información en los artículos de conocimientos sobre cómo trabajar con un caso o cómo resolverlo de forma más eficaz. 

-   [Visión general de la gestión de casos](cases.md)
-   [Configurar seguridad, procesos y categorías de casos](plan-case-management.md)

## <a name="record-templates"></a>Plantillas de registro
Las plantillas de registro pueden ayudarle a crear registros más rápidamente. Puede crear plantillas de registro para no tener que especificar los valores de campo que se utilizan a menudo explícitamente para cada registro nuevo. 

-   [Plantillas de registro](record-templates.md)
- [Crear una plantilla de registro para facilitar la entrada de datos](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Guía de tareas)
- [Usar una plantilla de registro para crear un nuevo registro](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Guía de tareas)

## <a name="general-organization-administration"></a>Administración de la organización general
-   [Cambiar el encabezado o el logotipo](../get-started/tasks/change-banner-or-logo.md) (Guía de tareas)
- [Configurar la gestión de documentos](configure-document-management.md)
- [Configurar y enviar correo electrónico](configure-email.md)
-   [Datos de fecha y hora y las zonas horarias](date-time-zones.md)








