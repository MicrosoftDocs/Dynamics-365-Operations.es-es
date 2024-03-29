---
title: Configuración de un índice de combustible de transportista
description: Esta guía muestra cómo crear una región de índice de combustible, un índice de combustible y un índice de combustible de transportista.
author: Weijiesa
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb976369f9e8254f76a4de18df619d4420cf0538
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672693"
---
# <a name="set-up-a-carrier-fuel-index"></a>Configuración de un índice de combustible de transportista

[!include [banner](../../includes/banner.md)]

Esta guía muestra cómo crear una región de índice de combustible, un índice de combustible y un índice de combustible de transportista. La región de índice de combustible especifica a qué región se debe aplicar el índice de combustible, y el índice de combustible especifica un precio por combustible para un período de tiempo concreto. Para reflejar el cambio de precios de combustible en el tiempo, puede asociar varios índices de combustible con un transportista.  Estas tareas las realiza normalmente el coordinador de transporte. Puede utilizar este procedimiento con la empresa de datos de demostración USMF o utilizar sus propios datos.


## <a name="create-a-fuel-index-region"></a>Creación de una región de índice de combustible
1. Vaya a Administración de transporte > Configuración > Índices de combustible > Regiones de índice de combustible.
    * Primero es necesario crear las distintas regiones donde se opera y calcular diferentes suplementos por combustible.  
2. Haga clic en Nuevo.
3. En el campo Región, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. Haga clic en Guardar.

## <a name="create-a-fuel-index"></a>Crear un índice de combustible
1. Vaya a Administración de transporte > Configuración > Índices de combustible > Índices de combustible.
    * Para las regiones configuradas es necesario introducir los precios reales del combustible.  
2. Haga clic en Nuevo.
3. En el campo Región, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Precio por litro, especifique un número.
6. En el campo Fecha y hora iniciales de vigencia, especifique una fecha y una hora.
7. Haga clic en Guardar.

## <a name="create-a-carrier-fuel-index"></a>Creación de un índice de combustible de transportista
1. Vaya a Administración de transporte > Configuración > Índices de combustible > Índices de combustible del transportista.
2. Haga clic en Nuevo.
3. En el campo Índice de combustible del transportista, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Haga clic en Nuevo.
6. En el campo Fecha y hora iniciales de vigencia, especifique una fecha y una hora.
7. En el campo Precio por litro de origen, escriba un número.
    * En este ejemplo, puede definir el campo Precio por litro de origen en "1.95".  
8. En el campo Precio por litro de destino, escriba un número.
    * En este ejemplo, puede definir el campo Precio por litro de origen en "2".  
9. En el campo Porcentaje, especifique un número.
    * En este ejemplo, puede definir el porcentaje en "3".  
10. En el campo Divisa, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, busque y seleccione el registro deseado.
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. Haga clic en Guardar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]