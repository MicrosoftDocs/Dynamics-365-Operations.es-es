---
title: Configurar frecuencias de pago
description: Microsoft Dynamics 365 Human Resources utiliza las frecuencias de pago para calcular el salario anual de prestaciones, determinar el importe de la prima de beneficios que un empleado paga en cada período de pago y la frecuencia con la que se paga a los proveedores.
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
ms.openlocfilehash: f5a2ad19d9f9f3a6afa2574d9fdb8841c70d6e6e
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114173"
---
# <a name="set-up-payment-frequencies"></a>Configurar frecuencias de pago

Microsoft Dynamics 365 Human Resources utiliza las frecuencias de pago para calcular el salario anual de prestaciones, determinar el importe de la prima de beneficios que un empleado paga en cada período de pago y la frecuencia con la que se paga a los proveedores.

Las frecuencias de pago de beneficios utilizan factores de conversión para convertir los períodos de pago de beneficios entre frecuencias de pago mensuales, semestrales, quincenales, semanales y diarias. Esto permite a las empresas definir la interdependencia entre las frecuencias de pago dentro de un plan de beneficios.

Los campos de factores de conversión identifican el factor de conversión de la frecuencia de pago a los períodos de pago estándar y permiten que el sistema haga cálculos entre las frecuencias de pago. La cantidad del factor de conversión también determina la cantidad de la prima de beneficio que un empleado debe pagar cada frecuencia de pago.

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Frecuencias de pago**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Frecuencia de pago** | Un nombre de frecuencia de pago único. |
   | **Descripción** | Descripción de la frecuencia de pago. |
   | **Período** | El período adecuado que mejor se ajusta a la frecuencia de pago del proveedor de beneficios y del empleado. La lista de períodos se compone de los períodos de pago estándar. |
   | **Número de períodos de pago** | El número de períodos de pago que representa la frecuencia con la que se paga al proveedor de beneficios o a los empleados. Esta cantidad se utilizará para calcular el importe del salario de beneficio anual del empleado. |
   | **Factor de conversión anual** | El factor de conversión anual para la frecuencia de pago. Por ejemplo, el factor de conversión anual para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 1 año) = 12 |
   | **Factor de conversión semestral** | El factor de conversión semianual para la frecuencia de pago. Por ejemplo, el factor de conversión semianual para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 2 veces al año) = 6 |
   | **Factor de conversión trimestral** | El factor de conversión trimestral para la frecuencia de pago. Por ejemplo, el factor de conversión trimestral para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 4 trimestres) = 3 |
   | **Factor de conversión mensual** | El factor de conversión mensual para la frecuencia de pago. Por ejemplo, el factor de conversión mensual para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 12 meses) = 1 |
   | **Factor de conversión bimensual** | El factor de conversión semimensual para la frecuencia de pago. Por ejemplo, el factor de conversión semimensual para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 24 (2 veces al mes)) = 0,5 | 
   | **Factor de conversión quincenal** | El factor de conversión anual para la frecuencia de pago. Por ejemplo, el factor de conversión anual para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 26 semanas) = 0,461538 |
   | **Factor de conversión semanal** | El factor de conversión anual para la frecuencia de pago. Por ejemplo, el factor de conversión anual para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 52 semanas) = 0,230769 |
   | **Factor de conversión diario** | El factor de conversión anual para la frecuencia de pago. Por ejemplo, el factor de conversión anual para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 365 días) = 0,032877 |
   | **Factor de conversión de horas** | El factor de conversión anual para la frecuencia de pago. Por ejemplo, el factor de conversión anual para la frecuencia de pago mensual es: </br></br>(12 pagos mensuales / 2080 horas) = 0,005769

4. Seleccione **Guardar**. 
