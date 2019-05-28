---
title: Recuento cíclico de ubicaciones parcial
description: Los planes de recuento cíclico dirigen las operaciones de recuento. Puede solicitar que solo los productos específicos y las variantes de producto entren en el recuento en lugar de todos los inventarios disponibles en una ubicación.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd7cb8b35023ed63af191545d01c60c2c7cc8ef5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570583"
---
# <a name="partial-location-cycle-counting"></a>Recuento cíclico de ubicaciones parcial

[!include [banner](../includes/banner.md)]

Los planes de recuento cíclico dirigen las operaciones de recuento. Puede solicitar que solo los productos específicos y las variantes de producto entren en el recuento en lugar de todos los inventarios disponibles en una ubicación.

Si utiliza los planes de recuento cíclico para crear trabajos de recuento, puede dirigir las operaciones que recuento reales. Puede solicitar que solo los productos específicos y las variantes de producto entren en el recuento en lugar de todos los inventarios disponibles en una ubicación. Al filtrar según productos específicos, el responsable del almacén puede reducir los costes generales de revisión, evitar errores de consolidación y ahorrar tiempo.

## <a name="how-to-configure-partial-location-cycle-counting"></a>Cómo configurar el recuento cíclico de ubicación parcial
Cuando se usa el proceso de trabajo de almacén para contar operaciones, un encabezado de trabajo se crea para cada ubicación. Al definir el plan de ciclo de recuento, puede usar la consulta **Seleccionar ubicaciones** para limitar trabajo de recuento cíclico que se crea. Al seleccionar los productos para el plan de recuento cíclico, puede seleccionar las consultas de producto y de la variante del producto para limitar lo que entra en el recuento. 

Puede asociar una **plantilla de trabajo** a un plan de recuento cíclico para definir cómo debe crearse el trabajo de recuento cíclico. La plantilla del trabajo para las operaciones de recuento se referencia directamente desde el plan de recuento cíclico. 

Cuando defina los detalles de la plantilla de trabajo, puede usar la opción **Saltos de línea de trabajo** para especificar si las líneas de trabajo deben agruparse por número de artículo o número de la variante del producto. Se requiere esta configuración si desea hacer el recuento del inventario disponible para los productos específicos en una ubicación. Las líneas de trabajo de recuento cíclico que se crean que tendrá el nivel de información que defina aquí, y la operación de recuento dirigida será administrada en función de este nivel. 

Si asocia planes de recuento cíclico a las plantillas de trabajo mediante la opción **Saltos de líneas de trabajo**, el campo **Recuento cíclico parcial** se ha activado para el trabajo de recuento cíclico que se crea, y las líneas de trabajo de recuento cíclico se crearán en función de la definición de la plantilla de trabajo. 

Antes de que el trabajo de recuento cíclico parcial se pueda procesar, debe, al menos, seleccionar **Mostrar número de artículo** para el elemento de menú del dispositivo móvil como parte de la configuración del recuento cíclico. Se pedirá al operador de almacenes que registre solo la información del recuento relacionada con las líneas de recuento (números de artículo y dimensiones del producto). El resto del inventario disponible será omitido para este proceso de recuento. 

Para el proceso de recuento cíclico parcial, la fecha o la hora de **Último recuento cíclico** no se actualizará para la ubicación.

## <a name="example"></a>Ejemplo
Para este ejemplo, solo se debe contar el número de artículo A0001 en el almacén 61.

1.  Se crea una plantilla de trabajo nueva para el recuento cíclico. La opción **Saltos de línea de trabajo** se usa para agrupar líneas de trabajo de recuento para el número de artículo. Por lo tanto, el trabajo de recuento cíclico que se crea tendrá líneas por número de artículo. También puede agrupar las líneas por número de variante del producto.
2.  Un nuevo plan de recuento cíclico se crea que hace referencia a la plantilla de trabajo recién creada. El plan de recuento cíclico incluye todas las ubicaciones en el almacén 61 (consulta **Seleccionar ubicaciones**) que se retienen en inventario para el número de artículo A0001. La selección de productos específicos se define en la sección **Selecciones producto de recuento cíclico**.
3.  Puede seleccionar productos para sus planes de recuento cíclico estableciendo el campo **Ubicaciones vacías** **Excluir vacío**. Cuando el plan de recuento cíclico se procesa, se crea el trabajo de recuento cíclico parcial para el número de artículo A0001. El proceso de recuento real se puede realizar mediante un elemento de menú del dispositivo móvil para el recuento cíclico dirigido.



<a name="additional-resources"></a>Recursos adicionales
--------

[Recuento cíclico](cycle-counting.md)

