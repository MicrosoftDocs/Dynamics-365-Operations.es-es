---
title: Oferta cerrada para solicitudes de presupuesto
description: Este tema describe cómo configurar ofertas selladas para mantener en secreto las respuestas a las ofertas del proveedor hasta que el personal de compras las abra.
author: GalynaFedorova
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: dfc19646d6724627c8a25bcfc8a6b2a70a73c261
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675160"
---
# <a name="sealed-bidding-for-rfqs"></a>Oferta cerrada para solicitudes de presupuesto

[!include [banner](../includes/banner.md)]

Las ofertas selladas mantienen en secreto las respuestas a las ofertas del proveedor hasta que el personal de compras las abra. Todas las ofertas que están relacionadas con una solicitud de presupuesto (RFQ) están disponibles primero para abrirse al vencimiento de la oferta. Antes de que se abra una oferta, solo los usuarios que tienen roles de usuario dedicados y que representan al proveedor pueden acceder a ella.

> [!IMPORTANT]
> La modificación o ampliación de formularios, o la creación de nuevos formularios o lógica empresarial puede anular la protección que ofrece Microsoft para las licitaciones selladas. Usted asume el riesgo de usar modificaciones, extensiones, nuevos formularios o lógica comercial, o la imposibilidad de usar la función de licitación sellada debido a dichas modificaciones, extensiones, nuevos formularios o lógica comercial.  Microsoft no es responsable de los daños que surjan de las modificaciones o extensiones de los formularios, o cualquier formulario nuevo o lógica empresarial que usted cree, o que un tercero cree para usted. Microsoft no proporciona soporte técnico o de otro tipo para modificaciones, extensiones, nuevos formularios o lógica comercial que usted haya realizado o que un tercero haya realizado en su nombre. Usted es el único responsable de cumplir con todas las leyes o regulaciones aplicables en relación con las licitaciones selladas.

## <a name="how-bids-are-kept-secure"></a>Cómo se mantienen seguras las ofertas

Las ofertas selladas utilizan cifrado asimétrico para cifrar la clave de cifrado de oferta (KEK) y cifrado simétrico para cifrar la oferta real. El sistema se integra con Microsoft Azure Key Vault para generar y administrar las claves de cifrado que se utilizan para cifrar las ofertas selladas. Cada oferta tiene su propia clave de cifrado. Este cifrado se mantiene seguro en un almacén de claves que es propiedad de la organización que ejecuta Dynamics 365 Supply Chain Management. El sistema accede al almacén de claves bajo demanda, siempre que se requiera cifrado y descifrado.

## <a name="setup-and-configuration"></a>Establecimiento y configuración

En esta sección se describen los requisitos previos que deben cumplirse antes de poder enviar solicitudes de oferta que requieran ofertas selladas.

### <a name="step-1-set-up-user-access-to-sealed-bidding"></a>Paso 1: configurar el acceso de los usuarios a las ofertas selladas

Cuando utiliza la oferta sellada, solo los usuarios que están configurados como la persona de contacto de un proveedor pueden ver, editar y enviar ofertas para ese proveedor hasta que expire el período de licitación. Estos usuarios deben tener el rol de **Proveedor (externo)** y deben establecerse como una persona de contacto para la cuenta del proveedor. La persona de contacto también debe tener permiso para colaborar con el proveedor, como se describe en [Configurar y mantener la colaboración de proveedores ](set-up-maintain-vendor-collaboration.md).

Dado que los usuarios que tienen los permisos adecuados y que están configurados como contactos de proveedores pueden acceder a las ofertas selladas de un proveedor, es importante realizar un seguimiento de quiénes son esos usuarios. El administrador del sistema que configura los usuarios y los roles de seguridad es responsable de limitar el acceso a las ofertas selladas a aquellos usuarios a los que realmente se les permite verlas.

### <a name="step-2-enable-the-sealed-bidding-feature"></a>Paso 2: habilite la función de oferta sellada

Antes de comenzar a configurar o utilizar esta función, debe asegurarse de que está disponible en su sistema. Los administradores pueden usar el espacio de trabajo **[Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo**: *Adquisición y abastecimiento*
- **Nombre de la función:** *Oferta sellada para solicitud de presupuesto*

### <a name="step-3-set-up-azure-key-vault"></a>Paso 3: configurar Azure Key Vault

Supply Chain Management utiliza claves de cifrado para proteger todas las ofertas selladas y mantenerlas en secreto hasta el momento adecuado. Aprovecha las capacidades de Key Vault para generar y administrar las claves necesarias. Por lo tanto, debe configurar una conexión desde Supply Chain Management a un almacén de claves para habilitar el sistema.

> [!IMPORTANT]
> El almacén de claves que utilice para las licitaciones selladas deben cumplir con los siguientes requisitos:
>
> - Si usa un espacio aislado para el desarrollo y las pruebas, debe tener una bóveda de claves dedicada para el espacio aislado y otra separada para la producción.
> - Cada almacén de claves debe crearse en una suscripción de Azure que sea propiedad de su organización (no la suscripción en la que está ejecutando Supply Chain Management).
> - Cada almacén de claves debe usarse exclusivamente para licitaciones selladas. No debe utilizar sus almacenes de claves de licitación selladas para ningún otro propósito.

Cada oferta recupera su propia clave secreta. Esta clave se utiliza cada vez que un usuario ve, actualiza o abre la oferta.

Key Vault genera la clave que se utiliza para recuperar el secreto cuando el proveedor selecciona **Oferta** en la interfaz de colaboración del proveedor. La clave caduca luego de un tiempo fijo que el gestor de adquisiciones establece en la página **Parámetros de adquisición y abastecimiento** en Supply Chain Management. Una vez que caduque la clave, nadie podrá ver, editar o abrir la oferta. Por lo tanto, es importante configurar la caducidad de la clave para que haya tiempo suficiente para que se complete el proceso de licitación.

En los siguientes tres pasos, configurará la conexión a Key Vault. Primero, configurará un almacén de claves para usar con ofertas selladas. A continuación, configurará Supply Chain Management para comunicarse con el almacén de claves. Finalmente, establecerá el tiempo de vencimiento de la clave.

### <a name="step-4-set-up-a-key-vault-to-use-with-sealed-bidding"></a>Paso 4: configurar un almacén de claves para usar con ofertas selladas

Siga estos pasos para configurar su almacén de claves. El orden de los pasos es importante.

1. Si aún no ha configurado una suscripción de Azure que sea independiente de la suscripción en la que está ejecutando Supply Chain Management, configúrela.
1. Configure un almacén de claves en su almacenamiento de Azure independiente. Para más información, vea [Mantenimiento del almacenamiento de Azure Key Vault](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).
1. Configure su aplicación Supply Chain Management para que funcione como cliente de su almacén de claves. Para más información, vea [Configurar el cliente de Azure Key Vault](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client).

### <a name="step-5-configure-key-vault-parameters-in-supply-chain-management"></a>Paso 5: configurar los parámetros del almacén de claves en Supply Chain Management

Para configurar Supply Chain Management para comunicarse con el almacén de claves durante la licitación sellada, siga estos pasos.

1. Inicie sesión en Supply Chain Management y vaya a **Administracion del sistema \> Configuración\> Parámetros de almacén de claves**.
1. Seleccione **Nuevo** para crear un registro y establecer los siguientes campos para él:

    - **Nombre** – Introduzca un nombre.
    - **Descripción** - Escriba una descripción.
    - **URL de almacén de claves** - Introduzca la URL predeterminada para su almacén de claves.
    - **Cliente de almacén de claves** - Introduzca el ID de cliente interactivo de la aplicación de Active Directory que está asociada con un almacén de claves para autenticación.
    - **Clave secreta de almacén de claves** - Introduzca la referencia secreta del certificado.
    - **Habilitado para licitación sellada** - Establezca esta opción en *Sí*.

![Página de parámetros de almacén de claves](media/sealed-bidding-key-vault-param.png "Página de parámetros de almacén de claves")

> [!NOTE]
> Puede habilitar solo una configuración de almacén de claves para licitaciones selladas a la vez. Antes de deshabilitar una configuración de almacén de claves existente, debe asegurarse de que todas las ofertas selladas que la usan estén abiertas. Inspeccione cada caso de solicitud de presupuesto de tipo *Sellado* y asegúrese de que todas las respuestas estén abiertas.

### <a name="step-6-set-the-key-expiration-time"></a>Paso 6: establecer el tiempo de caducidad de la clave

Para establecer el tiempo de vencimiento que se aplica a la clave que se genera para cada nueva oferta, siga estos pasos.

1. Vaya a **Parámetros de adquisición y abastecimiento \> Configuración \> Parámetros de adquisición y abastecimiento**.
1. En la ficha **Solicitud de presupuesto**, en el campo **Desplazamiento de días**, introduzca el número de días que debe durar el período de solicitud de presupuesto. Cuando se crea una solicitud de presupuesto, la cantidad de días que introduce aquí se agrega a la fecha del sistema para definir la fecha de vencimiento predeterminada para la solicitud de presupuesto.
1. En el campo **Desplazamiento del día de caducidad de la clave de cifrado**, introduzca la cantidad de días que cada clave de cifrado debe ser válida después de su emisión. Una vez que caduque la clave de cifrado, nadie podrá ver, editar o abrir la oferta sellada que la usa.

> [!TIP]
> El valor del campo **Desplazamiento del día de caducidad de la clave de cifrado** no debe ser menor que el valor del campo **Desplazamiento de días**.

### <a name="step-7-set-the-default-bid-type"></a><a name="set-default-bid-type"></a>Paso 7: establezca el tipo de oferta predeterminado

Cada caso de solicitud de presupuesto tiene un tipo de oferta. El tipo de oferta define si ese caso de solicitud de presupuesto ofrece licitación abierta o sellada.

#### <a name="rfq-cases-that-dont-have-a-solicitation-type"></a>Casos de solicitud de presupuesto que no tienen un tipo de solicitud

Para establecer el tipo de oferta predeterminado que se asigna a los nuevos casos de solicitud de presupuesto a los que no se les asigna un tipo de solicitud cuando se crean, siga estos pasos.

1. Vaya a **Parámetros de adquisición y abastecimiento \> Configuración \> Parámetros de adquisición y abastecimiento**.
1. En la ficha **Solicitud de presupuesto**, establezca el campo **Tipo de oferta** como *Sellada*.

#### <a name="rfq-cases-that-have-a-solicitation-type"></a>Casos de solicitud de presupuesto que tienen un tipo de solicitud

Para establecer el tipo de oferta predeterminado que se asigna a los nuevos casos de solicitud de presupuesto a los que se les asigna un tipo de solicitud cuando se crean, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Configuración \>> Solicitud de presupuesto \> Tipo de solicitud**.
1. Cree un nuevo tipo de solicitud o seleccione un tipo de solicitud existente en el que desee utilizar un tipo de oferta de *Sellada*.
1. Establezca el campo **Tipo de oferta** en *Sellada*.
1. Repita estos pasos para cada tipo de solicitud adicional en el que desee implementar la licitación sellada.

> [!TIP]
> No es necesario asignar un tipo de solicitud cuando se crea una nueva solicitud de presupuesto. Si se asigna un tipo de solicitud, el tipo de oferta predeterminado de una solicitud de presupuesto puede recuperarlo. De lo contrario, se puede utilizar el tipo de solicitud predeterminado que se define en los parámetros de adquisición y abastecimiento.

## <a name="the-sealed-bidding-process"></a>Proceso de licitación sellada

La licitación sellada sigue casi el mismo proceso que se describe en [ Resumen de solicitudes de presupuesto (solicitud de presupuesto)](request-quotations.md). La principal diferencia es que los datos de la oferta y sus anexos se mantienen cifrados hasta que se abre la oferta.

> [!IMPORTANT]
> Los [Cuestionarios](/dynamicsax-2012/appuser-itpro/view-and-respond-to-questionnaires) no están cifrados y no deben usarse para recopilar información confidencial

Esta es una visión general del proceso:

1. Puede crear y enviar una solicitud de presupuesto a uno o más proveedores.
1. Los proveedores responden presentando su oferta sellada.
1. Abra las ofertas después de la fecha de vencimiento de la entrada de ofertas.
1. Las ofertas se vuelven visibles y puede evaluarlas y compararlas.
1. Una vez que se acepta una oferta, genera una orden de compra, genera un acuerdo de compra o actualiza una solicitud de compra.

### <a name="create-an-rfq-case-that-uses-sealed-bidding"></a>Crear un caso de solicitud de presupuesto que utilice licitación sellada

El proceso de creación de un caso de solicitud de presupuesto para licitación sellada es casi el mismo que el proceso de licitación no sellada. Para obtener información sobre cómo crear ambos tipos de casos de solicitud de presupuesto, consulte [Crear una solicitud de presupuesto](tasks/create-request-quotation.md). Esta sección destaca algunas consideraciones importantes al crear una solicitud de presupuesto para licitación sellada.

Los casos de solicitud de presupuesto para licitación sellada deben tener un **Tipo de oferta** *Sellada*. Hay tres formas de asignar este valor a un caso de solicitud de presupuesto:

- Establecer el valor directamente en el caso de solicitud de presupuesto después de crearla.
- Definir la oferta sellada como el tipo de oferta predeterminada para todos los casos de solicitud de presupuesto en los parámetros de Adquisición y abastecimiento. (Vea la sección [Establecer el tipo de oferta predeterminado](#set-default-bid-type) anterior en este tema.)
- Cuando cree un nuevo caso de solicitud de presupuesto, seleccione un tipo de solicitud que esté configurado para licitación sellada. (Vea la sección [Establecer el tipo de oferta predeterminado](#set-default-bid-type)).

Para licitación sellada, el valor de **Fecha y hora de vencimiento** de la solicitud de presupuesto establece cuándo se pueden abrir las ofertas enviadas. El valor de **Fecha y hora de vencimiento** de cada línea coincidirá con el valor del encabezado.

No puede cambiar el tipo de oferta después de que se envía un caso de solicitud de presupuesto.

### <a name="vendors-respond-to-an-rfq"></a>Los proveedores responden a una solicitud de presupuesto

Los proveedores que responden a una oferta sellada utilizan el mismo procedimiento que utilizan para responder a las ofertas abiertas, como se describe en [Trabajar con solicitudes de presupuesto en el espacio de trabajo de licitación de proveedores](vendor-collaboration-work-customers-dynamics-365-operations.md#working-with-rfqs-in-the-vendor-bidding-workspace). Para obtener instrucciones detalladas sobre cómo trabajar tanto con ofertas abiertas como con ofertas selladas, consulte [Introducir y comparar ofertas de solicitud de presupuesto y adjudicación de contratos](tasks/enter-compare-rfq-bids-award-contracts.md). La única diferencia entre el procesamiento de ofertas selladas y el procesamiento de ofertas abiertas es que, hasta que expire el período de licitación, los profesionales de adquisiciones no pueden abrir la oferta sellada de un proveedor. Solo una persona de contacto del proveedor puede abrir la oferta sellada de ese proveedor.

> [!IMPORTANT]
> Para licitaciones selladas, los proveedores pueden cargar archivos adjuntos solo en formato PDF. No se aceptarán otros formatos.

Después de que un usuario proveedor registrado seleccione **Oferta** en una solicitud de presupuesto de oferta sellada, puede introducir sus datos de oferta y esos datos se mantendrán seguros. Los proveedores pueden guardar su trabajo mientras preparan una oferta, volver a consultarlo con la frecuencia necesaria y luego enviarlo cuando esté listo. Los proveedores también pueden ver su oferta después de enviarla. Si los proveedores deben cambiar su oferta después de enviarla, pueden recuperarla, actualizarla y volver a enviarla en cualquier momento hasta que expire el período de licitación.

Las siguientes condiciones se aplican durante la licitación sellada:

- Durante la licitación sellada, el sistema crea un diario de *Solicitud de presupuesto*.
- Cuando un proveedor envía una oferta, se crean diarios de solicitud de presupuesto sin líneas que tienen un precio sellado.
- Una vez que se abre el caso, se crean los diarios de solicitud de presupuesto que tienen un precio y una cantidad. Puede acceder a este diario seleccionando **Diarios de solicitud de presupuesto** en la página **Todas las solicitudes de presupuesto**.
- El sistema almacena un registro de cada acción que realizan los usuarios en una oferta sellada. Estas acciones incluyen ver, editar y guardar la oferta. Este registro es visible tanto para el proveedor como para los profesionales de adquisiciones que tienen acceso a la oferta.
- A medida que avanza la oferta, los profesionales de adquisiciones pueden ver su estado. El estado será *El proveedor está realizando una actualización* o *Envío realizado por el proveedor*.
- El estado de las líneas en una oferta sellada permanece *Enviado* hasta que se abra la oferta.
- Si el proveedor opta por rechazar una oferta, la oferta tendrá un estado de **Progreso de respuesta** de *Rechazado por proveedor*. Este estado será visible para el personal de adquisiciones.
- Las respuestas en los cuestionarios **no** se almacenan en forma cifrada en la base de datos. Por lo tanto, no están sellados. Sin embargo, no estarán visibles en la interfaz de usuario de solicitud de presupuesto hasta que se abra el caso.

### <a name="all-sealed-bid-activities-are-logged"></a>Todas las actividades de oferta sellada se registran

Un registro detallado registra todas las actividades y acciones de los usuarios para una oferta. El registro de actividad permite a las organizaciones determinar quién actualizó una oferta durante su vigencia y cuáles fueron las actualizaciones. También permite a las organizaciones confirmar que solo las personas autorizadas accedieron a una oferta sellada. El registro de actividad está disponible en la página **Actividad** de todas las ofertas.

### <a name="review-rfq-activity"></a>Revisar la actividad de solicitud de presupuesto

Cada interacción con la oferta se registra y se puede ver en la página **Actividad**. En la ilustración siguiente se muestra un ejemplo.

![Ejemplo de la página Actividad](media/sealed-bidding-rfq-activity.png "Ejemplo de la página Actividad")

Los proveedores pueden acceder a la página **Actividad** seleccionando **Actividad** en la página **Solicitud de presupuesto de oferta sellada**. El personal de adquisiciones puede acceder seleccionando **Actividad** en la página **Solicitud de presupuesto**. El registro de actividades proporciona una visibilidad completa para los proveedores y el personal de adquisiciones que han accedido a la oferta. Por tanto, puede revelar cualquier acceso no autorizado.

### <a name="unseal-sealed-bids"></a>Abrir ofertas selladas

Cuando el valor de **Fecha y hora de vencimiento** que se configuró para un caso de solicitud de presupuesto de oferta sellada ha pasado, el botón **Abrir**. Seleccione **Abrir** para abrir todas las ofertas para el caso de solicitud de presupuesto seleccionado. Todos los datos de la oferta y los archivos adjuntos se vuelven visibles para que se puedan administrar las respuestas al caso. Además, se crean diarios que contienen los datos de las ofertas enviadas.

El evento de apertura se registra y se puede ver en la página **Actividad**.

### <a name="process-accepted-bids"></a>Procesar ofertas aceptadas

El proceso de comparar y aprobar ofertas previamente selladas es el mismo que el proceso para ofertas abiertas. Para obtener información sobre cómo puntuar, comparar, rechazar y aceptar ofertas sin sellar, consulte [Introducir y comparar ofertas de solicitud de presupuesto y adjudicación de contratos](tasks/enter-compare-rfq-bids-award-contracts.md).

## <a name="the-rfq-activity-log-can-never-be-deleted"></a>El registro de actividad de la solicitud de presupuesto nunca se puede eliminar

Nadie, ni siquiera los administradores y el soporte de Microsoft, pueden editar o eliminar el registro de actividad de la solicitud de presupuesto. Esta restricción ayuda a garantizar la imparcialidad del proceso de licitación sellada. También ayuda a garantizar que se mantenga una pista de auditoría precisa.
