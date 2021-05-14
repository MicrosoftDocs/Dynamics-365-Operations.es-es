---
title: Parámetros de administración de devoluciones
description: Este tema describe la página de parámetros de administración de devoluciones. Esta página contiene configuraciones que afectan la publicación, actualizaciones de estado, secuencias de números y otros comportamientos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: be98f3fada7491382946b40615fab5a58c2861d7
ms.sourcegitcommit: 890a0b3eb3c1f48d786b0789e5bb8641e0b8455e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920022"
---
# <a name="rebate-management-parameters"></a>Parámetros de administración de devoluciones

[!include [banner](../includes/banner.md)]

La página **Parámetros de gestión de devoluciones** se utiliza para definir la configuración que se aplica al módulo **Gestión de devoluciones**. Estas configuraciones afectan la publicación, actualizaciones de estado, secuencias de números y otros comportamientos. La configuración de esta página se comparte entre las entidades jurídicas y los usuarios que tienen los permisos de seguridad adecuados pueden modificarla.

Para abrir la página **Parámetros de gestión de devoluciones**, vaya a **Devoluciones y deducciones \> Configuración \> Parámetros de gestión de devoluciones**. Luego, configure los campos que se describen en las siguientes subsecciones.

## <a name="rebate-management-tab"></a>Pestaña Gestión de devoluciones

La siguiente tabla describe los campos que están disponibles en la pestaña **Administración de devoluciones** de la página **Parámetros de gestión de devoluciones**.

| Campo | Descripción |
|---|---|
| Estado predeterminado | Seleccione el estado predeterminado para todas las ofertas nuevas. Para definir el conjunto de valores de estado que está disponible para su selección, utilice la [página **Estados de devoluciones**](rebate-statuses.md). |
| Proceso por dimensión | Seleccione si las transacciones de provisión, devolución y cancelación deben procesarse por dimensión financiera. Cuando esta opción está activada, el sistema utiliza dimensiones financieras para las transacciones de origen. |
| Compruebe si se ha publicado anteriormente | <p>Seleccione el comportamiento del sistema si las transacciones de devolución no contabilizadas se procesan más de una vez durante el mismo período:</p><ul><li>**Advertencia**: el sistema permite a los usuarios anular las líneas de transacciones originales, pero se muestra una advertencia.</li><li>**Error**: el sistema evita que los usuarios anulen las líneas de transacciones originales y se muestra un mensaje de error. |
| Publicar diarios automáticamente | Seleccione si el sistema debe publicar automáticamente los diarios propuestos. Esos diarios incluyen diarios que se utilizan para provisiones y deducciones de clientes, y también diarios de facturas de impuestos de proveedores. |
| Contabilizar facturas de servicios periódicas | Seleccione si el sistema debe publicar automáticamente las facturas de servicios. Esta opción solo se aplica a las facturas de servicios en las que el tipo de pago se establece en *Deducciones de clientes de facturas fiscales*. |
| Referencia de pedido de artículo de devolución | Seleccione la referencia de devolución para usar en pedidos de compra y venta que se generan a partir del proceso de devolución (*Ninguno*, *Oferta de devoluciones y deducciones*, *Número de devoluciones y deducciones*, *Número de transacción de devolución*, o *Notas del documento*). |
| Usar proceso de reclamación | <p>Establezca esta opción en *Sí* para utilizar una proceso de reclamaciones. De esta manera, puede marcar las transacciones que la Administración de devoluciones crea como reclamadas o no reclamadas, y luego registrar solo las transacciones reclamadas.</p><p>Por ejemplo, calcula devoluciones por transacciones de un mes, pero el cliente ha dejado dos días sin reclamar. En este caso, las transacciones no reclamadas se volverán a crear la próxima vez que ejecute la función *Proceso* durante el mismo período.</p><p>Si configura esta opción en *No*, se registran todas las transacciones de reclamaciones.</p> |
| Incluir orden de tipo de diario | Para acuerdos o líneas de acuerdos en los que el tipo de transacción se establece en *Pedido*, esta opción controla si un pedido de cliente del tipo *Diario* se debe incluir. Proporciona flexibilidad si esos tipos de pedidos se utilizan en escenarios en los que aún no debería aplicarse una devolución. |

## <a name="number-sequences-tab"></a>Ficha Secuencias numéricas

Use la pestaña **Secuencias numéricas** en la página **Parámetros de gestión de descuentos** para asignar códigos de secuencia numérica a las diferentes secuencias numéricas que utiliza la gestión de devoluciones. La siguiente tabla describe el propósito de cada una de esas secuencias numéricas. Para obtener más información sobre las secuencias numéricas, consulte [Resumen de secuencias numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md) y sus temas relacionados.

| Referencia | Descripción |
|---|---|
| Acuerdo de devoluciones y deducciones | La secuencia numérica asigna un valor clave único a cada acuerdo de devolución. Esta clave se usa cuando se crean acuerdos. |
| Número de devoluciones y deducciones | La secuencia numérica asigna un valor clave único a cada devolución. Esta clave se utiliza para identificar las relaciones de devoluciones. |
| Número de transacción de devolución | La secuencia numérica asigna un valor clave único a cada transacción de devolución. Esta clave se utiliza para identificar las relaciones de transacciones. |
| Factura de impuestos | La secuencia numérica asigna un valor clave único a cada factura de devolución. Esta clave se utiliza cuando los diarios de devoluciones se contabilizan automáticamente. |

## <a name="feature-visibility-tab"></a>Pestaña Visibilidad de funciones

La gestión de devoluciones agrega características (campos y funciones) a varias páginas de uso frecuente en Microsoft Dynamics 365 Supply Chain Management. Esas páginas incluyen páginas relacionadas con pedidos de venta y acuerdos de venta. Si está utilizando Administración de devoluciones, debe hacer que esas funciones estén visibles en todas partes antes de poder beneficiarse de ellas. Si no está utilizando Administración de devoluciones, puede ocultar las funciones para mantenerlas fuera del camino.

En la pestaña **Visibilidad de la función** de la página **Parámetros de administración de devoluciones**, configure la opción **Activar** en *Sí* para hacer visibles las características de administración de devoluciones dondequiera que estén disponibles. Establézcalo en *No* para ocultar las funciones en páginas comunes fuera del módulo de **Administración de devoluciones**. Sin embargo, incluso cuando la opción está configurada en *No*, el propio módulo, incluida la página **Parámetros de administración de devoluciones**, permanecerá disponible para los usuarios que tengan los permisos apropiados para acceder a ella.
