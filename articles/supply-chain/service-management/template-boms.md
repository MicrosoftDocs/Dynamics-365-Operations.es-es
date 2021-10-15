---
title: Plantilla de L. MAT
description: Una plantilla de lista de materiales (L. MAT) le proporciona una lista estandarizada de componentes para objetos de servicio de los que se realiza un mantenimiento periódico.
author: kamaybac
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d34502d74590595f26ba5aae78158ed893a095df
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571316"
---
# <a name="template-boms"></a>Plantilla de L. MAT

[!include [banner](../includes/banner.md)]

Una plantilla de lista de materiales (L. MAT) le proporciona una lista estandarizada de componentes para objetos de servicio de los que se realiza un mantenimiento periódico. Los componentes que aparecen en la plantilla de L. MAT representan los subcomponentes individuales del objeto de servicio. Aplicando una L. MAT de plantilla a un objeto de servicio, puede realizar un registro de los subcomponentes que se han sustituido en el objeto de servicio.

Para aplicar una plantilla de L. MAT a un acuerdo de servicio o a un pedido de servicio, debe vincularla a la relación de objetos de servicio.

> [!NOTE]
> Puede aplicar solo una plantilla de L. MAT con un objeto de servicio.

## <a name="create-a-template-bom"></a>Crear plantilla de L. MAT manual

La siguiente tabla contiene información sobre los distintos métodos que puede usar para crear una plantilla de L. MAT.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Método</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Producción</p></td>
<td><p>La L. MAT de plantilla se basa en un pedido de producción. Esta opción solo es aplicable si trabaja en un ambiente de producción. La ventaja es que dispone de un listado actual y detallado de los componentes que componen un artículo.</p></td>
</tr>
<tr class="even">
<td><p>Artículo BOM</p></td>
<td><p>La L. MAT de plantilla se basa en una L. MAT de artículo. La L. MAT del artículo, a diferencia de la L. MAT de producción, es una lista estática de los componentes que componen un artículo.</p></td>
</tr>
<tr class="odd">
<td><p>Plantilla existente</p></td>
<td><p>La plantilla se basa en una L. MAT de plantilla existente.</p></td>
</tr>
<tr class="even">
<td><p>Manual</p></td>
<td><p>Si sabe qué piezas de repuesto son las que se sustituyen habitualmente en un objeto de servicio, podrá crear su L. MAT de plantilla de forma manual. Este método ayuda a garantizar que los componentes que se incluyen en la plantilla reflejen los requisitos reales de su área de trabajo.</p></td>
</tr>
</tbody>
</table>

## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>Aplicar la L. MAT de plantilla a un acuerdo de servicio o en un pedido de servicio

Puede aplicar una plantilla de L. MAT a un acuerdo de servicio, a un pedido de servicio, o a ambos. El primero normalmente abarca una relación de largo plazo con un cliente. El historial de sustituciones registradas en la L. MAT de servicio está formado por datos de los que podrá disponer para el acuerdo de servicio.

También puede aplicar una L. MAT de plantilla a un pedido de servicio para registrar el historial del servicio que se ha realizado en un objeto de servicio.

## <a name="copy-the-history-of-a-service-bom"></a>Copiar el historial de una L. MAT de servicio

Puede copiar el historial de una línea de L. MAT de servicio de un acuerdo de servicio a otro. Al copiar el historial de servicio entre los acuerdos de servicio, puede conservar el registro de las sustituciones realizadas a un artículo.

### <a name="example"></a>Ejemplo

Ha configurado un acuerdo de servicio de tres años para el vehículo de un cliente. Durante ese período, el cliente se acostumbrará al buen servicio prestado por la empresa. Por lo tanto, cuando expire el contrato, el cliente deseará configurar uno nuevo. Ahora puede negociar un acuerdo más favorable para la empresa. Dado que el registro de componentes sustituidos puede resultar de utilidad en el futuro, puede copiar el historial de la L. MAT de servicio en el nuevo acuerdo.

## <a name="modify-the-template-bom"></a>Modificar la plantilla de L. MAT

Si una plantilla de L. MAT no se ha vinculado a un objeto de servicio, puede modificar o eliminar las líneas. Una vez vinculada la plantilla de L. MAT a un objeto de servicio, puede modificar solo la versión local de la L. MAT. Si desea duplicar la configuración de una versión local de una plantilla de L. MAT, puede crear una nueva plantilla de L. MAT basada en la versión local. Para obtener más información, consulte [Modificar un L. MAT de servicio](modify-service-bom.md).

Si reemplaza un artículo que esté en la L. MAT, puede registrar la sustitución en la línea de L. MAT en el diseñador de L. MAT. Si lo desea, también es posible crear una línea de pedido de servicio para el objeto de sustitución. Si crea una línea de pedido de servicio, puede facturar el artículo de sustitución. Si no crea una línea de pedido de servicio para una sustitución, el registro de sustitución se conserva para realizar un seguimiento del historial del objeto de servicio.

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>Cambiar el modo en que se muestra la información de la línea de L. MAT

Puede cambiar el modo que se muestra la información de la línea de L. MAT para todas las listas L. MAT de plantilla y de servicio. Los cambios se aplican a todas las plantillas de L. MAT y L. MAT de servicio. Esto incluye a todas las que estén asociadas a los objetos de servicio.

## <a name="set-up-number-sequences-for-template-boms"></a>Configurar secuencias numéricas para la plantillas de L. MAT

Para usar las L. MAT de plantilla, debe configurar dos secuencias numéricas. Configure una secuencia numérica para la L. MAT de plantilla y otra para el número de línea del historial de L. MAT.

> [!NOTE]
> Las secuencias numéricas se usan para asignar identificadores a los registros que los necesiten. Antes de poder asignar una secuencia numérica a una L. MAT de plantilla o a un número de línea del historial de L. MAT, debe configurar los códigos de secuencias numéricas.

## <a name="set-up-number-sequences"></a>Configurar secuencias numéricas

1. En la página de lista **Secuencias numéricas**, cree las secuencias numéricas para las plantillas de L. MAT. y el número de línea del historial de L. MAT.
1. Seleccione **Gestión de servicio** \> **Configuración** \> **Parámetros de la gestión de servicio**.
1. Seleccione **Secuencias numéricas** y, a continuación, seleccione un código de secuencia numérica para las referencias de la secuencia numérica que haya creado en el formulario **Secuencias numéricas**.
1. Cierre el formulario para guardar los cambios.

> [!NOTE]
> El número de línea del historial de L. MAT lo usa el sistema para asociar las transacciones del historial de L. MAT a un acuerdo de servicio o a un pedido de servicio. El número no se muestra en la interfaz de usuario.

## <a name="see-also"></a>Consulte también

[Crear plantilla de L. MAT manual](create-template-bom.md)

[Gestionar plantilla de L. MAT en las relaciones de objetos de acuerdos de servicio](manage-template-boms-on-object-relations.md)

[Modificar un L. MAT de servicio](modify-service-bom.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
