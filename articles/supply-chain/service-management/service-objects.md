---
title: Visión general de los objetos de servicio
description: Los objetos de servicio son los activos y los productos de un cliente para los que puede realizar un servicio.
author: ShylaThompson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ded41bb49c9ce4f0ceb003d1d7537aa4b2023a60
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840494"
---
# <a name="service-objects-overview"></a>Visión general de los objetos de servicio

[!include [banner](../includes/banner.md)]

Los objetos de servicio son los activos y los productos de un cliente para los que puede realizar un servicio. En función del tipo de servicio proporcionado, los objetos pueden ser tangibles o intangibles:

-  Los objetos tangibles son elementos, tal como una máquina o un edificio, sobre los que puede realizar una tarea de servicio física.

    Un objeto de servicio tangible también puede ser un artículo de inventario creado en el formulario Detalles de producto emitido. En función del grupo de dimensiones de inventario que vincule al elemento, puede crear un objeto de servicio en un nivel de detalle que incluya el número de serie del artículo. Esto puede ser de utilidad si debe realizar un seguimiento del artículo exacto que el objeto de servicio representa.

    Un objeto de servicio tangible también puede ser un artículo que no esté relacionado directamente con la producción directa o cadena de suministro de una empresa. Por ejemplo, un kit de herramientas que se usa para las reparaciones en un pedido de servicio puede ser un objeto de servicio que no está incluido en el inventario. En este caso, no se registra como artículo de inventario.

-  Los objetos intangibles son cosas inmateriales, como un conjunto de cuentas o un documento legal, sobre las que se pueden realizar tareas de servicio.

## <a name="example-of-an-intangible-service-object"></a>Ejemplo de un objeto de servicio intangible

La empresa A mantiene los registros financieros de varias pequeñas empresas. Uno de los clientes de la compañía A es el equipo de fútbol local, para el que la Empresa A realiza la contabilidad semanal y la auditoría anual de las cuentas del club. Las cuentas del club están configuradas en el formulario Objetos de servicio y se especifican como el objeto del acuerdo de servicio. Hay dos líneas de acuerdo de servicio para el objeto. La línea 1 es la contabilidad semanal con un intervalo semanal asignado a la línea, y la línea 2 es la auditoría anual con un intervalo anual asignado a ella.

## <a name="related-topics"></a>Temas relacionados

[Crear objetos del servicio](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]