---
title: Libro mayor de contabilidad de inventario global
description: Este tema describe los libros de contabilidad de inventario global, que se definen mediante una combinación de una moneda, un calendario, una convención y una asociación con una entidad jurídica.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273220"
---
# <a name="global-inventory-accounting-ledger"></a>Libro mayor de contabilidad de inventario global

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

La contabilidad de inventario global tiene su propio conjunto de libros mayores. Cada vez que se procesa una transacción relacionada con el inventario para una entidad legal relevante, el sistema puede contabilizar esa transacción en cualquier número de libros de contabilidad de inventario global, según sea necesario.

Un libro es un registro de medidas de débito y de crédito. Estas medidas se clasifican utilizando elementos de costo y cuentas del libro mayor auxiliar. Un libro de contabilidad de inventario global se define por su combinación de una moneda, un calendario, una convención y una asociación con una entidad jurídica.

Para configurar sus libros de contabilidad de inventario global, vaya a **Contabilidad global de inventarios \> Configuración \> Libros mayores de contabilidad de inventario global**. Para cada libro, establezca los siguientes campos:

- **Nombre**: especifique el nombre del libro.
- **Descripción**: escriba una descripción del libro.
- **Calendario fiscal** - Especifique el calendario fiscal para el libro mayor.
- **Tipo de moneda y tipo de cambio** - Utilice los campos de esta ficha desplegable para seleccionar la moneda de contabilidad que utiliza el libro mayor y el tipo de tipo de cambio. La moneda que seleccione puede diferir de la moneda que utiliza la entidad jurídica. En la Contabilidad de inventario global, los usuarios pueden definir tantos libros de costes como necesiten. La contabilidad de inventario global admite la contabilidad de inventario en múltiples monedas y en múltiples valoraciones. Establezca los campos siguientes:

    - **Divisa** - Seleccione la moneda de cálculo de costes en la que se actualizan los valores relacionados con el inventario. Estos valores incluyen el valor del inventario, el costo de los bienes vendidos, el inventario en tránsito y todo tipo de variaciones.
    - **Tipo de tipo de cambio** - Seleccione el tipo de cambio que el sistema debe usar para convertir el monto de la transacción en la moneda de la transacción y el costo estándar de los artículos en la moneda de cálculo de costos.

- **Nombre de la convención** - Especificar una convención. Una convención es una colección de políticas que establecen cómo se contabilizarán los costos en este libro mayor.
- **Entidad legal** - El libro mayor contabilizará los documentos que se contabilizan en la entidad jurídica seleccionada.
- **Cebado** - Seleccione si las transacciones de inventario que se crearon antes de que se creara el libro mayor deben procesarse de acuerdo con la moneda y la convención en el libro mayor. Seleccione uno de los siguientes valores:

    - **Activado** - El libro mayor debe procesar las transacciones que se crearon antes de que se creara el libro mayor.
    - **Desactivado** - El libro mayor debe procesar solo las transacciones que se crearon después de que se creara el libro mayor.

    > [!IMPORTANT]
    > **No** podrá regresar y configurar este campo después de ingresar nuevos documentos.

- **Estado** - El sistema establece automáticamente el estado de los libros de contabilidad recién creados en *Preparar*.
