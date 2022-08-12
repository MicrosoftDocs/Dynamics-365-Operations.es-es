---
title: Configurar deducciones
description: Usar deducciones en Microsoft Dynamics 365 Human Resources para determinar cuánto, si corresponde, deducir del sueldo de un empleado por cada prestación.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2fb5f5b0b50f407f58193aafd79f28dd1fd432ee
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066804"
---
# <a name="configure-deductions"></a>Configurar deducciones


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Usar deducciones en Microsoft Dynamics 365 Human Resources para determinar cuánto, si corresponde, deducir del sueldo de un empleado por cada prestación. Las deducciones son efectivas a partir de una fecha, por lo que puede mantener un registro histórico de la información de la deducción. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Deducciones**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Deducción** | Un id. único que se utiliza para identificar la deducción de prestaciones. |
   | **Descripción** | Una descripción de la deducción. |
   | **Vigente** | La fecha de inicio. El valor predeterminado de la fecha actual del sistema. |
   | **Caducidad** | La fecha de finalización. El valor predeterminado es 12/31/2154, que significa nunca. |
   | **Título** | El código de encabezado del sistema de nóminas que esta deducción usará para la parte de la deducción del empleado al procesar las prestaciones de la nómina. Se utiliza cuando usa un proveedor de nómina externo. |
   | **Referencia del empleado para deducciones de nómina** | Código de deducción del sistema de nóminas que esta deducción usará para la parte del empleado de la deducción al procesar las prestaciones de la nómina. |
   | **Partida de importe** | El código de encabezado del sistema de nóminas que este importe de deducción usará para la parte de la deducción del empleado al procesar las prestaciones de la nómina. Normalmente, se utiliza cuando usa un proveedor de nómina externo. |
   | **Se puede eliminar** | Especifica si un valor exportado de Dynamics 365 Finance puede hacer que el valor se elimine en el sistema de nómina. |
   | **Columnas emparejadas** | Especifica si se debe exportar el encabezado y el importe de deducción en columnas adyacentes emparejadas al sistema de nómina. |
   | **Fecha de vigencia del cambio** | La fecha en la que entrará en vigor el cambio de deducción de prestaciones. En esta fecha, la deducción de prestaciones cambia y todos los planes de prestaciones asociados con esta deducción se actualizan, siempre y cuando ejecute el proceso de **Actualización de cambio de deducción**. |
   | **Cambio de deducción completado** | La casilla de **Cambio de deducción completado** se seleccionará automáticamente una vez que el proceso de cambio de actualización de deducción haya completado los cambios de deducción de prestaciones. |
   
4. Para realizar un seguimiento y mantener los cambios en la configuración de la tasa de prestaciones, seleccione **Acciones** y luego seleccione **Mantener versiones**.

5. Seleccione **Guardar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

