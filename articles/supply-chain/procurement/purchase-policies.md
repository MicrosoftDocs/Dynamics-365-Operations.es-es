---
title: Directivas de compra
description: "Este artículo proporciona información acerca de las directivas de compra. Una directiva de compra es una colección de reglas que controlan el proceso de solicitud. Las directivas de compra ayudan a los administradores de compras a implementar su estrategia de compras creando una estructura de directiva que está de acuerdo con los requisitos de compras estratégicas de la organización."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqSourcingPolicyRule, SysPolicy, SysPolicyListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 11614
ms.assetid: 729a304d-0f3f-4ccb-bd5b-46ee0976c57f
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 675a7a8b0da228e789ee37ca8fe1d0c0ea01c283
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="purchasing-policies"></a>Directivas de compra

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de las directivas de compra. Una directiva de compra es una colección de reglas que controlan el proceso de solicitud. Las directivas de compra ayudan a los administradores de compras a implementar su estrategia de compras creando una estructura de directiva que está de acuerdo con los requisitos de compras estratégicas de la organización.

Una directiva de compra consta de un conjunto de reglas de directivas. Para definir una regla de directivas, en primer lugar se selecciona un tipo de regla. Al crear una regla para el tipo de regla definiendo la configuración, la fecha inicial y la fecha final de la regla.  

Por ejemplo, un administrador crea una directiva, selecciona el tipo de regla **Directiva de catálogo** y, a continuación, agrega una regla de directivas de catálogo a la directiva. Esta regla de directivas de catálogo especifica que se debe usar el catálogo de Adventure para las compras internas. Tras la asociación de la directiva de compra con una organización concreta, los empleados de dicha organización ven el catálogo de Adventure al crear solicitudes.

## <a name="assigning-policies-to-organizations"></a>Asignación de directivas a organizaciones
Para que una directiva pueda surtir efecto, debe asociarse con una organización. Las directivas de compra se asocian con el propósito de jerarquía **Control interno de compras**. Así pues, las directivas de compra solo se aplican a organizaciones en jerarquías que tengan el propósito de jerarquía de **Control interno de compras**. También puede seleccionar organizaciones en la lista plana de entidades jurídicas de la tabla CompanyInfo. Estas entidades jurídicas se designan en el marco de directiva como "Empresas".

## <a name="determining-which-rule-to-apply"></a>Determinación de qué regla se desea aplicar
Según la manera en que configure las directivas de compra, los usuarios de una organización pueden verse afectados por varias reglas. En los siguientes ejemplos se muestran diferentes formas en las que puede configurar directivas de compras y especificar la manera en que se aplican las directivas cuando se produce una transacción.

### <a name="example-1-simple-purchasing-policy-configuration"></a>Ejemplo 1: configuración de directiva de compras sencilla

Las organizaciones pequeñas y menos complejas pueden configurar directivas de compra por entidad jurídica y pueden usar únicamente la jerarquía organizativa Empresas.  

Para Fabrikam, un pequeño negocio, los requisitos de compra varían muy poco en la organización. Las reglas de compras solo varían entre las entidades jurídicas de la organización. Por ejemplo, los empleados de Fabrikam Canadá y los empleados de Fabrikam Estados Unidos compran bienes y servicios de diferentes catálogos y de diferentes proveedores. Por eso, Fabrikam configura sus directivas de compra en el nivel de entidad jurídica.  

Fabrikam crea dos directivas de compra. La directiva A se aplica a su entidad jurídica de Estados Unidos, 1111. La directiva B se aplica a su entidad jurídica de Canadá, 2222. Cuando un empleado de la entidad jurídica 1111 crea una solicitud de compra, las reglas de directivas se obtienen de la directiva A. Por ejemplo, el catálogo de productos que el empleado ve en la regla de directivas del catálogo para la directiva A.  

Cuando un empleado de la entidad jurídica 2222 crea una solicitud de compra, las reglas de directivas se obtienen de la directiva B.  

**Nota:** Si un empleado de la entidad jurídica 1111 compra un artículo en nombre de un empleado de la entidad jurídica 2222, se aplican las reglas de directivas que se especifican para la entidad jurídica 2222 (es decir, las reglas de directivas de la directiva B).

### <a name="example-2-complex-purchasing-policy-configuration"></a>Ejemplo 2: configuración de directiva de compras compleja

En el ejemplo anterior, todas las reglas de compra se definieron en una jerarquía organizativa única, en este caso, la jerarquía organizativa Empresas. No obstante, una organización compleja puede definir directivas para varias jerarquías organizativas.  


Contoso es una empresa grande que requiere reglas de compra complejas para controlar el proceso de solicitud. Contoso ha definido reglas para dos jerarquías organizativas diferentes: Departamento y Control de compra mundial.  

La directiva 123 se define para la jerarquía organizativa Departamento para el departamento de ventas del Reino Unido. En la directiva 123, la regla de control de solicitud de compra especifica que se deben aplicar restricciones para cantidades de pedido mínimas. En esta regla, está activada la opción **Exigir las restricciones mínimas en la cantidad del pedido**.  

La directiva 456 se ha definido para la jerarquía organizativa de control de solicitud de compra Global para el departamento de Ventas y marketing. En la directiva 456, la regla de control de solicitud de compra no especifica que se deben aplicar restricciones por cantidades de pedido mínimo. En esta regla, está desactivada la opción **Exigir las restricciones mínimas en la cantidad del pedido**.  

Sam trabaja en el departamento de ventas del Reino Unido en la oficina del Reino Unido de Contoso. Las directivas de las jerarquías organizativas Control de compra mundial y Departamento son aplicables a su departamento. Cuando Sam crea una solicitud de compra, el sistema debe determinar qué directiva se desea aplicar. El administrador del sistema configura los parámetros de la directiva de compra para especificar qué directivas de compra se deben aplicar en el siguiente orden de prioridad:

1.  Control de compra mundial
2.  Departamento
3.  Empresas

Por lo tanto, la directiva 456 se aplica a la solicitud de compra que crea Sam y no se requiere ninguna cantidad de pedido mínima para la solicitud de compra.

## <a name="policy-rules"></a>Reglas de directivas
### <a name="catalog-policy-rule"></a>Regla de directivas del catálogo

La regla de directivas de catálogo determina qué usuarios del catálogo de compras se ven al crear solicitudes de compra. Si se concede permiso a un usuario para solicitar productos en nombre de otro usuario, la solicitud usa la regla de directivas del catálogo que se define para la entidad jurídica y la unidad operativa del solicitante para determinar qué catálogo debe mostrarse. Antes de poder definir una regla de directivas de catálogo, debe crear un catálogo de compras y publicarlo.

### <a name="category-access-policy-rule"></a>Regla de directivas de acceso a categorías

La regla de directivas de acceso de categorías determina a qué categorías tienen acceso los usuarios al crear solicitudes de compra. Si no se especifica ninguna regla, todas las categorías de compra se pueden agregar a la solicitud de compra.

1.  Seleccione la opción **Incluir regla principal** para aplicar la regla de directivas de acceso de categoría de la organización principal a la categoría.
2.  En el panel **Categorías disponibles**, seleccione las categorías a las que se aplica la regla. Cuando selecciona una categoría, todas las categorías que están por encima en la jerarquía también se agregan a la lista **Categorías seleccionadas**.
3.  Seleccione la opción **Incluir categorías** para aplicar la regla a todas las subcategorías de la categoría seleccionada.

### <a name="category-policy-rule"></a>Regla de directivas de categorías

La regla de directivas de categoría define cómo pueden seleccionar los usuarios proveedores para cada categoría. También define los requisitos de los procesos de recepción y de facturación.

### <a name="re-approval-rule-for-purchase-orders"></a>Regla de nueva aprobación para pedidos de compra

La regla de nueva aprobación es una regla opcional que define los criterios para requerir reaprobación al realizar cambios en un pedido de compra. Los campos seleccionados se evalúan en flujo de trabajo de pedido de compra cuando se configura la condición "Requiere nueva aprobación de pedido de compra" en el flujo de trabajo.

> [!NOTE]
> La distribución contable siempre se restablece cuando se modifica un pedido de compra aprobado con administración de cambios. Así que debe tener en cuenta que, si desea evitar una nueva aprobación de un pedido de compra cuando se cambian determinados campos, el campo Accounting distribution.changed NO se debe incluir como campo seleccionado para la nueva aprobación. 

### <a name="purchase-requisition-rfq-rule"></a>Regla de solicitud de presupuesto para solicitud de compra

La regla de solicitud de presupuesto de solicitud de compra define los criterios para requerir una solicitud de presupuesto para una línea de solicitud de compra. Si una línea reúne las condiciones, el sello de solicitud de presupuesto informal o el de solicitud de presupuesto formal aparece en la línea de pedido.

### <a name="purchase-requisition-control-rule"></a>Regla de control de la solicitud de compra

La regla de control de solicitud de compra es una regla opcional. Cuando crea reglas de este tipo, puede establecer opciones en diferentes fichas:

-   En la ficha **Envío de flujo de trabajo** puede configurar los campos que deben incluirse en la línea de solicitud para enviar la solicitud para que se apruebe cuando el propósito de solicitud sea **Consumo**.
-   En la ficha **Cantidades de pedido** puede configurar los campos necesarios en la solicitud de compra en determinadas condiciones. También puede exigir cantidades de pedido.
-   En la ficha **Fechas**, puede configurar si la fecha de contabilidad es la misma que la fecha solicitada.
-   En la ficha **Dirección** puede definir si se permite al usuario crear nuevas direcciones en el sistema para aplicarlo a la solicitud de compra.

### <a name="requisition-purpose-rule"></a>Regla de propósito de pedido

La regla de propósito de solicitud es una regla opcional que determina el tipo de propósito de solicitud permitido para una entidad jurídica específica. A menos que se indique otro propósito contrario en esta regla, las solicitudes tendrán automáticamente un propósito **Consumo** cuando se creen.

### <a name="replenishment-category-access-policy-rule"></a>Regla de directivas de acceso de categorías de reabastecimiento

La regla de directiva de acceso de categoría de reabastecimiento es una regla opcional que determina los productos disponibles para satisfacer la demanda de la solicitud para una entidad jurídica específica cuando el propósito de la solicitud sea **Reabastecimiento**.

### <a name="replenishment-control-rule"></a>Regla de control de reabastecimiento

La regla de control de reabastecimiento es una regla opcional que define los campos que se deben especificar en la línea de solicitud para que la solicitud se envíe para aprobarse cuando el propósito de solicitud sea **Reabastecimiento**.

### <a name="purchase-order-creation-and-demand-consolidation-rule"></a>Regla de creación de pedidos de compra y consolidación de la demanda

La regla de la creación de pedido de compra y consolidación de demanda define las reglas de directivas que usar cuando se genera un pedido de compra desde una solicitud de compra aprobada. Cuando crea reglas de este tipo, puede establecer opciones en diferentes fichas:

-   En la ficha **Pedido de compra dividido** puede definir los criterios de división de líneas de solicitudes de compra en distintos pedidos de compra.
-   En la ficha **Transferencia de precio/descuento** puede definir cuándo volver a calcular el acuerdo de precios cuando se crea un pedido de compra:
    -   **Solo si no hay acuerdo comercial**: los precios y descuentos se transfieren de la solicitud de compra solo si no hay acuerdo comercial o precio base aplicables. Si existe un acuerdo comercial o un precio base para el artículo o el proveedor, se volverán a calcular los precios y descuentos según el acuerdo comercial o el precio base y se aplicarán al pedido de compra. Salvo especificación de lo contrario, este es el comportamiento predeterminado.
    -   **Siempre**: los precios y descuentos se transfieren siempre desde la solicitud de compra.

    También puede permitir que el solicitante cambie el método de transferencia de precio y descuento para las líneas de solicitud de compra individuales, independientemente de la regla de transferencia de precio y descuento que se defina. Active la opción **Permitir anulación manual por línea de solicitud de compra** si desea permitir esta capacidad.
-   En la ficha **Transferencia de descripción de artículos** puede transferir la descripción del artículo del pedido cuando se origina desde una solicitud de presupuesto.
-   En la ficha **Tolerancia de precios** puede definir reglas para volver a enviar las solicitudes de compra aprobadas mediante el proceso de revisión cuando aumente el precio de un artículo del catálogo de compras. Defina el importe máximo en el que puede aumentar el importe neto del artículo de línea de una solicitud de compra desde que se aprueba la solicitud y hasta que se crea el pedido de compra. El importe neto se calcula mediante la fórmula siguiente: (\[Cantidad × (Precio unitario – Descuento) ÷ Precio unitario\] + Gastos varios de compra) × (100 – Porcentaje de descuento) ÷ 100 Las líneas de solicitud de compra que sobrepasan la tolerancia de precios definida se reservan para su procesamiento manual. Las reglas que configure en la ficha **Procesamiento de errores** determinan el modo en que se procesan las líneas de la solicitud de compra.
-   En la ficha **Procesamiento de errores** puede configurar la regla de procesamiento que se aplica a una solicitud de compra si esta no se puede validar durante la creación del pedido de compra debido a un error del proveedor o a un error en la tolerancia de precios. Seleccione una de las siguientes opciones:
    -   **Sin acción**: las líneas de solicitud de compra permanecen en la página **Liberar solicitudes de compra aprobadas**. El estado de las líneas de la solicitud de compra se mantiene en **Aprobado**. Sin embargo, los errores se deben resolver antes de que se pueda generar un pedido de compra para las líneas de solicitud de compra.
    -   **Cancelar la línea de la solicitud de compra**: se cancelan las líneas de solicitud de compra. El solicitante puede crear nuevas solicitudes de compra para las líneas canceladas si aún quiere solicitar los artículos de línea.
    -   **Crear nueva línea de solicitud de compra**: se crean líneas de solicitud de compra. Se generarán nuevas solicitudes de compra que contengan solo las líneas de solicitud de compra que han tenido errores en la validación. Las nuevas solicitudes de compra que se generen tendrán el estado **Borrador**. Dichas solicitudes de compra se pueden volver a enviar a revisión una vez solucionados los errores de validación. Al preparador de las líneas de solicitud de compra se le notifica que las líneas se cancelaron y que se generaron nuevas solicitudes de compra para las líneas de solicitud de compra que fallaron.
-   En la ficha **Creación manual de pedidos de compra** puede definir los parámetros que determinan si una solicitud de compra se debe procesar manualmente, o si se puede convertir automáticamente a un pedido de compra. Los parámetros se pueden aplicar a los artículos de catálogo interno, de catálogo externo, o a artículos de fuera del catálogo. Seleccione una de las siguientes opciones:
    -   **Crear pedidos de compra manualmente**: cree manualmente pedidos de compra para todas las solicitudes de compra aprobadas.
    -   **Crear pedidos de compra automáticamente**: cree pedidos de compra automáticamente para todas las solicitudes de compra aprobadas. No se reservan solicitudes de compra para crear manualmente pedidos de compra.
    -   **Crear pedidos de compra de forma automática excepto en estas condiciones**: cree manualmente pedidos de compra para solicitudes de compra que coincidan con los criterios que defina. Todas las solicitudes de compra aprobadas restantes se convierten automáticamente en pedidos de compra. Si selecciona **Crear pedidos de compra de forma automática excepto en estas condiciones**, puede agregar categorías de compras y proveedores para especificar qué líneas de la solicitud de compra aprobadas se reservan para su procesamiento manual. Esta opción se puede aplicar a los artículos de catálogo interno, de catálogo externo y a artículos de fuera del catálogo. Cuando selecciona una categoría de compras, se seleccionan también todas las subcategorías definidas para dicha categoría de compras. Seleccione la opción **Todo** para que un tipo determinado de línea de solicitud de compra reserve ese tipo de línea para su procesamiento manual.

    Si desea generar automáticamente pedidos de compra a partir de solicitudes de compra aprobadas durante la ejecución de un trabajo por lotes de generación de pedidos de compra, seleccione la opción **Ejecutar la creación automática de pedidos de compra como trabajo por lotes**. Esta opción solo se aplica a las solicitudes de compra que no necesitan un procesamiento manual. Al ejecutar la generación automática de pedidos de compra como un trabajo por lotes, puede programar esta actividad en un momento en que los recursos estén menos restringidos. Si se ha seleccionado la opción **Se requiere pago por adelantado** en las líneas de solicitud de compra, seleccione la opción **Cuando la solicitud está configurada para anticipo** para conservar las solicitudes de compra aprobadas para procesarlas de manera manual. Las solicitudes de compra que se mantienen para el procesamiento manual se pueden filtrar para que se visualicen solo las líneas de solicitudes de compra que requieran el pago por adelantado.
-   En la ficha **Consolidación de la demanda** puede definir los parámetros que determinan si las solicitudes de compra que se procesan manualmente se pueden tener en cuenta para la consolidación de solicitudes de compra. Los parámetros se pueden aplicar a los artículos de catálogo interno, de catálogo externo, o a artículos de fuera del catálogo. Seleccione una de las siguientes opciones:
    -   **No permitir consolidación de la demanda**: las líneas de solicitudes de compras sin aprobar pueden optar a consolidación de demanda. Esta opción se selecciona de forma predeterminada y solo se aplica a las líneas de solicitudes de compra que requieren un procesamiento manual para la creación de pedidos de compra.
    -   **Permitir siempre consolidación de la demanda**: todas las líneas de solicitud de compra sin aprobar pueden optar a consolidación de demanda. **Nota:** si selecciona la opción **Permitir siempre consolidación de la demanda** en la ficha **Consolidación de la demanda** pero selecciona la opción **Crear automáticamente pedidos de compra** en la ficha **Creación manual de pedidos de compra**, todas las solicitudes de compra se conservan para procesarse manualmente.
    -   **Permitir consolidación de la demanda en estas condiciones**: defina los criterios que determinan si las líneas de solicitud de compra aprobadas pueden optar a consolidación de demanda. Para cada tipo de línea de solicitud de compra, puede definir los criterios por categoría de compra y proveedor. Si selecciona **Permitir consolidación de la demanda en estas condiciones**, puede definir los criterios por categoría de compra y proveedor para cada tipo de línea de solicitud de compra. Cuando selecciona una categoría de compras, se seleccionan también todas las subcategorías definidas para dicha categoría de compras. Si selecciona la opción **Todo** para un tipo determinado de línea, todas las solicitudes de compra de ese tipo de línea son aptas para la consolidación de la demanda.





