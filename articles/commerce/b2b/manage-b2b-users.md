---
title: Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B
description: Este tema describe cómo agregar, eliminar y editar usuarios socios comerciales en sitios web de comercio electrónico de empresa a empresa (B2B) de Microsoft Dynamics 365 Commerce y en la sede de Commerce.
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ef8ae583f18048fc6a36adf38ee7be0fb5b02fcd
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686333"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B

[!include [banner](../../includes/banner.md)]

Este tema describe cómo agregar, eliminar y editar usuarios socios comerciales en sitios web de comercio electrónico de empresa a empresa (B2B) de Microsoft Dynamics 365 Commerce y en la sede de Commerce.

> [!NOTE]
> - El tema [Administrar socios comerciales B2B utilizando jerarquías de clientes](partners-customer-hierarchies.md) es un requisito previo para este documento.
> - Asegúrese de inicializar la entidad de tipos de documentos en la sede de Commerce abriendo el formulario **Tipos de documentos** en **Administración de la organización \> Gestión de documentos \> Tipos de documentos**.

Los sitios web de comercio electrónico B2B requieren que las organizaciones se registren para convertirse en socios comerciales. Una vez que una organización envía los datos de registro a un sitio web de comercio electrónico B2B, la solicitud de registro pasa por un proceso de calificación. Si la organización logra calificarse, se incorpora como socio comercial.

Una vez que una organización se incorpora como socio comercial, se identifica al usuario de la organización que inició la solicitud para convertirse en socio comercial como el usuario administrador, y se le otorgan privilegios para incorporar usuarios autorizados adicionales del sitio web de comercio electrónico B2B. Estos usuarios autorizados podrán realizar pedidos en nombre del socio comercial.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Configurar el usuario administrador para un nuevo socio comercial

Los socios comerciales potenciales pueden iniciar el proceso de incorporación a un sitio web de comercio electrónico B2B enviando una solicitud de incorporación a través de un vínculo en el sitio web B2B. Luego pueden usar el formulario personalizable para proporcionar los detalles necesarios para la incorporación y el registro. Cuando se envía la solicitud, aparece una página de confirmación de envío. Si se aprueba el envío, la empresa para la que se envió la solicitud se convierte en socio comercial y el solicitante (es decir, el usuario que inició la solicitud de incorporación) se convierte en el usuario administrador del socio comercial.

Para aprobar una solicitud de socio comercial en la sede central de Commerce, siga estos pasos.

1. Vaya a **TI de Retail y Commerce \> Programación de distribución**.
1. Ejecute el trabajo **P-0001** para extraer todas las solicitudes de incorporación de socios comerciales a la sede central de Commerce.
1. Una vez que se haya ejecutado correctamente el trabajo **P-0001**, vaya a **TI de Retail y Commerce \> Cliente** y ejecute el trabajo **Sincronizar clientes y canalizar solicitudes**. Una vez que se haya ejecutado correctamente este trabajo, las solicitudes de incorporación se crean como clientes potenciales del tipo **Cliente potencial B2B** en la sede central de Commerce. 
1. Vaya a **Clientes \> Todos los clientes potenciales** y seleccione el registro de cliente potencial del nuevo socio comercial para abrir la página de detalles del cliente potencial.
1. En la pestaña **General**, seleccione **Convertir \> Aprobar/Rechazar** para aprobar la solicitud de incorporación. Cuando aparezca el mensaje de confirmación, confirme que desea continuar con el proceso y apruebe la solicitud. La aprobación cambia el campo **Estado** del registro del cliente potencial a **Aprobado**. Se envía un correo electrónico a la dirección de correo electrónico del solicitante para confirmar que se ha aprobado su organización como socio comercial. También se crea una jerarquía de clientes, donde el solicitante se agrega como administrador del socio comercial.

    > [!NOTE]
    > Actualmente, el correo electrónico de confirmación se envía inmediatamente después de la aprobación. Sin embargo, la futura funcionalidad de Commerce permitirá que el administrador active manualmente los correos electrónicos.

1. Vaya a **TI de Retail y Commerce \> Programa de distribución** y ejecute el trabajo **1010 (Clientes)** para enviar los nuevos registros de clientes y jerarquía de clientes a la base de datos del canal.

> [!NOTE]
> Para garantizar que los nuevos registros de clientes se envíen a la base de datos del canal, al menos una de las libretas de direcciones asociadas con el cliente debe incluirse en la libreta de direcciones de clientes asociada con la tienda en línea. Puede automatizar este proceso configurando la libreta de direcciones en el cliente predeterminado de la tienda en línea para que el sistema copie el valor de la libreta de direcciones para cada nuevo cliente.

Tras sincronizar los registros de clientes y jerarquías de clientes con la base de datos del canal, el solicitante podrá iniciar sesión en el sitio web de comercio electrónico B2B con la dirección de correo electrónico que proporcionó al enviar la solicitud de incorporación. Los usuarios pueden utilizar el flujo de registro para definir la contraseña de su cuenta. Para obtener información sobre cómo habilitar el registro del proveedor de identidad B2C de Azure Active Directory (Azure AD) y vincularlo al registro del cliente B2B que se creó en la aprobación del cliente potencial, consulte [Habilitar vinculación automática](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>Notifique a los prospectos B2B cuando sean aprobados o rechazados

Cuando aprueba o rechaza una solicitud de incorporación de un cliente potencial B2B, puede enviar automáticamente una notificación por correo electrónico al cliente potencial.

Para configurar notificaciones por correo electrónico en la sede de Commerce para eventos del tipo de notificación de **Cliente potencial B2B aprobado** o **Cliente potencial B2B rechazado**, siga estos pasos.

1. Cree plantillas de correo electrónico para los correos electrónicos que se enviarán a los clientes potenciales cuando se active el tipo de notificación de **Cliente potencial B2B aprobado** o **Cliente potencial B2B rechazado**. Para obtener información sobre los marcadores de posición que admiten los tipos de notificación, consulte [Tipos de notificación](../email-templates-transactions.md#notification-types). Para obtener información sobre cómo crear plantillas de correo electrónico, consulte [Crear una plantilla de correo electrónico](../email-templates-transactions.md#create-an-email-template).
1. Agregue los tipos de notificación de **prospecto B2B aprobado** y **prospecto B2B rechazado** a su perfil de notificación por correo electrónico y asígnelos a las plantillas de correo electrónico que creó. Para obtener más información sobre cómo perfiles de notificación, consulte [Configurar un perfil de notificación de correo electrónico](../email-notification-profiles.md).

## <a name="onboard-additional-business-partner-users"></a>Incorporar usuarios socios comerciales adicionales

El usuario administrador socio comercial puede incorporar usuarios socios comerciales adicionales al sitio web de comercio electrónico B2B según sea necesario.

Para incorporar usuarios socios comerciales adicionales a un sitio web de comercio electrónico B2B, siga estos pasos.

1. Inicie sesión en el sitio web de comercio electrónico B2B como administrador.
1. Vaya a **Mi cuenta \> Usuarios de la organización \> Ver detalles** y seleccione **Agregar un usuario**.
1. Introduzca la información necesaria y, a continuación, seleccione **Guardar**. El estado del nuevo usuario se establece en **Pendiente**.

Una vez que se hayan ejecutado los trabajos **P-0001** y **Sincronizar clientes y solicitudes del canal**, se creará un registro de cliente de tipo **Persona** para el nuevo usuario en la sede central de Commerce. Este registro de cliente también está asociado con el registro de jerarquía de clientes del socio comercial correspondiente. Además, se envía un correo electrónico a la dirección de correo electrónico del nuevo usuario para notificarle que se ha agregado como usuario de la organización del socio comercial y que ahora puede iniciar sesión en el sitio web de comercio electrónico B2B.

Después, ejecute el trabajo **1010 (Clientes)** para sincronizar el nuevo usuario del socio comercial con la base de datos del canal.

Una vez que se haya sincronizado el registro del cliente, el estado del usuario en el sitio web de comercio electrónico B2B se establece en **Activo**, y el nuevo usuario podrá iniciar sesión en el sitio web de comercio electrónico B2B utilizando su dirección de correo electrónico. Los usuarios pueden utilizar el flujo de registro para definir la contraseña de su cuenta. Para obtener información sobre cómo habilitar el registro del proveedor de identidad B2C de Azure AD y vincularlo al registro del cliente B2B que se creó en la sede central de Commerce, consulte [Habilitar vinculación automática](/dynamics365/commerce/identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Editar los detalles del usuario del socio comercial

Para editar los detalles de los usuarios socios comerciales, siga estos pasos.

1. Inicie sesión en el sitio web de comercio electrónico B2B como administrador.
1. Vaya a **Mi cuenta \> Usuarios de la organización \> Ver detalles**, seleccione el botón **Editar** (símbolo de lápiz), realice los cambios necesarios y, a continuación, seleccione **Guardar**. Los cambios entrarán en vigor cuando se hayan ejecutado los trabajos **P-0001**, **Sincronizar clientes y solicitudes del canal** y **1010 (Clientes)**.

## <a name="remove-a-business-partner-user"></a>Quitar un usuario socio comercial

Cuando sea necesario, un administrador puede eliminar los usuarios existentes de una organización socio comercial de la lista de usuarios que pueden acceder al sitio web de comercio electrónico B2B.
Para quitar un usuario socio comercial, siga estos pasos.
- Inicie sesión en el sitio web de comercio electrónico B2B como administrador.
- Vaya a **Mi cuenta > Usuarios de la organización \> Ver detalles** y seleccione el botón **Quitar** (símbolo "X"). Cuando aparezca un mensaje de confirmación, confirme que desea quitar el usuario. El cambio entrará en vigor cuando se hayan ejecutado los trabajos **P-0001**, **Sincronizar clientes y solicitudes del canal** y **1010 (Clientes)**.

> [!NOTE]
> Al quitar un usuario de la lista de usuarios que pueden acceder al sitio web de comercio electrónico B2B, el registro de cliente correspondiente se quita del registro de jerarquía de clientes del socio comercial. Sin embargo, el registro del cliente en sí no se elimina de la sede central de Commerce.

## <a name="onboard-existing-customers-as-business-partners-on-the-b2b-e-commerce-website"></a>Incorporar clientes existentes como socios comerciales en el sitio web de comercio electrónico B2B

Los administradores pueden incorporar socios comerciales y usuarios directamente en la sede central de Commerce. Esta capacidad es útil para incorporar a sus socios comerciales existentes en el sitio web de comercio electrónico B2B.

Para incorporar socios comerciales y usuarios directamente en la sede central de Commerce, siga estos pasos.

1. Cree o seleecione un cliente del tipo **Organización** para agregarlo como socio comercial.
1. Cree o seleccione un cliente del tipo **Persona** para agregarlo como administrador o usuario para el socio comercial. Asegúrese de que las direcciones de correo electrónico principales están asociadas con los clientes. Estas direcciones de correo electrónico se utilizan para iniciar sesión en el sitio web. 

    > [!NOTE]
    > El sistema debe poder encontrar un registro de cliente único para los usuarios que deberían poder iniciar sesión en el sitio web. Si el sistema encuentra más de un cliente que tiene la misma dirección de correo electrónico principal en la entidad jurídica, el usuario no podrá iniciar sesión en el sitio web.

1. Cree un id. de jerarquía de clientes.
1. Escriba un nombre en el campo **Nombre**.
1. En el campo **Organización**, introduzca el cliente de la organización del socio comercial.
1. En la ficha desplegable **Jerarquía**, seleccione **Agregar**.
1. En el campo **Nombre**, seleccione un cliente del tipo **Persona**.
1. Seleccione el rol **Administrador** para el cliente que debe designarse como administrador.
1. Repita este proceso para agregar más clientes a la jerarquía.

## <a name="additional-information"></a>Información adicional

- Todos los trabajos que se mencionan en este tema pueden configurarse para ejecutarse según una programación en un formato por lotes. La expectativa es que los socios comerciales configuren los trabajos por lotes según sea necesario.
- Actualmente, solo se puede designar un registro de usuario/cliente como usuario administrador, y ese rol solo se puede cambiar en la sede central de Commerce. No se ofrece funcionalidad de autoservicio que permita a los socios comerciales designar múltiples administradores o cambiar administradores de sitios web de comercio electrónico B2B.
- Aunque se pueden definir límites de gasto para los usuarios, aún no se ha implementado el cumplimiento de los límites de gasto durante el proceso de entrada de pedidos.
- Toda la lógica empresarial y la validación de la experiencia de un usuario en un sitio web de comercio electrónico B2B se basan en la configuración del registro del cliente que se asigna al usuario en la sede central de Commerce.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un sitio de comercio electrónico B2B](set-up-b2b-site.md)

[Administrar socios comerciales B2B utilizando jerarquías de clientes](partners-customer-hierarchies.md)

[Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B](payment-method.md)

[Establecer límites de cantidad de productos para sitios de comercio electrónico B2B](quantity-limits.md)

[Visión general de las secuencias numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
