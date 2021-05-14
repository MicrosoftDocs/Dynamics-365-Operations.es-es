---
title: Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B
description: Este tema describe cómo los administradores pueden agregar, editar y eliminar usuarios socios comerciales en sitios web de comercio electrónico de empresa a empresa (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6beee4cc4c0dd36f49a38ee49a1a23ad9b513360
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936665"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B

[!include [banner](../../includes/banner.md)]

Este tema describe cómo los administradores pueden agregar, editar y eliminar usuarios socios comerciales en sitios web de comercio electrónico de empresa a empresa (B2B).

Los sitios web de comercio electrónico B2B requieren que las organizaciones se registren para convertirse en socios comerciales. Una vez que una organización envía los datos de registro a un sitio web de comercio electrónico B2B, pasa por un proceso de calificación. Si la organización logra calificarse, se incorpora como socio comercial.

Una vez que una organización se incorpora como socio comercial, se identifica al usuario de la organización que inició la solicitud para convertirse en socio comercial como el usuario administrador, y se le otorgan privilegios para incorporar usuarios autorizados adicionales del sitio web de comercio electrónico B2B. Estos usuarios autorizados podrán realizar pedidos en nombre del socio comercial.

## <a name="turn-on-the-b2b-e-commerce-capabilities-feature-in-commerce-headquarters"></a>Activar la característica de funciones de comercio electrónico B2B en la sede central de Commerce

La característica de funciones de comercio electrónico B2B en la sede central de Commerce permite a las organizaciones incorporar socios comerciales y definir usuarios administradores. Esta característica también permite a los administradores crear y administrar usuarios y equipos de socios comerciales, y asignarles roles específicos. Por último, permite a los usuarios socios comerciales crear plantillas de pedidos y utilizar pedidos existentes para volver a encargar productos.

Para activar la característica de funciones de comercio electrónico B2B en la sede central de Commerce, siga estos pasos.

1. Vaya a **Áreas de trabajo \> Administración de características**.
1. En la pestaña **Todos**, filtre por el campo **Módulo** con el término **Retail y Commerce**.
1. Busque y seleccione la característica llamada **Habilitar el uso de funciones de comercio electrónico B2B** y, a continuación, seleccione **Habilitar ahora**.

## <a name="create-a-number-sequence-and-add-it-to-commerce-shared-parameters"></a>Crear una secuencia numérica y agregársela a los parámetros compartidos de Commerce

Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que necesitan identificadores. Para obtener más información sobre las secuencias numéricas, consulte [Información general de secuencias numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Para crear una secuencia numérica y agregársela a los parámetros compartidos de Commerce en la sede central de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Secuencias numéricas \> Secuencias numéricas** y cree una secuencia numérica.
1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros compartidos de Commerce** y agregue la nueva secuencia numérica a la referencia de **Id. de de jerarquía de clientes**.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Configurar el usuario administrador para un nuevo socio comercial

Los socios comerciales potenciales pueden iniciar el proceso de incorporación a un sitio web de comercio electrónico B2B enviando una solicitud de incorporación a través de un vínculo en el sitio. Una vez que un usuario socio comercial potencial selecciona el vínculo, puede proporcionar los detalles necesarios para la incorporación y el registro. Cuando se envía la solicitud, aparece una página de confirmación de envío. Si se aprueba el envío, el solicitante (es decir, el usuario que inició la solicitud de incorporación) se convierte en el usuario administrador del socio comercial.

Para aprobar y configurar un usuario administrador de socio comercial en la sede central de Commerce, siga estos pasos.

1. Vaya a **TI de Retail y Commerce \> Programación de distribución**.
1. Ejecute el trabajo **P-0001** para extraer todas las solicitudes de incorporación de socios comerciales a la sede central de Commerce.
1. Una vez que se haya ejecutado correctamente el trabajo **P-0001**, vaya a **TI de Retail y Commerce \> Cliente** y ejecute el trabajo **Sincronizar clientes y socios comerciales desde el modo asincrónico**. Una vez que se haya ejecutado correctamente este trabajo, las solicitudes de incorporación se crean como registros de clientes potenciales en la sede central de Commerce. El campo **Id. de tipo** de estos registros se establece en **Cliente potencial B2B**.
1. Vaya a **Clientes \> Todos los clientes potenciales** y abra la página de clientes potenciales.
1. Seleccione el registro de cliente potencial del nuevo socio comercial para abrir la página de detalles del cliente potencial.
1. En la pestaña **General**, seleccione **Convertir \> Aprobar/Rechazar** para aprobar o rechazar la solicitud de incorporación. Cuando aparezca un mensaje de confirmación, confirme que desea continuar con el proceso y apruebe la solicitud. Se envía un correo electrónico a la dirección de correo electrónico del solicitante para confirmar que se ha aprobado su organización como socio comercial.

    Después de aprobar la solicitud, el campo **Estado** del registro del cliente potencial se establece en **Aprobado**. Además, se crean dos nuevos registros de clientes en el sistema: un registro de cliente **De tipo organización** para la organización del socio comercial y un registro de cliente **De tipo persona** para el solicitante. También se crea un registro de jerarquía de clientes para el socio comercial. <!--(Please refer to the Org modeling of B2B customer section in this document for more information)-->

1. Vaya a **TI de Retail y Commerce \> Programa de distribución** y ejecuta el trabajo **1010** (**Clientes**) para enviar los registros de clientes y jerarquía de clientes recién creados a la base de datos del canal.

Una vez que se haya aprobado la solicitud y se hayan sincronizado los registros de clientes y jerarquías de clientes con la base de datos del canal, el solicitante podrá iniciar sesión en el sitio web de comercio electrónico B2B con la dirección de correo electrónico que proporcionó al enviar la solicitud. Los usuarios pueden utilizar el flujo de registro para definir la contraseña de su cuenta.

## <a name="onboard-additional-business-partner-users"></a>Incorporar usuarios socios comerciales adicionales

El usuario administrador socio comercial puede incorporar usuarios socios comerciales adicionales al sitio web de comercio electrónico B2B según sea necesario.

Para incorporar usuarios socios comerciales adicionales a un sitio web de comercio electrónico B2B, siga estos pasos.

1. Inicie sesión en el sitio web de comercio electrónico B2B como administrador.
1. Vaya a **Mi cuenta \> Usuarios de la organización \> Ver detalles** y seleccione **Agregar un usuario**.
1. Introduzca la información necesaria y, a continuación, seleccione **Guardar**. El estado del nuevo usuario se establece en **Pendiente**.

    Una vez que se hayan ejecutado los trabajos **P-0001** y **Sincronizar clientes y socios comerciales desde el modo asincrónico**, en la sede central de Commerce se crea un registro de cliente **De tipo Persona**. Este registro de cliente también está asociado con el registro de jerarquía de clientes del socio comercial correspondiente. Además, se envía un correo electrónico a la dirección de correo electrónico del nuevo usuario para notificarle que se ha agregado como usuario de la organización del socio comercial y que ahora puede iniciar sesión en el sitio web de comercio electrónico B2B.

1. Ejecute el trabajo **1010** (**Clientes**) para sincronizar el nuevo usuario del socio comercial con la base de datos del canal.

Una vez que se haya sincronizado el registro del cliente, el estado del usuario en el sitio web de comercio electrónico B2B se establece en **Activo**, y el nuevo usuario podrá iniciar sesión en el sitio web de comercio electrónico B2B utilizando su dirección de correo electrónico. Los usuarios pueden utilizar el flujo de registro para definir la contraseña de su cuenta.

## <a name="edit-business-partner-user-details"></a>Editar los detalles del usuario del socio comercial

Para editar los detalles de los usuarios socios comerciales, siga estos pasos.

1. Inicie sesión en el sitio web de comercio electrónico B2B como administrador.
1. Vaya a **Mi cuenta \> Usuarios de la organización \> Ver detalles**, seleccione el botón **Editar** (símbolo de lápiz), realice los cambios necesarios y, a continuación, seleccione **Guardar**. Los cambios entrarán en vigor cuando se hayan ejecutado los trabajos **P-0001**, **Sincronizar clientes y socios comerciales desde el modo asincrónico** y **1010** (**Clientes**).

## <a name="remove-a-business-partner-user"></a>Quitar un usuario socio comercial

Cuando sea necesario, un administrador puede eliminar los usuarios existentes de una organización socio comercial de la lista de usuarios que pueden acceder al sitio web de comercio electrónico B2B.

Para quitar un usuario socio comercial, siga estos pasos.

1. Inicie sesión en el sitio web de comercio electrónico B2B como administrador.
1. Vaya a **Mi cuenta \> Usuarios de la organización \> Ver detalles** y seleccione el botón **Quitar** (símbolo "X"). Cuando aparezca un mensaje de confirmación, confirme que desea quitar el usuario. El cambio solo surtirá efecto cuando se hayan ejecutado los trabajos **P-0001**, **Sincronizar clientes y socios comerciales desde el modo asincrónico** y **1010** (**Clientes**).

> [!NOTE]
> Al quitar un usuario de la lista de usuarios que pueden acceder al sitio web de comercio electrónico B2B, el registro de cliente correspondiente se quita del registro de jerarquía de clientes del socio comercial. Sin embargo, el registro del cliente en sí no se elimina de la sede central de Commerce.

## <a name="onboard-business-partner-and-users-in-commerce-headquarters"></a>Incorporación de socios comerciales y usuarios en la sede central de Commerce

Los administradores pueden incorporar socios comerciales y usuarios directamente en la sede central de Commerce.

Para incorporar socios comerciales y usuarios directamente en la sede central de Commerce, siga estos pasos.

1. Cree un registro de cliente **De tipo organización** para la organización del socio comercial.
1. Cree registros de clientes **De tipo persona** para usuarios socios comerciales. Asegúrese de especificar una dirección de correo electrónico principal para cada cliente.
1. Para cada registro de cliente **De tipo persona** que haya que designar como usuario administrador de la organización del socio comercial, en la ficha desplegable **Retail**, establezca la opción **Administrador B2B** en **Sí**.
1. Cree un id. de jerarquía de clientes. Escriba un nombre en el campo **Nombre**.
1. En el campo **Organización**, introduzca el cliente de la organización del socio comercial.
1. Seleccione **Agregar** y, a continuación, seleccione un cliente en el campo **Nombre**.
1. Repita este proceso para agregar clientes adicionales a la jerarquía.

## <a name="additional-information"></a>Información adicional

- Todos los trabajos que se mencionan en este tema pueden configurarse para ejecutarse según una programación en un formato por lotes. La expectativa es que los socios comerciales configuren los trabajos por lotes según sea necesario.
- Actualmente, solo se puede designar un registro de usuario/cliente como usuario administrador, y ese rol solo se puede cambiar en la sede central de Commerce. No se ofrece funcionalidad de autoservicio que permita a los socios comerciales designar múltiples administradores o cambiar administradores de sitios web de comercio electrónico B2B.
<!--- The modules and labels of the different fields referenced in the screenshots for e-commerce are only for illustration purposes. Customers have complete control on the placement of the B2B related modules and the labels.-->
- Aunque se pueden definir límites de gasto para los usuarios, aún no se ha implementado el cumplimiento de los límites de gasto durante el proceso de entrada de pedidos.
- Toda la lógica empresarial y la validación de la experiencia de un usuario en un sitio web de comercio electrónico B2B se basan en la configuración del registro del cliente que se asigna al usuario en la sede central de Commerce.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un sitio de comercio electrónico B2B](set-up-b2b-site.md)

[Crear jerarquías de modelado de organización para organizaciones B2B](org-model.md)

[Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B](payment-method.md)

[Establecer límites de cantidad de productos para sitios de comercio electrónico B2B](quantity-limits.md)

[Visión general de las secuencias numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]