---
title: Capacidades de recursos
description: En este artículo se proporciona información acerca de las capacidades de recursos. Una capacidad es la posibilidad de que un recurso de operaciones realice una actividad concreta. El artículo explica cómo se usan las capacidades y los conceptos relacionados, como el nivel de aptitud y la prioridad, para seleccionar los recursos adecuados para una actividad.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability, WrkCtrTable, WrkCtrCapRes, WrkCtrApplicableResources
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29961
ms.assetid: 30e38233-2a64-4070-911f-8ffd78dd8281
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 260537767d083445aa908c850526a5472c529763
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572778"
---
# <a name="resource-capabilities"></a>Capacidades de recursos

[!include [banner](../includes/banner.md)]

En este artículo se proporciona información acerca de las capacidades de recursos. Una capacidad es la posibilidad de que un recurso de operaciones realice una actividad concreta. El artículo explica cómo se usan las capacidades y los conceptos relacionados, como el nivel de aptitud y la prioridad, para seleccionar los recursos adecuados para una actividad.

Una capacidad es la posibilidad de que un recurso de operaciones realice una actividad concreta. Un recurso de operaciones puede tener más de una capacidad asignada, y una capacidad puede asignarse a más de un recurso. Puede asignar temporalmente capacidades a recursos definiendo una fecha de inicio y una fecha de vencimiento en la asignación de la capacidad. Cuando la capacidad para un recurso haya vencido, el recurso no se puede volver a programar para un proyecto o una producción que requiera dicha capacidad. Las capacidades que han vencido se pueden renovar. Puede eliminar capacidades siempre y cuando no se incluyan en una relación de ruta o formen parte de una ruta de producción de un pedido de producción activo. En general, tenga cuidado al eliminar las capacidades. En su lugar, considere si se debe ajustar la fecha de vencimiento en los recursos asignados a la capacidad. Las capacidades se pueden asignar a todos los tipos de recursos: Herramienta, Proveedor, Máquina, Ubicación, Instalación o Recursos humanos.

## <a name="level"></a>Nivel
Varios recursos suelen tener la misma capacidad funcional pero en distintos niveles de habilidades (por ejemplo, fuerza, velocidad de proceso o precisión). Por lo tanto, cuando asigna una capacidad a un recurso, puede especificar un valor de **Nivel**. El nivel es un valor numérico simple. Si especifica que una capacidad es un requisito de recurso para una ruta de producción, también puede especificar un valor de **Nivel mínimo necesario** para dicha capacidad. El motor de programación luego selecciona solo los recursos que tienen la capacidad necesaria en un nivel que sea igual a o supere el nivel mínimo que se especifica en el requisito de recurso.

## <a name="priority"></a>Prioridad
A los recursos de operaciones que tienen las mismas capacidades se les puede asignar una prioridad. Luego, si hay varios recursos que tienen capacidades que satisfagan los requisitos de programación en el nivel necesario, y tienen capacidad sin formato, el motor de programación puede seleccionar entre los recursos. Si **Prioridad** se selecciona en el campo **Selección del recurso principal** en la página **Parámetros de programación**, el recurso que tiene la máxima prioridad (el menor valor numérico en el campo **Prioridad**) se selecciona en primer lugar durante la programación.

## <a name="resource-requirements"></a>Requisitos de recursos
Al definir los requisitos de recursos para una ruta de producción, puede especificar una o más capacidades como requisitos. Durante la programación de producción, las capacidades que están definidas en los requisitos de recursos de la operación de ruta se asocian a las capacidades que están definidas para los recursos. Se seleccionan los recursos que tienen las capacidades que cumplen los requisitos. Si varios recursos tienen la misma capacidad funcional pero distintas aptitudes (como punto fuerte, velocidad de proceso o precisión), puede definir varias capacidades o usar el nivel de la capacidad para habilitar la capacidad del recurso. Este es un ejemplo:

-   En una ruta, el tiempo de proceso de exploración se establece en 10 unidades por hora, pero el requisito se define como Exploración.
-   Tiene dos máquinas de exploración: M1 y M2.
-   La capacidad Exploración se asigna a los dos recursos: la máquina M1 y la máquina M2.
-   La máquina M1 puede explorar dos unidades por hora y la máquina M2 puede explorar 11 unidades por hora.

En este ejemplo, las dos máquinas pueden ser seleccionadas por el motor de programación puesto que ambas cumplen el requisito de capacidades básicas (Exploración). Sin embargo, la máquina M1 sólo puede explorar dos unidades por hora. Debido a que este índice es mucho menor que las 10 unidades por hora que se especifican en la ruta, la máquina M1 provocará problemas de producción si se ha seleccionado. Existen dos formas de resolver este problema y de asegurarse de que se selecciona la máquina M2:

-   Crear dos capacidades diferentes: Exploración de baja velocidad y Exploración de alta velocidad. Defina Exploración de baja velocidad como la exploración que tiene un tiempo de proceso de 1 a 9 unidades por hora. Defina la Exploración de alta velocidad como la exploración que tiene un tiempo de proceso de 10 a 19 unidades por hora. Después asigne a la máquina M1 la capacidad de baja velocidad de exploración, y asigne a la máquina M2 la capacidad de alta velocidad de exploración. Finalmente, cambie el requisito de capacidad del recurso en la ruta a exploración de alta velocidad. De este modo, el motor de programación seleccionará la máquina correcta (M2).
-   Use el nivel de la capacidad para habilitar la capacidad de exploración que se asigna a las máquinas de exploración. Especifique que la máquina M1 tiene la capacidad de exploración en un nivel de 2.0, y que la máquina M2 tiene la capacidad de exploración en un nivel de 11,0. A continuación, especifique que 10,0 es el nivel mínimo necesario para el requisito de capacidad de exploración en la ruta. El motor de programación a continuación determinará que solo la máquina M2 de cumple los requisitos del recurso.

## <a name="competencies-for-human-resources"></a>Competencias para recursos humanos
Cuando tiene los recursos de operaciones del tipo **Recursos humanos** que están vinculados a los trabajadores en recursos humanos, también puede aprovecharse de las capacidades de trabajadores al definir los requisitos de recurso para una ruta de producción. Es decir, también puede especificar los requisitos para las aptitudes, los cursos, los certificados o los cargos específicos. El motor de programación podrá entonces seleccionar los recursos que están vinculados a los trabajadores, y la selección se basará en las capacidades de dichos trabajadores. Las capacidades se configuran en Recursos humanos, no en la página **Capacidades de recursos**. Al definir las aptitudes, los cursos, certificados o los cargos como requisitos de recurso, debe usar la funcionalidad de Recursos humanos y vincular cada recurso del tipo **Recursos humanos** a un trabajador correspondiente. Si no utiliza la funcionalidad de recursos humanos, puede definir las capacidades en la página **Capacidades de recursos** que se asemeja o es idéntica a las capacidades de recursos humanos. Sin embargo, la página **Capacidades de recurso** no incluye la función necesaria para mantener las aptitudes, los cursos, las certificaciones o los cargos.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]