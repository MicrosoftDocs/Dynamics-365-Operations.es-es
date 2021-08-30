---
title: Parámetros de integración de nómina
description: Este tema describe los parámetros de integración de nóminas de Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c489b99d5d05ddac46d222e701512288aeb10583a5e829212e0e1c924622f16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712082"
---
# <a name="payroll-integration-parameters"></a>Parámetros de integración de nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Antes de usar la Integración de nómina de Dynamics 365 Human Resources, debe configurar los parámetros descritos en este tema.

## <a name="enable-payroll-address"></a>Habilitar la dirección de la nómina

Para poder utilizar la dirección de nómina, debe habilitarla desde el [formulario de parámetros compartidos](hr-setup-shared-parameters.md) en la pestaña Integración de Nómina.

## <a name="define-the-identification-type"></a>Permite definir el tipo de identificación

Para exponer el ID del tipo de identificación en la [entidad de empleados de nómina](hr-admin-integration-payroll-api-payroll-employee.md), debe [configurar los parámetros de recursos humanos](hr-setup-shared-parameters.md) para cada empresa.

1. En el espacio de trabajo **Administración de compensación**, en los vínculos, seleccione **Parámetros de Human Resources**. 
2. Sobre la pestaña **Integración de nómina**, especifique el valor de los siguientes campos.

| Campo | Descripción |
| --- | --- |
| Usar tipos de identificación en el procesamiento de nóminas | Cuando se selecciona esta opción, el ID del tipo seleccionado se expondrá en la entidad de empleado de nómina. |
| Tipo de identificación | El tipo de identificación a exponer en el campo **mshr_payrollemployeeentityid** de la [entidad de empleados de nómina](hr-admin-integration-payroll-api-payroll-employee.md). |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
