---
title: Requisitos previos para la conversión de costes estándar
description: En este tema se describen tareas para realizar antes de ejecutar una conversión de coste estándar.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 50891
ms.assetid: 73af66cf-c924-45be-837a-a648dbd05a31
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1fa43c8e32c4af8fc7e3ad5f3eb457dbdae1d39e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675293"
---
# <a name="prerequisites-for-a-standard-cost-conversion"></a>Requisitos previos para la conversión de costes estándar

[!include [banner](../includes/banner.md)]

En este tema se describen tareas para realizar antes de ejecutar una conversión de coste estándar. 

Antes de ejecutar una conversión de costes estándar, siga estos pasos:

1.  Defina un **grupo de modelos de artículos** para los costes estándar. Utilice la página Grupos de modelos de artículo para crear un grupo de modelos de artículos con un modelo de inventario de costes estándar. Cuando configure una tarea de conversión de costes estándar, asignará este grupo de modelos de artículos a los artículos que se van a convertir.
2.  Asigne un **grupo de costes** a cada artículo.
    -   El grupo de costes asignado a un artículo adquirido puede utilizarse como base para asignar cuentas contables relacionadas con los costes estándar. Esto puede incluir la asignación de cuentas contables para las desviaciones de precios de compras. En un entorno de fabricación, el grupo de costes que se asigna a los componentes adquiridos incluye también la segmentación de costes en los costes calculados de un artículo fabricado.
    -   El grupo de costes que se asigna a un artículo fabricado puede utilizarse como base para asignar cuentas contables relacionadas con los costes estándar, por ejemplo, para asignar cuentas contables de desviaciones de producción.

3.  Asigne una **cantidad de pedido estándar** a un artículo fabricado si tiene costes constantes. La cantidad de pedido estándar de un artículo fabricado actúa como tamaño de lote de contabilidad para amortizar o prorratear los costes constantes. Estos pueden incluir horas de configuración en las operaciones de enrutamiento o una cantidad de componentes constante en una lista de materiales (L. MAT).
4.  Asigne **cuentas contables generales** relacionadas con costes estándar, principalmente de desviaciones de revalorización. Use la página **Registro** (**Gestión de inventarios** &gt; **Configuración**) para asignar cuentas de contabilidad general relacionadas con costes estándar. Como mínimo, es necesario asignar al proceso de conversión de costes estándar la cuenta de desviación de revalorización de todos los artículos y todos los grupos de coste. Utilice la página **Plan de cuentas** para definir las cuentas contables generales que se requerirán para los costes estándar. Utilice la página **Combinaciones de registro** para habilitar el uso de las relaciones de costes (de tablas, grupos y todos los costes) antes de definir las reglas de registro de artículos.
5.  Defina los parámetros de inventario relacionados con los costes estándar. Utilice la ficha **Secuencias numéricas** de la página **Parámetros de gestión de inventario y almacenes** para asignar una secuencia numérica a asientos de revalorización. Un asiento de revalorización se genera cuando la conversión de costes estándar modifica el valor de inventario de un artículo. Utilice la página **Parámetros de gestión de inventario y almacenes** para definir parámetros de control de costes (en la ficha **Contabilidad de inventario**) para definir dos parámetros relacionados con los costes estándar.
    -   Use el campo **Análisis de costes** para seleccionar No o Sublibro de contabilidad. La selección de Sublibro de contabilidad recibe el nombre de "análisis de costes activo". El análisis de costes activo es fundamental para calcular, conservar y ver la segmentación de grupos de costes en la estructura de productos de múltiples niveles de los artículos de costes estándar. Cuando el análisis de costes está activo, puede informar y analizar lo siguiente en formato de un solo nivel, de varios niveles o formato total:
        1.  Inventario
        2.  Trabajo en proceso (WIP)
        3.  Coste de bienes vendidos (COGS) por grupo de costes

        Cuando se activa el análisis de costes, el coste del artículo fabricado almacenará la segmentación de grupo de costes en el registro de costes. Si no selecciona ningún valor en el campo **Análisis de costes**, la segmentación del grupo de costes no se mantendrá para los artículos de coste estándar. Es decir, el coste estándar de un artículo fabricado se calculará y mantendrá como un solo importe sin la segmentación de grupos de costes, y las contribuciones de costes de los componentes fabricados se agregarán al importe único.
    -   Utilice el campo **Desviaciones a estándar** para seleccionar grupos resumidos o por costes. La selección por grupo de costes permite identificar desviaciones de precio de compra y las desviaciones de producción por grupo de costes. Esto también le permite identificar los cuatro tipos de desviaciones de producción (tamaño de lote, cantidad, precio y de sustitución). Si selecciona Resumen, no podrá identificar las desviaciones por grupo de costes ni los cuatro tipos de desviaciones de la producción. Únicamente podrá ver información resumida de las desviaciones de producción. La directiva sobre desviación es independiente de la directiva de análisis de costes. Es decir, puede seleccionar una directiva de análisis de costes 0 y seleccionar desviaciones por grupo de costes, de forma que sigan mostrándose las desviaciones de la producción por grupo de coste.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]