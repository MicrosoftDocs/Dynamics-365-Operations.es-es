---
title: Configurar nombres de diarios de arrendamiento
description: Este tema explica cómo definir nombres de diarios de arrendamiento. Los nombres de los diarios de arrendamiento especifican los diarios en los que se contabilizan las entradas que se originan en Arrendamiento de activos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 89c5fc768aafe9e5de9adcde32e7b4d0a084941b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990926"
---
# <a name="set-up-lease-journal-names"></a>Configurar nombres de diarios de arrendamiento

[!include [banner](../includes/banner.md)]

Los nombres de los diarios de arrendamiento especifican los diarios en los que se contabilizan las transacciones que se originan en Arrendamiento de activos. Solo los nombres de diarios asignados al tipo de diario **Arrendamiento de activos** aparecen en los campos **Reconocimiento inicial** y **Nombre del diario mensual** de la página **Parámetros de arrendamiento de activos**. Solamente el tipo de diario **Registro de facturas de proveedores** se puede asignar al campo **Nombre del diario de facturas**.

Para configurar los nombres de los diarios de arrendamiento, siga estos pasos.

1. Vaya a **Arrendamiento de activos \> Configuración \> Parámetros de arrendamiento de activos**.
2. En la pestaña **General**, en el campo **Nombre del diario de reconocimiento inicial**, seleccione un diario. Todas las entradas del diario de reconocimiento inicial se registrarán en este nombre de diario.
3. En el campo **Nombre de diario de facturas**, seleccione un diario. Si la opción **Pagar al proveedor** está configurada en **Sí** para el libro de arrendamiento, las facturas de pago de arrendamiento y gastos se publicarán en este nombre de diario.
4. En el campo **Nombre de diario de arrendamiento**, seleccione un diario. Todos los movimientos de depreciación, intereses y reclasificación a corto plazo se registrarán en este nombre de diario. Si la opción **Pagar al proveedor** está configurada en **No** para el libro de arrendamiento, las movimientos de pagos de arrendamientos y de pagos de gastos se publicarán en este nombre de diario.
