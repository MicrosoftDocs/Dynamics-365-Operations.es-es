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
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 01bfc5198b62cfe56df9ec6763d5d0ff95f13ed5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571002"
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
