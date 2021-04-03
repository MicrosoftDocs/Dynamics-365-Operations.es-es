---
title: Configurar las opciones de idoneidad de contacto personal
description: Configurar opciones de idoneidad para contactos personales en Microsoft Dynamics 365 Human Resources. Los contactos personales pueden ser beneficiarios o dependientes.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f300ac917ac21db9fffbffcc6eb8589357c0a3e
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466215"
---
# <a name="configure-personal-contact-eligibility-options"></a>Configurar las opciones de idoneidad de contacto personal

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo le muestra cómo configurar tipos de contactos personales para usar en prestaciones de Microsoft Dynamics 365 Human Resources. Los contactos personales pueden ser beneficiarios o dependientes. 

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