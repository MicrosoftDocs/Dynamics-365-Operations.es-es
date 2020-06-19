---
title: Trabajar con artículos serializados en el PDV
description: Este tema explica cómo administrar artículos serializados en la aplicación de punto de venta (POS).
author: boycezhu
manager: annbe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: eedb64ae04345cb94bdd8cc68de833cfcfd40119
ms.sourcegitcommit: 39981582778b0a62567324452485a6721ca18284
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "3407507"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Trabajar con artículos serializados en el PDV

[!include [banner](includes/banner.md)]

Muchos minoristas venden productos que requieren control de serie. Estos artículos se denominan *artículos serializados*. Algunos minoristas pueden querer mantener números de serie para fines de seguimiento. Otros minoristas pueden querer capturar números de serie durante el proceso de venta, para fines de servicio y garantía. Este tema explica cómo puede administrar artículos serializados en la aplicación de punto de venta (POS) de Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configuración de número de serie

Un artículo se considera un artículo serializado si se le asigna un grupo de dimensiones de seguimiento configurado para permitir números de serie. En la sede central de Commerce, en la página **Grupos de dimensión de seguimiento**, seleccione la opción **Activo** para habilitar los números de serie para el proceso de inventario. Para habilitar los números de serie para el proceso de ventas, seleccione la opción **Activo en el proceso de ventas**.

En la ficha desplegable **Dimensiones de seguimiento**, si la opción **Recibo en blanco permitido** está activada, el número de serie es una entrada opcional durante el proceso de recepción de inventario. Si la opción está desactivada, se requiere el número de serie.

En la ficha desplegable **Números de serie**, si la opción **Control de número de serie** está activada, el número de serie debe ser único por unidad. En otras palabras, no se permiten números de serie duplicados.

## <a name="serialized-items-in-the-receiving-process"></a>Artículos serializados en el proceso de recepción

La operación **Inventario entrante** de la aplicación POS permite a los usuarios realizar las siguientes tareas para los artículos serializados:

- Registre los números de serie con los artículos serializados cuando dichos artículos se reciban en la tienda mediante un pedido de compra.
- Valide los números de serie registrados previamente con los artículos serializados cuando dichos artículos se reciban en la tienda mediante un pedido de compra u orden de transferencia.

> [!NOTE]
> Para usar la operación **Inventario entrante** para registrar o validar un artículo serializado, el artículo debe tener asignado un grupo de dimensiones de seguimiento que esté configurado para permitir números de serie para la opción **Activo**, no la opción **Activo en el proceso de ventas**.

Para comenzar el proceso de recepción, en la operación **Inventario entrante**, puede comenzar en la vista **Recibiendo ahora**, escaneando el código de barras del artículo o introduciendo el id. del artículo. Alternativamente, puede comenzar en la vista **Lista completa de pedidos** seleccionando manualmente el artículo.

Si el artículo que se selecciona o recibe es un artículo serializado, el panel **Detalles** para el elemento contiene un vínculo **Administrar número de serie** que abre la página **Gestión del número de serie**. Alternativamente, puede abrir la página **Gestión del número de serie** bien seleccionando **Número de serie** en la barra de aplicaciones de la vista de detalles del pedido o seleccionando **Administrar número de serie** en el cuadro de diálogo que le aparecerá durante el proceso de recepción. La página **Gestión del número de serie** enumera todas las líneas de número de serie abiertas que están pendientes de registro o validación. Puede haber dos pestañas en esta página: una para el artículo actual y otra para todos los artículos serializados del pedido.

El campo **Estado** de la página **Gestión del número de serie** proporciona información sobre la etapa actual en la que se encuentra cada número de serie:

- **No registrado**: el número de serie no se ha proporcionado o el número de serie registrado previamente aún no se ha validado.
- **Registrando**: el número de serie se ha registrado y guardado localmente en la base de datos de canales de la tienda, o se ha validado el número de serie registrado previamente. Solo los números de serie que tienen un estado de **Registrando** se enviarán a la sede de Commerce cuando termine de recibir.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrar números de serie frente a artículos serializados

Para una orden de compra, un cuadro de diálogo que le aparece durante el proceso de recepción de un artículo serializado ofrece la opción **Administrar número de serie**. Puede seleccionar esa opción para abrir la página **Gestión del número de serie** y comenzar a registrar números de serie. También puede omitir este paso durante el proceso de recepción y proporcionar la entrada más tarde, antes de que se contabilice el recibo.

Por defecto, se muestra la pestaña para el artículo actual. Todas las líneas de números de serie tienen un valor de número de serie vacío y un estado de **No registrado**. Puede escanear códigos de barras de números de serie o puede seleccionar **Número de serie** en la barra de la aplicación para introducir continuamente números de serie en el cuadro de diálogo. Los números de serie que introduce aparecen en la lista, y el estado de las líneas de número de serie se cambia a **Registrando**. El número máximo de números de serie que puede registrar en la lista es igual a la cantidad de recepción. Si comete un error, puede seleccionar **Editar** o **Limpiar** en el panel **Detalles** para realizar cambios en los números de serie que ha introducido.

También puede registrar números de serie en la pestaña **Todos los artículos serializados** de la página **Gestión del número de serie**. En la lista, seleccione el artículo contra el que quiere registrar números de serie.

Durante el registro del número de serie en esta página, se produce la validación de duplicación. Si intenta introducir un número de serie duplicado para un artículo para el que está activado el control de número de serie, recibirá un mensaje de error y deberá proporcionar un número diferente.

### <a name="validate-serial-numbers-on-serialized-items"></a>Validar números de serie en artículos serializados

Para una orden de transferencia, el lado de salida debe registrar previamente los números de serie de los artículos serializados durante el proceso de envío. Para un pedido de compra, el proveedor puede proporcionar información sobre el número de serie a través de un aviso de envío anticipado (ASN), y usted puede registrar previamente los números en los artículos que se enviarán. En ambos casos, los números de serie se conocen antes del recibo. Por lo tanto, en el lado de entrada, solo tiene que validar que recibió lo que se suponía que debía recibir.

Para validar los números de serie, puede abrir la página **Gestión del número de serie**, ya sea durante el proceso de recepción o en cualquier momento antes de que se contabilice el recibo. Para cada artículo serializado que tiene números de serie registrados previamente, todos los números de serie se configuran automáticamente en un estado inicial de **No registrado** en esta página. Para validar los números de serie, puede escanearlos o introducirlos. A medida que se introduce el número de serie, la aplicación valida si coincide con los números de serie registrados previamente. Si coinciden, sus estados cambian a **Registrando**. En caso contrario, recibirá un mensaje de error. El número máximo de números de serie que puede validar en la lista es igual a la cantidad de recepción.

También puede validar números de serie en la pestaña **Todos los artículos serializados** de la página **Gestión del número de serie**. En la lista, seleccione el artículo contra el que quiere validar números de serie.

## <a name="additional-resources"></a>Recursos adicionales

[Operación de inventario entrante en PDV](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)
