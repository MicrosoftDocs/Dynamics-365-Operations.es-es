---
title: Copiar clientes mediante secuencias numéricas compartidas
description: En este tema se explica cómo usar secuencias numéricas compartidas para copiar un cliente en otra entidad jurídica pero conservando el mismo id. de cliente.
author: mikefalkner
manager: aolson
ms.date: 08/31/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 848c5b21afccb544e2b3d26ecc8cadac0c860796
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184149"
---
# <a name="copy-customers-by-using-shared-number-sequences"></a>Copiar clientes mediante secuencias numéricas compartidas

[!include [banner](../includes/banner.md)]

Puede usar secuencias numéricas compartidas para asignar los id. de cliente. Las secuencias numéricas compartidas también le permiten copiar clientes desde una entidad jurídica a otra pero usando los mismos id. de cliente en ambas entidades jurídicas.

## <a name="setup"></a>Configuración

La característica se activa al usar una secuencia numérica compartida para asignar los id. de cliente. Debe usar la misma secuencia numérica en todas las entidades jurídicas en la que desee copiar un cliente. Cambie la secuencia numérica del cliente en la página **Parámetros de clientes** para cada entidad jurídica. Seleccione **Clientes** \> **Parámetros** y, a continuación, la pestaña **Secuencias numéricas**.

También puede configurar las secuencias numéricas de cliente para cada grupo de clientes. Estas secuencias numéricas también se deben compartir. Se usa primero la secuencia numérica para un grupo de clientes. Si no se especifica ninguna secuencia numérica para un grupo de clientes, se usa la secuencia numérica especificada en la página **Parámetros de clientes**.

También puede copiar clientes entre entidades jurídicas si usa id. de clientes manuales. Sin embargo, si intenta copiar un cliente en una entidad jurídica en la que ya existe el id. de cliente, no se iniciará el proceso de copia.

## <a name="copy-a-customer"></a>Copiar un cliente

Para copiar un cliente, seleccione **Nuevo** en la página de lista **Todos los clientes** para abrir el cuadro de diálogo **Crear cliente**. Tenga en cuenta que el nuevo id. de cliente no se asigna inmediatamente. Este comportamiento difiere del comportamiento en versiones anteriores. Dado que aún no ha seleccionado el grupo de clientes, el sistema no puede determinar la secuencia numérica correcta que se usará. Además, no puede determinar si está intentando crear un cliente nuevo o copiar un cliente. Por lo tanto, no se asigna el id. del cliente hasta que no selecciona **Guardar** en la parte inferior del cuadro de diálogo.

Si está creando un cliente nuevo, puede continuar rellenando todos los campos como lo hace normalmente. Cuando haya terminado, y seleccione **Guardar**, verá que el id. del cliente se asignó automáticamente. También, para secuencias numéricas manuales, verá que se usó su id. de cliente manual.

Para copiar un cliente, en el campo **Nombre**, escriba uno o más caracteres que representen al cliente que busca. Un cuadro de diálogo de búsqueda muestra una lista de partes que podrían representar al cliente que busca. Al seleccionar una de las partes, aparece información adicional en el lado derecho del cuadro de diálogo:

- La pestaña **General** muestra el número de teléfono y la dirección de la parte.
- La pestaña **Roles** muestra los roles que la parte seleccionada puede tener y la entidad jurídica donde tiene cada rol.
- La pestaña **Id. de registro de impuestos** muestra los id. de registro de impuestos que están asignados a la parte.

Puede copiar una parte si tiene un rol de cliente y si tiene dicho rol en una entidad jurídica que no sea la entidad jurídica actual. Cuando encuentre una parte que cumpla esos criterios, siga estos pasos.

1. Aparece una opción **Copiar cliente**. Esta opción se establece en **No** de forma predeterminada. Para copiar el cliente en la entidad jurídica actual, establezca la opción en **Sí**. 
2. Aparece​ un campo **Entidad jurídica**. Seleccione la entidad jurídica desde la que copiar el cliente. Si el cliente existe en una entidad jurídica, el campo se establece en esa entidad jurídica de forma predeterminada.
3. Seleccione **Seleccionar**. Se crea el nuevo cliente.

## <a name="validation"></a>Validación

Al copiar un cliente, el sistema intenta guardar la nueva información del cliente. Las validaciones se ejecutan para comprobar que los datos que se copiaron son correctos. Recibe un mensaje de error para cada validación con error. Los mensajes de error explican qué información se debe actualizar. La copia del cliente no se puede guardar hasta que no se corrijan todos los errores de validación.

## <a name="copy-a-customer-by-using-tax-exempt-number-search-feature"></a>Copiar un cliente mediante la función de búsqueda del número de identificación fiscal

También puede copiar clientes mediante la función de búsqueda del número de identificación fiscal que se encuentra en el grupo **Registro** de la pestaña **Cliente** del panel de acciones de la página **Todos los clientes**. El cuadro de diálogo **Búsqueda de NIF** que aparece muestra los números de identificación fiscal, el id. del cliente, el nombre del cliente y la entidad jurídica en la que se usa el identificador fiscal. Solo puede copiar un cliente si se encuentra en una entidad jurídica que no es la entidad jurídica actual. Tras seleccionar un cliente que cumpla este criterio, siga estos pasos.

1. Aparece una opción **Copiar cliente**. Esta opción se establece en **No** de forma predeterminada. Para copiar el cliente en la entidad jurídica actual, establezca la opción en **Sí**. 
2. Seleccione **Seleccionar**. Se crea el nuevo cliente.
