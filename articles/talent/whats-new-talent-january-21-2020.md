---
title: Novedades y cambios en Dynamics 365 Talent (21 de enero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/21/2020
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
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e9dee64e94c904cfe07c6a7766f6a60b1d60a2db
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528131"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-21-2020"></a>Novedades y cambios en Dynamics 365 Talent (21 de enero de 2020)

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract. Hemos agregado funcionalidad a Attract para dar soporte a nuestro reciente anuncio, [Creación de un personal más exitoso con Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).

### <a name="download-environment-data"></a>Descargar datos de entorno

Los administradores pueden descargar los datos de su entorno. Los datos se exportan en formato JSON estándar con todos los trabajos, candidatos y configuraciones exportados en un archivo zip. Para obtener más información, consulte [Exportar datos de Attract y Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

### <a name="restricting-access-to-environments-for-non-admin-users"></a>Restringir el acceso a entornos para usuarios que no son administradores

Los administradores ahora pueden restringir el acceso al entorno para usuarios que no son administradores. Esta acción no se puede deshacer. Para obtener más información, consulte [Restringir el acceso a Attract](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

### <a name="exporting-onboarding-guides"></a>Exportación de guías de incorporación

Los usuarios ahora pueden exportar todas sus guías de incorporación y plantillas de incorporación en formato de documento de Word. Para obtener más información, consulte [Exportar datos de Attract y Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2726. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="most-recent-annual-compensation-field-in-verify-employment-form-isnt-consistent-392092"></a>El campo de compensación anual más reciente del formulario de comprobación de empleo no es coherente (392092)

Esta versión incluye un cambio que mostrará coherentemente la última divisa en función del selector de empresa en el formulario **Comprobar empleo**.

### <a name="known-as-field-added-to-the-feedback-recipient-lookup-407789"></a>Conocido como campo agregado a la búsqueda de destinatarios de comentarios (407789)

Al proporcionar comentarios sobre el rendimiento, la búsqueda de trabajadores no proporcionó suficiente información para determinar si los comentarios van a la persona correcta. Agregamos una columna **Conocido como** para ayudar a identificar el nombre único del empleado.
 
### <a name="hcmworkerpayrollinfo-record-is-created-without-an-association-to-a-worker-394526"></a>El registro HcmWorkerPayrollInfo se crea sin una asociación a un trabajador (394526)

Esta versión incluye un cambio para no escribir registros HCMWorkerPayrollInfo sin referencia a un empleado.

### <a name="able-to-edit-department-when-navigating-from-position-hierarchy-341001"></a>Capaz de editar el departamento al navegar desde la jerarquía de posición (341001)

Cuando se ha configurado la seguridad para denegar el acceso a los departamentos de edición, la edición se deshabilita al navegar al formulario **Departamentos** en todos los escenarios.

## <a name="coming-soon"></a>Próximamente

Una nueva solución Common Data Service estará disponible pronto con los siguientes cambios:

| Descripción | Cambio |
| --- | --- |
| La entidad **Puesto de trabajo** cambia | <ul><li>Se ha agregado **Región de compensación**</li><li>Se ha agregado **Dimensiones financieras**</li></ul> |
| La entidad **Trabajador** cambia | <ul><li>Se ha agregado **Orden del nombre**</li><li>Se ha agregado **Trabaja desde casa**</li><li>Se ha agregado **Idioma**</li><li>Se ha agregado **Antigüedad**</li><li>Se ha agregado **Fecha de aniversario**</li><li>Se ha agregado **Fecha de contratación original**</li></ul> |
| La entidad **Empleo** cambia | <ul><li>Se ha agregado **Dimensiones financieras**</li><li>Se ha agregado **Razón de la finalización**</li><li>**Fecha de finalización** ha cambiado de nombre a **Fecha de transición**</li><li>Se ha agregado **Fechas del período de pruebas**</li></ul> |
| La entidad **Dirección del trabajador** cambia | <ul><li>Se ha agregado **Dirección postal**</li><li>**Línea de dirección 1**, **Línea de dirección 2** y **Línea de dirección 3** marcadas para eliminación</li></ul> |
| Nuevas entidades de configuración de compensación variable | <ul><li>**Tipo de plan de compensación variable**</li><li>**Plan de compensación variable**</li><li>**Reglas de atribución**</li><li>**Nivel de plan de compensación variable**</li></ul> |
| Nueva entidad **Empleo de calendario de trabajador** | <ul><li>Se ha agregado la entidad **Calendario de trabajo**</li></ul> |


[!INCLUDE[footer-include](../includes/footer-banner.md)]