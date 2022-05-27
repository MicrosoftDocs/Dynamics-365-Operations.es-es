---
title: Configuración del proveedor agregada para el costo descargado
description: Este tema describe los nuevos campos que se agregan a la página de proveedores existente cuando habilita el módulo de costo de entrega. Utilice estos campos para configurar los proveedores que utilizará junto con las funciones de costo de entrega.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: b4e02397f7a4cdeaa21b451268b16e4fbe773612
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690537"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Configuración del proveedor agregada para el costo descargado

[!include [banner](../../includes/banner.md)]

Cuando habilita el módulo **Costo descargado**, se agregan nuevos campos a la página **Proveedores** existente. Utilice estos campos para configurar los proveedores que utilizará junto con las funciones de costo de entrega.

Para configurar los campos relevantes, vaya a **Adquisiciones y abastecimiento \> Vendedores \> Todos los proveedores**. Abra un proveedor existente o cree uno nuevo y luego seleccione **Detalles varios**. Todos los nuevos campos que el módulo **Coste de aterrizaje** agrega aparecen debajo del título **Viajes**. En la siguiente tabla se describen estos campos.

| Campo | Descripción |
|---|---|
| Tipo de envío | <p>Seleccione el rol del proveedor en relación con el costo de entrega:</p><ul><li>**Ninguno** - El proveedor no tiene un rol específico relacionado con el costo de entrega. Este valor es la configuración predeterminada, porque la mayoría de los proveedores probablemente no tendrán un rol específico.</li><li>**Compañía de envios** - El vendedor es una empresa de transporte. Los proveedores que tienen este tipo de envío están disponibles para su selección en el campo **Compañía de envios** en la página **Viajes**.</li><li>**Agente de aduana** - El vendedor es un agente de aduanas. Los proveedores que tienen este tipo de envío están disponibles para su selección en el campo **Agente de aduanas** en la página **Folios**.</li><li>**Agente** - El vendedor es un agente. Los proveedores que tienen este tipo de envío están disponibles para su selección en el campo **Agente** de las páginas **Proveedores** y **Pedidos de compra**.</li></ul> |
| Grupo de tipos de costes | Asignar al proveedor a un grupo de tipos de costos con el fin de seleccionar [costos automáticos](auto-cost-setup.md). |
| Puerto de origen | Seleccione el puerto de origen del viaje. |
| Agente | El agente predeterminado cuando se realizan compras al proveedor. |
| Importar proveedor de gestión de costes | <p>Indique si el proveedor es un proveedor de costo de entrega.</p><p>**Consejo:** Puede utilizar este campo junto con la seguridad a nivel de registro para limitar las órdenes de compra que se muestran cuando se crea un viaje.</p> |
| Empresa de transporte | Seleccione la empresa de envío predeterminada que se utiliza cuando se crean órdenes de compra para el proveedor. |
| Proveedor de servicios | Indique si el vendedor es proveedor de servicios. |
| Grupo de tolerancias de exceso o falta | Seleccione el grupo de tolerancia por encima / por debajo del valor predeterminado para el proveedor. |
