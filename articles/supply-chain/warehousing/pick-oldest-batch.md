---
title: "Seleccionar el lote más antiguo en un dispositivo móvil"
description: "Este tema describe cómo configurar y aplicar las opciones para seleccionar el lote más antiguo desde un dispositivo móvil."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: ee45fed40b10dbe913c73e1186b726a39831816d
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017

---

# <a name="pick-oldest-batch-on-a-mobile-device"></a>Seleccionar el lote más antiguo en un dispositivo móvil

[!include[banner](../includes/banner.md)]

Puede acceder a la configuración **Seleccionar lote más antiguo** mediante un menú de dispositivo móvil y le permite forzar o advertir a trabajadores de almacén que seleccionen el lote más antiguo de su ubicación actual.  

## <a name="where-it-applies"></a>Dónde se aplica
Seleccionar lote más antiguo se configura en elementos de menú del dispositivo móvil y realiza la selección de artículos del lote siguiente.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>Cómo ajustar la configuración de Seleccionar lote más antiguo 
Para los artículos configurados para usar el trabajo existente, **Seleccionar lote más antiguo** se puede establecer en **Ninguno**, **Advertencia**, o **Forzar** en un menú del dispositivo móvil.

**Ninguno**: los trabajadores no recibirán ningún mensaje y podrán seleccionar los lotes en su ubicación.

**Advertencia** y **Forzar**: una lista de lotes con la fecha de vencimiento más antigua se mostrará sobre el control de lotes cuando el trabajador seleccione un lote. Si la ubicación está controlada por matrículas, una lista de matrículas que tengan el lote más antiguo se mostrará sobre el control del número de matrícula. 
-   **Advertencia**: si un trabajador elige una matrícula o lote que no se encuentren en la lista mostrada, el control queda en blanco y se muestra una advertencia de que hay un lote más antiguo para seleccionar. Para poder continuar el trabajo, el trabajador puede volver a seleccionar la misma matrícula o lote.  
-   **Forzar**: los trabajadores seguirán recibiendo el mensaje de que hay un lote más antiguo que se puede seleccionar.

