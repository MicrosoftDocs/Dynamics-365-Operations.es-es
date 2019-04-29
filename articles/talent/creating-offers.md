---
title: Crear, aprobar y firmar propuestas
description: Este tema informa de cómo crear, aprobar, y firmar una propuesta para un candidato mediante Dynamics 365 for Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-19
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8b2b49621624e937bed310c9d3f3193a10b38290
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "859652"
---
# <a name="creating-approving-and-signing-offers"></a>Crear, aprobar y firmar ofertas

[!include[banner](../includes/banner.md)]

En muchos casos, la preparación de un paquete de oferta para un candidato tiene que ser un proceso muy rápido.
Mediante el uso de las plantillas configuradas por el administrador de Attract reducirá el tiempo y el esfuerzo que los creadores necesitan para preparar y enviar las ofertas para un candidato.

## <a name="create-an-offer"></a>Crear una oferta

Cuando está activada la aplicación de administración de la propuesta, cualquier usuario con el rol de administrador o de reclutador de contratación puede preparar un paquete de propuesta para el candidato. Para preparar la oferta, haga lo siguiente.

1.  Desplácese al trabajo y a la solicitud del candidato para el que está creando la propuesta.

1.  Vaya a **Etapa de oferta** y haga clic en **Preparar oferta**.

    Se le redirigirá a la aplicación de la oferta donde puede ver el candidato con el estado **Nuevo**. También puede ver otras ofertas a las que está contribuyendo, como creador o aprobador.

1.  Haga clic en **preparar oferta**. 
    
    Verá una selección de distintos paquetes de oferta que han sido puestos a disposición por el administrador.

1.  Seleccione un paquete y hacen clic en **Listo** para iniciar la preparación de la propuesta.

    Se carga la plantilla de paquete de la oferta con los detalles correspondientes del trabajo y el candidato rellenados en la propuesta.

1.  Todos los marcadores de posición de los datos de la oferta que forman parte del paquete de la propuesta están visibles en la página de destino. Puede rellenar todos los valores del paquete en esta página.

    En la página de destino, también puede ver todas las plantillas de documento de la oferta que forman parte del paquete de la propuesta.

1.  Ahora puede editar el contenido de la propuesta, en función de cómo la plantilla fue configurada por el administrador.

1.  Si necesita eliminar los documentos marcados como no requerido, puede hacerlo.

1. Cuando todos los marcadores de los datos de la propuesta estén rellenados, haga clic en **Guardar** para guardar un borrador de la propuesta.

>[!NOTE]
> Una vez guardado un borrador, puede eliminar el borrador de versión de la propuesta o seleccionar una nueva plantilla del paquete, en caso necesario.


## <a name="approve-an-offer"></a>Aprobar una oferta

La mayoría de las propuestas deben pasar por un proceso de aprobación para asegurarse de que la propuesta cumple con los estándares necesarios. Si una propuesta no cumple con los estándares, por ejemplo si el creador de la propuesta no siguió las reglas de los datos de la propuesta e invalidó los valores de la propuesta, el proceso de aprobación es obligatorio. Para enviar una propuesta para su aprobación, haga lo siguiente.

1.  Cuando la propuesta se encuentra en un estado de borrador, agregue los aprobadores en el **Panel del aprobador**. 
    >[!NOTE]
    > Los administradores de contratación se agregan como aprobador de forma predeterminada. Puede elegir cualquier usuario de su organización como aprobador para la propuesta.

1.  Si es necesario, asigne los aprobadores en un método secuencial de aprobación o un método en paralelo de aprobación. Esta opción solo estará disponible si se ha configurado como tal por el administrador.
    >[!NOTE]
    > Si el proceso de aprobación es secuencial, puede editar la secuencia de aprobadores si es necesario.

1.  Cuando haya acabado de definir la cadena de aprobación, puede editar el contenido del correo electrónico de aprobación y enviar la notificación a los aprobadores. Haga clic en **Enviar a aprobadores**.
    >[!NOTE]
    > Si la propuesta no era estándar, está obligado a proporcionar una justificación.

1.  Si el creador de la propuesta elige omitir a un aprobador, puede especificar una nota e ir al aprobador siguiente.

Los aprobadores recibirán un correo electrónico que les pedirá aprobar la propuesta. Pueden hacer clic en el vínculo del mensaje de correo electrónico para abrir la propuesta, para revisar el paquete completo de la propuesta, y para aprobarlo o devolverlo al creador de la propuesta. Los aprobadores de la propuesta necesitarán agregar una nota adicional si rechazan el paquete de la propuesta para otras ediciones. 

En los casos en que hay una nueva versión de la propuesta creada antes de que actúe el aprobador, este no podrá aprobar o rechazar la propuesta.

## <a name="offer-versioning"></a>Versiones de la oferta 

Una vez aprobada la oferta o devuelta para realizar otras ediciones, puede elegir la opción **Habilitar edición** para crear una nueva versión de la propuesta. La nueva versión de la propuesta tiene todos los valores de los datos de la propuesta y la lista de aprobadores de la última versión. 

Los aprobadores pueden alternar entre diferentes versiones de la propuesta si las versiones fueron compartidas con ellos para obtener su aprobación. Asimismo, un aprobador o un creador de la propuesta puede elegir eliminar una versión específica de la propuesta de borrador para volver al estado anterior.


## <a name="send-an-offer-to-a-candidate"></a>Enviar una oferta a un candidato 

Cuando se haya guardado, aprobado y preparado la propuesta para enviarla al candidato, haga clic en **Enviar al candidato**.

Existen varias acciones que puede realizar antes de enviar la propuesta al candidato.
-  Puede ver la lista de documentos que son parte del paquete de la oferta que se enviará al candidato.

-  Puede especificar una fecha de vencimiento de la propuesta. Se espera que los candidatos acepten o rechacen la propuesta antes de la fecha de vencimiento.  Se enviará el candidato un aviso 48 horas antes de que caduque la propuesta.

-  Puede haber documentos adicionales que desee incluir en el proceso de aceptación de la propuesta. Tendrá la opción de mostrar el tipo de documentos requerido.

- Opción de firma electrónica: Hay dos maneras de conectar el proveedor de firma electrónica de su elección. Vaya a **Configuración de usuario** en **Oferta**. En **Conexiones** conecte con **Adobe Sign** o **DocuSign**. Como alternativa, se le pedirá que conecte la página **Enviar oferta al candidato** si la conexión no se liquidó ya basándose en la configuración del usuario. La cuenta de la firma electrónica solo necesitará conectarse una vez. La misma licencia para usuarios se usa para todos los paquetes futuros de la oferta que envíe el mismo usuario. 

### <a name="adobe-sign"></a>Adobe Sign
Si se ha seleccionado Adobe Sign como método preferido de firma electrónica, los creadores de la propuesta necesitan conectar su licencia de Adobe Sign en este paso. 

### <a name="docusign"></a>DocuSign
Si se ha seleccionado DocuSign como método preferido de firma electrónica, los creadores de la propuesta necesitan conectar su licencia de DocuSign. Cuando haya iniciado sesión, la cuenta predeterminada y los permisos asociados al perfil de DocuSign del usuario se vinculan a Talent Attract. 

-  Puede ver y editar la plantilla de correo electrónico según sea necesario.

Cuando la propuesta esté lista y haga clic en **Enviar al candidato**, el candidato recibirá un mensaje de correo electrónico indicando que una oferta está esperando que la revise.

>[!NOTE]
> Si está usando Adobe Sign o DocuSign y se produce un error al enviar la oferta al candidato, intente desconectar y volver a conectar la cuenta de usuario de la firma electrónica desde **Configuración del usuario**. Si persiste el problema, contacte con nuestro soporte siguiendo el vínculo **Informar de un problema**.

## <a name="candidates-actions-after-receiving-an-offer"></a>Acciones del candidato después de recibir una propuesta

Una vez que se haya notificado al candidato que una oferta se ha compartido con él, puede hacer clic en el vínculo que está en su correo electrónico para ir al panel de la solicitud y ver la propuesta. El panel mostrará al candidato cualquier actividad que tenga aún que completar.

1.  Para ver la propuesta y todos los documentos relacionados, el candidato debe hacer clic en **Ver oferta**.

    Los candidatos también pueden descargar el paquete de oferta en un formato .zip.

1.  Para aceptar la propuesta, los candidatos deben hacer clic en **Ir a la firma** para cada documento que forme parte del paquete de la propuesta.

1.  Cuando todos los documentos se hayan firmado y se hayan aceptado individualmente, el candidato debe elegir finalizar el proceso de aceptación haciendo clic en **Aceptar oferta** en la parte superior de la página.

1.  Para rechazar la propuesta, el candidato debe hacer clic en **Rechazar oferta** en la parte superior de la página, seleccionar un motivo adecuado, agrega un comentario según sea necesario, y después hacer clic en **Rechazar**.

1.  Después de aceptar o rechazar la propuesta, el candidato puede continuar permaneciendo en la vista de la propuesta o regresar al panel de la solicitud.

1.  Si hubiera otros documentos solicitados como parte del proceso de aceptación de la propuesta, el candidato tiene que elegir cargar los documentos según sea necesario y etiquetarlos con el tipo de documento solicitado.

1.  Se notificará al creador de la propuesta cuando todos los documentos se hayan cargado y se haya firmado el paquete de la propuesta.


## <a name="withdrawing-an-offer"></a>Retirada de una oferta

Se puede retirar una oferta a un candidato en cualquier momento por diferentes motivos. 
1.  Retire la propuesta haciendo clic en el botón de elipsis (**…**) y, a continuación, haga clic en **Retirar la oferta**. 

2. Un mensaje aparecerá preguntando si se ha puesto en contacto con el candidato sobre el cambio de estado. Si todavía no se ha puesto en contacto con el candidato, tendrá la opción de enviar un correo electrónico al candidato en el que se le informe de más acciones. 

   La propuesta dejará de estar accesible al candidato.


## <a name="closing-an-offer"></a>Cierre de una oferta 

Cuando una oferta se ha aceptado, rechazado, o se ha retirado sin otras acciones necesarias, puede cerrar la oferta para que no se edite más este paquete de propuesta.
