---
title: Especificar los datos del candidato y de la solicitud manualmente
description: Este procedimiento muestra cómo mantener manualmente la información de los candidatos y sus solicitudes.
author: twheeloc
ms.date: 01/10/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a00e20569f05730296ef611938a94b73ebb7f6f5
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735329"
---
# <a name="enter-applicant-and-application-data-manually"></a>Especificar los datos del candidato y de la solicitud manualmente

> [!NOTE]
> La funcionalidad de contratación en este tema se denominará Proyectos de contratación y se centra en los solicitantes, las solicitudes y los proyectos de contratación.  


Este procedimiento muestra cómo mantener manualmente la información de los candidatos y sus solicitudes. Puede especificar y mantener información personal, fechas y horas de entrevistas, referencias, capacidades y los solicitudes de alojamiento de los candidatos. También puede actualizar el estado de las solicitudes de empleo de los candidatos y crear cartas o mensajes de correo electrónico para comunicarse con ellos. Al crear un registro de candidato, se creará un registro de la persona para dicho candidato en la libreta de direcciones global. Para crear este procedimiento se utiliza la empresa de datos de prueba **USMF**.

## <a name="create-a-new-applicant-record"></a>Creación de un nuevo registro de candidato nuevo

1. Vaya a **Recursos humanos \> Contratación \> Candidatos \> Candidatos**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, escriba un valor.
4. En el campo **Apellido**, escriba un valor.

    Puede especificar información adicional del candidato, si disponible de ella. Por ejemplo, su cualificación más alta, su puesto actual de trabajo o su empleador anterior.

5. Expanda la sección **Información de contacto**.
6. Seleccione **Agregar**.
7. En el campo **Descripción**, escriba **Correo electrónico de comunicación**.
8. En el campo **Tipo**, seleccione una opción.
9. En el campo **Dirección y número de contacto**, escriba un valor.

    Esta dirección de correo electrónico se usará para generar la comunicación por correo electrónico con el candidato.

10. Seleccione **Agregar**.
11. En el campo **Descripción**, especifique un valor.
12. En el campo **Dirección y número de contacto**, escriba un valor.

    Utilice este campo para introducir información personal adicional sobre el candidato, según sea necesario. Por ejemplo, la fecha de nacimiento, el origen étnico, el sexo o el estado civil del candidato.

13. En el panel de acciones, seleccione **Competencias**.

    Puede especificar el perfil de competencia del candidato, como sus aptitudes, su experiencia profesional, su formación, exámenes o certificados. Esta información se puede usar para asignar las aptitudes del candidato a las aptitudes asociadas con los trabajos definidos en los datos de su empresa.

## <a name="create-an-application-for-the-applicant"></a>Creación de una solicitud para el candidato

1. Seleccione **Solicitudes**.
2. Seleccione **Nuevo**.
3. En el campo **Proyecto de contratación**, seleccione la flecha desplegable para abrir la búsqueda.

    Al seleccionar un proyecto de contratación, se asegura de que se asocie al candidato con una vacante específica incluida en dicho proyecto de contratación.

4. En la lista, busque y seleccione el registro deseado.
5. En la lista, seleccione el vínculo de la fila seleccionada.

    De forma predeterminada, el trabajo y el departamento se basan en el proyecto de contratación seleccionado.

6. Seleccione **Guardar**.

    Después de guardar la solicitud, puede adjuntar documentos. Estos documentos pueden incluir la experiencia, los premios y la carta de presentación del solicitante.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
