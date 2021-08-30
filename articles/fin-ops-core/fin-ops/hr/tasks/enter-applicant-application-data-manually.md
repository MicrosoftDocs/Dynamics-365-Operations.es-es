---
title: Especificar los datos del candidato y de la solicitud manualmente
description: Este procedimiento muestra cómo mantener manualmente la información de los candidatos y sus solicitudes.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52805c56ed5be13c9e940cf887ece55487060539c0cae97ae5a1bcecd491fbcb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712518"
---
# <a name="enter-applicant-and-application-data-manually"></a>Especificar los datos del candidato y de la solicitud manualmente

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo mantener manualmente la información de los candidatos y sus solicitudes.   Puede especificar y mantener información personal, fechas y horas de entrevistas, referencias, capacidades y los solicitudes de alojamiento de los candidatos. También puede actualizar el estado de las solicitudes de empleo de los candidatos y crear cartas o mensajes de correo electrónico para comunicarse con ellos. Al crear un registro de candidato, se creará un registro de la persona para dicho candidato en la libreta de direcciones global.       La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-a-new-applicant-record"></a>Creación de un nuevo registro de candidato nuevo
1. Vaya a Recursos humanos > Contratación > Candidatos > Candidatos.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el campo Apellidos, escriba un valor.
    * Puede especificar información adicional del candidato, si disponible de ella. Por ejemplo, su cualificación más alta, su puesto actual de trabajo o su empleador anterior.  
5. Expanda la sección Información de contacto.
6. Haga clic en Agregar.
7. En el campo Descripción, escriba "Correo electrónico de comunicación".
8. En el campo Tipo, seleccione una opción.
9. En el campo Dirección y número de contacto, escriba un valor.
    * Esta dirección de correo electrónico se usará para generar la comunicación por correo electrónico con el candidato.  
10. Haga clic en Agregar.
11. En el campo Descripción, escriba un valor.
12. En el campo Dirección y número de contacto, escriba un valor.
    * Información personal del candidato.  
    * Puede especificar otra información personal para el candidato, si fuera necesario. Por ejemplo, la fecha de nacimiento, el origen étnico, el sexo o el estado civil.  
13. En el panel de acciones, haga clic en Competencias.
    * Puede especificar el perfil de competencia del candidato, como sus aptitudes, su experiencia profesional, su formación, exámenes o certificados.  
    * Esta información se puede usar para asignar las aptitudes del candidato a las aptitudes asociadas con los trabajos definidos en los datos de su empresa.   

## <a name="create-an-application-for-the-applicant"></a>Creación de una solicitud para el candidato
1. Haga clic en Solicitudes.
2. Haga clic en Nuevo.
3. En el campo Proyecto de contratación, haga clic en el botón desplegable para abrir la búsqueda.
    * Al seleccionar un proyecto de contratación, se asociará al candidato con una vacante específica incluida en dicho proyecto de contratación.  
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
    * De forma predeterminada, el trabajo y el departamento se basan en el proyecto de contratación seleccionado.  
6. Haga clic en Guardar.
    * Tras guardar la solicitud, puede adjuntarle documentos, incluida la experiencia del candidato, los títulos y una carta de presentación.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]