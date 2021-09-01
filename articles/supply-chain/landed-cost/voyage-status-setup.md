---
title: Configuración del estado del viaje
description: Este tema describe cómo establecer los valores de estado que los usuarios pueden asignar a los viajes.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 994ce5245ce36a3d063782aff738e752d33c8cc91b438b9dc683eedbd7f13a5a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760499"
---
# <a name="voyage-status-setup"></a>Configuración del estado del viaje

[!include [banner](../../includes/banner.md)]

Sobre la página **Estados del viaje**, establece el conjunto de valores de estado que los usuarios pueden asignar a los viajes. Los usuarios pueden asignar valores de estado de viaje a todos los niveles de un viaje: viaje, contenedor de envío, folio, orden de compra y artículo (líneas de compra y líneas de orden de transferencia). Se utilizan para dos propósitos:

- Informar al usuario sobre el estado del viaje, contenedor de envío, folio, orden de compra o artículo (líneas de compra y líneas de orden de transferencia).
- Limite el uso del área de costos evitando modificaciones o eliminaciones.

Para configurar los estados de su viaje, vaya a **Coste de aterrizaje \> Configuración \> Estados del viaje**. Allí puede agregareliminar y editar estados usando los botones del panel de acciones.

Cada área de costo tiene su propio conjunto y jerarquía de estados de viaje. Por lo tanto, en la página **Estados del viaje**, en el **Área de costo**, primero debe seleccionar el área de costo para la que desea ver o crear estados de viaje. Luego, para cada estado de viaje, configure los campos que se describen en la siguiente tabla, según sea necesario. Tenga en cuenta que el estado de un viaje también se puede cambiar automáticamente por eventos del sistema, como las reglas que se han establecido mediante el uso del centro de control de seguimiento.

| Campo | Descripción |
|---|---|
| Estado de viaje | Especifique el nombre del estado del viaje. |
| Descripción | Introduzca una descripción del estado del viaje. |
| Modificar | Seleccione esta casilla de verificación si los usuarios pueden modificar los viajes que tienen este estado. |
| Borrar | Seleccione esta casilla de verificación si los usuarios pueden eliminar los viajes que tienen este estado. |
| Obligatoria | Seleccione esta casilla de verificación para que el estado del viaje sea obligatorio, de modo que no se pueda omitir. |
| Principal | Utilice este campo para establecer una jerarquía entre los valores de estado. Los estados de la travesía se pueden cambiar (ya sea de forma manual o automática) solo hacia abajo en la jerarquía, de un estado principal a uno de sus estados secundarios.

> [!NOTE]
> Debe configurar solo los estados de viaje específicos que utiliza su organización. Los estados de viaje típicos incluyen *Confirmado*, *Mercancías en tránsito*, *Recibido*, *Listo para calcular el costo* y *Estimado*. Sin embargo, pueden estar presentes otros estados.
