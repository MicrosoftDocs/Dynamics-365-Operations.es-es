---
title: Información general de las organizaciones y las jerarquías organizativas
description: Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio.
author: sericks007
ms.date: 01/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.custom:
- "17291"
- intro-internal
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8e8f2c2004582f42c3f464fedf9f3d049b5278f
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7992086"
---
# <a name="organizations-and-organizational-hierarchies-overview"></a>Visión general de las organizaciones y las jerarquías organizativas

[!include [banner](../includes/banner.md)]

Una organización es un grupo de personas que trabajan juntas para llevar a cabo un proceso empresarial o lograr un objetivo. Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio.

## <a name="organizations"></a>Organizaciones

Puede definir los siguientes tipos de organizaciones internas: entidades jurídicas, unidades operativas y equipos.

Todas las organizaciones internas son tipos de la entidad **Parte**. Por tanto, estas organizaciones usan la libreta de direcciones para almacenar información de contactos y direcciones. Un parte, que puede ser una persona o una organización, puede pertenecer a una o varias libretas de direcciones.

### <a name="legal-entities"></a>Entidades jurídicas

Una entidad jurídica es una organización que tiene una estructura jurídicas registrada o legislada. Las entidades jurídicas pueden realizar contratos legales y tienen la obligación de preparar declaraciones para dar a conocer su rendimiento.

Una empresa en un tipo de entidad jurídica. Actualmente, las empresas son el único tipo de entidad jurídica que se puede crear y todas las entidades jurídicas están asociadas a un identificador de empresa. Esta asociación existe porque algunas áreas funcionales del programa usan un id. de empresa, o DataAreaId, en sus modelos de datos. En estas áreas funcionales, las empresas se usan como un límite para la seguridad de datos. Los usuarios sólo pueden acceder a los datos de la empresa en la que han iniciado sesión en ese momento.

### <a name="operating-units"></a>Unidades operativas

Una unidad operativa es una organización que se usa para dividir el control de los recursos económicos y los procesos operativos de un negocio. Las personas de una unidad operativa tienen el deber de optimizar el uso de recursos escasos, mejorar los procesos y responder de su rendimiento.

Los tipos de unidades operativas se incluyen los centros de coste, las unidades de negocio, los flujos de valor, los departamentos y los canales de Commerce. En la siguiente tabla se proporciona más información sobre cada tipo de unidad operativa.

| Tipo de unidad operativa | Descripción | Propósito |
|---------------------|-------------|---------|
| Centro de coste         | Unidad operativa cuyos directores se responsabilizan de los gastos presupuestados y reales. | Se usa para la administración y control operativo de procesos empresariales que abarcan las entidades jurídicas. |
| Unidad de negocio       | Unidad operativa semiautónoma que se crea para cumplir objetivos empresariales estratégicos. | Se usa para la notificación financiera basada en industrias o líneas de productos que la organización produce independientemente de la entidades jurídicas. |
| Flujo de valor        | Unidad operativa que controla uno o más flujos de producción. | Se usa comúnmente en la producción ajustada para controlar las actividades y flujos requeridos para suministrar un producto o servicio a los consumidores. |
| Departamento          | Una unidad operativa que representa una categoría o parte funcional de una organización y que realiza una tarea determinada, como las ventas o la contabilidad. | Se usa para informar sobre las áreas funcionales. Un departamento puede tener responsabilidad de pérdidas y ganancias y puede estar compuesto de un grupos de centros de coste. |
| Canal comercial      | Una unidad operativa que representa una tienda física, una tienda en línea o centro de llamadas. | Se usa para la administración y el control operativo de una o varias tiendas dentro o a través de entidades jurídicas. |

### <a name="teams"></a>Equipos

Un equipo es una organización cuyos miembros comparten una responsabilidad, un interés o un objetivo común. Los equipos no pueden usarse en las jerarquías organizativas.

## <a name="organizational-hierarchies"></a>Jerarquías organizativas

Configure jerarquías organizativas para ver e informar sobre su negocio desde diferentes perspectivas. Por ejemplo, puede configurar una jerarquía de entidades jurídicas para informes estatutarios, legales o de impuestos. Configure una jerarquía basada en unidades operativas para elaborar información financiera que no sea legalmente necesaria pero que se use para control interno. Por ejemplo, puede crear una jerarquía de compras para controlar directivas de compras, reglas y procesos empresariales.

> [!NOTE]
> Una vez que se ha agregado una unidad de operación a una jerarquía, la unidad operativa no se puede borrar. 

A cada jerarquía se le asigna un propósito. El propósito de una jerarquía determina los tipos de organizaciones que se pueden incluir en la jerarquía. El propósito también determina en qué escenarios de aplicación se puede usar una jerarquía.

Las organizaciones de una jerarquía pueden compartir parámetros, directivas y transacciones. Una organización puede heredar o reemplazar los parámetros de su organización principal. Sin embargo, los datos maestros compartidos, como los productos y las libretas de direcciones, se aplican a toda la organización y no pueden reemplazarse para organizaciones individuales. La creación de organizaciones y jerarquías requiere una planificación cuidadosa. Para obtener más información, consulte [Planificación de la jerarquía organizativa](plan-organizational-hierarchy.md).

## <a name="additional-resources"></a>Recursos adicionales
- [Planificación de su jerarquía organizativa](plan-organizational-hierarchy.md)
- [Crear una jerarquía organizativa](tasks/create-organization-hierarchy.md)
- [Crear una entidad jurídica](tasks/create-legal-entity.md)
- [Crear una unidad operativa](tasks/create-operating-unit.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
