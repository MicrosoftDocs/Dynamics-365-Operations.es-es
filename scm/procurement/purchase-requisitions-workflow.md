---
title: Flujo de trabajo de solicitudes de compra
description: "El proceso del flujo de trabajo mueve las solicitudes de compra por el proceso de revisión, desde un estado inicial de Borrador a un estado final de Aprobado. Cuando se envía una solicitud de compra a revisión, se inicia el proceso del flujo de trabajo. Cuando se aprueba una solicitud de compra, se puede generar un pedido de compra para las líneas de la solicitud de compra y enviarlo al proveedor para su cumplimiento."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqAuthorization, WorkflowParticipantExpenToken
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2234
ms.assetid: dad3ba5a-2892-45d2-874a-300896f59b34
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2d28e92fa853d155bc62932625e0e714cdf4edcc
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="purchase-requisition-workflow"></a>Flujo de trabajo de solicitudes de compra

[!include[banner](../includes/banner.md)]


El proceso del flujo de trabajo mueve las solicitudes de compra por el proceso de revisión, desde un estado inicial de Borrador a un estado final de Aprobado. Cuando se envía una solicitud de compra a revisión, se inicia el proceso del flujo de trabajo. Cuando se aprueba una solicitud de compra, se puede generar un pedido de compra para las líneas de la solicitud de compra y enviarlo al proveedor para su cumplimiento.

Para que una solicitud de compra se pueda enviar a revisión, debe configurar un flujo de trabajo. El proceso del flujo de trabajo puede incluir uno o varios pasos de revisión en cualquier orden. El proceso del flujo de trabajo también se puede configurar para omitir las tareas de revisión y aprobar automáticamente la solicitud de compra. Puede configurar el proceso del flujo de trabajo para enrutar la solicitud de compra como un solo documento o puede enrutar líneas individuales de la solicitud de compra a los revisores adecuados. También puede crear un escenario en el que la solicitud de compra se enrute como un documento único a algunos revisores y las líneas seleccionadas de la solicitud de compra se enruten a otros revisores.  

Si las líneas de la solicitud de compra se revisan de manera individual, el proceso de revisión se debe completar para todas las líneas de la solicitud de compra para que el proceso del flujo de trabajo pueda moverse al siguiente paso y para que el proceso de revisión de la solicitud de compra en conjunto pueda completarse. Cuando se haya completado el proceso de revisión de la solicitud de compra y de todas sus líneas, el estado global de la solicitud de compra se actualizará a **Aprobado**.  

Puede configurar su flujo de trabajo para representar el proceso empresarial de las solicitudes de compra de su organización. Al configurar el proceso del flujo de trabajo de solicitud de compra, tenga en cuenta las preguntas siguientes:

-   ¿Qué gastos se deben revisar?
-   ¿Qué gastos se pueden aprobar automáticamente?
-   ¿Quién tiene que aprobar y revisar las solicitudes de gastos? ¿A qué rol se ha asignado a estos usuarios?
-   ¿Qué proceso se debe seguir cuando un revisor no está disponible?

En los ejemplos siguientes se muestran dos maneras de configurar un flujo de trabajo para solicitudes de compra.

## <a name="example-1-route-a-purchase-requisition-as-a-single-document-for-review"></a>Ejemplo 1: enrutar una solicitud de compra como un documento único para revisión
En la siguiente ilustración se muestra la manera en la que una solicitud de compra puede fluir por el proceso de revisión del flujo de trabajo como un único documento. Las líneas de la solicitud de compra no se enrutan de manera individual. Los roles siguientes están incluidos en el proceso de flujo de trabajo de este ejemplo:

-   **Solicitante**: usuario que ha solicitado los artículos o servicios. El solicitante puede preparar la solicitud de compra, o bien otro trabajador puede preparar la solicitud de compra en nombre del solicitante. Este trabajador es el preparador. El preparador es el responsable de gestionar la solicitud de compra mediante el proceso de revisión. Solo el preparador de la solicitud de compra la puede modificar.

**Nota**: se pueden conceder a un trabajador los permisos adecuados para crear una solicitud de compra en nombre de otra persona. Use la página **Permiso de solicitud de compra** para configurar estos permisos.

-   **Agente de compras**: usuario que realiza la revisión de una compra y que puede aprobar el documento.
-   **Administrador del solicitante**: usuario que realiza la revisión administrada y que puede aprobar el documento.

![Proceso de revisión de flujo de trabajo de solicitudes de compra](./media/purchreqworkflowoverview_submission.gif)  
En este ejemplo, el proceso del flujo de trabajo de la solicitud de compra incluye los pasos siguientes:

1.  El preparador envía una solicitud de compra a revisión.
2.  El agente de compra recibe una notificación. Las notificación solicita que el agente de compras compruebe la información de la solicitud de compra. Si falta información necesaria, el agente de compras puede agregarla o devolver la solicitud de compra al preparador para que la agregue. Una vez se haya rellenado la información necesaria, la solicitud de compra puede pasar al paso siguiente del proceso de revisión.
3.  El administrador del solicitante revisa la solicitud de compra. La solicitud de compra se puede enrutar al administrador del solicitante si, por ejemplo, el importe de la solicitud de compra supera el límite de gastos del solicitante para solicitudes de compra. El administrador del solicitante puede aprobar o rechazar la solicitud de compra, o devolverla al preparador para que realice cambios.

## <a name="example-2-route-the-individual-purchase-requisition-lines-for-review"></a>Ejemplo 2: enrutar líneas individuales de la solicitud de compra para revisión
En la siguiente ilustración se muestra la manera en la que las líneas de una solicitud de compra individual se pueden enrutar a través de un flujo de trabajo. En general, el proceso de cada línea suele ser el mismo que el proceso para una solicitud de compra que se revisa como un documento único. Sin embargo, cada línea debe completar el proceso de flujo de trabajo de forma individual para que el flujo de trabajo se pueda completar para toda la solicitud de compra.  

En este ejemplo, un trabajador introduce una solicitud de pósters y camisetas para una campaña de marketing. El coste de los pósters se divide entre el departamento de marketing y el departamento de ventas. Si el coste de los pósters o de las camisetas supera la autoridad del límite de firmas para directores de departamento, el administrador del grupo deberá revisar también la solicitud de compra.  

Los roles siguientes están incluidos en el proceso de flujo de trabajo de este ejemplo:

-   **Solicitante**: usuario que ha solicitado los artículos o servicios. El solicitante puede preparar la solicitud de compra, o bien otro trabajador puede preparar la solicitud de compra en nombre del solicitante. Este trabajador es el preparador. El preparador es el responsable de gestionar la solicitud de compra mediante el proceso de revisión. Solo el preparador de la solicitud de compra la puede modificar.

**Nota**: se pueden conceder a un trabajador los permisos adecuados para crear una solicitud de compra en nombre de otra persona. Use la página **Permiso de solicitud de compra** para configurar estos permisos.

-   **Agente de compras**: usuario que realiza la revisión de una compra y que puede aprobar el documento.
-   **Administrador del solicitante**: usuario que realiza la revisión administrada y que puede aprobar el documento.
-   **Director de departamento**: usuario que realiza la revisión de gastos y que puede aprobar el documento.
-   **Director de grupo**: usuario que realiza la revisión de autoridad de firmas y que puede aprobar el documento.

![Proceso de revisión del flujo de trabajo de la línea de la solicitud de compra](./media/purchreqlineworkflowoverview.gif)  
En este ejemplo, el proceso del flujo de trabajo de las líneas de la solicitud de compra incluye los pasos siguientes:

1.  El preparador envía una solicitud de compra a revisión. Cada línea se enruta al revisor configurado para recibirla en el proceso del flujo de trabajo.
2.  El agente de compra recibe una notificación. La notificación solicita que el agente de compras compruebe la información de la solicitud de compra y de las líneas de la solicitud de compra. Cuando el agente de compras abre la solicitud de compra, todas las líneas están visibles, pero un indicador visual muestra las líneas que se han enviado al agente de compras para su revisión. Si falta información necesaria, el agente de compras puede agregarla o devolver una línea de la solicitud de compra al preparador para que la agregue. Una vez se haya rellenado la información necesaria, la línea de la solicitud de compra puede pasar al paso siguiente del proceso de revisión. Las líneas de la solicitud de compra pueden continuar por el proceso de revisión de forma independiente unas de otras.
3.  El administrador de la línea del solicitante revisa y aprueba las líneas de la solicitud de compra. La aprobación podría enrutarse al director del solicitante si, por ejemplo, el importe de una línea de la solicitud de compra supera el límite de gasto del solicitante para las líneas de solicitud de compra. El administrador puede aprobar o rechazar una de las líneas de la solicitud de compra, o ambas.
4.  El director del departamento de marketing revisa las líneas de la solicitud de compra para los pósters y las camisetas. El administrador del departamento de ventas revisa la línea de la solicitud de compra solo de los pósters, porque es el único coste que corre a cargo del departamento de ventas.
5.  El director del grupo revisa y aprueba la línea de la solicitud de compra para las camisetas solo si se requiere la aprobación del director del grupo porque, por ejemplo, el importe de la línea de solicitud de compra supera el límite de aprobación del director de departamento. El administrador del grupo no tiene que aprobar la línea de la solicitud de compra de los pósters.

## <a name="configuring-a-workflow-for-purchase-requisitions"></a>Configuración de flujos de trabajo para solicitudes de compra
Para dirigir una solicitud de compra a revisión, debe configurar los procesos de flujo de trabajo de la solicitud de compra. El proceso de flujo de trabajo definido controlará la interacción entre el usuario que ha solicitado los artículos (el solicitante) y el revisor y el aprobador del flujo de trabajo. La ruta de la solicitud de compra depende de las condiciones que se especifican en la configuración del flujo de trabajo. Por ejemplo, estas condiciones determinan cuándo debe enrutarse la solicitud de compra, a qué usuario o rol se debe enrutar y las acciones que los usuarios pueden realizar.  

En los ejemplos de este tema se muestra cómo se puede enrutar una solicitud de compra a través de un flujo de trabajo como un documento único o como líneas individuales de la solicitud de compra. También puede configurar un flujo de trabajo para solicitudes de compra que refleje la revisión de control interno de las solicitudes de compra definidas para su organización.  

Los participantes o los revisores a los que una tarea está asignada en un flujo de trabajo pueden ser miembros de un grupo de usuarios concreto, usuarios que tengan un rol de seguridad concreto, usuarios asociados al remitente en una jerarquía directiva o usuarios con nombre o usuarios que tienen responsabilidades de gastos específicas.

### <a name="purchase-requisition-expenditure-reviewers"></a>Revisores de gastos de solicitud de compra

Las configuraciones de revisor de gastos permiten enrutar de manera dinámica los gastos para su revisión según el usuario asignado a un rol del proyecto o a una dimensión financiera donde se cobran los gastos. El proceso del flujo de trabajo usa el rol de proyecto especificado o el propietario de la dimensión financiera para determinar a quién se debe enrutar el gasto.  

Puede definir una o varias configuraciones de revisor de gastos y, a continuación, seleccionar una cuando cree un flujo de trabajo. Puede configurar los valores del revisor de gastos para todas las entidades jurídicas de su organización. Una vez definidas las configuraciones del revisor de gastos, asigne una configuración a la tarea del flujo de trabajo.  

No tiene por qué definir las configuraciones del revisor de gastos. Por el contrario, puede asignar usuarios o grupos de usuarios específicos como revisores al definir el flujo de trabajo. Sin embargo, si tiene una organización compleja, los revisores de gastos pueden aumentar la eficacia del proceso de aprobación. Además, si configura revisores de gastos, no es necesario actualizar las asignaciones del revisor de flujo de trabajo cada vez que un revisor cambia de rol de trabajo.  

Puede configurar revisores de gastos en la página **Revisores de gastos de solicitudes de compra**. Cree una configuración de revisor de gastos y especifique valores para cada entidad jurídica de la organización. Para las solicitudes asignadas a un proyecto, puede especificar el rol responsable de revisar las solicitudes: director de proyecto, controlador de proyecto o director de ventas del proyecto. Los gastos se enrutarán al usuario asignado al rol especificado. También puede enrutar los gastos al propietario de la dimensión financiera si selecciona la opción de dimensión financiera correspondiente en la ficha **Distribuciones de la organización**.  

Para usar uno de los revisores de gastos que ha configurado en un flujo de trabajo, debe establecer la opción **Tipo de participante** en**Participantes de gastos** en las propiedades de**Asignación** del elemento de flujo de trabajo correspondiente.

<a name="see-also"></a>Consulte también
--------

[Creación de un pedido para consumo (Guía de tareas)](https://ax.help.dynamics.com/en/wiki/create-a-requisition-for-consumption/)

[Definición de flujos de trabajo de procesos empresariales para solicitudes de compra](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Flujos de trabajo de adquisición y abastecimiento](procurement-sourcing-workflows.md)

[Visión general de solicitudes de compra](purchase-requisitions-overview.md)




