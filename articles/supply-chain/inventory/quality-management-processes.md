---
title: Información general sobre gestión de calidad y disconformidades
description: Este artículo presenta las características de gestión de calidad y disconformidades en Microsoft Dynamics 365 Supply Chain Management y explica cómo pueden ayudar a mejorar la calidad del producto en su cadena de suministro.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11574"
- intro-internal
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 510dee78f6fed02e6511aedad00fcb1b15195470
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907504"
---
# <a name="quality-and-nonconformance-management-overview"></a>Información general sobre gestión de calidad y disconformidades

[!include [banner](../includes/banner.md)]

Este artículo presenta las características de gestión de calidad y disconformidades en Microsoft Dynamics 365 Supply Chain Management y explica cómo pueden ayudar a mejorar la calidad del producto en su cadena de suministro.

El control de calidad requiere realizar pruebas de los productos y gestionar el material de disconformidad. Los procesos de gestión de calidad ayudan a garantizar un nivel superior de la calidad del producto en la cadena de suministro. Estos procesos también ayudan a optimizar los procesos de la cadena de suministro y la satisfacción del cliente. La gestión de calidad puede ayudarle a gestionar los plazos de entrega con productos de disconformidad, independientemente del punto de origen de los productos. Puede vincular resultados de diagnóstico a tareas de corrección. El sistema puede programar tareas para corregir problemas y, por tanto, ayudar a evitar que estos problemas se repitan en el futuro. La gestión de calidad también le permite realizar un seguimiento de los problemas (incluidos los problemas internos) por tipo de problema, y le permite identificar soluciones como soluciones a corto plazo o a largo plazo. Las estadísticas acerca de los indicadores clave de rendimiento (KPI) proporcionan información sobre problemas de disconformidad que se han producido anteriormente y las soluciones aplicadas para corregirlos. Puede usar los datos históricos para ayudar a revisar la eficacia de las medidas de calidad que se han aplicado anteriormente y determinar medidas adecuadas en el futuro.

La gestión de calidad puede ayudarle a gestionar los plazos de entrega cuando maneja productos de disconformidad, independientemente de su punto de origen. Dado que los tipos de diagnóstico están vinculados a la corrección de los informes, Supply Chain Management puede programar las tareas para corregir los problemas y evitar que se repitan.

Además de la funcionalidad para gestionar la disconformidad, la gestión de calidad incluye la funcionalidad de realizar un seguimiento de las incidencias por tipo de problema (inclusocuando se trata de problemas internos) y para identificar soluciones como de corto plazo o largo plazo. Las estadísticas acerca de los indicadores clave de rendimiento (KPI) proporcionan información sobre el historial de problemas de disconformidad anteriores y las soluciones utilizadas para corregirlos. Puede usar los datos históricos para revisar la eficacia de las medidas de calidad anteriores y determinar las medidas adecuadas que se deben usar en el futuro.

Al configurar una asociación de calidad, Supply Chain Management puede generar pedidos de calidad para varios procesos empresariales, eventos y condiciones. La asociación de calidad puede cubrir un artículo concreto, un determinado grupo de éstos o todos los artículos.

## <a name="examples-of-the-use-of-quality-management"></a>Ejemplos del uso de la gestión de calidad

La gestión de calidad es flexible y puede ejecutarse de distintas maneras para satisfacer los requisitos de niveles específicos de operaciones de la cadena de suministro. En los ejemplos siguientes se muestran usos posibles de estas características:

- Inicie automáticamente un proceso de control de calidad en función de los criterios predefinidos (por ejemplo, cuando ocurre el registro del almacén de un pedido de compra para un proveedor específico).
- Bloquear el inventario durante la inspección para evitar que el inventario no aprobado se use (bloqueo completo de las cantidades de pedido de compra).
- Use el muestreo del artículo como parte de una asociación de calidad para definir la cantidad de inventario físico actual que debe inspeccionarse. El muestreo puede basarse en cantidades fijas, en un porcentaje o en una matrícula completa.
- Crear pedidos de calidad para recepciones parciales. Para crear un pedido de calidad basado en la cantidad que se recibe físicamente con un pedido, debe seleccionar la casilla **Por cantidad actualizada** en la página **Muestreo de artículos** .
- Permite crear tipos de prueba que incluyen mínimo, máximo y valores de prueba de destino, y realizar pruebas cualitativas en contraposición a cuantitativas que tengan resultados de validación predefinidos.
- Especifique un nivel de calidad aceptable (AQL) para controlar las tolerancias de medida de calidad.
- Especifique los recursos que una operación de inspección requiere, por ejemplo instrumentos de prueba y un área de prueba.

> [!NOTE]
> La característica _Administración de la calidad para procesos de almacén_ amplía las capacidades de la gestión de calidad. Si está utilizando esta función, vea [Gestión de calidad para procesos de almacén](quality-management-for-warehouses-processes.md) para ver ejemplos que muestran cómo funciona la gestión de calidad cuando está habilitada.

## <a name="controlling-the-quality-management-process"></a>Control del proceso de gestión de calidad

Estas son algunas maneras de controlar el proceso de gestión de calidad:

- Cree pedidos de calidad basados en puntos desencadenadores, como "al recibir el producto" para las operaciones entrantes o "al recoger el producto" para las operaciones salientes.
- Documente los resultados de prueba y determine si los resultados cumplen con los criterios de prueba establecidos y los AQL.
- Gestione documentos para especificaciones detalladas de los productos y notas de usuario específicas como parte del proceso de inspección.
- Mantenga productos de disconformidad y correlacione esos productos con la información adicional sobre disconformidad para hacer un seguimiento de la causa original de un problema.
- Documente el coste de gestionar una disconformidad. Este coste puede incluir los artículos (como piezas de recambio), gastos varios y las horas necesarias para corregir la disconformidad.
- Programe procesos de corrección de errores mediante la gestión de correcciones vinculada a los pedidos de calidad.

[![Proceso de gestión de calidad.](media/quality-management-process-diagram.png)](media/quality-management-process-diagram.png)

## <a name="product-testing-and-quality-orders"></a>Pruebas de productos y pedidos de calidad

Las pruebas de productos generalmente reciben el nombre de control de calidad y pedidos de calidad. La funcionalidad de control de calidad le permite hacer lo siguiente:

- Definir las pruebas que se deben realizar para el material. Estas pruebas incluyen las especificaciones de calidad, el instrumento de prueba aplicable, los documentos que describen la prueba, un plan de muestreo y los niveles de calidad aceptables (AQL).
- Cree un pedido de calidad que identifique las pruebas que se deben llevar a cabo para un pedido específico, como un pedido de compras o un pedido de producción, o para una cantidad de inventario específica. Los pedidos de calidad pueden generarse manualmente o pueden hacerlo automáticamente según las instrucciones de calidad.
- Defina las instrucciones de calidad relacionadas con los pedidos de compra, cuarentena, producción o venta en cada proceso empresarial, de modo que se pueda generar automáticamente un pedido de calidad que identifique los requisitos de pruebas para el material entrante o saliente.
- Registre los resultados de las pruebas en un pedido de calidad, valide los resultados de las pruebas con respecto al AQL e imprima un certificado de análisis que muestre los resultados de las pruebas.

## <a name="nonconformance"></a>No conformidad

Una disconformidad describe un artículo que tiene un problema de calidad. El proceso de disconformidad le permite crear un pedido de disconformidad que describa la cantidad de material disconforme, el origen del problema, el tipo de problema y notas aclaratorias. Puede definir una clasificación de tipos de problemas para que el análisis del material de disconformidad resulte más fácil. También puede imprimir una etiqueta de disconformidad y un informe de disconformidad para guiar la disposición del material de disconformidad. Por ejemplo, la etiqueta y el informe pueden indicar una condición **No utilizable** o **Uso restringido**.

La tabla siguiente muestra los seis tipos de disconformidad predeterminados y describe la información que se debe registrar para cada tipo.

| Tipo de no conformidad | Información del origen |
|---|---|
| Cliente | El número de cuenta del cliente, el número de pedido de ventas o un número de lote de una transacción de pedido de ventas. Por ejemplo, la disconformidad podría estar relacionada con un envío de un pedido de ventas específico o con los comentarios de un cliente acerca de la calidad del producto. |
| Solicitud de servicio | El número de cuenta del cliente, el número de pedido de ventas o un número de lote de una transacción de pedido de ventas. Por ejemplo, la disconformidad podría estar relacionada con un envío de un pedido de ventas específico o con la queja de un cliente acerca de la calidad del artículo. |
| Proveedor | El número de cuenta del proveedor, el número de pedido de compra o un número de lote de una transacción de pedido de compra. Por ejemplo, la disconformidad podría estar relacionada con la recepción de un pedido de compra o con las preocupaciones de un proveedor acerca de una parte de su suministro. |
| Producción | El número de orden de producción o un número de lote de una transacción de orden de producción. Por ejemplo, la disconformidad podría estar relacionada con un lote específico producido. |
| Interno | El número de pedido de calidad o un número de lote de una transacción de pedido de calidad. Por ejemplo, la disconformidad podría estar relacionada con las pruebas efectuadas como parte del pedido de calidad o con la preocupación del empleado acerca de la calidad del producto. |
| Producción de coproductos | Una disconformidad de pedido de producción de coproductos relacionada con pedidos de producción de lote. |

Las disconformidades se asocian a un tipo de problema. Los tipos de problema se definen en la página **Tipos de problemas**, donde se especifica qué tipos de problema se pueden asociar con cada tipo de disconformidad. Por ejemplo, los tipos de problemas de disconformidad del tipo **Solicitud de servicio** podrían reflejar una clasificación de quejas del cliente, mientras que los tipos de problemas de disconformidad del tipo **Interno** podrían representar una clasificación de códigos de defecto.

A la hora de crear una nueva disconformidad, debe seleccionar el tipo de disconformidad y el tipo de problema. El estado de aprobación inicial es **Nuevo**, que representa una solicitud de acción. El siguiente paso es cambiar el estado de aprobación a **Aprobado** o **Rechazado** para indicar que se actuará o no acerca del campo de disconformidad. También puede cerrar un caso de disconformidad (seleccionando una casilla aparte) para indicar que se ha terminado, o reabrirlo para indicar que es necesario seguir analizando el caso.

Puede incluir comentarios en un caso de disconformidad adjuntando un documento. Conviene definir un tipo de documento exclusivo para los casos de disconformidad mediante la página **Tipo de documento**. Puede usar la página **Configuración del informe** para definir si los comentarios para este tipo de documento se deben imprimir en el informe y la etiqueta de disconformidad. El informe y la etiqueta de conformidad pueden ayudar con la disposición de material. Se pueden generar informes y etiquetas de manera selectiva en función de ciertos criterios de selección asociados a un caso de disconformidad. Estos criterios incluyen el número de caso de disconformidad, el artículo, el cliente, el proveedor y el estado.

El informe de disconformidad muestra el número de disconformidad, el artículo y el tipo de problema. En función de la directiva de configuración del informe, el informe también puede mostrar notas relacionadas sobre el caso de disconformidad. La etiqueta de disconformidad muestra información parecida, e incluye también la zona de cuarentena y el tipo (como **Uso restringido** o **No utilizable**) que se ha asignado al caso de disconformidad para ayudar a guiar la disposición del material defectuoso.

## <a name="approved-nonconformance"></a>Disconformidad aprobada

Opcionalmente, se pueden definir una o más operaciones relacionadas para una no conformidad aprobada. Una operación relacionada describe el trabajo que se debe efectuar, y contiene una lista predefinida de operaciones de calidad definidas por el usuario y texto descriptivo del motivo del trabajo. Una vez definida una operación, se pueden definir los gastos varios, los artículos y las horas de trabajo que se requieren para efectuar el trabajo. Los costes calculados se muestran para la operación relacionada y los costes totales calculados se muestran para la no conformidad. Los costes calculados y los detalles subyacentes (acerca de artículos, horas de trabajo y gastos varios) representan información de referencia y solo se usan en la función de control de calidad.

También es posible crear un pedido de calidad a partir de un caso de disconformidad realizando primero una consulta de pedidos de calidad y, a continuación, creando el nuevo pedido de calidad. Por ejemplo, un pedido de calidad puede identificar la necesidad de probar (o volver a probar) el material defectuoso. El nuevo pedido de calidad creado muestra el vínculo a la no conformidad de origen.

Opcionalmente, puede vincular un caso de disconformidad a otro y crear uno nuevo a partir de otro existente. Por ejemplo, el vínculo puede reflejar la interconexión entre problemas de calidad.

## <a name="correction-handling"></a>Gestión de correcciones

La página **Correcciones** permite crear una lista de casos de disconformidad que se deben corregir. Cada elemento de corrección está asociado al tipo de diagnóstico que hizo que se descubriera el problema. La página **Correcciones** también contiene información relativa a quién debe realizar la acción correctiva y cuándo. Puede describir los detalles del problema y de la acción correctiva requerida adjuntando un documento a la corrección. Después de gestionar o corregir el caso de disconformidad, se "cierra" el elemento de corrección seleccionando la opción **Finalizado**. También puede indicar que la solución ha sido una solución a corto plazo.

Conviene definir un tipo de documento exclusivo para las correcciones mediante la página **Tipo de documento**. Después podrá usar la página **Configuración del informe** para definir si los comentarios para este tipo de documento se deben imprimir en el informe de corrección. El informe de corrección impreso muestra información acerca del caso de disconformidad y las notas relacionadas. El informe también incluye información sobre la corrección, como el tipo de diagnóstico y las notas de corrección relacionadas.

## <a name="additional-resources"></a>Recursos adicionales

- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Bloqueo del inventario](inventory-blocking.md)
- [Órdenes de cuarentena](quarantine-orders.md)
- [Inspeccionar la calidad de las mercancías](tasks/inspect-quality-goods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
