---
title: Actualizar costes estándar para un nuevo artículo fabricado
description: Este artículo proporciona orientación para actualizar los costes estándar para un nuevo artículo fabricado.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79693
ms.assetid: ba64b70f-3f4c-4373-9a7d-8fd07c45a8cf
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ebd53d66eb81bbee9d3e67d05102c8df413d2a3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214111"
---
# <a name="update-standard-costs-for-a-new-manufactured-item"></a>Actualizar costes estándar para un nuevo artículo fabricado

[!include [banner](../includes/banner.md)]

Este artículo proporciona orientación para actualizar los costes estándar para un nuevo artículo fabricado. 

En las directrices siguientes se supone que se usa el enfoque de dos versiones para actualizar costes estándar. En este enfoque, una versión de gestión de costes contiene los costes estándar que se definieron originalmente para el período congelado y la segunda versión de gestión de costes contiene las actualizaciones incrementales relacionadas con los nuevos artículos fabricados. Las actualizaciones incrementales se especifican como registros de coste en la segunda versión de gestión de costes y, finalmente, se activan. El enfoque de dos versiones requiere que defina una segunda versión de gestión de costes. Esta son las instrucciones para definir esta versión de gestión de costes:

-   Asigne un tipo de gestión de costes de **Coste estándar**.
-   Asignar un identificador significativo que indica el contenido de la versión de gestión de costes, como **2016-ACTUALIZACIONES**.
-   En el grupo de campos **Permitir tipos de precio**, asegúrese de que **Precio de coste** se establece en **Sí**.
-   Permita que se especifiquen registros de costes para todos los sitios (es decir, deje el campo **Sitio** en blanco). Si especifica un sitio, los registros de costes se pueden especificar solo para ese sitio.
-   Usar un principio de reserva de **Activo**.

Para agregar nuevos artículos de fabricación a lo largo del período congelado, siga estos pasos:

1.  Utilice la página **Configuración de la versión de gestión de costes** para permitir la entrada de registros de coste en la segunda versión de gestión de costes que contenga las actualizaciones incrementales. Impida la activación de costes pendientes donde la activación se permitirá después de que los costes pendientes se hayan definido completamente y de manera precisa. Indique una fecha de inicio en blanco como directiva en la versión de gestión de costes y, a continuación, especifique una fecha de inicio al especificar cada registro de coste. La fecha de inicio debe representar una fecha anterior a la compra o fabricación de los artículos nuevos.
2.  Use la página **Precio de artículo** para entrar los registros de coste de los nuevos artículos comprados. Para cada uno, especifique la versión de gestión de costes que contenga las actualizaciones incrementales y use una fecha de inicio anterior a la fecha de fabricación prevista de los nuevos artículos fabricados.
3.  Calcule el coste de los nuevos artículos fabricados mediante el formulario **Cálculo**. Abra la página **Cálculo** en la página **Mantenimiento de la versión de gestión de costes** y, a continuación, seleccione la versión de gestión de costes que contenga las actualizaciones incrementales. Utilice los criterios de selección para especificar el nuevo artículo fabricado y uno de sus componentes fabricados. En una estructura de productos multinivel, también es posible que sea necesario especificar cualquier artículo principal que contenga los nuevos artículos fabricados como componente. Especifique una fecha de inicio para el cálculo de la lista de materiales (L. MAT.) que corresponda al inicio de la fabricación de los nuevos artículos fabricados. La fecha de inicio debe estar dentro de las fechas vigentes de la versión L. MAT y versión de ruta del artículo. **Nota:** Un registro de costes ausente podría indicar un nuevo artículo fabricado. Los cálculos de L. MAT pueden limitarse a los artículos con costes ausentes.
4.  Compruebe que los costes calculados de los nuevos artículos fabricados están completos y precisos. Utilice la página **Completar** para revisar los costes calculados de todos los registros de coste de artículos y también revisar si hay algún mensaje de aviso del registro de información. También puede usar la página **Cálculo** para revisar una lista de costes calculados.
5.  Utilice la página **Configuración de la versión de gestión de costes**  para modificar el indicador de bloqueo y permitir la activación de los registros de costes pendientes incluidos en la segunda versión de gestión de costes.
6.  Use la página **Activar precios** (que se abre desde la página **Mantenimiento de la versión de gestión de costes**) para habilitar todos los registros de costes pendientes en la segunda versión de gestión de costes. También puede habilitar los registros de costes pendientes para los artículos individuales haciendo clic en el botón **Activar** de la página **Precio de artículo**.
7.  Use la página **Configuración de la versión de gestión de costes** para modificar los indicadores de bloqueo de la segunda versión de gestión de costes para impedir la actualización posterior de los datos. Las directivas de bloqueo impiden la entrada de nuevos costes pendientes y la activación de costes pendientes.




