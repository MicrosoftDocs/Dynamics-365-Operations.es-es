---
title: Visión general de las organizaciones y las jerarquías organizativas
description: Una organización es un grupo de personas que trabajan juntas para llevar a cabo un proceso empresarial o lograr un objetivo. Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.custom: 17291
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 368569f2cdd389b6fc99ddcf05f35cc9a750ec9e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797055"
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
| Canal de Commerce      | Una unidad operativa que representa una tienda física, una tienda en línea o un mercado en línea. | Se usa para la administración y el control operativo de una o varias tiendas dentro o a través de entidades jurídicas. |

### <a name="teams"></a>Equipos

Un equipo es una organización cuyos miembros comparten una responsabilidad, un interés o un objetivo común. Los equipos no pueden usarse en las jerarquías organizativas.

## <a name="organizational-hierarchies"></a>Jerarquías organizativas

Configure jerarquías organizativas para ver e informar sobre su negocio desde diferentes perspectivas. Por ejemplo, puede configurar una jerarquía de entidades jurídicas para informes estatutarios, legales o de impuestos. Configure una jerarquía basada en unidades operativas para elaborar información financiera que no sea legalmente necesaria pero que se use para control interno. Por ejemplo, puede crear una jerarquía de compras para controlar directivas de compras, reglas y procesos empresariales.

A cada jerarquía se le asigna un propósito. El propósito de una jerarquía determina los tipos de organizaciones que se pueden incluir en la jerarquía. El propósito también determina en qué escenarios de aplicación se puede usar una jerarquía.

Las organizaciones de una jerarquía pueden compartir parámetros, directivas y transacciones. Una organización puede heredar o reemplazar los parámetros de su organización principal. Sin embargo, los datos maestros compartidos, como los productos y las libretas de direcciones, se aplican a toda la organización y no pueden reemplazarse para organizaciones individuales. La creación de organizaciones y jerarquías requiere una planificación cuidadosa. Para obtener más información, consulte [Planificación de la jerarquía organizativa](plan-organizational-hierarchy.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]