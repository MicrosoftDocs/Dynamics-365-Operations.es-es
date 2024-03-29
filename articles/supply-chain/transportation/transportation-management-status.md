---
title: Estados de administración de transporte
description: Este artículo explica cómo crear un estado de transporte y asignar ese estado a un estado de transportista.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9b20570a87a9f8969ca6dcf898176fd40f88eeca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897384"
---
# <a name="transportation-management-statuses"></a>Estados de administración de transporte

[!include [banner](../includes/banner.md)]

Configure códigos maestros de estados de transporte para interpretar códigos proporcionados por sus transportistas de envío. Esto le permite integrarse con los transportistas de envío para proporcionar un estado. El estado del transporte que proporciona para un código de estado maestro de transporte puede ayudarle a realizar un seguimiento del estado de una carga, de un envío o de un contenedor. El estado de transporte específico para una carga, envío o contenedor solo se puede actualizar mediante la integración de datos y no manualmente a través de la interfaz de usuario.

## <a name="create-a-transportation-status"></a>Crear un estado de transporte

Para crear un estado de transporte, siga estos pasos:

1. Vaya a **Administración de transporte \> Configuración \> Maestros de estado de transporte**.
1. Seleccione **Nuevo** para crear un nuevo estado maestro de transporte.
1. En el campo **Maestro de estado de transporte**, escriba un código único para el código de transporte.
1. En el campo **Tipo de transporte**, seleccione ya sea *Transportista de envío* o *Cubo* como el tipo de transporte.
1. Ingrese un nombre y estado de transporte.
1. Cierre la página.

## <a name="map-a-transportation-status-to-a-carrier-status"></a>Asignar un estado de transporte a un estado de transportista

Para asignar un estado de transporte a un estado de transportista, siga estos pasos:

1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Maestros de estado de transporte**.
1. Seleccione **Nuevo** para asignar un código de un transportista de envío a un código maestro de estado de transporte.
1. Seleccione la identificación única para el transportista de envío y el servicio de transportista.
1. Seleccione el código de estado del transporte que desea asignar al código del transportista de envío seleccionado.
1. Especifique el código externo que usa el transportista de envío.
1. Cierre la página.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]