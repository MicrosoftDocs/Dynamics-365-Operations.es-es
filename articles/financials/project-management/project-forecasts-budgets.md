---
title: Previsiones y presupuestos del proyecto
description: Microsoft Dynamics 365 for Finance and Operations proporciona previsiones y presupuestos de proyecto para gestionar y controlar los proyectos.
author: KimANelson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ForecastModel, ProjYearEndProcess
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23501
ms.assetid: 4e6d1384-19a2-4232-b3f3-d2590c218bd7
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e31a013d6bf33b92b02bd9645a19380ba07f4a05
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="project-forecasts-and-budgets"></a>Previsiones y presupuestos del proyecto

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations proporciona dos formas de gestionar y controlar los proyectos: previsiones de proyecto y presupuestos de proyecto. 

Puede usar la previsión si su organización tiene una perspectiva operativa y se centra en los ingresos y costes derivados de transacciones específicas. Puede usar la gestión presupuestaria si su organización se centra en mayor medida en los importes financieros. 

Tanto las previsiones como los presupuestos de proyecto usan modelos de previsión que contienen los importes de transacción proyectados. 

Cada método tiene sus propias ventajas. Debe considerar los siguientes puntos antes de seleccionar un método para su organización.

|                           |                                          |                                                    |
|---------------------------|------------------------------------------|----------------------------------------------------|
|                           | **Previsión de proyecto**                  | **Presupuesto de proyecto**                              |
| **Asignación por períodos**     | No puede asignar explícitamente transacciones durante un período fiscal. Por el contrario, la previsión y el control de la previsión se basan en la duración del proyecto. Dado que las previsiones se basan en una fecha concreta, debe inferir el período desde la fecha. | Puede asignar las transacciones a la totalidad del proyecto o a un período fiscal. Si asigna a un período, puede transferir los importes no usados al siguiente período fiscal. |
| **Visualización de las transacciones**  | Puede ver las transacciones en los formularios de previsión, donde se muestran las previsiones de toda la empresa y para todos los proyectos, independientemente de la jerarquía. Para centrarse en un proyecto concreto, debe filtrar los datos.                                       | Puede ver las transacciones presupuestadas para una única jerarquía de proyecto. Por lo tanto, puede ver los detalles de la transacción para un proyecto principal o sus subproyectos.                 |
| **Variables de la transacción** | Cuando introduce las transacciones de previsión, puede usar todos los atributos que existen para una transacción real. Esto permite obtener una previsión más detallada. Por ejemplo, puede especificar los detalles de cantidad, trabajadores, artículos o propiedades de línea.         | Cuando introduce detalles presupuestarios, solo puede usar importes, categorías y actividades.                    |
| **Seguridad**              | La previsión se basa en transacciones que se introducen en los formularios de previsión y no implica ningún mecanismo de control de procesos. Cualquier trabajador con permisos para un formulario de previsión puede revisar la información sin aprobación.                                        | La gestión presupuestaria utiliza el sistema de flujos de trabajo, lo que habilita la administración de cambios y permite mantener un historial de las revisiones.         |
| **Tipos de entrada**           | Las entradas de transacciones de previsión se basan en el número de unidades y en el coste y los precios de las unidades de ventas.  | Los detalles presupuestarios se basan en los importes, que se dividen entre costes e ingresos.                                          |
| **Modelos de previsión**       | Ya que todas las previsiones deben estar asociadas a un modelo, puede crear varios modelos de previsión y también establecer submodelos.           | La gestión presupuestaria de proyectos limita los modelos de previsión que se usan para la gestión presupuestaria. Una menor cantidad de modelos de previsión puede ayudar a aumentar la coherencia en las proyecciones.                           |
| **Saturaciones de costes**         | Solo puede permitir o rechazar la entrada de las transacciones que provocarían una saturación de costes.   | La gestión presupuestaria de proyectos proporciona a los usuarios opciones de control adicionales. Puede permitir las advertencias y las saturaciones.                    |
| **Control**               | El control de previsión se realiza mediante la reducción de previsión. Los importes reales se restan de los saldos de transacciones de previsión sin trazas de auditoría. Esto puede dificultar el seguimiento de la ubicación en que se realizaron las transacciones reales.                   | En el control presupuestario de proyectos, los importes reales se restan de los importes del presupuesto restante. Esto permite realizar trazas de auditoría más claras.                                   |

## <a name="project-forecasts"></a>Previsiones de proyectos
Si usa la previsión de proyecto, puede especificar transacciones de previsión para cada tipo de transacción en los formularios de previsión. En las transacciones de previsión, puede usar cualquier atributo disponible para una transacción real, por ejemplo, rentabilidad de línea, atributos de línea, trabajadores o descripciones. También puede proyectar el tiempo que transcurrirá desde que se produzca un coste hasta que se facture al cliente. 

Las transacciones de previsión de proyecto se basan en unidades e importes. 

Debe asociar cada previsión de proyecto a un modelo de previsión. Cuando especifica una transacción de previsión, se sugiere automáticamente un modelo de previsión. El modelo de previsión actúa como contenedor para las transacciones de previsión. 

Puede designar los modelos de previsión como submodelos para el modelo. Esto le permite realizar la previsión para región, período de tiempo o departamento. Puede copiar las transacciones de previsión de un modelo para crear un modelo nuevo y transferirlas a la contabilidad general. Dado que existe una relación unívoca entre una previsión y un modelo, cada modelo de previsión constituye un presupuesto independiente de proyecto. 

Los modelos de previsión usan la reducción de la previsión como mecanismo de control de los proyectos. La reducción de la previsión permite que las transacciones reales reduzcan los saldos de transacción de previsión. Sin embargo, dado que la reducción de la previsión se aplica al proyecto superior de la jerarquía, ofrece una visión limitada de los cambios de la previsión. Por ejemplo, si un trabajador está asociado a un subproyecto, las transacciones reales del trabajador se registran en el proyecto principal. Esto puede hacer difícil realizar el seguimiento de los cambios porque no se puede determinar fácilmente qué transacción de qué subproyecto provocó una reducción en el importe de previsión. Por lo tanto, es una buena idea crear una copia de un modelo de previsión para la reducción de previsión que se usa. Puede usar informes para ver qué se preveía originalmente. 

Puede revisar, copiar, eliminar o transferir las previsiones de proyecto a un presupuesto de contabilidad general. Sin embargo, no existe ningún control del proceso. Cualquier trabajador que tiene permiso para un formulario de previsión puede crear revisiones sin necesidad de revisión.

-   **Revisar**: puede revisar una transacción de previsión en los mismos formularios en que se crearon las entradas originales.
-   **Copiar o eliminar**: al copiar transacciones de previsión, se copian las líneas de transacción de un modelo de previsión a otro. Al eliminar una previsión, se eliminan las transacciones de previsión del modelo de previsión. Para limitar las transacciones de previsión que se copian o eliminan, seleccione fechas y tipos de transacción específicos. Esto le permite copiar o eliminar solo partes concretas de una previsión.
-   **Transferir**: al transferir una previsión de proyecto a un presupuesto de contabilidad general, se transfieren las transacciones de previsión de un modelo de previsión a un presupuesto de contabilidad general. Puede sobrescribir cualquier transacción transferida previamente al presupuesto de contabilidad general al que transfiere la previsión de proyecto.

## <a name="project-budgets"></a>Presupuestos de proyecto
El método de presupuesto de proyecto es más sencillo que la previsión, aunque no se integra con los modelos de previsión. Usa un formulario de una sola entrada para los detalles de presupuesto originales y las revisiones, y solo permite las proyecciones basadas en importe, categoría o actividad. 

Con el presupuesto de proyecto, es necesario enviar todos los presupuestos y revisiones originales al flujo de trabajo del proyecto para su aprobación. Los flujos de trabajo proporcionan un mayor control sobre el proceso y crean un registro de historial de cambios. 

El presupuesto de proyecto es similar al presupuesto de contabilidad general, pero su configuración es más rápida y sencilla. En el caso de los proyectos, no es necesario configurar muchas de las opciones del presupuesto de contabilidad general, como las secuencias numéricas o la divisa, de forma independiente.

Los presupuestos de proyecto se asocian automáticamente a dos modelos de previsión: uno para el presupuesto original y otro para el presupuesto restante. Por lo tanto, los informes basados en modelos de previsión puedan usar los datos presupuestarios. Al comprometer un presupuesto de proyecto, el sistema crea transacciones de previsión basadas en los modelos asociados que se usan para fines de informes y control.

## <a name="forecast-models"></a>Modelos de previsión
Los modelos de previsión tienen una jerarquía de una sola capa. Esto significa que una previsión de proyecto se debe asociar a un modelo de previsión.

Si utiliza la previsión de proyecto, puede identificar los modelos como submodelos. A continuación, puede crear previsiones por departamentos, períodos de tiempo o regiones. Por ejemplo, podría crear un modelo de previsión para un año y, a continuación, crear submodelos para las previsiones regionales del noreste, el sureste, el noroeste y el suroeste que envían los encargados regionales. Mediante la selección de diferentes opciones en los informes disponibles, puede visualizar la información por previsión total o por submodelos.




