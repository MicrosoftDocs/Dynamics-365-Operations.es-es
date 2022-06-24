---
title: Configurar un catálogo externo para la adquisición electrónica de marcaje de salida
description: Este artículo describe el uso de un catálogo externo o del catálogo de marcaje de salida para recopilar información de presupuestos de un proveedor y agregarla a una solicitud.
author: GalynaFedorova
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests, CatExternalCatalogConfiguration, CatCXMLCartLogList
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b109ec1db39240e6816d79092763b4686857676
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882500"
---
# <a name="set-up-an-external-catalog-for-punchout-e-procurement"></a>Configurar un catálogo externo para la adquisición electrónica de marcaje de salida

[!include [banner](../includes/banner.md)]

Con el catálogo externo, puede asegurarse de que la información del producto y de precios que procese posteriormente en Supply Chain Management, sea precisa y actualizada. La solicitud puede aprobarse y convertirse en un pedido de compra y se puede presentar el pedido al proveedor.

Cuando el catálogo externo se configura y un empleado está preparando una solicitud, habrá una opción para redirigir a un sitio externo, el catálogo externo, y devolver la cesta de la compra que se creó en el sitio externo. Esta comunicación se basa en el protocolo cXML y tiene que configurarse entre los sistemas de la organización que compra y la que vende.

Para establecer la comunicación, el proveedor tiene que proporcionar datos que usted utilizará en la configuración del catálogo externo, como identidad, dominio de la empresa del comprador, por ejemplo, “DUNS” y “número DUNS”, credenciales y el URL para acceder al catálogo de proveedores.

## <a name="setting-up-an-external-catalog"></a>Configuración de un catálogo externo

El catálogo externo debe habilitar que un empleado que especifique una solicitud de compra sea redirigido a un sitio externo para seleccionar productos. Los productos que el empleado seleccione en el catálogo externo se devuelven con información de precio actualizada y de aquí se pueden agregar a la solicitud de compra. La intención no es permitir a los empleados realizar un pedido en el sitio externo. Cuando configure el catálogo externo, debe asegurarse de que el propósito del sitio al que se puede acceder por el catálogo externo sea recopilar información de presupuestos y no realizar un pedido real.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>Para configurar un catálogo de proveedores externos, complete estas tareas:

1. Configure una jerarquía de categorías de compras. Para obtener más información, consulte [Configurar directivas para jerarquías de categorías de compras](tasks/set-up-policies-procurement-category-hierarchies.md).
2. Registre el proveedor en Supply Chain Management. Para poder configurar las opciones de acceso al catálogo externo del proveedor, antes debe configurar el proveedor y el contacto del proveedor en Microsoft Dynamics 365. También debe agregar el proveedor del catálogo externo a la categoría de compras seleccionada. Para obtener más información acerca del registro de proveedores, consulte [Gestionar usuarios de colaboración de proveedor](manage-vendor-collaboration-users.md). Para obtener información sobre cómo asignar a un proveedor a una categoría de compras, consulte [Aprobar proveedores para categorías de compras específicas](tasks/approve-vendors-specific-procurement-categories.md).
3. Asegúrese de que las unidades de medida y la divisa que usa el proveedor se han configurado. Para obtener información sobre cómo crear una unidad de medida, consulte [Gestionar unidades de medida](../pim/tasks/manage-unit-measure.md).
4. Configure el catálogo de proveedores externos con los requisitos del sitio del catálogo externo de su proveedor. Para obtener más información sobre esta tarea, consulte [Configurar el catálogo de proveedores externos](#configure-the-external-vendor-catalog).
5. Pruebe la configuración del catálogo externo del proveedor para comprobar que sea válida y que se puede acceder al catálogo externo del proveedor. Use la acción **Validar la configuración** para validar el mensaje de configuración de la solicitud que haya definido. Este mensaje debería hacer que se abra el sitio de catálogo externo del proveedor en una ventana del navegador. Durante la validación, no podrá pedir artículos y servicios del proveedor. Para pedir artículos y servicios, debe acceder al catálogo del proveedor a través de una solicitud de compra.
6. Active el catálogo externo mediante el botón **Activar catálogo** en la página **Catálogos externos** . El catálogo externo deberá activarse antes de que los empleados puedan usarlo. Puede desactivar el catálogo externo en cualquier momento.


## <a name="configure-the-external-vendor-catalog"></a>Configurar el catálogo de proveedores externos

Esta sección proporciona más detalles sobre la tarea 4 de la sección anterior.

1. Escriba un nombre y una descripción para el catálogo externo del proveedor. El nombre que escriba aparecerá en el carro que representa el catálogo externo que se muestra a los empleados que crean una solicitud. Los empleados pueden hacer clic en el carro para abrir el catálogo en el sitio del catálogo externo del proveedor.
2. Agregue una imagen mediante la acción **Imagen del catálogo externo** . La imagen aparecerá en el carro que representa el catálogo externo que se muestra a los empleados que crean una solicitud. Tenga en cuenta que la anchura y la altura de la imagen deben ser iguales. De lo contrario, la imagen no se muestra correctamente.
3. Seleccione si la página web del catálogo externo del proveedor debe aparecer en la misma ventana de explorador en la que el empleado ha creado la solicitud, o abrirse en una ventana nueva.
4. Seleccione el proveedor para el catálogo. En el lista **Entidades jurídicas** existe una fila para cada entidad jurídica donde el proveedor está configurado. Para permitir que los usuarios soliciten productos directamente del catálogo del proveedor en algunas personas jurídicas pero no otras, puede usar el botón **Impedir acceso** o **Permitir acceso** para cada entidad jurídica donde desea que el catálogo esté o no disponible.
5. En el campo **Caducidad predeterminada (días)**, escriba el número de días durante el cual un presupuesto recibido del catálogo externo es válido y se puede usar para comprar al proveedor externo. Cuando se crea un presupuesto y se recupera del sitio del catálogo externo del proveedor; el presupuesto será válido a partir de la fecha del sistema actual y seguirá siendo válido durante el número de días que escriba en este campo.
6. Haga clic en el botón **Agregar** para empezar a asignar las categorías de compras al catálogo externo. A continuación, en la lista de nombre de categoría, seleccione una categoría. La lista de categorías es un superconjunto de categorías de compras a las que se ha asignado al proveedor en todas las entidades jurídicas configuradas para dicho proveedor.

    > [!NOTE]
    > Las directivas de compra se utilizan para permitir o restringir el acceso a las categorías para la entidad jurídica compradora o unidad operativa receptora. El marcaje de salida a un catálogo externo requiere que se permita el acceso al menos a una de las categorías de compras asignada al catálogo.

7. Configure el mensaje de solicitud de configuración de cXML que se enviará al proveedor. El formato del mensaje generado automáticamente es la plantilla mínima que se requiere para iniciar una sesión. Rellene los valores de las etiquetas.

En cualquier momento, puede recargar la plantilla de mensajes generada por el sistema haciendo clic en **Restaurar formato de mensaje**. Tenga en cuenta que si restaura el formato del mensaje, el mensaje actual se sustituye por el formato de mensaje generado automáticamente, que tiene etiquetas vacías.

### <a name="cxml-setup-message"></a>Mensaje de configuración de cXML
A continuación verá una descripción de las etiquetas que se incluyen en la plantilla:

| Campo | Descripción | 
|---------|---------|
|< Header >< From >< Credential domain=”” >|El dominio de la empresa del comprador.|
|< Header >< From >< Credential>< Identity >< /Identity > | La identidad de la empresa del comprador.|
|< Header >< To >< Credential domain=”” > | El dominio de la empresa del proveedor.|
|< Header >< To >< Credential>< Identity >< /Identity> | La identidad de la empresa del proveedor.|
|< Header >< Sender >< Credential domain=”” > | El dominio de la empresa del comprador.|
|< Header >< Sender >< Credential >< Identity >< /Identity> | La identidad de la empresa del comprador.|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|El secreto compartido para la empresa del comprador.|
|< Request deploymentMode=”” >|La implementación de prueba o en producción.|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|El URL del extremo de marcaje de salida del proveedor.|

### <a name="extrinsic-elements"></a>Elementos extrínsecos

Un elemento extrínseco es información adicional, como un nombre de usuario basado en un usuario que marca la salida. Se establece el elemento extrínseco cuando se realiza el marcaje y puede enviarse en el mensaje de configuración de la solicitud.
Su proveedor puede tener un requisito para recibir un elemento extrínseco en la solicitud de configuración. En ese caso, debe agregar el elemento extrínseco a la lista de elementos extrínsecos en la sección **Formato de mensaje** de la página **Catálogo externo**.
Especifique un nombre para el elemento extrínseco que el proveedor pueda reconocer y asignar a un valor. Las opciones de valores son: nombre de usuario, correo electrónico del usuario o valor aleatorio.
Para obtener más información acerca del protocolo de cXML, consulte el [sitio web cXML.org](http://cxml.org/).

## <a name="post-back-message"></a>Mensaje de confirmación
El mensaje de confirmación es el mensaje que se recibe del proveedor cuando el usuario completa la compra en el sitio externo y vuelve a Supply Chain Management. Los mensajes de confirmación no se pueden configurar. Los mensajes se basan en la definición del protocolo cXML. A continuación se indica la información que puede formar parte del mensaje de confirmación que se recibe en una línea de solicitud.

| Mensaje recibido del proveedor | Copiado a línea de pedido|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |Cantidad|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|Identificador de artículo externo|
|< ItemDetail>< UnitPrice >< Money currency=”” >| Divisa|
|< ItemDetail >< UnitPrice >< Money >< /Money >| Precio unitario|
|< ItemDetail >< Description ShortName=”” >|Nombre del producto|
|< ItemDetail >< Description >< /Description >|Incluido en la descripción del artículo; nombre del producto si ShortName no se especifica.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|Unidad|
|< ItemDetail >< Classification >< /Classification >|Incluido en la descripción del artículo|
|< ItemDetail >< Classification domain=”” >|Incluido en la descripción del artículo|

## <a name="delete-an-external-catalog"></a>Eliminar un catálogo externo
Eliminar un catálogo externo con la acción Eliminar en la página.

Si se ha solicitado un producto del catálogo de proveedores externo, no se podrá eliminar el catálogo de proveedores externo. En su lugar, el estado del catálogo de proveedor externo se establece como inactivo. Si desea impedir el acceso al sitio del catálogo del proveedor externo, pero no eliminarlo, cambie el estado del catálogo externo a Inactivo.

## <a name="additional-resources"></a>Recursos adicionales

- [Mejoras de cXML de compra](purchasing-cxml-enhancements.md)
- [Usar catálogos externos para la adquisición electrónica de marcaje de salida](use-external-catalogs-for-punchout.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]