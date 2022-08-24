---
title: EUR-00015 Configurar Id. de IVA
description: Este procedimiento recorre los requisitos previos de registro del identificador de IVA, como configuración de un tipo de registro y asignación a la categoría del registro.
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
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
ms.openlocfilehash: 26120765b61a27cab544c37163a34a0ef18da30a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283794"
---
# <a name="eur-00015-set-up-vat-id"></a>EUR-00015 Configurar Id. de IVA

[!include [banner](../../includes/banner.md)]

Este procedimiento recorre los requisitos previos de registro del identificador de IVA, como configuración de un tipo de registro y asignación a la categoría del registro. Puede obtener información adicional acerca del identificador de registro y el procesamiento del identificador de registro, incluidas requisitos previos necesarios, en el artículo de ayuda Id. de registro. 

Esta información se aplica a todos los países o regiones europeos. La tarea se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal de entidad jurídica en Alemania. Esta tarea está destinada a administradores del sistema. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.

1. Vaya a Administración de la organización > Libreta de direcciones global > Tipos de registro > Tipos de registro.
2. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
3. En el campo Nombre, escriba "Id. de IVA".
4. En el campo Descripción, número de IVA.
5. En el campo País o región, especifique o seleccione un valor DEU
6. Seleccione Sí en el campo Único.
    * Seleccione esta casilla para comprobar si el Id. de IVA es único.  
7. Seleccione Sí en el campo Principal para país.
    * Seleccione esta casilla si el Id. de IVA debe ser efectivo para todas las direcciones que pertenecen al país/región especificados.  
8. Haga clic en Crear.
9. Haga clic en Agregar.
10. En el campo País o región, especifique o seleccione un valor ITA
11. En el campo Formato, escriba "###########".
    * Cuando se especifica un identificador de registro de este tipo para el país o la región seleccionada, el identificador de registro se comprueba según este formato.  
12. Seleccione la casilla Único.
    * Seleccione esta casilla para comprobar si el Id. de IVA es único.  
13. Seleccione la casilla Principal para país.
    * Seleccione esta casilla si el Id. de IVA debe ser efectivo para todas las direcciones que pertenecen al país/región especificados.  
14. Haga clic en Guardar.
15. Vaya a Administración de la organización > Libreta de direcciones global > Tipos de registro > Categorías de registro.
16. Haga clic en Nuevo.
17. En el campo País o región, especifique o seleccione un valor Id. de IVA, DEU
18. En el campo Categoría de registro, seleccione "Id. de IVA".
    * Asigne el tipo de registro que ha creado anteriormente a una categoría de registro predefinida.  
19. Haga clic en Nuevo.
20. En el campo País o región, especifique o seleccione un valor Id. de IVA, ITA
21. En el campo Categoría de registro, seleccione "Id. de IVA".
    * Asigne el tipo de registro que ha creado a una categoría de registro predefinida.  
22. Haga clic en Guardar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
