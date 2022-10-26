---
title: 'Grupos de configuración de la solución de Invoice Capture '
description: Este artículo proporciona información general sobre los grupos de configuración en la solución de Invoice Capture .
author: sunfzam
ms.date: 09/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cfe5ae35b4f87a350d944b30a49251081766ad27
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691221"
---
# <a name="invoice-capture-solution-configuration-groups"></a>Grupos de configuración de la solución de Invoice Capture 

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Los usuarios pueden administrar la lista de campos de factura y la configuración de revisión manual para entidades legales mediante el uso de grupos de configuración. Los usuarios pueden establecer configuraciones de factura para diferentes entidades legales en grupos. Todas las entidades legales en el mismo grupo de configuración usan los mismos campos de factura y configuración de revisión manual.

## <a name="manage-configuration-groups"></a>Administrar grupos de configuración

Para administrar grupos de configuración usando la aplicación, vaya a **Configuración** y luego seleccione **Configuración del sistema \> Definir el componente de grupos de configuración**.

Sobre la página **Definir grupos de configuración**, la pestaña principal muestra la lista de grupos de configuración que se han definido. También muestra un grupo de configuración predeterminado. Para cada grupo de configuración, hay las siguientes acciones disponibles:

- **Copiar un grupo de configuración** – Puede crear un nuevo grupo de configuración duplicando un grupo existente. El nuevo grupo tiene los mismos valores que el grupo original para todos los campos excepto **Nombre del grupo** y **Descripción del grupo**. Después de duplicar el grupo de configuración, seleccione **Aceptar**.
- **Eliminar grupos de configuración** – Para eliminar un grupo de configuración, selecciónelo y luego seleccione **Borrar**.

    > [!NOTE]
    > No puede eliminar el grupo de configuración predeterminado.

- **Editar el ID de un grupo de configuración** – Para editar el ID de un grupo de configuración, seleccione el campo **Identificación del grupo** y actualice el valor. El ID de grupo no debe contener espacios ni caracteres especiales, y no debe exceder los 20 caracteres.

    > [!NOTE]
    > El valor del campo **Identificación del grupo** solo se puede actualizar una vez.

- **Editar la descripción de un grupo de configuración** – Para editar la descripción de un grupo de configuración, seleccione el campo **Descripción** y actualice el valor.
- **Cambiar la configuración de revisión manual** – Los usuarios pueden decidir si una factura debe revisarse manualmente. Para cambiar la configuración de revisión manual, seleccione la opción **Necesita revisión manual**. Las siguientes opciones están disponibles:

    - **Siempre revisión manual** – Seleccione esta opción si las facturas en el grupo de configuración siempre requieren revisión manual.
    - **Para errores y advertencias** – Seleccione esta opción si las facturas que contienen mensajes de error o mensajes de advertencia requieren revisión manual.
    - **Para errores** – Seleccione esta opción si las facturas que contienen mensajes de error o mensajes de advertencia requieren revisión manual.

- **Cambiar la configuración de puntuación de confianza** – La puntuación de confianza son metadatos que proporciona la solución de Invoice Capture  para informar sobre la precisión de los datos de factura reconocidos. Cuanto mayor sea la puntuación, más precisos podrían ser los datos reconocidos. La configuración permite a los usuarios definir cuándo se requiere una revisión manual, según la puntuación de confianza. Los usuarios pueden cambiar el umbral de puntuación de confianza para las facturas. Para actualizar la configuración de puntuación de confianza, seleccione el campo **Puntuación de confianza** y actualice el valor.

    Hay dos tipos de alertas para las puntuaciones de confianza:

    - **Advertencia** – Los campos de factura que tienen puntajes de confianza por encima del umbral de advertencia se consideran correctos. El umbral de advertencia debe ser superior al umbral de error e inferior a 100.
    - **Error** – Los campos de factura que tienen puntajes de confianza bajo el umbral de advertencia se consideran incorrectos. Se mostrarán mensajes de error al usuario. El umbral de error debe ser superior a 0 (cero) e inferior al umbral de advertencia. Se mostrarán mensajes de advertencia para los campos de la factura que tengan puntajes de confianza entre el umbral de advertencia y el umbral de error.

- **Administrar campos de factura** – Los usuarios pueden administrar la lista de campos de factura que se muestra en el visor de lado a lado. Sobre la pestaña **Gestión de campos de factura**, seleccione el símbolo de engranaje, seleccione los campos de factura para agregar y luego seleccione **Guardar**. Los campos seleccionados se añadirán a la lista. Para eliminar un campo de factura de la lista, seleccione **Remover** en el campo.

### <a name="manage-file-filters-optional"></a>Administrar filtros de archivos (opcional)

Administrar filtros de archivos permite a los usuarios definir filtros adicionales para los archivos de facturas entrantes. Los archivos que no cumplan con los criterios de filtrado se recibirán y aparecerán en la lista **Archivos recibidos**, pero mostrarán errores de validación de archivos. Este comportamiento difiere del comportamiento de los filtros que se definen en el canal. Para esos filtros, los archivos que no cumplan con los criterios no se recibirán en absoluto. Los usuarios pueden revisar los archivos entrantes y decidir si cada archivo es una factura no válida, y pueden dejarlo obsoleto o incluirlo manualmente para reconocerlo e incluirlo en las facturas capturadas.

Cuando se instala la solución de Invoice Capture , se define un filtro de archivos predeterminado. Este filtro de archivos es global. Si desea una configuración de filtro diferente, puede actualizar el filtro predeterminado. Si un campo es obligatorio, seleccione **Requerido**. 

### <a name="accepted-file-size"></a>Tamaño de archivo aceptado

Puede elegir el tamaño de archivo aceptado.

> [!NOTE]
> Los archivos de más de 20 480 kilobytes (KB) no son compatibles.

### <a name="supported-file-types"></a>Tipos de archivos compatibles

Actualmente se admiten los siguientes tipos de archivo:

- PDF
- PNG
- JPG
- JPEG
- TIF
- TIFF
