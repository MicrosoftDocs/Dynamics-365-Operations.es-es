---
title: Configurar las opciones de idoneidad de contacto personal
description: Configurar opciones de idoneidad para contactos personales en Microsoft Dynamics 365 Human Resources. Los contactos personales pueden ser beneficiarios o dependientes.
author: andreabichsel
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 071523e2a1e9de6f0ed2b77e4ad6802efb0073f7
ms.sourcegitcommit: 08797bc43e93ea05711c5a70dd7cdb82cada667a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "6558258"
---
# <a name="configure-personal-contact-eligibility-options"></a>Configurar las opciones de elegibilidad de contacto personal

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema explica cómo configurar los tipos de contactos personales que pueden usarse en prestaciones de Microsoft Dynamics 365 Human Resources. Los contactos personales son las personas que estarán cubiertas por sus planes (dependientes) o que se beneficiarán de sus planes (beneficiarios). Los dependientes suelen ser cónyuges o hijos. Los beneficiarios pueden ser cónyuges, hijos, fideicomisos o padres.

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Opciones de idoneidad para contactos personales**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Opción de idoneidad** | Un nombre o código de opción de idoneidad único para identificar la opción de idoneidad. |
   | **Descripción** | Descripción breve de la opción de idoneidad. |
   | **Código de idoneidad de contacto** | Código del sistema que mejor describe la opción de idoneidad personal. Puede elegir entre: <ul><li>Relación</li><li>Estudiante</li><li>Dependiente mayor de edad</li><li>Dependiente deshabilitado demasiado mayor</li></ul> |
   | **Estado** | El estado de la opción de idoneidad. Si el estado de una opción de idoneidad está configurado como inactivo, no puede seleccionar esa opción de idoneidad de contacto personal para contactos personales. |
   | **Relación** | Especifica la relación entre el contacto personal y el empleado. Este campo solo está activo si el código de idoneidad de contacto está establecido en Relación. |
   | **Vencimiento** | La edad máxima de un contacto personal idóneo para el plan de prestaciones. Este campo solo está activo si selecciona una relación. Esta edad se compara con la edad calculada del contacto personal. La edad calculada es: (Fecha de cobertura - fecha de nacimiento del contacto personal / 365). Este número siempre es un entero. |

4. Seleccione **Guardar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
