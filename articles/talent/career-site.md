---
title: La funcionalidad del sitio de Proyectos profesionales en Attract
description: "Este artículo proporciona una visión general de la funcionalidad del sitio de Proyectos profesionales de candidatos en Microsoft Dynamics 365 for Talent - Attract. También se explica cómo configurar esta funcionalidad."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: es-es
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a>La funcionalidad del sitio de Proyectos profesionales en Attract

[!include [banner](includes/banner.md)]

Este artículo proporciona una visión general de la funcionalidad del sitio de Proyectos profesionales de candidatos en Microsoft Dynamics 365 for Talent: Attract. También se explica cómo configurar esta funcionalidad.

## <a name="overview"></a>Información general

Attract ofrece un sitio de Proyectos profesionales para cada entorno de inquilino. Por ejemplo, si una organización tiene un entorno de desarrollo y un entorno de prueba, un sitio de Proyectos profesionales se aprovisiona para el entorno de desarrollo, y otro sitio de Proyectos profesionales se aprovisiona para el entorno de prueba. Cada sitio de Proyectos profesionales es **aislado completamente** y tiene su propio mecanismo de autenticación. Los trabajos y los perfiles del candidato no se comparten entre los sitios de la Proyectos profesionales.

De forma predeterminada, el sitio de la Proyectos profesionales es público. Por lo tanto, los candidatos pueden ver todos los trabajos que están marcados como externos sin tener que iniciar sesión. Sin embargo, el resto de las acciones requieren que los candidatos inicien sesión.

## <a name="career-site-management"></a>Gestión del sitio de desarrollo profesional

Los siguientes elementos en el sitio de la Proyectos profesionales son controlados mediante la configuración:

- **Nombre de la organización:** El nombre de la organización aparece en la barra de navegación en la parte superior del sitio de Proyectos profesionales. Mediante la selección del nombre de la organización, los candidatos van a una página que enumera las vacantes.
- **Logotipo de la organización:** Una imagen del logotipo de la organización aparece en la parte superior izquierda del sitio de Proyectos profesionales. Mediante la selección de la imagen del logotipo, los candidatos van a una página que enumera las vacantes.

Para establecer los valores para el nombre y el logotipo de la organización, inicie sesión en Attract como administrador, seleccione **Centro de administración** en el menú **Parámetros** (el símbolo de engranaje), y seleccione la pestaña **Información de la empresa**.

> [!NOTE]
> La imagen del logotipo que aparece en el sitio de Proyectos profesionales tiene un altitud fija de 20 píxeles (px). La imagen que agrega en el centro de gestión se escala para caber. Por lo tanto, en función de la imagen, el ancho puede cambiar.

## <a name="career-site-url"></a>URL del sitio de desarrollo profesional

Al [registrar un trabajo externo](./Creating-jobs-Attract.md#postings) por primera vez, puede copiar el vínculo **Solicitar** de la aplicación Attract. La dirección URL para este vínculo estará en el formato siguiente: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`

La dirección URL del sitio de Proyectos profesionales es una subcadena de la dirección URL **Solicitar**. Incluye todo hasta el nombre de la empresa. Por lo tanto, para la dirección URL **Solicitar** anterior, la dirección URL del sitio de Proyectos profesionales is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.

## <a name="authentication-options"></a>Opciones de autenticación

Los candidatos tienen las siguientes opciones de inicio de sesión para un sitio de Proyectos profesionales de Attract:

- Cuenta personal:

    - LinkedIn
    - Microsoft
    - Google
    - Facebook

- Cuenta del trabajo o del centro educativo:

    - Microsoft Azure Active Directory (Azure AD)

El inicio de sesión de Azure AD es solo para candidatos internos. Por lo tanto, solo funciona para candidatos internos que usan las credenciales de Azure AD de la empresa. Por ejemplo, un candidato que está actualmente empleado en Contoso Ltd quiere solicitar un trabajo en una empresa sin relación con la suya, Alpine Ski House. En este caso, el inicio de sesión no tendrá éxito si el empleado intenta usar sus credenciales de Azure AD de Contoso Ltd.

## <a name="create-and-maintain-a-profile"></a>Creación y mantenimiento de un perfil

Una vez que los candidatos inicien sesión en el sitio de Proyectos profesionales, pueden seleccionar **Mi perfil** en la barra de navegación en la parte superior de la página para crear y mantener su perfil. El perfil incluye información personal, información sobre la experiencia profesional, detalles de formación, documentos, vínculos, e información acerca habilidades. Una vez que se cree un perfil, se puede usar para solicitar trabajos en los que el candidato está interesado. Los perfiles también ayudan a Attract a recomendar los trabajos correctos para los candidatos.

## <a name="find-the-right-job"></a>Encuentre el trabajo correcto

En la página de la lista de trabajos, los candidatos pueden buscar un trabajo específico especificando términos de búsqueda. La funcionalidad de búsqueda busca los términos de búsqueda en los puestos y descripciones de trabajos, y muestra los trabajos apropiados como resultados. Los candidatos pueden filtrar los resultados en cualquier momento, en función de la ubicación del trabajo o la función de trabajo.

Los candidatos también pueden ver un conjunto de trabajos que se recomiendan en el sitio de Proyectos profesionales. Los trabajos que se recomiendan a un candidato se basan en las solicitudes, perfil, y curriculums vitae anteriores del candidato.

> [!NOTE]
> Se muestran las recomendaciones de trabajo si al menos hay 10 trabajos publicados en el sitio de Proyectos profesionales, y si el candidato ha completado su perfil.

## <a name="apply-for-jobs"></a>Solicitud de trabajos

Una vez que los candidatos encuentren el trabajo correcto, pueden solicitar el trabajo mediante el botón **Solicitar** en la página de detalles del trabajo. En este punto, los candidatos pueden crear un perfil nuevo o revisar la información en su perfil existente. Los candidatos también pueden cargar un currículum, según convenga, y después enviar la solicitud de trabajo.

## <a name="check-application-status"></a>Comprobar el estado de la solicitud

Una vez que los candidatos hayan solicitado uno o más trabajos, pueden seleccionar **Solicitudes** en la barra de navegación en la parte superior de la página para ver sus solicitudes abiertas y cerradas. Cuando los candidatos abren una de sus solicitudes, ven la etapa actual y acciones pendientes que deben completar. Por ejemplo, si un candidato debe proporcionar fechas potenciales para entrevistas personales, la página muestra sus opciones.

## <a name="internal-jobs"></a>Trabajos internos

Actualmente, los trabajos marcados como internos y enviados al sitio de Proyectos profesionales de Attract no aparecen en el sitio de Proyectos profesionales. Son accesibles solo a través de la dirección URL **Solicitar** directa que puede ser copiada de la aplicación Attract.

