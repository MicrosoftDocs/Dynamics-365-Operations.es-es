---
title: EUR-00015 Búsqueda de la parte mediante el Id. de IVA
description: Este procedimiento muestra cómo realizar una búsqueda de parte mediante un identificador de registro.
author: AdamTrukawka
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
ms.openlocfilehash: 0688de30327abe0925efe3daf44bcbab8a096c97
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288482"
---
# <a name="eur-00015-party-search-using-vat-id"></a>EUR-00015 Búsqueda de la parte mediante el Id. de IVA

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo realizar una búsqueda de parte mediante un identificador de registro. Antes de poder completar este procedimiento, debe configurar identificadores de IVA y especificar cualquier Id. de IVA para proveedores, clientes o entidades jurídicas.

Este procedimiento se aplica a todos los países o regiones europeos. Este procedimiento se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal en Alemania. Este procedimiento se ha creado para un administrador de proveedores o un administrador de clientes. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.

1. Vaya a Administración de la organización > Libreta de direcciones global > Libreta de direcciones global.
2. Haga clic en Búsqueda de id. de registro.
3. Haga clic en Agregar.
4. En el campo Tipo de registro, especifique o seleccione un valor.
    * Por ejemplo, en el caso de que desee encontrar a las partes con un identificador de registro del tipo identificador de IVA, seleccione el identificador del IVA.  
5. En el campo País o región, especifique o seleccione un valor.
    * Por ejemplo, escriba DEU.  
6. En el campo Número de registro, escriba un valor.
7. Haga clic en Buscar.
    * Todas partes con ese identificador del registro se mostrará.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
