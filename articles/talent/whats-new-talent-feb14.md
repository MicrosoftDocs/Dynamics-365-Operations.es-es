---
title: Novedades y cambios en Dynamics 365 Talent (14 de febrero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 32f3bab38233833498ed566fa1558a023b3bc0dd
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899229"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-14-2019"></a>Novedades y cambios en Dynamics 365 Talent (14 de febrero de 2019)

Este tema describe las características que son nuevas o que se han cambiado en Talent.

## <a name="changes-in-attract"></a>Cambios en Attract
En esta versión se incluyen correcciones de errores menores.

## <a name="changes-in-onboarding"></a>Cambios en Onboarding
En esta versión se incluyen correcciones de errores menores.
 
## <a name="changes-in-core-hr"></a>Cambios en Core HR 
**Compilación 8.1.2146**

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a>La entidad de compensación fija del empleado no exporta todos los registros
Con este cambio, la entidad **Compensación fija del empleado** ahora exportará todos los registros. La entidad puede ser utilizada para crear y actualizar registros existentes de compensación fija para los empleados. 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a>La fecha de finalización del empleo no cumple los valores preferidos de zona horaria del empleado
Las fechas de finalización del empleo ahora cumplen la zona horaria preferida del usuario al crear o finalizar el empleo en una empresa.
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a>Las direcciones del Reino Unido se muestran en Analytics como direcciones del este de Suiza
En esta versión, un cambio se ha realizado para corregir la desalineación en las direcciones del informe "Recuento de personal por ubicación" de la **Dirección de personal**.
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a>El código de finalización no se rellena en el registro de asignación de puesto del trabajador al finalizar el puesto
Un cambio se ha realizado para establecer el código de “motivo de la finalización” en el valor predeterminado al finalizar la asignación de puesto de los empleados.

### <a name="new-entity-created-for-job-compensation-levels"></a>Creada una nueva entidad para los niveles de compensación de trabajo
Se ha creado una nueva entidad de marco de gestión de datos (DMF). La entidad se encarga de la creación y la actualización de los niveles de compensación, los valores de mercado, y la información de encuesta para cada trabajo definido en el sistema.
