---
title: Abastecimiento con LinkedIn Recruiter
description: Este tema proporciona información sobre el uso del aprendizaje automático para obtener recomendaciones del trabajo y del candidato de trabajo.
author: andreabichsel
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 4ac7a302e5bf589beb2b560b0ff5818e90c67139
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "859583"
---
# <a name="sourcing-with-linkedin-recruiter"></a>Abastecimiento con LinkedIn Recruiter
[!include[banner](../includes/banner.md)]

LinkedIn es la base de datos más grande del mundo y a menudo el principal sistema que los reclutadores utilizan para buscar candidatos, comunicarse con ellos y conseguir candidatos para trabajos que los reclutadores quieren cubrir. La integración de LinkedIn Recruiter con Dynamics 365 for Talent: Attract facilita que los usuarios empleen, y conserven los datos en sincronización entre los dos sistemas.

> [!NOTE]
> Necesita el complemento de contratación completa y asientos de LinkedIn Recruiter para poder usar la integración de LinkedIn Recruiter con Attract.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Configurar LinkedIn Recruiter con Attract 

Para poder usar las capacidades de LinkedIn Recruiter, primero debe configurar el acceso de nivel de contrato o de nivel de empresa con su instancia de Attract. Para completar el proceso de configuración, debe trabajar con el usuario que es un administrador en su contrato de LinkedIn Recruiter. Realice los pasos siguientes para configurar LinkedIn Recruiter con Attract.

1.  Inicie sesión en Attract como administrador y vaya a **Configuración de administrador**.

2.  En el panel izquierdo, haga clic en la pestaña **Integración de LinkedIn**.

[![Vista de administrador de Attract para iniciar la integración de LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3.  Haga clic en **Conectar** para iniciar la configuración y obtener orientación durante el proceso de inicio de sesión en LinkedIn.

4.  Si tiene usuarios en varios contratos de LinkedIn, seleccione el contrato que desea conectar al sistema de Attract. Si tiene un usuario solo en un contrato de LinkedIn, este paso no será necesario.

5.  El widget de LinkedIn ahora se cargará en la configuración de administrado con la lista de integraciones mostrada. En **Sistema de reclutador conectar**, haga clic en **Solicitar**.

[![Vista de administrador de Attract para solicitar la integración de LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6.  Después de que se solicite la integración desde Attract, se mostrará como **Listo para socios** y estará listo para activarse desde **Configuración de gestión de reclutador**. Si ve **Notificar al socio** en esta página, espere unos segundos, haga clic en **Notificar al socio**, y actualice la página. Debe ahora mostrarse como **Listo para socios**.

[![Vista de gestión de Attract para indicar que el lado de Attract de las solicitudes se ha realizado](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

Para completar el paso siguiente, debe tener un privilegio de administración en su contrato de LinkedIn Recruiter.

7.  Inicie sesión en LinkedIn mediante la cuenta de administración y vaya al LinkedIn Recruiter en la parte superior derecha. 

8. En el menú **Más** en la parte superior de la pantalla, haga clic en **Valores de administración**, y haga clic en la pestaña **ATS** .

El sistema de Attract se mostrará con un par de opciones que se pueden activar.

9. Si desea permitir solo una exportación en 1 clic para el **Indicador en ATS** y el **Widget del perfil En ATS**, seleccione **Acceso de nivel de empresa**. Si desea habilitar todas las funciones de acceso de nivel de empresa más el historial de InMail, el historial de notas y el acceso de perfil del comprobante de InMail, seleccione **Acceso de nivel de contrato**.

10. Conecte el nivel de acceso deseado desde su configuración **Admin-ATS** de LinkedIn Recruiter.

[![Activar la integración de Attract desde la vista de administración de LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

12. Vuelva a la configuración de gestión de Attract como AttractAdmin y seleccione la pestaña **Integración de LinkedIn**. Ahora debe ver la carga del widget de LinkedIn mostrando **Habilitado** con el nivel de acceso seleccionado activado.

[![Integración de LinkedIn Recruiter completa](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="using-linkedin-recruiter-capabilities"></a>Usar las capacidades de LinkedIn Recruiter

Después de que las capacidades de LinkedIn Recruiter hayan sido habilitadas por el administrador de Attract, están disponibles para que los administradores y los reclutadores de contratación puedan acceder a ellas. Para usar estas capacidades, conecte su cuenta de LinkedIn en **Configuración del usuario**. Varias capacidades estarán disponibles después de que se hayan conectado la configuración de gestión y de usuario.

### <a name="in-ats-profile-widget"></a>Widget del perfil En ATS

Puede ver el perfil de LinkedIn del candidato en Attract. El widget de LinkedIn mostrará el perfil del candidato cuando la información de ATS coincida con la información de LinkedIn de sus usuarios.

Para ver un perfil, vaya el perfil del candidato desde un trabajo o un grupo de talentos. En el perfil del candidato, seleccione la pestaña **LinkedIn** y el widget del perfil se cargará. También puede guardar el candidato en sus proyectos de LinkedIn Recruiter en esta página.
1. Si LinkedIn ha encontrado la coincidencia basándose en el correo electrónico y el ID de miembro de LinkedIn (coincidencia exacta), el perfil del candidato se mostrará. El usuario aún le queda una opción para vincular/desvincular el perfil.

2. Si LinkedIn no puede encontrar el candidato basándose en su correo electrónico o el Id de miembro, se mostrará una lista de coincidencias de posibles de candidatos basadas en el nombre del candidato y el usuario puede elegir a uno de ellos y vincular el perfil.  

3. Si LinkedIn no puede encontrar ningún candidato basándose en el nombre, indicará que no se han encontrado ninguna coincidencia.

### <a name="1-click-export"></a>Exportación en 1 clic 

Mientras busca candidatos en LinkedIn, puede exportar el candidato en 1 clic a los trabajos que tiene ahora vacantes. Realice los pasos siguientes para una exportación en 1 clic. Para completar estos pasos, compruebe que se le asigne el rol de administrador de contratación o de reclutador para el trabajo y que el trabajo esté en la etapa **cliente potencial**.

1.  Cree el trabajo, asigne los roles adecuados, y active el trabajo.

2.  Cuando se activa el trabajo, desplácese hasta LinkedIn Recruiter.

3.  Encuentre el candidato que está buscando y vaya a su perfil.

4.  Usando el cuadro de búsqueda de la tarjeta de contacto, busque el trabajo mediante el título o el identificador de trabajo que se ha activado en Attract. Si no encuentra el trabajo, haga clic en **Cambiar ATS** para encontrar la instancia de Attract correcta.

5. Tras seleccionar el trabajo, haga clic en **Exportar**. Ahora Attract obtiene al candidato.

6.  Vaya a Attract y abra el trabajo respectivo. Puede encontrar el candidato que acaba de exportar en la etapa **cliente potencial** del trabajo.

### <a name="in-ats-indicator"></a>Indicador en la solicitud de presupuesto 

Usando LinkedIn Recruiter, puede saber si un candidato ha solicitado otros trabajos en su organización, ver en qué etapa están de la solicitud de trabajo y consultar comentarios de Attract en LinkedIn Recruiter.

1.  Abra LinkedIn Recruiter y encuentre el perfil del candidato que busca.

2.  Trasládese hacia abajo para ver la sección **En-ATS** en el perfil del candidato.

3.  Puede usar este widget para ver toda la información sobre el candidato que se encuentra en Attract desde la vista de LinkedIn Recruiter.

4.  Seleccione la pestaña **Trabajos y estados** para ver los trabajos de los que forman parte, el último estado, y cómo han avanzado en cada trabajo.

5.  Seleccione la pestaña **Comentarios sobre la entrevista** para consultar los comentarios que los entrevistadores han registrado en Attract.

6.  Seleccione la pestaña **Notas** para ver las notas que se han capturado para este candidato en Attract.

> [!NOTE]
> El candidato y los datos de la aplicación no se sincronizarán con el LinkedIn Recruiter si el candidato no ha pasado de la etapa de candidato.

### <a name="inmail-history"></a>Historial de InMail

El historial de LinkedIn InMail está disponibles con acceso de nivel de contrato con LinkedIn Recruiter. Cuando se habilita, puede ver el historial completo de InMail con el candidato. También puede ver quién más de su organización ha intercambiado InMail con el candidato, aunque no puede ver los mensajes intercambiados entre ellos.

Para ver el historial de InMail, vaya al perfil de un candidato, vaya a la ficha **LinkedIn** y desplácese a la parte inferior de la página para ver el historial. Puede ver el historial de InMail si ha tenido una conversación con el candidato. Los mensajes de InMail se sincronizarán con Attract cada par de horas.

### <a name="notes-history"></a>Historial de notas 

El historial de notas de LinkedIn está disponibles con acceso de nivel de contrato con LinkedIn Recruiter. Cuando se habilitan, puede ver las notas sobre el candidato que han sido capturadas por varios reclutadores de su organización.

Para ver el historial de notas, vaya al perfil de un candidato, vaya a la ficha **LinkedIn** y desplácese a la parte inferior de la página para ver el historial. Puede ver todas las notas sobre el candidato desde LinkedIn Recruiter.

### <a name="inmail-stub-profile"></a>Perfil comprobante de InMail

El perfil del comprobante de InMail está disponible con acceso de nivel de contrato con LinkedIn Recruiter. Si los candidatos aceptan compartir sus perfiles de LinkedIn con cualquier usuario de su organización, puede realizar el seguimiento de los candidatos en Attract y se creará un registro de candidato nuevo para cada candidato. Puede ver la dirección de correo electrónico del candidato si el candidato ya existe en el sistema con una dirección de correo electrónico o ha elegido compartir la dirección con el reclutador.

Para ver la lista de candidatos, vaya a **Grupos de talentos** para ver un grupo de talentos de LinkedIn creado por el sistema. Este grupo de talentos contiene la lista de candidatos y sus perfiles de comprobante tal y como se recibieron de LinkedIn, donde se muestra el nombre del candidato y sus apellidos. El identificador de correo electrónico del candidato se mostrará si el candidato había elegido compartir su dirección de correo electrónico.
