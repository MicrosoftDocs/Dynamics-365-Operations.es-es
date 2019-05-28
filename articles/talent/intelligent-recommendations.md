---
title: Recomendaciones inteligentes
description: Este tema explica cómo se puede usar el aprendizaje automático para proporcionar recomendaciones para los trabajos y los candidatos de trabajo.
author: andreabichsel
manager: AnnBe
ms.date: 03/25/2019
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
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: fb31b413cfe3cd168bbb12ce6070325ff5f736da
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519009"
---
# <a name="intelligent-recommendations"></a>Recomendaciones inteligentes

[!include[banner](../includes/banner.md)]

El aprendizaje automático puede ayudar reclutadores y a los administradores de contratación a identificar rápidamente a los candidatos mejor situados para un puesto. También puede ayudar a los candidatos viables a encontrar el puesto que mejor se adapta a su perfil e intereses. A medida que se usan estas características, y se proporcionan valoraciones, las recomendaciones mejorarán.

> [!NOTE] 
> - Las características de recomendación inteligente solo están disponibles con el [Complemento de contratación completa](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - La funcionalidad de la que se habla en este tema esta disponible como parte de una versión preliminar. El contenido y la funcionalidad están sujetos a cambios. Para utilizar esta función, pida que un administrador la active usando la **Configuración de administración** en Attract. Establezca **Recomendación del candidato**, **Recomendación de trabajo**, y **Recomendación del candidato** a **Activado**. Para obtener más información, consulte [Acceder a las características de vista previa en Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature). 


## <a name="candidate-recommendations"></a>Recomendaciones de candidatos

Dado que las propuestas de empleo pueden atraer a cientos de candidatos, puede resultar difícil para que los reclutadores y los responsables de contratación encuentren candidatos cuyos aptitudes e historial son los requeridos para el puesto. Al analizar la correlación entre la descripción del trabajo y los requisitos, y los datos de curriculums vitae y de los perfiles de los candidatos, se puede usar el aprendizaje automático para genearr recomendaciones del candidato. Las recomendaciones de candidatos pueden ayudar reclutadores y a los administradores de contratación a identificar los talentos mejor situados y a moverlos a la etapa de la entrevista con más rapidez. Para cualquier trabajo, si hay más de diez candidatos o candidatos potenciales que tienen curriculums vitae o perfiles completos, los candidatos o candidatos viables que mejor cumplan los requisitos de trabajo aparecen en la sección **Candidatos a tener en cuenta** en la página **Trabajo**.

Para cualquier candidato recomendado, puede seleccionar **Ver candidato** en la tarjeta del candidato para revisar el perfil del candidato y actuar en su solicitud. Puede usar el botón de puntos suspensivos (**...**) para abrir el perfil del candidato en una nueva ficha. Puede usar puntos suspensivos para proporcionar valoraciones acerca de la recomendación. De esta manera, puede ayudar a ajustar el motor de recomendación y a mejorar las recomendaciones futuras. Cualquier recomendación que no le guste se eliminará de la sección **Candidatos a tener en cuenta** al actualizar la página **Trabajo**. Puede usar la tarjeta de valoración para indicar por qué no encontró la recomendación útil.

## <a name="job-recommendations"></a>Recomendación de trabajos 

Cuando un empleado potencial utiliza el sitio de Proyectos profesionales para solicitar un trabajo, Attract recomienda otros puestos vacantes en la organización. Estas recomendaciones se basan en las solicitudes anteriores del cliente viable y en su currículum o perfil del candidato. Por lo tanto, las recomendaciones de trabajo ayudan a los candidatos viables a identificar rápidamente los trabajos que se ajusten mejor a ellos. Las recomendaciones de trabajo se ofrecen a los clientes viables si hay más de diez trabajos publicados en el sitio de Proyectos profesionales. Los candidatos potenciales pueden abrir los detalles de una oferta de empleo desde la tarjeta de recomendación. También pueden proporcionar comentarios sobre una recomendación para ayudar a mejorar las recomendaciones futuras.

## <a name="prospect-recommendations"></a>Recomendaciones de candidato 

Cuando un puesto nuevo está disponible, revisar todos los últimos candidatos y su red de talento completa puede llevar tiempo. Para que Attract le ayude a hacer esto, puede usar algoritmos de aprendizaje automático. Esto significa que Attract revisa todos los candidatos y sugiere a aquellos que son una buena coincidencia tan pronto como cree el trabajo. Para ver estas recomendaciones, active la fase **Candidato** para el trabajo. Puede tardar hasta un minuto para que Attract digitalice toda la base de datos de candidatos para hacer recomendaciones.

Las recomendaciones aparecen como tarjetas en la pestaña **Candidatos** de los trabajos que tengan la fase **Candidato** activada. Estas tarjetas enumeran las aptitudes que se encuentran en el perfil de candidatos, junto con cualquier información de la calificación de la formación. Si encuentra una recomendación que le interese, puede agregar al candidato como posible candidato para el trabajo.

> [!NOTE]
> Si ha empezado a usar Attract recientemente, deberá esperar a tener 10 o más candidatos con perfiles completos o curriculums vitae antes de que pueda usar esta capacidad.

Para evitar cualquier prejuicio potencial en las recomendaciones, Attract solo analiza los perfiles del candidato según aptitudes, las cualificaciones y otras palabras clave que coinciden con la descripción del trabajo. Además, antes de la evaluación, Attract elimina la información personal que podría identificar al candidato de los perfiles.
