---
title: Copiar proveedores mediante secuencias numéricas compartidas
description: En este tema se explica cómo usar secuencias numéricas compartidas para copiar un proveedor en otra entidad jurídica pero conservando el mismo id. de proveedor.
author: sunfzam
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 4cea8269082b39e2374ffb3c3dc82def8ce35679
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358474"
---
# <a name="copy-vendors-by-using-shared-number-sequences"></a>Copiar proveedores mediante secuencias numéricas compartidas

[!include [banner](../includes/banner.md)]

Puede usar secuencias numéricas compartidas para asignar los id. de proveedor. Las secuencias numéricas compartidas también le permiten copiar proveedores desde una entidad jurídica a otra pero usando los mismos id. de proveedor en ambas entidades jurídicas.

## <a name="setup"></a>Configuración

La característica se activa al usar una secuencia numérica compartida para asignar los id. de proveedor. Debe usar la misma secuencia numérica en todas las entidades jurídicas en la que desee copiar un proveedor. Cambie la secuencia numérica del proveedor en la página **Parámetros de proveedores** para cada entidad jurídica. Seleccione **Proveedores** \> **Configuración** \> **Parámetros de proveedores** y, a continuación, la pestaña **Secuencias numéricas**.

También puede configurar las secuencias numéricas de proveedor para cada grupo de proveedores. Estas secuencias numéricas también se deben compartir. Se usa primero la secuencia numérica para un grupo de proveedores. Si no se especifica ninguna secuencia numérica para un grupo de proveedores, se usa la secuencia numérica especificada en la página **Parámetros de proveedores**.

También puede copiar proveedores entre entidades jurídicas si usa id. de proveedores manuales. Sin embargo, si intenta copiar un proveedor en una entidad jurídica en la que ya existe el id. de proveedor, no se iniciará el proceso de copia.

## <a name="copy-a-vendor"></a>Copiar proveedor

Para copiar un proveedor, seleccione **Nuevo** en la página de lista **Todos los proveedores** para abrir la página **Todos los proveedores, nuevo registro**. El nuevo id. de proveedor no se asigna inmediatamente. Este comportamiento difiere del comportamiento en versiones anteriores. Dado que aún no ha seleccionado el grupo de proveedores, no se puede determinar la secuencia numérica correcta que se usará. Además, no puede determinar si está intentando crear un nuevo proveedor o copiar un proveedor. Por lo tanto, no se asigna el id. del proveedor hasta que no se seleccione **Guardar** en la parte inferior de la página.

Si está creando un proveedor nuevo, puede continuar rellenando todos los campos como lo hace normalmente. Cuando haya terminado, y seleccione **Guardar**, el id. del proveedor se asigna automáticamente. También, para secuencias numéricas manuales, verá que se usó su id. de proveedor manual.

Para copiar un proveedor, en el campo **Nombre**, escriba uno o más caracteres que representen al cliente que busca. Un cuadro de diálogo de búsqueda muestra una lista de partes que podrían representar al proveedor que busca. Al seleccionar una de las partes, aparece información adicional en el lado derecho del cuadro de diálogo:

- La pestaña **General** muestra el número de teléfono y la dirección de la parte.
- La pestaña **Roles** muestra los roles que la parte seleccionada puede tener y la entidad jurídica donde tiene cada rol.
- La pestaña **Id. de registro de impuestos** muestra los id. de registro de impuestos que están asignados a la parte.

Puede copiar una parte solo si tiene un rol de proveedor y si tiene dicho rol en una entidad jurídica que no sea la entidad jurídica actual. Cuando encuentre una parte que cumpla esos criterios, siga estos pasos.

1. Aparece una opción **Copiar proveedor**. Esta opción se establece en **No** de forma predeterminada. Para copiar el proveedor en la entidad jurídica actual, establezca la opción en **Sí**. 
2. Aparece​ un campo **Entidad jurídica**. Seleccione la entidad jurídica desde la que copiar el proveedor. Si el proveedor existe en una entidad jurídica, el campo se establece en esa entidad jurídica de forma predeterminada.
3. Seleccione **Seleccionar**. Se crea el nuevo proveedor.

## <a name="validation"></a>Validación

Al copiar un proveedor, se intenta guardar la nueva información del proveedor. Las validaciones se ejecutan para comprobar que los datos que se copiaron son correctos. Recibe un mensaje de error para cada validación con error. Los mensajes de error explican qué información se debe actualizar. No se puede guardar la copia del proveedor hasta que no se corrijan todos los errores de validación.

## <a name="copy-a-vendor-by-using-the-tax-exempt-number-search-feature"></a>Copiar un proveedor mediante la función de búsqueda del número de identificación fiscal

También puede copiar proveedores mediante la función de búsqueda del **número de identificación fiscal** que se encuentra en el grupo **Registro** de la pestaña **Proveedor** del panel de acciones de la página **Todos los proveedores**. El cuadro de diálogo **Búsqueda de NIF** que aparece muestra los números de identificación fiscal, el id. del proveedor, el nombre del proveedor y la entidad jurídica en la que se usa el identificador fiscal. Solo puede copiar un proveedor si se encuentra en una entidad jurídica que no es la entidad jurídica actual. Tras seleccionar un proveedor que cumpla este criterio, siga estos pasos.

1. Aparece una opción **Copiar proveedor**. Esta opción se establece en **No** de forma predeterminada. Para copiar el proveedor en la entidad jurídica actual, establezca la opción en **Sí**.
2. Seleccione **Seleccionar**. Se crea el nuevo proveedor.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
