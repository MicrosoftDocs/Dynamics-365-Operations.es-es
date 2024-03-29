---
title: Ejecución programada
description: En este artículo se explica la ejecución programada en Administración de activos.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e9d6af5c224f683481378da57708fda3c1b7207
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848060"
---
# <a name="scheduled-execution"></a>Ejecución programada

[!include [banner](../../includes/banner.md)]

 

Puede utilizar niveles de servicio de la orden de trabajo para configurar la ejecución programada. (Para obtener más información sobre los niveles de servicio de la orden de trabajo, consulte [Nivel de servicio y descripción](service-level-and-description.md).) La ejecución programada brinda flexibilidad en la planificación de trabajo para los trabajadores de mantenimiento, ya que puede configurar requisitos más o menos detallados para el intervalo durante la que se debe completar una orden de trabajo. Por ejemplo, un trabajador de mantenimiento que completa un trabajo más rápido de lo esperado en una instalación de producción podría pasar a otro trabajo cercano que se planificó para la semana actual pero no necesariamente para el día actual. Este enfoque permite la optimización de la planificación del trabajador y la finalización del trabajo.

La configuración de ejecución programada, que está relacionada con las órdenes de trabajo, puede ser genérica o específica. Puede configurar líneas genéricas que no se limitan a tipos de órdenes de trabajo específicas, tipos de activos, etc. Como alternativa, puede crear líneas de ejecución programadas que se aplican a un tipo de orden de trabajo específica, tipo de activo, tipo de trabajo de mantenimiento, etc.

1. Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Ejecución programada**.
2. Seleccione **Nueva** para crear una línea de ejecución programada.
3. En los campos **Ubicación técnica**, **Tipo de orden de trabajo**, **Tipo de activo**, **Fabricante**, **Modelo**, **Categoría de tipo de trabajo de mantenimiento**, **Tipo de trabajo de mantenimiento**, **Variante de tipo de trabajo de mantenimiento** y **Comercio**, seleccionar valores como sea necesario.
4. En el campo **Nivel de servicio**, seleccione un nivel de servicio de la orden de trabajo. Si deja este campo en blanco, haga el tipo más genérico de línea de ejecución programada. Para obtener un ejemplo de una línea genérica, vea el primer registro en la ilustración que se indica a continuación. Esa línea habilita todas las órdenes de trabajo que no tienen ningún nivel de servicio de la orden de trabajo que se programe para una fecha y hora específica.
5. En el campo **Ejecución programada**, seleccione el intervalo de tiempo.
6. Seleccione **Guardar**.

![Ejecución programada.](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]