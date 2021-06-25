---
title: Visión general de los requisitos previos de los costes estándar
description: Este tema describe los pasos básicos para el uso de costes estándar.
author: AndersGirke
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f2e1620de804f42688ad8d05232e38178b5fb80
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187731"
---
# <a name="prerequisites-for-standard-costs-overview"></a>Visión general de los requisitos previos de los costes estándar

[!include [banner](../includes/banner.md)]

Este tema describe los pasos básicos para el uso de costes estándar. Los pasos posteriores dependen de las operaciones de la empresa. Por ejemplo, los pasos difieren para un entorno de no fabricación, un entorno de fabricación que no usa enrutamientos y un entorno de fabricación que usa enrutamiento. 

Para establecer los costes estándar, siga estos pasos.

**1. Cree un grupo de modelos de artículos para los costes estándar.**

Use el formulario **Grupos de modelos de artículo** para crear un nuevo grupo de costes estándar y asignar un modelo de inventario de **Coste estándar**. El identificador del grupo de modelos de artículos debería tener significado, como por ejemplo **Coste est**. Active las casillas para indicar que el grupo debe permitir inventario negativo financiero, y ese debe registrar el inventario físico y el inventario financiero. Este grupo de costes estándar se asignará a los artículos.

**2. Defina las cuentas contables relacionadas con las desviaciones de coste estándar.** 

Use la página **Plan de cuentas** para definir las cuentas contables relacionadas con las desviaciones de coste estándar. Estas cuentas contables deben definirse antes de que puedan asignarse en la página **Registro**. Las cuentas contables pueden reflejar grupos de artículos y grupos de coste.

**3. Asigne cuentas contables a los registros de artículos relacionados con las desviaciones de coste estándar.** 

Use la página **Registro** para asignar las cuentas contables relacionadas con desviaciones de coste estándar. Puede especificar la cuenta contable de la desviación por artículo (o grupo de artículos) y por grupo de costes (o tipo de grupo de costes), o puede especificar que la cuenta contable se aplicará a todos los artículos y todos los grupos de costes. Estas opciones corresponden a las relaciones de coste para tablas, grupos y todo. 

Antes de definir las reglas de registro de artículos, utilice la página **Combinaciones de transacción** para habilitar las relaciones de costes (para tablas, grupos y todo).

**4. Defina los parámetros de inventario relacionados con los costes estándar.** 

-  Utilice la pestaña **Contabilidad de inventario** en la página **Configuración de directivas de contabilidad de inventario > Parámetros** para definir los parámetros de control de costes relacionados con los costes estándar.

    -  En el campo **Análisis de costes**, seleccione **Ninguno** o **Sublibro de contabilidad**. Si selecciona **Sublibro de contabilidad**, el análisis de costes es un análisis de costes *activo* . El análisis de costes activo es fundamental para calcular, conservar y ver la segmentación de grupos de costes en la estructura de productos de múltiples niveles de los artículos de costes estándar. La activación del análisis de costes le permite notificar y analizar el inventario, el trabajo en proceso (WIP) y el coste de las mercancías vendidas (COGS) por grupo de costes en un solo nivel, en múltiples niveles o en un formato único. Cuando el análisis de costes es activo, si activa el cote del artículo fabricado, la segmentación de grupo de costes se almacenará en el registro de costes del artículo. 

    -  Si selecciona **Ninguno**, la segmentación del grupo de costes no se mantendrá para los artículos de coste estándar. Es decir, el coste estándar de un artículo fabricado se calculará y mantendrá como un importe único, sin la segmentación de grupos de costes. Las contribuciones de costes de los componentes fabricados se agregarán al importe único.

-  En el campo **Desviaciones a estándar**, seleccione **Resumido** o **Por grupo de costes**. Si selecciona **Por grupo de costes**, puede identificar desviaciones de precio de compra y desviaciones de producción por grupo de costes. También puede identificar los cuatro tipos de desviaciones de producción: el tamaño de lote, la cantidad, el precio y las desviaciones de sustitución. Si selecciona **Resumido**, no podrá identificar las desviaciones por grupo de costes ni los cuatro tipos de desviaciones de la producción. Solo podrá ver información resumida de las desviaciones de producción.

-  Las directivas sobre desviaciones a estándar son independientes de las directivas de análisis de costes. Es decir, puede seleccionar una directiva de análisis de costes de **Ninguno** y seleccionar desviaciones por grupo de costes, de forma que sigan mostrándose las desviaciones de la producción por grupo de coste.

**5. Cree versiones de gestión de costes para los costes estándar.** 

Use el formulario **Configuración de la versión de gestión de costes** para crear una o más versiones de gestión de costes para los costes estándar. A cada versión se debe designar un tipo de gestión de costes de **Costes estándar** y permitir contenido para incluir datos de coste.

**6. Preparar un cliente estándar para usar costes estándar.** 

Los clientes que deseen modificar sus artículos existentes a un modelo de inventario de costes estándar deberán usar la página **Conversiones de costes estándar**.


## <a name="related-topics"></a>Temas relacionados

[Visión general de conversión de costes estándares](standard-cost-conversion-overview.md)

### <a name="blogs"></a>Blogs

#### <a name="community-blogs"></a>Blogs de la comunidad

- [Cómo configurar los costes estándar de materiales directos en Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [Costes laborales directos estándar en Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]