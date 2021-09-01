---
title: Perfiles de clasificación
description: Este tema describe cómo configurar datos para perfiles de clasificación.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de5789e1b8e36fc52f308967961fe12389628209ff423e26928d1fb15395a08f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772385"
---
# <a name="rating-profiles"></a>Perfiles de clasificación

Un perfil de calificación se parece a un contrato de logística (pero no a un contrato legal). Se utiliza para determinar las tarifas de transporte de cargas. 

Cada perfil de clasificación es único para un transportista de envío. En el perfil, se asocia el transportista de envío a una tasa maestra. La tasa maestra define la asignación de base de tasa y la base de tasa. La base de tasa determina la tasa del transportista.

Puede configurar un perfil de clasificación mediante una página genérica que muestra una visión general de todos los perfiles de clasificación existentes. Alternativamente, puede configurar un perfil de clasificación directamente a partir del transportista de envío. En ambos casos, la información que configura para el perfil de calificación es la misma.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>Cree o edite un perfil de calificación en la página Perfiles de calificación

Sobre la página **Perfiles de calificación**, puede revisar todos los perfiles de calificación disponibles. También puede editar perfiles existentes y crear perfiles nuevos.

1. Vaya a **Administración de transporte \> Configuración \> Clasificación \> Perfil de clasificación**.
1. En el panel de acciones, seleccione **Nuevo** para agregar un nuevo perfil de calificación a la cuadrícula, o seleccione **Editar** para editar un perfil existente.
1. En la fila del perfil de calificación nuevo o existente, configure los siguientes campos:

    - **Perfil de clasificación** – Especifique un identificador (id.) y una descripción únicos para el perfil de clasificación.
    - **Nombre** - Especifique un nombre descriptivo para el perfil de clasificación.
    - **Transportista de envío** - Seleccione un transportista. El perfil de calificación que está configurando también se mostrará en la página **Transportistas de envío** del operador seleccionado.
    - **Sitio** y **Almacén** - Seleccione un sitio y un almacén.
    - **Motor de tarifas** - Seleccione el motor de tarifas para el perfil de calificación.
    - **Maestro de tarifas** - Seleccione el maesetro de tarifas para el perfil de calificación. Puede usar la tasa maestra para definir un tipo de base de tasa y una base de tasa. Para obtener más información, vea [Configurar maestros de tarifas](set-up-rate-masters.md).
    - **Motor de tiempo de tránsito** - Seleccione el motor de tiempo de tránsito para el perfil de calificación.
    - **Índice de combustible de transportista** – Seleccione el motor de cálculo de tránsito y el índice de combustible del transportista para el perfil de clasificación.
    - **Fecha y hora de inicio del efecto** y **Fecha y hora de finalización efectiva** - Definir el período en el que debe estar activo el perfil de calificación.

1. En el panel Acciones, seleccione **Guardar**.

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>Cree un perfil de calificación directamente en la página Transportistas de envío

1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Transportistas de envío**.
1. Seleccione un transportista de envío en la lista.
1. En la ficha desplegable **Perfiles de clasificación**, haga clic en **Nuevo** para crear un perfil de clasificación.
1. Configure los campos para el nuevo perfil de calificación. Estos campos corresponden a los campos de la página **Perfiles de calificación**, como se describe en la sección anterior de este tema.

> [!NOTE]
> Perfiles que se crean en la página **Transportistas de envío** también se muestran en la página **Perfiles de calificación**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]