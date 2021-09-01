---
title: Crear un perfil de ubicación
description: Este tema explica cómo crear un perfil de ubicación en Dynamics 365 Supply Chain Management.
author: ShylaThompson
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8e06490761488881a7ea1c57cf9eb3d12dd7624753593e4aacd3c07b6a3f6998
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750037"
---
# <a name="create-a-location-profile"></a>Crear un perfil de ubicación

[!include [banner](../../includes/banner.md)]

Este tema explica cómo crear un perfil de ubicación en Dynamics 365 Supply Chain Management. Cada ubicación en el almacén requiere un perfil de ubicación asociado que describa las propiedades de la ubicación, por ejemplo, si la ubicación permite artículos mezclados. En este procedimiento crearemos un perfil para una ubicación que no requiere el control del número de matrícula. Habilitaremos artículos mezclados y los estados de inventario mezclados, y permitiremos el recuento cíclico. Puede utilizar este procedimiento en la empresa de datos de demostración USMF.


1. En el Panel de exploración, vaya a **Módulos > Gestión de almacenes > Configuración > Almacén >Perfiles de ubicación**.
2. Seleccione **Nuevo**.
3. En el campo **Id. de perfil de ubicación**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Formato de ubicación**, especifique o seleccione un valor.
6. En el campo **Tipo de ubicación**, especifique o seleccione un valor.
7. En el campo **Id. de perfil de administración de muelles**, especifique o seleccione un valor.
8. Seleccione **Sí** en el campo **Permitir artículos combinados**.
9. Seleccione **Sí** en el campo **Permitir estados de inventario combinados**.
10. Seleccione **Sí** en el campo **Permitir recuento cíclico**.
11. Seleccione **Guardar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]