---
title: "Cálculos de L con costes estándar"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcGroup, BOMCalcTable, ProdParmBOMCalc
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 65571
ms.assetid: ca17e6dd-b16a-4bbc-8682-b16345ab9906
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: deeecd478febe0afc45b90f7d962e955af46210f
ms.lasthandoff: 03/31/2017


---

# <a name="bom-calculations-with-standard-costs"></a>Cálculos de L con costes estándar



La información sobre los artículos adquiridos que se utiliza en el cálculo de costes estándar de L. MAT incluye:
-   Coste: los costes de un artículo comprado se mantienen como registros de coste específico del sitio en una versión de gestión de costes para costes estándar. Cada registro de costes tiene una fecha de vigencia, y la fecha del cálculo de la lista de materiales determina el registro de costes que se usará. Por ejemplo, un cálculo de la lista de materiales con una fecha de cálculo futura puede usar un registro de costes con un estado pendiente y una fecha de vigencia futura.
-   Grupo de costes: el grupo de costes asignado al artículo adquirido proporciona la base para la segmentación de costes de los costes calculados del artículo fabricado.
-   Las condiciones de aviso que se incorporan al grupo de cálculo de la lista de materiales del artículo permiten al cálculo de la lista de materiales para identificar problemas potenciales. Esto puede suceder cuando el artículo comprado tiene un coste cero, una cantidad cero en una lista de materiales o un registro de coste obsoleto. Las condiciones de aviso aplicables pueden anularse al iniciar un cálculo de lista de materiales.

La información sobre los artículos fabricados que se utiliza en el cálculo de costes estándar de L. MAT incluye:
-   Cantidad de pedido estándar el inventario: la cantidad de pedido estándar del artículo para el inventario actúa como el tamaño del lote de contabilidad predeterminado para la amortización de costes constantes en un cálculo de lista de materiales. El tamaño del lote de contabilidad también reflejará el múltiplo de la cantidad de pedido si se especifica.
-   Las condiciones de aviso que se incorporan al grupo de cálculo de la lista de materiales del artículo permiten al cálculo de la lista de materiales para identificar problemas potenciales. Un ejemplo podría ser que el artículo fabricado no tiene una lista de materiales o ruta. Las condiciones de aviso aplicables pueden anularse al iniciar un cálculo de lista de materiales.

La información sobre las listas de materiales que se utiliza en el cálculo de costes estándar de L. MAT incluye:
-   Versión de la lista de materiales: la versión de la lista de materiales asignada al artículo fabricado tiene fechas de inicio y finalización de vigencia, así como un estado de aprobado y activo. La versión de la cuenta puede ser empresarial o específica del sitio, y puede reflejar opcionalmente los puntos de interrupción de cantidad.
-   Cantidad del artículo de la línea de lista de materiales: un componente comúnmente tiene una cantidad requerida, pero puede ser una constante. La cantidad del componente se expresa normalmente para producir un artículo principal, pero puede ser expresada por 100 o por 1000 para gestionar las emisiones con precisión decimal. La cantidad del componente también se puede calcular en función de medidas.
-   El valor residual de los artículos de línea de L. MAT: los componentes pueden incluir una cantidad variable o constante de valor residual planificado.
-   Las fechas válidas de los artículos de línea de L. MAT: los componentes pueden incluir las fechas inicial y final.
-   Tipo de producción de los artículos de línea de la lista de materiales: el tamaño del lote de gestión de costes para la amortización de costes constantes reflejará la cantidad del cálculo de la lista de materiales y un modo de expansión de "hacer para pedir", debido a que el cálculo de la lista de materiales supone que el componente fabricado se producirá en la cantidad exacto, y no en su cantidad de pedido estándar.
-   La sub-L. MAT de los componentes fabricados: los componentes fabricados pueden incluir opcionalmente una versión de L. MAT específica, que puede utilizarse en lugar de la versión de L. MAT activa actual del artículo en el cálculo de L. MAT.
-   La subruta de los componentes fabricados: los componentes fabricados pueden incluir opcionalmente una versión de ruta específica, que puede utilizarse en lugar de la versión de ruta activa actual del artículo en el cálculo de L. MAT.
-   Número de operación e impacto de los porcentajes de valor residual: el número de operación vincula un componente con una operación específica, y las operaciones pueden tener un porcentaje de valor residual. El vínculo permite que los cálculos de la lista de materiales represente porcentajes de valor residual y porcentajes acumulativos de valores residuales a través de operaciones múltiples en la cantidad pedida de componente.
-   El artículo de línea de la lista de materiales omitido en el cálculo de costes: se puede omitir un componente en el cálculo de la lista de materiales.

La información sobre recursos de operaciones que se utiliza en el cálculo de costes estándar de la lista de materiales incluye:
-   Costes por hora: los costes por hora asociados a un recurso de operaciones se expresan como categorías de coste que se asignan para configurar tiempo y tiempo de ejecución. Estas categorías de coste se deben identificar para los grupos de recursos y los recursos de operaciones. Los costes por hora asociados a una categoría de coste pueden ser específicos del sitio o empresariales.
-   Costes unitarios: algunos entornos de fabricación asignan costes de recursos de operaciones por unidad de salida, que sería expresado como una categoría de coste diferente para la cantidad. Por ejemplo, los costes relacionados con la cantidad pueden reflejar las tarifas de mano de obra por pieza, o un fabricante de pintura puede asignar costes de recursos de operaciones por galón de salida.
-   Información anulada de recursos de operaciones de rutas: las operaciones heredan la información de rutas de las categorías de costes, donde esta información puede ser anulada. Los cálculos de la lista de materiales utilizarán la información de categorías de costes especificada en las operaciones de rutas.
-   Grupo de costes para una categoría de costes: el grupo de costes asignado a una categoría de costes proporciona el segmento de coste de los costes calculados de un artículo fabricado. Por ejemplo, se pueden usar diferentes grupos de costes para segmentar los costes calculados que están asociados a las máquinas y la mano de obra o con tiempo de preparación y ejecución.

La información sobre rutas que se utiliza en el cálculo de costes estándar de L. MAT incluye:
-   Versión ruta: la versión ruta asignada al artículo fabricado tiene fechas de inicio y finalización de vigencia, así como un estado de aprobado y activo. La versión de ruta debe ser específica para un sitio, y puede reflejar opcionalmente los puntos de interrupción de cantidad.
-   Tiempo de la operación de rutas: el tiempo se puede especificar para el tiempo de ejecución y el tiempo de preparación. El tiempo por hora comúnmente se expresa para producir un artículo principal, pero puede expresarse por 100 o por 1000 para gestionar las emisiones con precisión decimal.
-   Tiempo de operación de rutas para recursos secundarios: un recurso secundario tiene el mismo número de operación que el recurso principal, y el mismo tiempo de operación de rutas. Por ejemplo, una operación puede requerir una máquina como recurso primario y mano de obra y herramientas como recursos secundarios.
-   Porcentaje de valor residual de operación e rutas: los cálculos de la lista de materiales representarán los porcentajes de valores residuales y los porcentajes acumulados de valores residuales a través de operaciones múltiples. Esto se aplica al tiempo necesario para las operaciones de enrutamiento y la cantidad solicitada para los componentes que se vinculan a los números de operación.
-   Categorías de coste para la operación de rutas: la información de recursos de operaciones sobre las categorías de costes se heredarán por las operaciones, donde puede anularse. Los cálculos de la lista de materiales utilizarán la información de categorías de costes especificada en las operaciones de rutas.

La información sobre los gastos generales de fabricación que se utiliza en el cálculo de costes estándar de L. MAT incluye:
-   Suplemento: la fórmula del cálculo del suplemento refleja un porcentaje del valor, por ejemplo del 100%, vinculado a un grupo de costes específico, como la mano de obra.
-   Índice: la fórmula del cálculo del índice refleja un importe por unidad, por ejemplo, 10,00 dólares USD por hora, vinculado a un grupo de costes específico, como la mano de obra.
-   Gastos generales basados en el tiempo frente a gastos generales basados en los materiales: los gastos generales de fabricación pueden estar vinculados a operaciones de rutas o a componentes de materiales.

La información sobre la versión de gestión de costes que se utiliza en el cálculo de costes estándar de L. MAT incluye:
-   Tipo de gestión de costes: la versión de gestión de costes debe contener costes estándar. Se aplican varias restricciones a los cálculos de la lista de materiales que usan costes estándar. Por ejemplo, estas restricciones especifican que los gastos varios se deben incluir en los costes unitarios y que el modo de expansión de cálculo de la lista de materiales debe constar de un único nivel.
-   Principio de reserva obligatorio: la versión de gestión de costes puede ordenar el uso de un principio de reserva, como usar una versión de gestión de costes especificada o los registros de coste activo. El principio de reserva obligatorio se aplica normalmente a una versión de gestión de costes que represente las actualizaciones incrementales en un enfoque de dos versiones para las actualizaciones de coste.
-   Indicador de bloqueo de costes pendientes: el indicador de bloqueo impide que se incluyan los costes pendientes de los artículos fabricados en los cálculos de L. MAT.
-   Fecha inicial especificada: la fecha inicial especificada se utiliza como fecha de cálculo predeterminada para todos los cálculos de L. MAT que incluyan la versión de gestión de costes.
-   Sitio especificado: los cálculos de L. MAT se limitarán al sitio especificado.
-   El contenido de la versión de gestión de costes debe incluir los costes: el contenido debe incluir costes. Puede incluir opcionalmente precios de ventas para calcular los precios de venta sugeridos para los artículos fabricados.

Pueden especificarse diversos orígenes de datos cuando se inicia el cálculo de L. MAT. Esta información incluye el sitio, la fecha de cálculo y la versión de gestión de costes.




