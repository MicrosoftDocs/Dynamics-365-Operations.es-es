---
title: Trabajar con artículos serializados en el PDV
description: Este tema explica cómo administrar artículos serializados en la aplicación de punto de venta (POS).
author: boycezhu
manager: annbe
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6ba01abc3d1a4496ec586a621aa03b4981f84d76
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415648"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Trabajar con artículos serializados en el PDV

[!include [banner](includes/banner.md)]

Muchos minoristas venden productos que requieren control de serie. Estos productos se denominan *artículos serializados*. Algunos minoristas pueden querer mantener números de serie en la tienda o el inventario del almacén para fines de seguimiento. Otros minoristas pueden querer capturar números de serie durante el proceso de venta, para fines de servicio y garantía. Este tema explica cómo puede administrar artículos serializados en la aplicación de punto de venta (POS) de Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configuración de número de serie

Un artículo se considera un artículo serializado si se le asigna un grupo de dimensiones de seguimiento configurado para permitir números de serie. En la central de Commerce, en la página **Seguimiento de grupos de dimensiones**, seleccione la opción **Activo** para habilitar los números de serie para el proceso de inventario, o seleccione la opción **Activo en proceso de venta** para habilitar números de serie para el proceso de venta.

En la ficha desplegable **Dimensiones de seguimiento**, active el parámetro **Recibo en blanco permitido** para permitir que el número de serie sea una entrada opcional durante el proceso de recepción de inventario de elemento serializado. La desactivación de este parámetro obliga a que el número de serie sea una entrada obligatoria. Del mismo modo, el parámetro **Problema en blanco permitido** controla si se requiere el número de serie durante el proceso de envío de inventario.

> [!NOTE]
> Para usar las operaciones de PDV **Inventario entrante** e **Inventario saliente** para registrar o validar números de serie frente a un artículo serializado, debe configurar ese artículo para que se asigne un grupo de dimensiones de seguimiento que esté configurado para permitir números de serie para la opción **Activo**, no la opción **Activo en el proceso de ventas**.

## <a name="serial-number-management-page"></a>Página de administración de números de serie

En las operaciones de PDV **Inventario entrante** e **Inventario saliente**, si el artículo que se selecciona, recibe o envía es un artículo serializado, el panel **Detalles** contiene una opción **Administrar número de serie** que se vincula con la página **Administración de números de serie** donde puede registrar o validar los números de serie del artículo. Alternativamente, puede abrir la página **Gestión del número de serie** bien seleccionando la acción **Número de serie** en la barra de aplicaciones de la vista de detalles del pedido o seleccionando la opción **Administrar número de serie** en el cuadro de diálogo que le aparecerá durante el proceso de recepción o envío. 

La página **Gestión del número de serie** enumera todas las líneas de número de serie abiertas que están pendientes de registro o validación. Puede haber dos pestañas en esta página: una para el artículo actual y otra para todos los artículos serializados del pedido.

El campo **Estado** de la página **Gestión del número de serie** proporciona información sobre la etapa actual en la que se encuentra cada número de serie:

- **No registrado**: el número de serie no se ha proporcionado o el número de serie registrado previamente aún no se ha validado (en el proceso de recepción).
- **Registrando**: el número de serie se ha registrado y guardado localmente en la base de datos de canales de la tienda, o se ha validado el número de serie registrado previamente. Solo los números de serie que tienen un estado de **Registrando** se enviarán a la sede de Commerce cuando termine de recibir o el cumplimiento.

## <a name="receive-serialized-items"></a>Recibir artículos serializados

La operación de PDV **Inventario entrante** permite a los usuarios realizar las siguientes tareas para los artículos serializados:

- Registre los números de serie con los artículos serializados cuando dichos artículos se reciban en la tienda mediante un pedido de compra.
- Valide los números de serie registrados previamente con los artículos serializados cuando dichos artículos se reciban en la tienda mediante un pedido de compra u orden de transferencia.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrar números de serie frente a artículos serializados

Para una orden de compra, aparecerá un cuadro de diálogo con la opción **Administrar número de serie** durante el proceso de recepción de un artículo serializado. Puede seleccionar esa opción para abrir la página **Gestión del número de serie** y comenzar a registrar números de serie. También puede omitir este paso durante el proceso de recepción y proporcionar la entrada más tarde, antes de que se contabilice el recibo.

Por defecto, se muestra la pestaña para el artículo actual. Todas las líneas de números de serie tienen un valor de número de serie vacío y un estado de **No registrado**. Puede escanear códigos de barras de números de serie o puede seleccionar **Número de serie** en la barra de la aplicación para introducir continuamente números de serie. Los números de serie que introduce aparecen en la lista, y su estado se cambia a **Registrando**. El número máximo de números de serie que puede registrar en la lista es igual a la cantidad de recepción. Si comete un error, puede seleccionar **Editar** o **Limpiar** en el panel **Detalles** para realizar cambios en los números de serie que ha introducido.

También puede registrar números de serie en la pestaña **Todos los artículos serializados** de la página **Gestión del número de serie**. En la lista, seleccione el artículo contra el que quiere registrar números de serie.

### <a name="validate-serial-numbers-on-serialized-items"></a>Validar números de serie en artículos serializados

Para una orden de transferencia, el lado de salida debe registrar previamente los números de serie de los artículos serializados durante el proceso de envío. Para un pedido de compra, el proveedor puede proporcionar información sobre el número de serie a través de un aviso de envío anticipado (ASN), y usted puede registrar previamente los números en los artículos que se enviarán. En ambos casos, los números de serie se conocen antes del recibo. Por lo tanto, en el lado de entrada, solo tiene que validar que recibió lo que se suponía que debía recibir.

Para validar los números de serie, puede abrir la página **Gestión del número de serie**, ya sea durante el proceso de recepción o en cualquier momento antes de que se contabilice el recibo. Para cada artículo serializado que tiene números de serie registrados previamente, todos los números de serie se configuran automáticamente en un estado inicial de **No registrado** en esta página. Para validar los números de serie, puede escanearlos o introducirlos. A medida que se introduce el número de serie, la aplicación valida si coincide con los números de serie registrados previamente. Si coinciden, sus estados cambian a **Registrando**. En caso contrario, recibirá un mensaje de error. Alternativamente, puede seleccionar directamente un número de serie y luego seleccionar la opción **Validar el número de serie** en el panel **Detalles** para marcar rápidamente ese número de serie como validado. El número máximo de números de serie que puede validar en la lista es igual a la cantidad de recepción.

También puede validar números de serie en la pestaña **Todos los artículos serializados** de la página **Gestión del número de serie**. En la lista, seleccione el artículo contra el que quiere validar números de serie.

## <a name="ship-serialized-items"></a>Enviar artículos serializados

Puede usar la operación de PDV **Inventario saliente** para registrar números de serie respecto a artículos serializados al enviarlos fuera de la tienda actual mediante una orden de transferencia.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrar números de serie frente a artículos serializados

Para transferir orden, aparecerá un cuadro de diálogo con la opción **Administrar número de serie** durante el proceso de envío de un artículo serializado. Puede seleccionar esa opción para abrir la página **Gestión del número de serie** y comenzar a registrar números de serie. También puede omitir este paso durante el proceso de envío y proporcionar la entrada más tarde, antes de que se registre el envío.

Por defecto, se muestra la pestaña para el artículo actual. Todas las líneas de números de serie tienen un valor de número de serie vacío y un estado de **No registrado**. Puede escanear códigos de barras de números de serie o puede seleccionar **Número de serie** en la barra de la aplicación para introducir continuamente números de serie. Los números de serie que introduce aparecen en la lista, y su estado se cambia a **Registrando**. El número máximo de números de serie que puede registrar en la lista es igual a la cantidad de recepción de envío. Si comete un error, puede seleccionar **Editar** o **Limpiar** en el panel **Detalles** para realizar cambios en los números de serie que ha introducido.

También puede registrar números de serie en la pestaña **Todos los artículos serializados** de la página **Gestión del número de serie**. En la lista, seleccione el artículo contra el que quiere registrar números de serie.

Opcionalmente, puede habilitar la validación de la disponibilidad del número de serie durante el registro del número de serie respecto a una orden de transferencia saliente. Con esta validación, si intenta enviar un número de serie que no está disponible en el inventario de la tienda de envío, recibirá un mensaje de error y deberá proporcionar un número diferente.

Para habilitar dicha validación, como requisito previo, debe programar los siguientes trabajos para que se ejecuten de forma periódica:

- **Retail y Commerce** > **Retail y Commerce IT** > **Productos e inventario** > **Disponibilidad de producto con dimensiones de seguimiento**
- **Retail y Commerce** > **Programas de distribución** > **1130** (**Disponibilidad del producto**)

## <a name="additional-resources"></a>Recursos adicionales

[Operación de inventario entrante en PDV](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Operación de inventario de salida en PDV](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)
