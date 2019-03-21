---
title: La funcionalidad del sitio de Proyectos profesionales en Attract
description: Este tema proporciona una visión general de la funcionalidad del sitio de Proyectos profesionales para el candidato en Attract
author: josaw1
manager: AnnBe
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 087ab4034a1e601e7f3514c77d56ef54b0c5c52d
ms.sourcegitcommit: 1ee613a88edddab036d145f27f19d071a4b8ad24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "389984"
---
# <a name="career-site-functionality-in-attract"></a>La funcionalidad del sitio de Proyectos profesionales en Attract

[!include[banner](../includes/banner.md)]

Este tema proporciona una visión general de la funcionalidad del sitio de Proyectos profesionales para el candidato en Microsoft Dynamics 365 for Talent: Attract También se explica cómo configurar esta funcionalidad.

Attract ofrece un sitio de desarrollo profesional para cada entorno de inquilino. Por ejemplo, si una organización tiene un entorno de desarrollo y un entorno de prueba, un sitio de Proyectos profesionales se aprovisiona para el entorno de desarrollo, y otro sitio de Proyectos profesionales se aprovisiona para el entorno de prueba. Cada sitio de Proyectos profesionales está aislado completamente y tiene su propio mecanismo de autenticación. Los trabajos y los perfiles del candidato no se comparten entre los sitios de Proyectos profesionales.

De forma predeterminada, el sitio de proyectos profesionales es público. Por lo tanto, los candidatos pueden ver todos los trabajos que están marcados como externos sin tener que iniciar sesión. Sin embargo, el resto de las acciones requieren que los candidatos inicien sesión.

## <a name="career-site-management"></a>Gestión del sitio de desarrollo profesional

Para establecer los valores para los siguientes elementos, inicie sesión en Attract como administrador, seleccione **Centro de administración** en el menú **Parámetros** (el símbolo de engranaje), y seleccione la pestaña **Información de la empresa**.

-   **Nombre de la organización:** El nombre de la organización aparece en la barra de navegación en la parte superior del sitio de Proyectos profesionales. Mediante la selección del nombre de la organización, los candidatos van a una página que enumera las vacantes.

-   **Logotipo de la organización:** Una imagen del logotipo de la organización aparece en la parte superior izquierda del sitio de Proyectos profesionales. Mediante la selección de la imagen del logotipo, los candidatos van a una página que enumera las vacantes.

    >   [!NOTE] 
    >   La imagen del logotipo que aparece en el sitio de Proyectos profesionales tiene un altitud fija de 20 píxeles (px). La imagen que agrega en el centro de gestión se escala para caber. Por lo tanto, en función de la imagen, el ancho puede cambiar.
 
Para establecer los valores para los siguientes elementos, inicie sesión en Attract como administrador, seleccione **Centro de administración** en el menú **Parámetros** (el símbolo de engranaje), y seleccione la pestaña **Gestión del sitio de desarrollo profesional**.

-   **Optimización del motor de búsqueda** - Cuando está habilitado, todos los trabajos públicos publicados en el sitio de Proyectos profesionales de Attract se podrán buscar mediante motores de búsqueda como Bing y Google.

    >   [!NOTE] 
    >   Es posible que haya un retraso entre activar este valor y buscar los resultados que aparecen, en función del motor de búsqueda que esté usando.
         
## <a name="career-site-urls"></a>URL del sitio de desarrollo profesional

La lista siguiente contiene direcciones URL de uso general del sitio de Proyectos profesionales y cómo acceder a ellas.

-   **Dirección URL de la página principal del sitio de la Proyectos profesionales** - Para ver la dirección URL de la página principal del sitio de Proyectos profesionales, inicie sesión en Attract como administrador, seleccione **Centro de administración** , en el menú **Valores** , y seleccione la pestaña **Administración del sitio de desarrollo profesional** .

-   **URL de solicitud de publicación de trabajo individual** - Cuando [publica un trabajo externo](Creating-jobs-Attract.md#postings) por primera vez, puede copiar el vínculo **Solicitar** de la aplicación Attract. La dirección URL para este vínculo estará en el formato siguiente: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)

-   **Dirección URL de publicación de trabajo individual** - La dirección URL del trabajo es una subcadena de la dirección URL de solicitud. Incluye todo hasta el número de trabajo. Por lo tanto, para la dirección URL de solicitud anterior, la dirección URL de publicación de trabajo es [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)

## <a name="authentication-options"></a>Opciones de autenticación

Los candidatos tienen las siguientes opciones de inicio de sesión para un sitio de Proyectos profesionales de Attract:

-   Cuenta personal:

    -   LinkedIn

    -   Microsoft

    -   Google

    -   Facebook

-   Cuenta del trabajo o del centro educativo:

    -   Microsoft Azure Active Directory (Azure AD)

El inicio de sesión de Azure AD es solo para candidatos internos. Por lo tanto, solo funciona para candidatos internos que usan las credenciales de Azure AD de la empresa. Por ejemplo, un candidato que está actualmente empleado en Contoso Ltd quiere solicitar un trabajo en una empresa sin relación con la suya, Alpine Ski House. En este caso, el inicio de sesión no tendrá éxito si el empleado intenta usar sus credenciales de Azure AD de Contoso Ltd.

## <a name="create-and-maintain-a-profile"></a>Creación y mantenimiento de un perfil

Una vez que los candidatos hana iniciado sesión en el sitio de Proyectos profesionales, pueden seleccionar **Mi perfil** en la barra de navegación en la parte superior de la página para crear y mantener su perfil.
El perfil incluye información personal, información sobre la experiencia profesional, detalles de formación, documentos, vínculos, e información acerca de habilidades. Una vez que se ha creado un perfil, se puede usar para solicitar trabajos en los que el candidato está interesado. Los perfiles también ayudan a Attract a recomendar los trabajos adecuados para los candidatos.

>   [!NOTE]
>   Si un candidato utiliza un identificador de correo electrónico para iniciar sesión mediante uno de los proveedores de autenticación enumerados anteriormente, ese identificador de correo electrónico predeterminado será el identificador de correo electrónico del contacto asociado al perfil. Sin embargo, este último se puede cambiar en cualquier momento y es completamente independiente del anterior. Attract siempre utilizará el identificador de correo electrónico del contacto para asociarlo con su perfil para todas las comunicaciones de correo electrónico.

## <a name="find-the-right-job"></a>Encuentre el trabajo correcto

En la página de la lista de trabajos, los candidatos pueden buscar un trabajo específico especificando términos de búsqueda. La funcionalidad de búsqueda busca los términos de búsqueda en los puestos y descripciones de trabajos, y muestra los trabajos apropiados como resultados. Los candidatos pueden filtrar los resultados en cualquier momento, en función de la ubicación del trabajo o la función de trabajo.

Los candidatos también pueden ver un conjunto de trabajos que se recomiendan en el sitio de Proyectos profesionales. Los trabajos que se recomiendan a un candidato se basan en las solicitudes, perfil, y curriculums vitae anteriores del candidato.

>   [!NOTE] 
>   Se muestran las recomendaciones de trabajo si al menos hay 10 trabajos publicados en el sitio de Proyectos profesionales, y si el candidato ha completado su perfil.

## <a name="apply-for-jobs"></a>Solicitud de trabajos

Una vez que los candidatos encuentren el trabajo correcto, pueden solicitar el trabajo mediante el botón **Solicitar** en la página de **detalles del trabajo**. En este punto, los candidatos pueden crear un perfil nuevo o revisar la información en su perfil existente.
Los candidatos también pueden cargar un currículum, según convenga, y después enviar la solicitud de trabajo.

## <a name="check-application-status"></a>Comprobar el estado de la solicitud

Una vez que los candidatos hayan solicitado uno o más trabajos, pueden seleccionar **Solicitudes** en la barra de navegación en la parte superior de la página para ver sus solicitudes abiertas y cerradas. Cuando los candidatos abren una de sus solicitudes, ven la etapa actual y las acciones pendientes que deben completar. Por ejemplo, si un candidato debe proporcionar fechas potenciales para entrevistas personales, la página muestra sus opciones disponibles.

## <a name="internal-jobs"></a>Trabajos internos

Actualmente, los trabajos marcados como internos y enviados al sitio de Proyectos profesionales de Attract no aparecen en el sitio de Proyectos profesionales. Son solo accesibles a través de la dirección URL **Solicitar** directa que puede ser copiada desde la aplicación Attract.
