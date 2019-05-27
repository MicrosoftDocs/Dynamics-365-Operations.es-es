---
title: Ver y exportar descripciones de campos
description: En este artículo se describe cómo ver las descripciones de campos y cómo utilizar la página Descripciones de campos para exportar las descripciones.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7be1495fc42b5f19884a7d9df747f6bec9b64680
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561700"
---
# <a name="view-and-export-field-descriptions"></a>Ver y exportar descripciones de campos

[!include [banner](../includes/banner.md)]

En este artículo se describe cómo ver las descripciones de campos y cómo utilizar la página Descripciones de campos para exportar las descripciones.

Microsoft Dynamics 365 for Finance and Operations tiene descripciones de campos para algunos de los campos más complejos. Estas descripciones aparecen al colocar el puntero sobre un campo. También puede ver y exportar descripciones en la página **Descripciones de campos**.

No todas las páginas tienen descripciones de campos. Queremos proporcionar descripciones solo para los campos más complejos y no donde el uso del campo es evidente. Por tanto, algunas páginas no tienen descripciones de campos, otras tienen algunas descripciones y algunas de las páginas más complejas, como muchas de las páginas de parámetros, tienen muchas descripciones.

Si tiene acceso al entorno de desarrollo de Finance and Operations, puede agregar nuevas descripciones de campo y personalizar las existentes. Por ejemplo, puede agregar información específica de la empresa a una descripción de campo. Para obtener más información, consulte [Personalizar ayuda de campo](../../dev-itpro/user-interface/customize-field-help.md).

## <a name="see-field-descriptions-in-the-user-interface"></a>Consulte las descripciones del campo en la interfaz del usuario.

Puede ver descripciones de los campos manteniendo el ratón sobre un campo. Si no hay ninguna descripción disponible, verá el nombre del campo al mantener el puntero sobre el campo.

> [!NOTE]
> En Dynamics AX 7.0 (febrero de 2016), las descripciones de campos solo se pueden ver en la página **Descripciones de campos**.

En la ilustración siguiente se muestra la descripción del campo que aparece al mantener el puntero sobre el campo **Bloquear artículos durante el recuento**.

[![Ejemplo de una descripción de campo](./media/field-description.png)](./media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>Utilice la página Descripciones de campos para ver y exportar la ayuda de campo.

La página **Descripciones de campos** permite ver y exportar descripciones de campos. Puede ver las descripciones que están disponibles para una página a la vez.

### <a name="view-the-descriptions-for-a-page"></a>Vea las descripciones de una página

Para ver las descripciones de una página, siga este paso.

- En el campo **Seleccionar una página**, escriba el nombre de la página. De forma alternativa, haga clic en la flecha para abrir una lista de todas las páginas y, a continuación, examine o filtre la lista.

Puede usar el nombre de la página que se muestra en la interfaz de usuario (IU) (por ejemplo, **Clientes**) o el nombre de código (nombre AOT) que está disponible al hacer clic con el botón secundario en una página (por ejemplo, **CustTable**).

Para obtener información sobre las diversas maneras de filtrar la lista de páginas, vea la sección "Buscar una página" más adelante en este artículo.

Si establece la opción **Incluir campos sin descripción** en **Sí**, se muestran todos los campos de la página, incluso si no tienen una descripción de campo.

### <a name="export-the-descriptions-for-a-page"></a>Exportar las descripciones de una página

Para exportar las descripciones de una página, siga estos pasos.

1. En el campo **Seleccionar una página**, seleccione una página.
2. Haga clic en el botón **Abrir de Microsoft Office** que se encuentra en la esquina superior derecha y, a continuación, haga clic en **FieldDescriptionTmp**.

### <a name="searching-for-a-page"></a>Buscar una página

Hay varias formas de buscar una página en el campo **Seleccionar una página**. En muchos casos deberá hacer clic en la flecha del campo **Seleccionar una página** para abrir la lista desplegable y, a continuación, seleccione entre una lista de páginas.

- Escriba una parte del nombre y, a continuación, abra la lista desplegable para seleccionar entre una lista de páginas filtrada.
- Abra la lista desplegable y, a continuación, haga clic en el encabezado **Nombre de página** en la parte superior de la liste o en el encabezado **Nombre AOT de página**. Aparece un cuadro de diálogo, donde puede utilizar las opciones de filtrado avanzadas, como **El nombre de la página empieza por**.
- Escriba el nombre completo de la página. Al usar esta opción, es mejor abrir la lista desplegable y ver qué más se encuentra en la lista, aunque se muestren las descripciones de campo.

    - Si hay una única coincidencia exacta del nombre, se muestran las descripciones de campo de esa página.
    - Si hay más de una coincidencia exacta, no se muestran descripciones. Debe abrir la lista desplegable y seleccionar la página que desea.
    - Si el nombre que ha escrito forma parte del nombre de otra página, vea las descripciones de la página. Sin embargo, si abre la lista desplegable, consulte las páginas adicionales que contienen ese nombre.

Por ejemplo, no se muestran descripciones al escribir **Recuento** en el campo **Seleccionar una página**. Abre la lista desplegable y ve que hay dos páginas con el nombre **Recuento**, así como varias páginas que contienen la palabra "Recuento" en el nombre. Si selecciona la página que tiene el nombre AOT **InventJournalCount**, se muestran las descripciones de campo de esa página. Sin embargo, si vuelve a abrir la lista desplegable, verá que, ahora, la lista contiene todas las páginas que tienen "InventJournalCount" como parte de su nombre de AOT.

## <a name="troubleshooting"></a>Solución de problemas

En esta sección se proporciona información que le ayudará a solucionar los problemas que puedan surgir al utilizar las descripciones de campos.

### <a name="i-cant-find-a-field-description"></a>No puedo encontrar una descripción de campo

Estamos en proceso de agregar descripciones de campos más complejos. Si necesita ayuda para un campo determinado, háganoslo saber agregando un comentario en este tema.

### <a name="the-field-description-isnt-helpful"></a>La descripción de campo no es útil

Háganoslo saber agregando un comentario en este tema. Si es posible, describa la información adicional que requiera.

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>No encuentro un campo en la página de Descripciones de campos

Para mostrar todos los campos de una página, establezca la opción **Incluir campos sin descripción** en **Sí**. Haga clic en el campo **Seleccionar una página** para comprobar que ha seleccionado la página correcta. Si el nombre que ha escrito forma parte de otro nombre de campo, probablemente haya seleccionado la página con el nombre más largo.

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>No encuentro una página en la página de Descripciones de campos

Para obtener información sobre las diversas maneras de encontrar páginas, vea la sección "Buscar páginas" anteriormente en este artículo. Si ha escrito el nombre exacto de la página, es posible que las descripciones de campo no se muestren si más de una página tiene el mismo nombre. Haga clic en la flecha del campo **Seleccionar una página** para abrir una lista filtrada de las páginas que están disponibles.

## <a name="additional-resources"></a>Recursos adicionales

[Ayuda para personalizar campo](../../dev-itpro/user-interface/customize-field-help.md)
