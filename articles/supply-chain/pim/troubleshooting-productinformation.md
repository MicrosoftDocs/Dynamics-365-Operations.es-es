---
title: Solucionar problemas de información del producto
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con información del producto.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5b74c1a769b3f0c3b848a034ed3d1bab76fda7eb5d8d62f4b3608d8706c696dc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778659"
---
# <a name="troubleshoot-product-information"></a>Solucionar problemas de información del producto

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con información del producto.

## <a name="i-cant-delete-a-released-product"></a>No puedo eliminar un producto publicado.

### <a name="issue-description"></a>Descripción del problema

Puede eliminar un producto lanzado y todas sus variantes solo si el producto lanzado no tiene ninguna transacción relacionada.

### <a name="issue-resolution"></a>Solución del problema

Siga estos pasos para eliminar un producto publicado o un producto maestro.

1. Cierre todas las transacciones abiertas para los artículos.
1. Reducir el inventario a 0 (cero).
1. Realizar cierre de inventario.
1. Elimine todas las variantes de producto del producto maestro que desea eliminar.

## <a name="can-i-change-the-item-number-of-a-released-product"></a>¿Puedo cambiar el número de artículo de un producto lanzado?

En la mayoría de los casos, no puede editar los números de artículo de los productos lanzados porque ese cambio hará que los datos se corrompan. Puede editar el número de artículo solo si debe reparar la corrupción de datos causada por un cambio de nombre anterior de la clave principal de ese producto lanzado, como se menciona en la lista de [funciones eliminadas o en desuso para Finance and Operations 10.0.0 con la actualización de la plataforma 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).

Si desea poder editar los números de artículo de los productos lanzados, [vote por esta idea en el portal Ideas](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a>El principio de descarga predeterminado del producto no se ingresa en la línea de lista de materiales.

### <a name="issue-description"></a>Descripción del problema

Cuando agrega un artículo a una línea de lista de materiales (BOM), el sistema no usa la información del principio de descarga predeterminada que está configurada para el artículo. En otras palabras, el principio de descarga del artículo no aparece en la página **Línea de lista de materiales**.

### <a name="issue-resolution"></a>Solución del problema

Si especifica un principio de descarga en una línea de lista de materiales, se aplicará a esa línea de lista de materiales. Sin embargo, si el principio de descarga está en blanco, o si no está configurado en una línea de lista de materiales, el principio de descarga que está configurado en el artículo se aplicará a esa línea de lista de materiales, aunque no se muestre en la línea de lista de materiales.

La lógica predeterminada para otras características de Microsoft Dynamics 365 Supply Chain Management no suele funcionar de esta manera. Sin embargo, el comportamiento actual no se puede cambiar. De lo contrario, algunas personalizaciones existentes que se basan en él podrían romperse.

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a>El sistema me permite guardar códigos de barras duplicados para diferentes artículos o para el mismo artículo que tiene diferentes dimensiones.

Actualmente, el sistema no aplica códigos de barras únicos y la adición de esta restricción sería un cambio radical. De hecho, Microsoft tiene evidencia de que algunas instalaciones de clientes existentes se romperían con este cambio. Sin embargo, consideraremos un cambio de diseño más amplio para habilitar esta función en el futuro.

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a>Recibo el siguiente mensaje de error cuando edito las plantillas de registro de artículos: "No se puede crear la ubicación del almacén porque el artículo no está almacenado. Para almacenar artículos, se debe seleccionar la opción Producto en inventario en el grupo de modelo de artículo asociado ".

### <a name="issue-description"></a>Descripción del problema

Este problema ocurre si sigue estos pasos para intentar crear una plantilla para un artículo que no está en stock.

1. Abra un producto lanzado que no esté disponible.
1. En el panel de acciones, en la pestaña **Opciones**, seleccione **Información de registro**.
1. En el cuadro de diálogo **Información de registro**, seleccione **Plantilla de cuentas de empresa**.

En este caso, recibirá el siguiente mensaje de error:

> No se puede crear la ubicación del almacén porque el artículo no está almacenado. Para almacenar artículos, se debe seleccionar la opción Producto en inventario en el grupo de modelo de artículo asociado.

### <a name="issue-resolution"></a>Solución del problema

El proceso de creación de plantillas de productos requiere una lógica adicional específica del producto. Por lo tanto, no puede usar el botón genérico **Plantilla de cuentas de empresa** para este propósito. En su lugar, siga estos pasos.

1. Abra un producto liberado.
1. En el panel de acciones, en la pestaña **Producto**, en el grupo **Nuevo**, seleccione **Modelo \> Crear plantilla compartida**.

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a>El texto de ayuda predeterminado que se agrega en los atributos del producto no se ingresa en un producto lanzado.

Una descripción y un texto de ayuda que se agregan en los atributos del producto no están visibles o ingresados de forma predeterminada en los productos lanzados. Este comportamiento se debe al diseño.

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a>La cantidad predeterminada que se ingresa difiere cuando se registra desde una lista de materiales y cuando se registra desde una versión de lista de materiales.

### <a name="issue-description"></a>Descripción del problema

De forma predeterminada, cuando agrega un artículo a una lista de materiales, la cantidad se establece en 1 en lugar de la cantidad definida en el campo **Min. ordene la cantidad** en la página **Configuración de orden predeterminada** de un producto seleccionado. Sin embargo, cuando agrega un artículo de una versión de lista de materiales y se seleccionan el artículo y la variante, la cantidad que se ingresa de forma predeterminada tiene en cuenta la cantidad mínima que se establece en la configuración de pedido predeterminada para las dimensiones específicas.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento es esperado. Sin embargo, el hecho de que la lógica difiera en la lista de materiales y la versión de la lista de materiales es un problema conocido. Sin embargo, este comportamiento no se modificará, porque un cambio podría afectar a muchos escenarios de clientes diferentes.

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a>En los detalles del producto publicados, no puedo cambiar las imágenes adjuntas que se cargaron desde la entidad de datos Adjuntos del documento del producto.

### <a name="issue-description"></a>Descripción del problema

Este problema puede ocurrir cuando adjunta una imagen a un elemento mediante la entidad de datos *Adjuntos de documentos del producto*. En este caso, se muestra la imagen del artículo para el artículo. Sin embargo, si selecciona **Cambiar imagen**, no se muestra nada en la lista de imágenes cargadas. Además, no se muestran archivos adjuntos para el artículo.

### <a name="issue-resolution"></a>Solución del problema

La entidad *EcoResProductDocumentAttachmentEntity* (*Adjuntos de documentos del producto*) importa documentos adjuntos para *productos* pero no para *productos lanzados*. (Los productos lanzados también se conocen como *artículos*). Para ver los archivos adjuntos de un elemento en la página **Detalles del producto publicado**, debe utilizar la entidad *EcoResReleasedProductDocumentA AttachmentEntity* (*Adjuntos de documentos de producto liberados*) en su lugar.

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a>El conector de Microsoft Flow muestra el siguiente mensaje de error: "Actualización no permitida para el campo 'ProductNumber'".

### <a name="issue-description"></a>Descripción del problema

Este problema ocurre si intenta actualizar el campo **Número de producto** usando la entidad V2 *Productos lanzados* y Microsoft Flow.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento es esperado. La capacidad de editar el número de producto para un producto lanzado se eliminó en Dynamics 365 Finance and Operations 10.0.0 con la actualización de la plataforma 24 para ayudar a prevenir la corrupción de datos. En casos excepcionales, cuando deba reparar la corrupción de datos causada por un cambio de nombre anterior de la clave principal de un producto lanzado, puede solicitar al Soporte de Microsoft que elimine temporalmente esta restricción.

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a>No puedo crear una variante de producto publicada en otra entidad legal.

### <a name="issue-description"></a>Descripción del problema

Si intenta liberar un producto maestro sin variantes y luego crea las variantes en cada entidad legal (empresa) según sean necesarias, no podrá liberar las variantes mediante el uso de sugerencias de variantes. Tampoco podrá crear las variantes manualmente.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño. Las relaciones de un producto maestro y las dimensiones que el maestro puede tomar se mantienen en un nivel compartido. Por lo tanto, no puede crear las dimensiones disponibles para un producto maestro compartido en la entidad jurídica específica donde se publican esas dimensiones y luego replicar el proceso en cada entidad jurídica donde se requieren las dimensiones. En su lugar, debe cambiar su proceso de lanzamiento para adaptarse al proceso diseñado.

Este es el proceso para lanzar productos.

1. Cree el producto maestro compartido y las dimensiones que se pueden liberar a las entidades legales.
1. Entregue los productos a las personas jurídicas mediante el uso de sugerencias de variantes o agregando manualmente las combinaciones que deberían publicarse.

Alternativamente, puede crear directamente el producto lanzado.

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a>Cuando lanzo una variante en otra empresa, recibo el siguiente mensaje de error: "Ya se ha creado una variante de producto con las dimensiones especificadas".

### <a name="issue-description"></a>Descripción del problema

Si ya se ha lanzado una variante de producto en una empresa A, e intenta liberarla en la empresa B utilizando el botón **Nuevo** en la página **Variantes de producto publicadas**, recibirá el siguiente mensaje de error:

> Ya se ha creado una variante del producto con las dimensiones especificadas.

### <a name="issue-resolution"></a>Solución del problema

El botón **Nuevo** de la página **Variantes de producto publicadas** crea la variante y la libera en el contexto de la empresa. Si la variante ya se ha creado, no puede utilizar **Nuevo** para liberarlo en otra empresa.

Para solucionar el problema, abra la página **Maestro de producto** y seleccione **Liberar producto** para liberar la variante existente en la empresa deseada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]