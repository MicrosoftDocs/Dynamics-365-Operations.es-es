---
title: Configuración del embalaje manual (febrero de 2016 y mayo de 2016)
description: El proceso de embalaje le permite validar y empaquetar productos en contenedores.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2843c42474fcd4afbbc2cd7753c0d06cfe467dbe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810375"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a>Configuración del embalaje manual (febrero de 2016 y mayo de 2016)

[!include [banner](../../includes/banner.md)]

El proceso de embalaje le permite validar y empaquetar productos en contenedores. En este proceso, los trabajadores de almacén seleccionan productos de las ubicaciones de almacenamiento y las mueven a una estación de embalaje donde comprueban los tipos y las cantidades de artículos, y los asignan a los contenedores adecuados. Cuando un contenedor se empaqueta por completo, pueden cerrarlo y moverlo a los muelles de salida, y los productos estarán listos para enviarse. Este procedimiento usa la empresa de demostración USMF. Este procedimiento es únicamente para las versiones de febrero de 2016 y mayo de 2016 de Dynamics 365 for Operations.


## <a name="set-up-location-profiles"></a>Configurar perfiles de ubicación
1. Vaya a Gestión de almacenes > Configurar > Almacén > Perfiles de ubicación.
2. Haga clic en Nuevo.
    * El perfil de la ubicación se usa para las instalaciones de embalaje y contiene información y reglas para una ubicación.  
3. En el campo Id. de perfil de ubicación, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Formato de ubicación, especifique o seleccione un valor.
6. En el campo Tipo de ubicación, especifique o seleccione un valor.
7. Seleccione Sí en el campo Permitir artículos combinados.
8. Seleccione Sí en el campo Permitir estados de inventario combinados.
9. Seleccione Sí en el campo Anular reglas para días de lote.
10. Cierre la página.

## <a name="set-up-warehouse-management-parameters"></a>Configurar parámetros de gestión de almacenes 
1. Vaya a Gestión de almacenes > Configurar > Parámetros de gestión de inventario y almacenes.
2. Haga clic en la ficha Embalaje.
3. En el campo Id. de perfil para la ubicación de embalaje, especifique o seleccione un valor.
    * Seleccione el perfil de ubicación que desea usar para embalaje.  
4. Cierre la página.

## <a name="set-up-container-types"></a>Configurar tipos de contenedor
1. Vaya a Administración de almacenes > Configurar > Contenedores > Tipos de contenedor.
2. Haga clic en Nuevo.
    * Se pueden definir los tipos de contenedores que se usarán. Puede especificar las dimensiones físicas del contenedor, incluida la tara, el peso máximo, el volumen máximo, la longitud máxima, el ancho y el peso.  Los atributos son campos personalizados que le permiten agregar dimensiones adicionales en el tipo de contenedor.     
3. En el campo Código de tipo de contenedor, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Tara, escriba un número.
6. Escriba un número en el campo Peso máximo.
7. En el campo Volumen, escriba un número.
8. En el campo Longitud, especifique un número.
9. En el campo Ancho, escriba un número.
10. En el campo Alto, escriba un número.
11. Haga clic en Guardar.
12. Cierre la página.

## <a name="set-up-packing-profiles"></a>Configurar perfiles de embalaje
1. Vaya a Gestión de almacenes > Configurar > Embalaje > Perfiles de embalaje.
2. Haga clic en Nuevo.
3. En el campo Id. del perfil de empaquetado, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Id. de perfil de cierre de contenedor, especifique o seleccione un valor.
    * Un id. de perfil de cierre de contenedor es opcional y es el perfil del contenedor de cierre predeterminado para este perfil de embalaje.  
6. En el campo Modo del id. de contenedor, seleccione una opción.
    * Esta opción determina si se generará automáticamente un id. de contenedor cuando se cree un o contenedor o si se creará un id. de contenedor manualmente.  
7. En el campo Tipo de contenedor, especifique o seleccione un valor.
    * El tipo de contenedor se usará de forma predeterminada cuando se cree un nuevo contenedor.  
8. Active la casilla Crear contenedor automáticamente al cerrar el contenedor.
9. Haga clic en Guardar.
10. Cierre la página.

## <a name="set-up-container-closing-profiles"></a>Configurar perfiles de cierre de contenedor
1. Vaya a Administración de almacenes > Configurar > Contenedores > Perfiles de cierre de contenedor.
    * Los perfiles de cierre del contenedor definen qué sucede cuando se cierra un contenedor. Puede configurar varios perfiles de contenedor de cierre.       
2. Haga clic en Nuevo.
3. En el campo Id. de perfil de cierre de contenedor, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Manifiesto en, seleccione una opción.
    * Especifique si se producirán manifiestos al cerrar contenedores de cierre o al confirmar el envío. Tenga en cuenta que los manifiestos requieren Administración de transporte. Los manifiestos se deben implementar en los motores de transporte para que funcionen.  
6. En el campo Almacén, especifique o seleccione un valor.
7. En el campo Ubicación predeterminada del envío final, especifique o seleccione un valor.
    * Esta será la ubicación a la que se moverán los productos después de que se cierren los contenedores. Esta ubicación debe tener un perfil de ubicación definido en Parámetros de almacén.  
8. En el campo Unidad de peso, especifique o seleccione un valor.
9. Haga clic en Guardar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]