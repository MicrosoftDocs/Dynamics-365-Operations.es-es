---
title: Novedades y cambios en Dynamics 365 for Talent (20 de marzo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/20/2019
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
ms.search.validFrom: 2019-03-20
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d69294b64c841c5486d694b129cf6c0f26fd93fd
ms.sourcegitcommit: c131672b02407a99aafd38957d04816a82997264
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2019
ms.locfileid: "892460"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-20-2019"></a>Novedades y cambios en Dynamics 365 for Talent (20 de marzo de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="setting-the-audience-on-activities"></a>Establecer la audiencia en actividades
Las actividades en el sistema podrán tener la audiencia definida. Las actividades relacionadas con procesos (como entrevista, programación, comentarios, y EEO) se pueden establecer para todos los candidatos, candidatos internos y candidatos externos. Las actividades personalizadas, como formularios de Microsoft, los vídeos de YouTube y contenido Web se pueden entregar a todos los candidatos, candidatos internos, candidatos externos o al equipo de contratación.  

### <a name="improve-career-site-job-discoverability-search-engine-optimization"></a>Garantizar la detectabilidad del sitio de empleo: Optimización del motor de búsqueda
Esta función permite a los rastreadores del motor de búsqueda acceder e indexar propuestas de trabajo en el sitio de empleo de Attract. Esto ayuda a los candidatos a encontrar los trabajos enviados al sitio de empleo de Attract mediante los motores de búsqueda más populares.

### <a name="show-login-hint-to-candidates-who-forgot-their-credentials"></a>Mostrar sugerencia de inicio de sesión a los candidatos que olvidaron sus credenciales.
Si un candidato olvidó las credenciales sociales que usaron para solicitar un empleo al abrir un vínculo que habían guardado o les habían enviado, ahora verán una sugerencia con el nombre del proveedor y de usuario (ofuscado). Esto les ayudará a usar las credenciales correctas para acceder a su solicitud de empleo.

### <a name="help-internal-candidates-explore-internal-jobs"></a>Ayuda a los candidatos internos a explorar trabajos internos
Se ha corregido un problema por el que los candidatos externos podían ver el nombre del reclutador o director de contratación de un empleo. Ahora sólo los candidatos internos pueden ver los miembros del equipo de contratación de un trabajo. También es más fácil para los candidatos internos ver y solicitar trabajos internos. Cuando un candidato intente tener acceso al vínculo para ver o solicitar un trabajo solo interno, se le obligará a autenticarse con las credenciales Azure Active Directory. Los candidatos internos también tienen la capacidad de ponerse en contacto con el miembro del equipo de contratación para expresar interés u obtener más información sobre el trabajo. Esta capacidad está disponible para todos los trabajos que son solo para los candidatos internos. Para obtener más información, consulte [Funcionalidad del sitio de carreras en Attract](./career-site.md).

### <a name="designate-silver-medalists-to-assign-high-value-applicants-for-future-positions"></a>Designar a los medallistas de plata para asignar a los candidatos de alto valor para puestos futuros.
Los reclutadores y los administradores de contratación conservan una lista actualizada de las solicitudes que encajaban bien en el puesto pero no podían hacer una oferta porque el puesto ya estaba ocupado. Tales candidatos, llamados los medallistas de plata, son valiosos ya que permiten reducir el tiempo de contratación la próxima vez que aparezca un puesto similar. Attract ahora permite a reclutadores y los administradores de contratación seleccionar a los medallistas de plata entre los candidatos si el candidato llega a la etapa de la oferta. La designación de medallista de plata aparecerá en la lista de candidatos para el trabajo, pero también en la vista de la reserva de talentos cuando estos candidatos sean miembros del conjunto de un reclutador o director de contratación. Además, la designación aparecerá en el historial de empleo como parte del perfil de la reserva de talento de un candidato. Puede obtener una vista previa de esta característica haciendo que un administrador la active usando [Administración de funciones en el centro de administración](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature)uso.

### <a name="add-applicants-to-talent-pools"></a>Agregar candidatos a grupos de talento
Ahora es más fácil agregar candidatos a las reservas de talento mediante una nueva acción en la lista de candidatos. Si selecciona el icono **Agregar a la reserva de talentos** , el reclutador o administrador de contratación puede elegir desde su lista de reservas de talento y agregar fácilmente a candidatos a las reservas de talentos correctas desde la lista de candidatos en un trabajo.

### <a name="configure-whether-a-resume-is-required-to-apply-for-a-particular-job"></a>Configurar si se requiere un currículum para solicitar un trabajo determinado
Según los comentarios de los clientes, los reclutadores podrán configurar si un currículum, en forma de un archivo cargado, es necesario para solicitar un trabajo determinado. Esta configuración es parte de la actividad de la aplicación, accesible en el proceso de contratación. Cuando está habilitada, se le solicitará a cada candidato potencial cargar un currículum cuando solicite este puesto. La solicitud no se considerará completa a menos que se haya cargado un currículum. Esto ayuda a reducir el ruido en la reserva de candidato asegurando que cada candidato proporcione información suficiente para permitir al reclutador evaluarle.

### <a name="candidates-can-apply-to-a-job-using-their-linkedin-profile"></a>Los candidatos pueden solicitar a un trabajo mediante su perfil de LinkedIn
Los candidatos que ya tienen el perfil actual actualizado en LinkedIn pueden solicitar trabajos con solo un solo clic mediante dicho perfil.

### <a name="track-how-a-candidate-profile-originated-in-the-system-and-where-your-applicants-discover-the-jobs-they-applied-for"></a>Sigue cómo un perfil del candidato se originó en el sistema y dónde sus candidatos descubren los trabajos que solicitan
Ahora puede saber cómo se originó el perfil de un candidato concreto en Attract mirando el origen del perfil en los detalles del candidato en la página **Perfil** de un perfil de la solicitud o de la reserva de talentos. De forma similar, puede saber cómo cualquier candidato ha descubierto el trabajo mirando el origen de la solicitud que se proporciona en **Actividad de la solicitud** en la fuente de la actividad de la solicitud. Esta información también está disponible en el historial de trabajo en el perfil de reserva de talentos. Cuando los reclutadores o gerentes de contratación agregan candidatos manualmente, también se les solicitará designar el origen de la solicitud o del perfil del candidato. Cuando un candidato hace una solicitud por primera vez, el origen del perfil será el mismo que el origen de la solicitud. Puede obtener una vista previa de esta característica haciendo que un administrador la active usando [Administración de funciones en el centro de administración](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature)uso. Tenga en cuenta que los candidatos y candidatos existentes no tendrán ninguna información de origen. Sin embargo, los reclutadores pueden agregar la información manualmente.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia del Dynamics 365 Talent: Onboard

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2195

### <a name="attract-integration-throws-duplicate-record-error-for-applications"></a>La integración de Attract muestra el error de registro duplicado para Solicitudes
En la actualización, se ha corregido un problema con los registros duplicados. El problema aparecía al abrir el espacio de trabajo **Dirección de personal**.

### <a name="unable-to-close-form-when-editing-name-sequence"></a>Incapaz de cerrar formulario al editar secuencia de nombre
Se han realizado cambios para corregir un problema al editar la secuencia de nombre en el formulario del trabajador.

## <a name="coming-soon"></a>Próximamente

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Seguridad de compensación avanzada (fija y variable)
En muchas organizaciones, los administradores de compensación y prestaciones solo pueden tener acceso a ciertos registros de compensación. Estos puede ser para ejecutivos o empleados regionales. Con este cambio, Recursos Humanos puede administrar y mantener los planes de compensación para distintos grupos de empleados en la organización. Puede asignar roles de seguridad a los planes fijos y variables, lo que determinará el acceso a los planes y los datos del empleado relacionados con los planes, como el salario y los registros de bonificaciones. Solo los roles con acceso concedido pueden procesar la compensación para estos empleados.

###  <a name="email-support-for-alerts"></a>Soporte de correo electrónico para avisos
Con Platform update 24, los usuarios pueden crear reglas de alertas que envían notificaciones por correo electrónico a los contactos cuando se activen con un evento.

### <a name="duplicate-employee-check-interface-changes"></a>Comprobación de empleado duplicado: cambios en la interfaz
Con este cambio, se detectan los duplicados a medida que se especifican los campos de nombre, y un estado muestra el número de duplicados encontrado. Puede seleccionar el vínculo proporcionado para abrir una nueva página para evaluar si utilizar la coincidencia detectada. Para evitar interrumpir la entrada de datos, el formulario de los duplicados no se abre automáticamente.


