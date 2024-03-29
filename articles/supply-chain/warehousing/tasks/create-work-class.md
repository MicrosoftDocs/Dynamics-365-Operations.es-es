---
title: Crear una clase de trabajo
description: Este procedimiento muestra cómo configurar una clase de trabajo.
author: Mirzaab
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c2a99771bc10f12f20fca1689b8786f3de8b316
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572322"
---
# <a name="create-a-work-class"></a>Crear una clase de trabajo

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo configurar una clase de trabajo. Las clases de trabajo se usan para dirigir y/o para limitar el tipo de líneas de pedido de trabajo que un trabajador de almacén puede procesar en un dispositivo móvil. Las líneas que un trabajador puede procesar se determinan a partir de las clases de trabajo en los elementos de menú del dispositivo móvil a los que el trabajador de almacén tiene acceso y la clase de trabajo especificada en las líneas de trabajo. Las clases de trabajo también se pueden usar para validar la ubicación de colocación para una línea de pedido de trabajo. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Este procedimiento va destinado al encargado de almacén.

1. Vaya a Gestión de almacenes > Configurar > Trabajo > Clases de trabajo.
2. Haga clic en Nuevo.
3. En el campo Identificador de la clase de trabajo, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Tipo de pedido de trabajo, seleccione una opción.
6. Haga clic en Nuevo.
7. En el campo Tipo de ubicación, escriba un valor.
    * Si selecciona un tipo de ubicación, se establece una restricción sobre dónde se pueden colocar los artículos una vez seleccionados. Esta configuración se usa cuando una directiva de ubicación intenta resolver la ubicación, o si un trabajador del almacén indica manualmente la ubicación para el elemento de menú del dispositivo móvil.  
8. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]