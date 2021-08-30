---
title: Configurar jerarquías organizativas
description: En este tema se describe cómo configurar jerarquías organizativas en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ce0732f32a9a80fc5b0ede7ae9f1c1ab9a68a89b2fb0b1821cb5df123ca5ca4a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746025"
---
# <a name="set-up-organization-hierarchies"></a>Configurar jerarquías organizativas

[!include [banner](includes/banner.md)]

En este tema se describe cómo configurar jerarquías organizativas en Microsoft Dynamics 365 Commerce.

Antes de crear canales, debe asegurarse de configurar sus jerarquías organizativas.

Puede usar jerarquías organizativas para ver e informar de su negocio desde diferentes perspectivas. Por ejemplo, puede configurar una jerarquía para informes estatutarios, legales o de impuestos. A continuación, puede configurar otra jerarquía para elaborar información financiera que no sea legalmente necesaria pero que se use para informes internos.

Antes de crear una jerarquía organizativa debe crear organizaciones. Para obtener más información, consulte [Crear entidades jurídicas](channels-legal-entities.md) o [Crear unidades operativas](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).


Para obtener más información, consulte los siguientes temas.
- [Visión general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [Planificar su jerarquía organizativa](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [Crear una jerarquía organizativa](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a>Crear una jerarquía organizativa

Para crear una jerarquía organizativa, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Jerarquía organizativa**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Nombre**, escriba un valor.
1. En la sección **Propósito**, seleccione **Asignar propósito**.
1. En la lista, busque y seleccione el registro deseado. Seleccione un propósito para asignar a su jerarquía organizativa.
1. En la sección **Jerarquías asignadas**, seleccione **Agregar**.
1. En la lista, marque la fila seleccionada. Busque la jerarquía que acaba de crear.
1. Seleccione **Aceptar**.

La siguiente imagen muestra un ejemplo de jerarquía organizativa creada para un conjunto de tiendas ficticio llamado "Adventure Works".

![Ejemplo de jerarquía organizativa.](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a>Agregar organizaciones a una jerarquía

Para agregar organizaciones a una jerarquía, siga estos pasos.

1. En la lista, busque y seleccione el registro deseado. Seleccione su jerarquía.
1. En el panel de acciones, seleccione **Ver**.
1. Agregue organizaciones según sea necesario.
1. Para agregar una organización, seleccione **Editar** y, a continuación, seleccione **Insertar**. Cuando haya terminado de realizar cambios, puede guardar un borrador o publicar los cambios.

En la siguiente imagen se muestra una entidad jurídica agregada en la raíz de la jerarquía con cuatro centros de coste agregados para los canales "Centro comercial", "Tienda de ofertas", "En línea" y "Centro de llamadas". Se pueden agregar a cada uno de ellos varios canales minoristas, de centro de llamadas y en línea.

![Ejemplo de diseñador de jerarquías.](media/hierarchy-designer.png)

## <a name="additional-resources"></a>Recursos adicionales

[Información general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planificación de su jerarquía organizativa](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Crear entidades jurídicas](channels-legal-entities.md)

[Crear unidades operativas](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[Resumen de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
