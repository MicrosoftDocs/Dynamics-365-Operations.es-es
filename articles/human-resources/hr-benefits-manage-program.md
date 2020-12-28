---
title: Definir y gestionar un programa de prestaciones
description: Los Recursos humanos ofrecen una serie de herramientas que se pueden usar para configurar y mantener prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores. En este artículo se ofrece información acerca de cómo configurar y gestionar prestaciones.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a7fe99d4982b8f35871b15e8049c39eb806e315c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420379"
---
# <a name="define-and-manage-a-benefits-program"></a>Definir y gestionar un programa de prestaciones

Human Resources ofrece una serie de herramientas que se pueden usar para configurar y mantener prestaciones, deducciones y los planes de compensación de los trabajadores que una organización ofrece o procesa para sus trabajadores. En este artículo se ofrece información acerca de cómo configurar y gestionar prestaciones.

## <a name="benefit-setup"></a>Configuración de prestaciones

Para que los trabajadores puedan inscribirse en prestaciones, debe crear los elementos de cada prestación. Estos elementos combinan planes de prestaciones similares y definen la configuración predeterminada, como las tasas de deducción y los detalles de contabilidad. Muchos de estos parámetros se pueden ajustar cuando los trabajadores se inscriben posteriormente en la prestación. Para cada plan de prestaciones, una organización puede ofrecer varias opciones de inscripción o un trabajador puede condonar inscripción en el plan. 

[![Flujo del proceso de prestaciones](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Elementos de beneficio

Para poder comenzar a crear prestaciones e inscribir trabajadores en ellas, debe definir los elementos que componen una prestación: el tipo, el plan y las opciones.

-   **Tipo**: un conjunto de planes de una prestación determinada, como cobertura médica o estacionamiento pagado.
-   **Plan**: una prestación concreta contratada a un proveedor.
-   **Opción**: el nivel de cobertura, como empleado sólo o como empleado y cónyuge/pareja.

Para cada tipo de prestación, como de visión o dental, una organización puede ofrecer uno o varios planes a sus trabajadores. Para cada plan, la organización puede ofrecer diferentes opciones. Por ejemplo, los trabajadores pueden comprar cobertura adicional de seguro de vida a término una, dos o tres veces su sueldo anual. Cada combinación de un plan y de opciones se convierte en una prestación en la que los trabajadores pueden inscribirse. 

[![imagen de prestación](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Idoneidad
Muchos factores determinan la idoneidad del trabajador para los distintos tipos de prestaciones que el empleador ofrece. Al crear una prestación en Dynamics 365 Human Resources, puede establecer el tipo de idoneidad que se aplica a dicha prestación. 

Puede hacer que una prestación esté disponible para todos los trabajadores. Por ejemplo, algunas empresas ofrecen pases de aparcamiento para todos los empleados como beneficio complementario. Cuando crea esta prestación, establece la idoneidad en **Todos los trabajadores son aptos**. 

Para otras prestaciones, como embargos y recaudaciones de impuestos, no se aplica la idoneidad. Al crear estos tipos de prestaciones, establece la idoneidad en **Omitir proceso de idoneidad**. 

Por último, la idoneidad de la prestación puede estar basada en reglas. Por ejemplo, una empresa ofrece dos tipos de prestación de seguro de vida a los empleados. Los empleados ejecutivos son aptos para un plan de seguro de vida, mientras que los demás empleados a jornada completa son aptos para el otro plan de seguro de vida. En Recursos humanos, puede crear una regla de idoneidad de prestación para encontrar todos los empleados ejecutivos y otra regla para buscar todos los demás empleados a jornada completa y después aplicar esas reglas a la prestación adecuada.

## <a name="enrollment"></a>Inscripción
Una vez que haya creado las prestaciones que su organización ofrece y la idoneidad determinada, puede inscribir a sus trabajadores en prestaciones. Puede inscribir a un único trabajador en prestaciones o bien, puede inscribir varios trabajadores en una o más prestaciones durante un proceso único. 

A veces, una organización deja de ofrecer determinadas prestaciones. En este caso, debe actualizar la prestación y los trabajadores que están inscritos en ella. La expiración de prestación masiva le permite cambiar la fecha de vencimiento tanto de una prestación como las inscripciones de trabajador para esa prestación al mismo tiempo. También puede seleccionar varios trabajadores inscritos en una prestación y cambiar la fecha final de cobertura. 

Del mismo modo, la extensión total de la prestación le permite ampliar la fecha de vencimiento tanto de una prestación como las inscripciones de trabajador para dicha prestación si decide ofrecer una prestación más tiempo de lo que planeó originalmente.


