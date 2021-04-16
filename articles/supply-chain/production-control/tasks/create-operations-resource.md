---
title: Crear un recurso de operaciones
description: Un recurso de operaciones realiza las actividades de un proyecto o de un proceso de producción.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9ab91c449293338469fa2832156a85c4c32301fd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829051"
---
# <a name="create-an-operations-resource"></a>Crear un recurso de operaciones

[!include [banner](../../includes/banner.md)]

Un recurso de operaciones realiza las actividades de un proyecto o de un proceso de producción. En este procedimiento se muestra cómo definir un recurso de operaciones. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.

1. Vaya a Recursos.
2. Haga clic en Nuevo.
3. En el campo Recurso, escriba un valor.
4. En el campo Descripción, escriba un valor.

## <a name="define-capacity-and-consumption-parameters"></a>Definir los parámetros de programación y de consumo
1. Expanda la sección Operación.
2. En el campo Porcentaje de residuos, escriba un número.
3. En el campo Categoría de configuración, especifique o seleccione un valor.
    * Especifique la categoría de coste que define cómo contabilizar el coste de la configuración.  
4. En el campo Tiempo de ejecución, especifique o seleccione un valor.
    * Especifique la categoría de coste que define cómo contabilizar el coste del tiempo de ejecución.  
5. En el campo Categoría por unidad/pieza, especifique o seleccione un valor.
    * Especifique la categoría de coste que define cómo contabilizar el coste de recursos a partir de la cantidad de salida.  
6. En el campo Unidad de capacidad, seleccione una opción.
    * Especifique la unidad en la que desea expresar la capacidad del recurso de operaciones.  
7. En el campo Capacidad, escriba un número.
8. En el campo Porcentaje de eficacia, especifique un número.
    * Especifique la eficacia que espera del recurso de operaciones. El porcentaje de eficacia ajusta el rendimiento del recurso de operaciones y afecta al tiempo reservado para el recurso.  
9. En el campo Porcentaje de programación de operaciones, especifique un número.
    * Especifique el porcentaje máximo de capacidad del recurso de operaciones que desea utilizar en la programación de operaciones.  
10. Seleccione Sí en el campo Capacidad limitada.
    * Establezca esta opción en Sí si el recurso de operaciones debe programarse en función de la capacidad real disponible y si deben tenerse en cuenta las reservas de capacidad existentes. Si esta opción se establece en No, se supone que el recurso de operaciones tiene capacidad infinita y el recurso puede estar reservado en exceso.  
11. Seleccione Sí en el campo Recurso de cuello de botella.

## <a name="define-working-times"></a>Definir los horarios de trabajo
1. Expanda la sección Calendarios.
2. Haga clic en Agregar.
3. En el campo Calendario, especifique o seleccione un valor.
    * Especifique el calendario laboral que define la capacidad (en horas) del recurso.  
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="define-resource-capabilities"></a>Definir capacidades de recursos
1. Expanda la sección Capacidades.
2. Haga clic en Agregar.
    * Una capacidad es la posibilidad de que un recurso de operaciones realice una actividad concreta. El motor de programación asigna los recursos emparejando los requisitos de recurso de cada actividad con las capacidades de recursos de operaciones disponibles.  
3. En el campo Capacidad, especifique o seleccione un valor.
4. En el campo Nivel, escriba un número.
    * Especifique el nivel de aptitud por el que el recurso procesa la capacidad.  
5. En el campo Prioridad, especifique un número.
    * Especifique la prioridad del recurso de operaciones con respecto a la capacidad. Al programar por prioridad, seleccione primero el recurso de operaciones con la máxima prioridad (el menor valor numérico).  

## <a name="assign-resource-to-resource-group"></a>Asignar un recurso a un grupo de recursos
1. Expanda la sección Grupos de recursos.
2. Haga clic en Agregar.
    * El grupo de recursos define el sitio, la unida de producción y el contexto de almacén para los recursos de operaciones. El recurso de operaciones solo puede programarse cuando está asignado a un grupo de recursos y solo en el sitio en el que se encuentra el grupo de recursos.  
3. En el campo Grupo de recursos, especifique o seleccione un valor.
4. En el campo Ubicación de entrada, especifique o seleccione un valor.
    * Especifique la ubicación de almacén cuyos materiales utiliza el recurso de operaciones.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]