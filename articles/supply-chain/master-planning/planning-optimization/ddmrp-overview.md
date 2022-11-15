---
title: Visión general de la planificación de requisitos de materiales basada en la demanda (DDMRP)
description: Este artículo proporciona información sobre la planificación de requisitos de materiales basada en la demanda (DDMRP), una metodología de planificación que se basa en el desacoplo de la oferta y la demanda.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: cf5ca3996a882111b840e3acb5e2a4f3f26ec4b7
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740860"
---
# <a name="demand-driven-material-requirements-planning-ddmrp-overview"></a>Visión general de la planificación de requisitos de materiales basada en la demanda (DDMRP)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Durante años, las empresas han utilizado la planificación de requisitos de materiales (MRP) como sistema para calcular los materiales y los componentes necesarios para fabricar un producto. Sin embargo, las cadenas de suministro ahora han cambiado. Las piezas tienen plazos de entrega más largos porque se obtienen cada vez más del extranjero. Por tanto, muchas empresas han informado que experimentan agotamiento o exceso de existencias, porque no saben cuánto inventario almacenar. También hay más fluctuaciones en el mercado (a veces previsiones imprecisas) y los clientes demandan productos en plazos cortos. Por tanto, hay escasez en la cadena de suministro en todo el mundo. Además, las herramientas de MRP a menudo dan a los planificadores miles de acciones para realizar. Por tanto, es difícil saber en qué centrarse. A menudo, la solución a muchos de estos problemas es cambiar a la planificación de requisitos de materiales basada en la demanda (DDMRP).

DDMRP es una metodología de planificación que se basa en el desacoplo de la oferta y la demanda. Este desacoplo se logra configurando puntos de desacoplo. Para esos artículos, se mantienen búferes que garantizan que se mantenga la cantidad correcta de existencias. El desacoplo de la oferta y la demanda ayuda a prevenir el "efecto látigo", porque la variabilidad no se transmite a lo largo de la cadena. (El *efecto látigo* se refiere a cómo las pequeñas fluctuaciones en la demanda a nivel minorista pueden causar fluctuaciones progresivamente mayores en la demanda a nivel mayorista, distribuidor, fabricante y proveedor de materia prima). Cada búfer está destinado a cubrir el uso medio de una pieza y también se puede ajustar para cubrir picos de demanda.

Se ha demostrado que DDMRP es una metodología de planificación valiosa para entornos variables donde los tiempos de tolerancia del cliente son más cortos que los tiempos de entrega acumulativos.

## <a name="the-five-components-of-ddmrp"></a>Los cinco componentes de DDMRP

DDMRP tiene cinco componentes secuenciales (pasos). Los primeros tres componentes definen esencialmente la configuración inicial y en evolución de un modelo de planificación de requisitos de materiales impulsado por la demanda. Los dos últimos componentes definen el día a día de la metodología.

1. **[Posicionamiento estratégico de inventario](ddmrp-inventory-positioning.md)** – Identificar puntos de desacoplo en la red de la cadena de suministro. Los puntos de desacoplo son puntos específicos de la cadena de suministro donde se coloca un búfer de inventario que supervisará y repondrá.
2. **[Perfiles y niveles de búfer](ddmrp-buffer-profile-and-levels.md)** – Para cada punto de desacoplo, identifique los tamaños de búfer (cantidad mínima, cantidad máxima y punto de realización de nuevo pedido) y la cantidad de pedido.
3. **[Ajustes de búfer dinámicos](ddmrp-buffer-profile-and-levels.md#dynamic-adjustments)** – Ajustar los niveles de búfer, en función de parámetros operativos variables o eventos futuros planificados.
4. **[Planificación basada en la demanda](ddmrp-planning.md)** – Generar pedidos de suministro a medida que se requieran. Estos pedidos de suministro incluyen pedidos de fabricación, pedidos de compra y pedidos de transferencia de existencias
5. **[Ejecución altamente colaborativa y visible](ddmrp-visual-and-collaborative-execution.md)** – Ejecutar los pedidos de suministro con ayuda de visualización.

DDMRP suele ser utilizado por fabricantes que tienen una lista de materiales (BOM) de varios niveles. Sin embargo, también se puede aplicar a redes de distribución y venta minorista.

## <a name="ddmrp-in-dynamics-365-supply-chain-management"></a>DDMRP en Dynamics 365 Supply Chain Management

DDMRP está incluido con Microsoft Dynamics 365 Supply Chain Management y no requiere cuotas de licencia adicionales. En Supply Chain Management, la funcionalidad DDMRP se ha agregado al módulo **Planificación maestra** existente. Sin embargo, requiere que use el complemento de Optimización de planificación.

DDMRP está integrado con las configuraciones de planificación existentes en Supply Chain Management y se usa junto con esas configuraciones para llegar a la configuración de planificación correcta para su negocio. Está controlado por un nuevo código de cobertura que es completamente diferente del período, mínimo/máximo, requisito, etc. No es un módulo nuevo y no reemplaza la funcionalidad de planificación existente. Sin embargo, ofrece más funcionalidad.
