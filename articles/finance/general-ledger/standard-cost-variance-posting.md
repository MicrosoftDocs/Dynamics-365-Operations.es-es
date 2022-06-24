---
title: Registro de desviación de coste estándar
description: Este artículo proporciona información sobre cómo registrar perfiles de costes estándar.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: e7b2d04f32b75dbd1354b3ef74a41ea1b6469c8a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894888"
---
# <a name="standard-cost-variance-posting"></a>Registro de desviación de coste estándar

Cuando utiliza el cálculo de costes estándar para uno o más productos en su organización, debe configurar los [requisitos previos para el coste estándar](/supply-chain/cost-management/prerequisites-standard-costs.md). Este artículo explica las cuentas de registro que se requieren para el paso 3 de los requisitos previos, "Asignar cuentas contables a registros de artículos que están relacionados con variaciones de costo estándar".

Pueden ocurrir diferentes tipos de desviaciones para compras y órdenes de producción. Para ver ejemplos de variaciones de producción, consulte [Fuentes comunes de variaciones de producción](/supply-chain/cost-management/common-sources-of-production-variances.md). Las variaciones en el precio de la orden de compra ocurren cuando usa el costo estándar para un artículo comprado y hay una diferencia entre el coste estándar del producto y el monto facturado en la orden de compra.

## <a name="sample-posting-profile-configuration"></a>Ejemplo de configuración del perfil de publicación

La siguiente tabla muestra ejemplos de los tipos de publicación predeterminados. Incluye ejemplos de cuentas principales y descripciones.

- La columna "¿Debe/Haber?" indica si la transacción registra un débito o un crédito generalmente. En algunos casos, una transacción puede registrar débitos o créditos.
- La columna "Cuenta de compensación" indica que el tipo de registro es una cuenta de compensación. En otras palabras, el importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior.
- La columna "P/F" indica el tipo de registro. "P" representa registro física y "F" representa registro financiero.
- La columna "Seguir" indica si la cuenta principal del tipo de publicación específico suele ser la misma que la cuenta principal de otro tipo de publicación. Específicamente, indica el tipo de publicación que se usa normalmente.

> [!NOTE]
> Las cuentas principales y los nombres de las cuentas principales de la tabla son solo sugerencias. Le recomendamos que trabaje con su contador para determinar la mejor configuración para sus necesidades comerciales.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | P/F | Seguir | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-----|--------|-------------|
| Desviación de precio de compra | 510310 | Desviación de precio de compra | Gasto | O bien | No | V | No aplicable | Esta cuenta se usa cuando hay una variación entre el precio de compra y el costo estándar en una orden de compra. |
| Revalorización del coste de inventario | 510330 | Revalorización del coste de inventario | Gasto | O bien | No | V | No aplicable | Esta cuenta se usa cuando se activa una nueva versión de costes para un artículo de coste estándar para revaluar el inventario disponible. |
| Desviación de cambio de coste | 510320 | Desviación de cambio de coste | Gasto | O bien | No | V | No aplicable | Esta cuenta se usa cuando hay una diferencia en los costes estándar entre los sitios, o cuando se devuelve un artículo y hay un cambio entre el coste estándar original y el coste estándar actual de un producto. |
| Desviación en el tamaño de lote de producción | 510370 | Desviación en el tamaño de lote de producción | Gasto | O bien | No | V | No aplicable | Esta cuenta se usa cuando existen diferencias entre la base de cálculo de la lista de materiales (BOM) y la cantidad real para el cálculo del costo de la orden de producción. |
| Desviación en el precio de producción | 510340 | Desviación en el precio de producción | Gasto | O bien | No | V | No aplicable | Esta cuenta se utiliza cuando existen diferencias de precio entre el coste estimado y el coste real de una orden de producción. |
| Desviación en la cantidad de producción | 510350 | Desviación en la cantidad de producción | Gasto | O bien | No | V | No aplicable | Esta cuenta se utiliza cuando existen diferencias de cantidad entre el coste estimado y los costes reales de una orden de producción. |
| Desviación de sustitución de producción | 510360 | Desviación de sustitución de producción | Gasto | O bien | No | V | No aplicable | Esta cuenta se usa cuando hay un consumo inesperado en una orden de producción. |
| Desviación por redondeo | 618160 | Diferencia por redondeo | Gasto | O bien | No | V | No aplicable | Esta cuenta se utiliza cuando existe una diferencia de redondeo cuando los costes de producción se calculan a partir de los costos estándar. |
