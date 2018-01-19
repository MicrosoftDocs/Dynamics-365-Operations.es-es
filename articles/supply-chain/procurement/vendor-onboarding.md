---
title: "Incorporación de proveedores"
description: "En este tema se describe el proceso para incorporación de nuevos proveedores. Explica las acciones que requieren para varios roles durante este proceso."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 4804fc1a52371284ab69d1490454bebd5e91fcd9
ms.contentlocale: es-es
ms.lasthandoff: 12/14/2017

---

# <a name="onboard-vendors"></a>Incorporación de proveedores
[!include[banner](../includes/banner.md)]
---

Los nuevos proveedores pueden incorporarse y registrarse como proveedores en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, en función de la información obtenida de una persona que represente al proveedor.

El proceso consta de los siguientes pasos, donde los distintos roles realizan acciones en el sistema.

1. **Administración de datos OData**: Importación de la entidad - la solicitud inicial es la solicitud de registro del proveedor potencial. Normalmente, esta solicitud procede de un origen como una página Web cliente hospedado que permite acceso anónimo. Los proveedores pueden realizar la inscripción al proporcionar información básica, como el nombre del proveedor, la justificación, el número de organización y el nombre y la dirección de correo electrónico de la persona de contacto. Las solicitudes se importan mediante la interfaz de gestión de datos.
2. **Página de lista de la solicitud de registro del proveedor potencial** - Según la información que se ofrece en la solicitud de registro del proveedor potencial, el profesional de compras va a decidir si el proveedor debe incorporarse. El profesional de compras ve la petición entrante en la página de lista **Solicitudes de registro del proveedor potencial** en Finance and Operations.
3. **Flujo de trabajo de abastecimiento de usuario** - Cuando un profesional de compras ha comprobado la información en la solicitud entrante y ha decidido continuar con el proceso incorporación, el flujo de trabajo de la solicitud de usuario aprovisiona al nuevo usuario y envia un mensaje de correo electrónico de invitación para aceptar a la persona de contacto como usuario autenticado de Microsoft Dynamics 365.
4. **Asistente de registro de proveedor** - la persona de contacto del proveedor inicia sesión en Finance and Operations mediante la nueva cuenta de usuario. Completa un asistente de registro de proveedor para proporcionar información como direcciones, información empresarial, categorías de compras y respuestas del cuestionario.
5. **Flujo de trabajo de aprobación** - Se crea la solicitud de proveedor que incluye la información de registro. Esta solicitud de proveedor se envía a un flujo de trabajo y se enruta para su revisión y aprobación.
6. **Creación de un maestro de proveedores y modificación del rol de usuario** - Cuando se aprueba la solicitud de proveedor, se crea un registro de proveedor. A la cuenta de usuario de la persona de contacto del proveedor se le concede permiso para la colaboración del proveedor o se desactiva.

En la tabla siguiente muestran los pasos y los roles que están involucrados en el proceso.

| Rol y "proceso"       | Administración de datos OData – importación de la entidad | Página de lista de solicitudes de registro de proveedor potencial | Flujo de trabajo de aprovisionamiento de usuario | Asistente de registro de proveedor | Flujo de trabajo de aprobación | Creación de un maestro de proveedores y modificación del rol de usuario |
|--------------------------|---|---|---|---|---|---|
| System                   | Se importa la solicitud de un nuevo proveedor. | | | | | Tras aceptar la solicitud de proveedor, se crea el registro de proveedor. |
| Profesional de compras | | Iniciar el proceso de incorporación. | | | Revisar y aceptar o rechazar la solicitud de proveedor. | |
| Administrador            | | | Crear una cuenta de usuario en Finance and Operations y Microsoft Azure. | | | |
| Persona de contacto del proveedor    | | | Enviar correo electrónico a la persona de contacto. | Registrar la información del proveedor. | | |

## <a name="importing-the-prospective-vendor-registration-request"></a>Importar la solicitud de registro del proveedor potencial

La solicitud de registro del proveedor potencial es una entidad en Finance and Operations. Puede configurar el sistema para importar datos mediante esta entidad. 

En la tabla siguiente se muestra la información que contiene esta entidad y que puede ser importada.

| Campo                        | Descripción |
|------------------------------|-------------|
| Nombre del proveedor                  | Nombre del proveedor. |
| Justificación comercial       | El motivo o motivos de la solicitud del proveedor. |
| Número de organización          | Un número de registro oficialmente conocido. |
| Línea de negocio             | La línea de negocios en la que está el proveedor. |
| Nombre de la persona de contacto  | El nombre de la persona que será invitada para registrar la información de proveedor. |
| Segundo nombre de la persona contacto | El segundo nombre de la persona que será invitada para registrar la información de proveedor. |
| Apellido de la persona de contacto   | El apellido de la persona que será invitada para registrar la información de proveedor. |
| Dirección de correo electrónico de la persona de contacto       | La dirección de correo electrónico que se usará para crear un nuevo usuario en Finance and Operations y que se registrará en la cuenta de unquilino de Azure Active Directory (Azure AD). |
| Fecha de envío               | La fecha en la que se creó la solicitud en un sistema externo. |
| Entidad jurídica                 | La entidad jurídica en la que el proveedor solicita hacerse proveedor. Este valor debe ser un código de entidad jurídica que se haya registrado en Finance and Operations. Si no se ha recibido ningún valor en el proceso de importación, se aplica un valor de los parámetros de la adquisición y abastecimiento. |
| Tipo de proveedor                  | El proveedor puede ser una organización o una persona. El tipo de proveedor determina cómo se crea el proveedor finalmente. |

Una vez importada la solicitud de registro del proveedor potencial, aparece en la página de lista **Solicitud de registro del proveedor potencial**. Desde esta página de lista, un responsable de compras puede invitar al usuario. Se envía una solicitud de usuario a un flujo de trabajo para aprovisionar al usuario.

## <a name="submitting-a-prospective-vendor-user-request"></a>Enviar una solicitud de usuario de proveedor potencial

El propósito de una solicitud de usuario de proveedor potencial es aprovisionar a la persona que envió la solicitud inicial, de modo que esta persona pueda iniciar sesión en Finance and Operations mediante la cuenta de correo electrónico que se ofrece en la solicitud de registro del proveedor potencial.

La solicitud de usuario del proveedor potencial se procesa por el flujo de trabajo de la solicitud de usuario. Este flujo de trabajo se comunica mediante la colaboración de Azure AD B2B. Crea un usuario en Finance and Operations que tenga la configuración de seguridad adecuada.

Los nuevos usuarios que estén configurados con los roles de seguridad siguientes:

- Usuario externo del sistema
- Proveedor potencial (externo)

El nuevo usuario recibirá un mensaje de correo electrónico generado por el flujo de trabajo de la solicitud de usuario. Este mensaje de correo electrónico invita al usuario a iniciar sesión en el sistema.

Para obtener información sobre la configuración de correo electrónico y el flujo de trabajo en general, consulte la descripción de un flujo de trabajo de la solicitud de usuario en [Configurar y mantener la colaboración del proveedor](set-up-maintain-vendor-collaboration.md).

## <a name="vendor-registration"></a>Registro de proveedor

Un usuario de proveedor potencial que inicie sesión en Finance and Operations verá la primera página del asistente de registro del proveedor, donde podrá introducir la información del proveedor.

El asistente refleja la configuración de la solicitud del proveedor. El país o la región donde el proveedor hace negocios determina qué información se solicita en el asistente y qué información es obligatoria.

Para obtener más información acerca de la configuración de la solicitud del proveedor, consulte [Configurar y mantener la colaboración del proveedor](set-up-maintain-vendor-collaboration.md). La tabla siguiente proporciona información general de las páginas del asistente y el propósito de cada página.

| Página                       | Descripción |
|----------------------------|-------------|
| País o región             | El país o región determina la configuración de la solicitud del proveedor que se aplica a las páginas del asistente restantes. También determina los valores en la búsqueda **Estado fiscal**. |
| Términos y condiciones       | Esta página podría estar disponible, según la configuración de la solicitud del proveedor. Si está disponible, el usuario debe confirmar los términos y condiciones para continuar. |
| Información del proveedor         | Esta página contiene el nombre del proveedor, que se introduce automáticamente desde la solicitud original del registro del proveedor potencial. También contiene el número de organización, el número de teléfono del proveedor, el número de fax, la dirección de correo electrónico y direcciones del proveedor para distintos fines. |
| Información de persona de contacto | Esta página contiene el nombre de la persona de contacto, que se introduce automáticamente desde la solicitud original del registro del proveedor potencial. También contiene el número de teléfono y la dirección de correo electrónico de la persona de contacto y direcciones de la persona de contacto para distintos fines. |
| Información de la empresa       | Esta página contiene los números de registro de impuestos (para los diferentes países o regiones) y a los números de empleados. También indica si el negocio es de propiedad minoritaria. |
| Categorías de compras     | Esta página contien las categorías de compras para las que el proveedor solicita aprobación. El usuario puede seleccionar categorías de la jerarquía de categorías de compras. Puede configurar el número de niveles que se muestran en la jerarquía en **Parámetros de adquisición y abastecimiento** &gt; **Colaboración del proveedor**, en &gt; **Adquisición y abastecimiento** **Configuración**. |
| Cuestionarios             | El asistente puede incluir un conjunto de cuestionarios para el proveedor. Los cuestionarios que aparecen en el asistente se configuran en la solicitud del proveedor o por categoría de compras. Si los cuestionarios se configuran por categoría de compras, las categorías de compras para las que el proveedor solicita aprobación para determinar los cuestionarios que aparecen en el asistente. En la página **Categorías de compras**, puede agregar un cuestionario en la categoría relevante y establecer el tipo de actividad para la **Incorporación del proveedor**. |

Cuando el usuario del proveedor potencial completa el asistente de registro del proveedor, se crea una solicitud del proveedor.

## <a name="manually-or-automatically-submit-a-vendor-request"></a>De forma manual o automáticamente enviía una solicitud de proveedor

Una solicitud de proveedor se puede crear como borrador y enviar manualmente a un flujo de trabajo. O bien, la solicitud de proveedor se puede enviar automáticamente a un flujo de trabajo cuando el asistente de registro de proveedor esté completo. Una solicitud se puede enviar manualmente si, por ejemplo, un responsable de compras desea evaluar si la solicitud debe enrutarse a través de un proceso de aprobación antes de que haya enviado al flujo de trabajo.

- Seleccione &gt; **Parámetros de la adquisición y abastecimiento** **Colaboración del proveedor**y, a continuación, seleccione **Enviar automáticamente el registro del proveedor potencial al flujo de trabajo** para configurar la solicitud del proveedor de modo que se envíe automáticamente a un flujo de trabajo cuando el asistente de registro de proveedor se complete.

## <a name="vendor-requests"></a>Solicitudes de proveedor

Las solicitudes del proveedor están disponibles en la página **Solicitudes de usuario de colaboración del proveedor**.

Una solicitud del proveedor contiene la información que el usuario del proveedor potencial haya especificado en el asistente de registro de proveedor.

La solicitud permite revisar la información del proveedor y decidir si el proveedor debe hacerse proveedor registrado en Finance and Operations.

La solicitud del proveedor se debe enviarse a un flujo de trabajo y debe enrutarse a los revisores y aprobadores relevantes. Para obtener información básica sobre cómo configurar los flujos de trabajo, consulte [Adquisición y abastecimiento](procurement-sourcing-workflows.md).

La siguiente tabla muestra los estados que las solicitudes de proveedor pueden tener.

| Estado                     | Descripción |
|----------------------------|-------------|
| Borrador                      | La solicitud del proveedor aún no se ha enviado. |
| Solicitud enviada          | Se ha enviado la solicitud del proveedor y el primer paso del flujo de trabajo se está procesando. |
| Revisión pendiente             | Si hay varios revisores en una tarea de flujo de trabajo, un revisor podrá aceptar la tarea de revisar la solicitud del proveedor y luego completar revisión. Si sólo hay un revisor, dicho participante puede completar la revisión seleccionando **completado** en la acción del flujo de trabajo. No tiene que aceptar el artículo de trabajo primero. |
| Aprobación solicitud pendiente   | La solicitud del proveedor se ha enrutado a los participantes para la aprobación y hay una opción para solicitar información adicional. Una solicitud de información adicional causa que el elemento de trabajo se enrute de nuevo al remitente. La solicitud del proveedor también puede aprobarse o rechazarse cuando se encuentra en este estado. |
| Solicitud de modificación de la aplicación | El aprobador ha solicitado información adicional y la solicitud del proveedor se ha enviado a la persona que envió la solicitud del proveedor. El remitente puede agregar la información solicitada y después volver a enviar la solicitud del proveedor. Si se vuelve a enviar una solicitud del proveedor, el estado vuelve a cambiar a **Petición pendiente de aprobación**. |
| Solicitud aprobada           | Este estado es una estado final. |
| Solicitud rechazada           | Este estado es una estado final. |

## <a name="approving-a-vendor-request"></a>Aprobar una solicitud del proveedor

Cuando se aprueba una solicitud del proveedor, se crea una cuenta de proveedor y el estado **Aprobado** aparece tanto en la solicitud inicial del registro del proveedor potencial como en la solicitud del proveedor.

Antes de que se apruebe una solicitud del proveedor, en la página **Nuevo proveedor**, en el ficha desplegable **General**, seleccione **Grupo de proveedores** para seleccionar un grupo de proveedores.

Si el usuario del proveedor potencial debe tener acceso a Finance and Operations como usuario de colaboración del proveedor que represente al proveedor, defina el permiso de acceso de colaboración del proveedor en **Sí**. Para desactivar la cuenta de usuario del proveedor potencial utilizado para el registro, establezca este permiso en **No**.

Si el permiso de acceso de colaboración del proveedor se establece en **Sí**, cuando se aprueba la solicitud del proveedor, se envía una solicitud para modificar los roles de usuario de modo que el usuario tenga los roles que se han definido para el tipo de **Proveedor** en **Roles externos**. Si este permiso se establece en **No**, cuando se aprueba la solicitud del proveedor, se envía una solicitud para desactivar al usuario. En este caso, se debe configurar el flujo de trabajo para desactivar una solicitud de usuario.

Para que se cree una cuenta de proveedor cuando se aprueba la solicitud del proveedor, la secuencia numérica para crear los proveedores desde las solicitudes del proveedor se debe establecer en **Automática**.

Para obtener información general de los permisos de acceso de un usuario de colaboración del proveedor, vea [Configurar y mantener la colaboración del proveedor](set-up-maintain-vendor-collaboration.md).

## <a name="rejecting-a-vendor-request"></a>Rechazar una solicitud del proveedor

Si se rechaza una solicitud del proveedor, se debe seleccionar el motivo del rechazo en la solicitud del proveedor.

Cuando se rechaza una solicitud del proveedor, se envía una solicitud para desactivar al usuario. En este caso, se debe configurar el flujo de trabajo para desactivar una solicitud de usuario. Para obtener más información, consulte [Configuar y mantener la colaboración del proveedor](set-up-maintain-vendor-collaboration.md).

Cuando se rechaza una solicitud del proveedor, el estado **Rechazada** aparece tanto en la solicitud inicial del registro del proveedor potencial como en la solicitud del proveedor.

## <a name="deleting-a-prospective-vendor-registration-request-in-various-statuses"></a>Eliminar una solicitud de registro del proveedor potencial en los distintos estados

Los distintos estados de una solicitud de registro del proveedor potencial ofrecen una visión general del progreso de la solicitud.

Mediante la acción **Eliminar** en la solicitud de registro del proveedor potencial, puede quitar y limpiar la cadena de registros que se han creado y puede desactivar la cuenta de usuario. El resultado de la acción **Eliminar** varía, en función del estado de la solicitud de registro del proveedor potencial, como se muestra en la siguiente tabla.

| Estado                   | Descripción del estado | Resultado de acción de la Eliminar |
|--------------------------|--------------------|-----------------------------------|
| Nueva                      | No se ha realizado ninguna acción en la solicitud. | La solicitud de registro del proveedor potencial ha sido eliminada. |
| Solicitado por el usuario           | Cuando se selecciona **Invitar usuario**, el estado cambia a **Usuario solicitado** y una solicitud de usuario potencial se crea y se envía a un flujo de trabajo de solicitud de usuario. | No puede eliminar una solicitud de registro del proveedor potencial que tenga este estado, ya que el flujo de trabajo de la solicitud de usuario no ha terminado. |
| Invitado por el usuario             | Se aprueba el flujo de trabajo de la solicitud de usuario y crea el usuario. | Se crea una solicitud para desactivar el usuario y se eliminará la solicitud de registro del proveedor potencial. |
| Registro en curso | El nuevo usuario ha iniciado sesión y ha iniciado el asistente de registro del proveedor. | Se crea una solicitud para desactivar el usuario y se eliminan la solicitud de registro del proveedor potencial y los datos que se especificaron en el asistente de registro de proveedor. |
| Solicitud de proveedor creada   | El asistente de registro del proveedor se ha completado. | Se crea una solicitud para desactivar el usuario y se eliminan la solicitud de registro del proveedor potencial, los datos que se especificaron en el asistente de registro del proveedor y la solicitud del proveedor.<blockquote>[!NOTE]<br>No puede usar la acción **Eliminar** cuando la solicitud del proveedor se encuentra en un proceso de revisión del flujo de trabajo.</blockquote> |
| Aprobada                 | La solicitud del proveedor ha sido aprobada. | Se eliminan la solicitud de registro del proveedor potencial, los datos que se especificaron en el asistente de registro del proveedor y la solicitud del proveedor. |
| Rechazado                 | La solicitud del proveedor ha sido rechazada. | Se eliminan la solicitud de registro del proveedor potencial, los datos que se especificaron en el asistente de registro del proveedor y la solicitud del proveedor. |

