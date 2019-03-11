---
title: Definir celdas de trabajo de lean manufacturing (producción ajustada)
description: Una celda de trabajo es una forma específica de grupos de recursos que pueden usarse en actividades de proceso de lean manufacturing.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, InventLocationIdLookup, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f31fbd2ed8e20b92527af88fc3c955d3c66a364
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "350398"
---
# <a name="define-lean-manufacturing-work-cells"></a>Definir celdas de trabajo de lean manufacturing (producción ajustada)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Una celda de trabajo es una forma específica de grupos de recursos que pueden usarse en actividades de proceso de lean manufacturing. Las celdas de trabajo tienen ubicaciones de entrada y salida y una definición de capacidad basada en un modelo de flujo de producción. Para obtener más información acerca de los conceptos básicos de las celdas de trabajo de lean manufacturing y de cálculos de capacidad, consulte las notas del producto sobre lean manufacturing. La empresa de datos de demostración usada para crear este procedimiento es USMF.


## <a name="create-a-work-cell"></a>Cree una celda de trabajo. 
1. Vaya a Administración de la organización > Recursos > Grupos de recursos..
2. Haga clic en Nuevo.
3. En el campo Grupo de recursos, escriba un valor.
    * El id. de celda de trabajo suele ser un código sistemático y tiene que ser único para la entidad jurídica.  
4. En el campo Descripción, escriba un valor.
    * La descripción contiene el nombre o el título de la celda de trabajo.  
5. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
    * Una celda de trabajo se encuentra en un sitio específico. Tanto el almacén de entrada como de salida y la ubicación se tienen que encontrar en este sitio.  
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. En el campo Unidad de producción, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione una unidad de producción a la que pertenezca esta celda de trabajo.  
9. Active la casilla Celda de trabajo.
    * Para usar un grupo de recursos como celda de trabajo lean, la casilla de la celda de trabajo tiene que estar seleccionada.  Tenga en cuenta que no se puede cambiar esta propiedad una vez creado el grupo de recursos.  
10. En el campo Almacén de entrada, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Para el control del material y de la contabilidad, el material almacenado provisionalmente en la planta se suele asignar a un almacén virtual específico. Sin embargo, si desea reabastecer las ubicaciones mediante el trabajo de almacén, deben formar parte del almacén de materias primas de recepción.  
12. En el campo Ubicación de entrada, haga clic en el botón desplegable para abrir la búsqueda.
13. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Tenga en cuenta que para una actividad de proceso, la ubicación de entrada se puede sobrescribir en general o para un producto o una variante del producto determinados definiendo las actividades de picking que alimentan la actividad del proceso. Las ubicaciones de entrada de una celda de trabajo no pueden estar controladas por matrículas de entidad de almacén.  
14. En el campo Almacén de salida, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, busque y seleccione el registro deseado.
    * En flujos de producción de actividad o líneas de producción múltiples, este es a menudo el almacén de entrada de la siguiente celda de trabajo o el almacén de tránsito o ventas donde un producto se suele transferir después del proceso de producción. Recuerde que al modelar los procesos de lean manufacturing, el transporte es normalmente inútil, como lo es la notificación del transporte.  
16. En la lista, haga clic en el vínculo de la fila seleccionada.
17. En el campo Ubicación de salida, haga clic en el botón desplegable para abrir la búsqueda.
    * En un flujo de producción con múltiples actividades de proceso, esto es a menudo la ubicación de entrada de la siguiente celda de trabajo.  
18. En la lista, busque y seleccione el registro deseado.
19. En la lista, haga clic en el vínculo de la fila seleccionada.
20. Expanda o contraiga la sección Operación.
    * Se debe proporcionar una Categoría de tiempo de ejecución para habilitar el cálculo de costes y el procesamiento de trabajos kanban lean.  
21. En el campo Categoría de tiempo de ejecución, haga clic en el botón desplegable para abrir la búsqueda.
22. En la lista, busque y seleccione el registro deseado.
    * La categoría de coste del tiempo de ejecución se usa en el cálculo de coste estándar y en la contabilización previa de los costes.  
23. En la lista, haga clic en el vínculo de la fila seleccionada.
24. Expanda o contraiga la sección Calendarios.
25. Haga clic en Agregar.
26. En el campo Calendario, haga clic en el botón desplegable para abrir la búsqueda.
27. En la lista, busque y seleccione el registro deseado.
    * Normalmente las celdas de trabajo de un sitio determinado usan el sitio el mismo calendario laboral. Si las celdas de trabajo pueden tener calendarios de tiempo de trabajo individuales, es posible que deba crear un calendario laboral específico para la celda de trabajo. Tenga en cuenta que el calendario debe tener un horario de trabajo estándar definido cuando se utiliza para una celda de trabajo lean, porque la definición de la capacidad se suele relacionar con el horario de trabajo estándar de un día laborable.  
28. En la lista, haga clic en el vínculo de la fila seleccionada.
29. Expanda o contraiga la sección Capacidad de la celda de trabajo.
30. Haga clic en Agregar.
31. En el campo Modelo de flujo de producción, haga clic en el botón desplegable para abrir la búsqueda.
32. En la lista, busque y seleccione el registro deseado.
    * Este procedimiento requiere el tipo de modelo de flujo de producción Capacidad de proceso, para mostrar la definición de la capacidad de proceso.  
33. En la lista, haga clic en el vínculo de la fila seleccionada.
34. En el campo Período de capacidad, seleccione una opción.
    * Se incluyen las siguientes opciones: Día laborable estándar: la capacidad se expresa por la duración del día laborable estándar del calendario laboral para la celda de trabajo. Para cada día, el tiempo de trabajo real se determina a partir del calendario y la capacidad disponible efectiva se calcula en función de eso.   Semana: habilita una capacidad semanal. No se realiza ningún ajuste por el horario de trabajo real.   Mes: permite una capacidad mensual. No se realiza ningún ajuste por la capacidad real.   Normalmente, el día laborable estándar se usa para períodos diarios y la capacidad semanal se usa para períodos de capacidad semanales.  
35. En el campo Cantidad promedio de proceso, especifique un número.
    * Tenga en cuenta que una operación lean nunca se configura para la máxima capacidad posible en un entorno ideal. En su lugar, se debe definir siempre la capacidad para las operaciones que se ejecutan en circunstancias normales.  
36. En el campo Unidad, haga clic en el botón desplegable para abrir la búsqueda.
37. En la lista, haga clic en el vínculo de la fila seleccionada.
38. Resuelva los cambios en la unidad.

## <a name="add-a-financial-dimension"></a>Agregar una dimensión financiera
1. Expanda o contraiga la sección Dimensiones financieras.
    * Tenga en cuenta que las dimensiones financieras definidas en el flujo de producción anulan la dimensión financiera de una celda de trabajo especificada.    Las dimensiones financieras que se pueden seleccionar dependen de la configuración de las dimensiones financieras del sistema. Los siguientes pasos corresponden a los datos de demostración establecidos en la empresa USMF. Al usar distintos datos, es posible que los pasos no sean aplicables.  
2. En el campo de centro de coste, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
    * Las dimensiones que se tienen que seleccionar en celdas de trabajo lean dependen de la implementación de las dimensiones financieras en el modelo de contabilidad para una entidad jurídica específica.  
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo de grupo de artículos, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="save"></a>Guardar
1. Haga clic en Guardar.

