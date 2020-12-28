---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (23 de enero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
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
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f97462f088fc1a3cb94f2a34204fc09f1cd66fb0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462419"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-23-2019"></a>Novedades y cambios en Dynamics 365 Talent - Core HR (23 de enero de 2019)

**Compilación 8.1.2121**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.

## <a name="changes"></a>Cambios

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a>Importación de compensación fija del empleado que no funciona al crear nuevos registros de compensación fija
Un cambio se ha realizado a la entidad de la compensación fija del empleado para recuperar el nivel de compensación al realizar la importación. Antes de esta versión, un mensaje se visualizaba indicando que se requería el nivel.

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a>Eliminación del campo de saldo mínimo desde el cuadro de diálogo de solicitud de licencia
El campo de **saldo mínimo** se ha eliminado del cuadro de diálogo **solicitud de licencia**. Este cambio afecta a todas las áreas en las que el tiempo libre puede ser solicitado.

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a>Actualización de datos para niveles de compensación que no actualizan en todas las situaciones
Un cambio se ha realizado para actualizar el nivel de compensación en planes de compensación fija. Este cambio rellenará el nivel de compensación de los planes fijos para el trabajo asignado al empleado.

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a>La información de nómina en la página de administración de cambios sólo está disponible si está abierta sesión como administrador del sistema
Este cambio permite a empleados con el rol de administrador acceder a la información de nómina en la página **Línea de tiempo de cambios > administrar cambios** para el puesto.

### <a name="job-fields-default-to-positions"></a>Los campos de trabajo toman puestos como valor predeterminado
Al cambiar el trabajo en un puesto, los campos de trabajo establecerán como valor predeterminado el puesto. Un mensaje de alerta aparecerá y dará la opción de aceptar los valores predeterminados o conservar los valores existentes de dichos campos.

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a>El período y el calendario de período de prueba no se muestran para los empleados contratados en el futuro.
Con este cambio, los campos **Período de prueba** y **Calendario** se han agregado a la página **Gestionar los cambios** para permitir la entrada de datos para empleados del futuro y pasados.

### <a name="platform-update-23-for-finance-and-operations"></a>Platform update 23 para Finance and Operations
Se han incluido correcciones de errores de menor importancia como parte de la Platform update 23 para Finance and Operations. Para obtener más información, consulte [Novedades y cambios en la actualización 23 de la plataforma Dynamics 365 Finance and Operations (enero de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23). 
