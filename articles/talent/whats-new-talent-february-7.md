---
title: Novedades y cambios en Dynamics 365 Talent (7 de febrero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
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
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 002dcd8253a0ab753ac9002e7027441db6d0b858
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462491"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-7-2019"></a>Novedades y cambios en Dynamics 365 Talent (7 de febrero de 2019)

Este tema describe las características que son nuevas o que se han cambiado en Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="interview-scheduling-enhancements"></a>Mejoras en la programación de la entrevista
Se han realizado mejoras en la experiencia completa de la programación de entrevistas. Ahora puede ver la disponibilidad del calendario de un candidato interno y usar el calendario del candidato interno para las recomendaciones de la programación. Para obtener más información acerca de la programación, consulte [Programación de entrevista y comentarios](interview-scheduling-feedback.md).

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a>Corregido el problema de no concordancia entre la publicación de oferta en LinkedIn y la empresa
Se ha corregido un problema por el que los trabajos publicados en LinkedIn desde Attract aparecían bajo una empresa incorrecta. Para obtener más información, consulte [Crear, aprobar y publicar trabajos en Attract](creating-jobs-attract.md).

### <a name="career-site-url-displayed-in-admin-settings"></a>URL del sitio de Proyectos profesionales que se muestra en la configuración de gestión
Ahora la dirección URL de la página principal del sitio de Proyectos profesionales se muestra en **Configuración de administrador** en **Gestión del sitio de desarrollo profesional**.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

**Compilación 8.1.2134**

### <a name="multiple-compensation-levels-supported-on-jobs"></a>Varios niveles de compensación compatibles en trabajos
Este cambio permite que más de un nivel de compensación se defina en un trabajo, lo que habilita intervalos de compensación fija del empleado que pueden variar entre los planes cuando se utiliza el mismo trabajo. 

Por ejemplo:    
*Trabajo* - Administrador de cuentas *Niveles de compensación asociados:* B1 y B2 - Cada nivel tiene un intervalo de valores definidos. B1 = Min 50 000, Med 60 000, Max 75 000 y B2 = Min 65 000, Med 74 000, Max 85 000. Al crear la compensación fija de los empleados, en función de las reglas de idoneidad definidas, ahora cada plan fijo podrá señalar al mismo trabajo y seleccionar diferentes niveles en el trabajo. Esto posibilita que los planes estén definidos en varias empresas/regiones y que apunten al mismo trabajo pero a diferentes intervalos sin duplicar trabajos en la cuenta para estas diferencias.

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a>El campo del nivel de compensación se ha agregado a la entidad de la compensación fija del empleado 
Con la actualización, se ha actualizado la entidad de compensación fija del empleado para incluir el campo **Nivel de compensación**. Esta adición facilita actualizar los planes de compensación fija del empleado. 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a>Actualización de la familia del trabajo cuando actualiza o crea nuevos puestos
Cuando cambie el trabajo de un puesto, **Familia de trabajo** ahora tomará un valor predeterminado basado en el trabajo seleccionado.

### <a name="performance-improvements-when-rendering-workspaces"></a>Mejoras del rendimiento al generar espacios de trabajo
Las fichas de análisis de zonas de trabajo ahora se cargarán solo cuando se tenga acceso a dichas páginas. Un indicador se mostrará durante la representación inicial de la página en la esquina superior izquierda de la página.


[!INCLUDE[footer-include](../includes/footer-banner.md)]