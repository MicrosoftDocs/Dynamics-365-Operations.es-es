---
title: Posicionamiento de inventario
description: Este artículo brinda información sobre el posicionamiento estratégico del inventario, lo que implica identificar puntos de desacoplo en su cadena de suministro, donde puede acumular inventario disponible para ayudar a reducir los plazos de entrega y absorber impactos en su cadena de suministro.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ReqGroup, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 847108575cbf7207282db00d731363c8cfad883a
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689548"
---
# <a name="inventory-positioning"></a>Posicionamiento de inventario

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

El posicionamiento estratégico del inventario implica identificar puntos de desacoplo en su cadena de suministro, donde puede acumular inventario disponible. Este enfoque se utiliza principalmente para ayudar a reducir los plazos de entrega y absorber los impactos en su cadena de suministro. Le permite mitigar el "efecto látigo", porque la variabilidad de la demanda no se transmite a lo largo de la cadena de suministro. (El *efecto látigo* se refiere a cómo las pequeñas fluctuaciones en la demanda a nivel minorista pueden causar fluctuaciones progresivamente mayores en la demanda a nivel mayorista, distribuidor, fabricante y proveedor de materias primas).

El posicionamiento de inventario es el primer paso de la planificación de requisitos de basada en la demanda (DDMRP).

## <a name="inventory-positioning-for-manufacturing"></a>Posicionamiento de inventario para fabricación.

Esta sección proporciona un ejemplo que muestra cómo tomar decisiones de posicionamiento de inventario si fabrica un producto de almohada típico. La almohada tiene una lista de materiales (BOM) de varios niveles, como se muestra en la siguiente ilustración.

![Ejemplo de lista de materiales (L.MAT) de varios niveles para un producto de almohada.](media/ddmrp-bom-example.png "Ejemplo de lista de materiales (L.MAT) de varios niveles para un producto de almohada")

### <a name="choose-your-decoupling-points"></a>Elija sus puntos de desacoplo

Cuando elija dónde colocar los puntos de desacoplo, tenga en cuenta los siguientes aspectos de cada artículo de la lista de materiales como criterio:

- Variabilidad externa
- Aprovechamiento y flexibilidad del inventario
- Protección de operaciones críticas
- Tiempo de tolerancia del cliente
- Horizonte de visibilidad de pedidos de venta
- Plazo de entrega potencial del mercado

En el ejemplo de la almohada, puede poner su primer punto de desacoplo en las *placas de espuma* por las siguientes razones:

- Es difícil obtener los materiales que se utilizan para fabricar las placas de espuma, y la disponibilidad es volátil. Por tanto, se cumple el criterio de *variabilidad externa*.
- Las placas de espuma se pueden cortar con muchas formas y tamaños diferentes para crear insertos de espuma para otros productos que fabrique, además de la almohada. Por tanto, se cumple el criterio *aprovechamiento y flexibilidad de inventario*.

A continuación, puede poner su próximo punto de desacoplo en el *kit de tela*, que es tela de almohada precortada. Puede elegir este punto porque solo tiene una máquina cortadora de tela. Por tanto, se cumple el criterio de *protección de operación crítica*.

Finalmente, puede poner su último punto de desacoplo en el artículo de almohada de producto terminado. Puede elegir este punto porque tiene un nivel muy bajo *tiempo de tolerancia del cliente* en ventas, y porque su *horizonte de visibilidad de pedidos de venta* es bastante corto. Por tanto, le conviene asegurarse de tener el inventario disponible para atender los pedidos entrantes. También puede establecer un precio más alto manteniendo el plazo de entrega así de corto, que es a lo que se refiere el criterio *plazo de entrega potencial del mercado*.

De acuerdo con este análisis, la ilustración siguiente muestra el aspecto que tendrá la lista de materiales de almohada. Los símbolos de inventario amarillos resaltan los puntos de desacoplo.

![Ejemplo de lista de materiales con puntos de desacoplo resaltados.](media/ddmrp-bom-decoupling-example.png "Ejemplo de lista de materiales con puntos de desacoplo resaltados")

### <a name="calculate-your-decoupled-lead-time"></a>Calcular el plazo de entrega desacoplado

Esta sección muestra cómo calcular los nuevos plazos de entrega después de haber introducido puntos de desacoplo.

En la siguiente ilustración del ejemplo de la almohada que se inició en la sección anterior, los plazos de entrega se muestran en cuadros grises en la parte superior izquierda de cada componente de la lista de materiales. Los cuadros que tienen un contorno rojo indican elementos que impulsan el plazo de entrega acumulativo (la suma de los tiempos de entrega más largos en cada nivel de la lista de materiales). Este plazo de entrega es de 21 días cuando se empieza desde cero.

![Ejemplo de lista de materiales con plazos de entrega.](media/ddmrp-bom-lead-times-example.png "Ejemplo de lista de materiales con plazos de entrega")

Sin embargo, si aplica los puntos de desacoplo que eligió anteriormente, los artículos desacoplados siempre tendrán existencias. Por tanto, tendrán un plazo de entrega de 0 (cero). El nuevo plazo de entrega de la almohada ahora es de solo cinco días: dos días para comprar el hilo y tres días para producir la almohada. Este plazo de espera se conoce como *plazo de entrega desacoplado*.

![Ejemplo de plazo de entrega desacoplado.](media/ddmrp-bom-decoupled-lead-time-example.png "Ejemplo de plazo de entrega desacoplado")

## <a name="strategic-inventory-positioning-in-a-retail-model"></a>Posicionamiento de inventario estratégico en un modelo minorista

Dado que los minoristas almacenan solo productos terminados, las listas de materiales no son un problema. Sin embargo, los minoristas pueden seguir usando DDMRP estableciendo un posicionamiento de inventario estratégico y niveles de búfer en función de las ubicaciones de almacenamiento en la red de distribución.

La siguiente ilustración muestra el ejemplo de una empresa que tiene un centro de distribución en Seattle y tiendas en Boston, Atlanta y Portland.

![Puntos de desacoplo basados en la ubicación en un modelo minorista.](media/ddmrp-retail-decoupl-points-example.png "Puntos de desacoplo basados en la ubicación en un modelo minorista")

Puede decidir que el tiempo de transferencia para mover un producto de manta entre el centro de distribución y las tiendas infringe su *tiempo de tolerancia del cliente*, porque sus clientes esperan que haya existencias de la manta cuando los visiten. En este caso, configurará un punto de desacoplo para el artículo de manta en cada una de las tres tiendas. Cada tienda tendrá diferentes niveles de reserva, según sus plazos de entrega, patrones de demanda, etc.

## <a name="implement-inventory-positioning-in-dynamics-365-supply-chain-management"></a>Implementar posicionamiento de inventario en Dynamics 365 Supply Chain Management

Esta sección describe cómo implementar su estrategia de posicionamiento de inventario en Microsoft Dynamics 365 Supply Chain Management.

### <a name="set-up-item-coverage-groups-that-create-decoupling-points"></a>Configurar grupos de cobertura de artículos que crean puntos de desacoplo

Los artículos se convierten en puntos de desacoplo cuando pertenecen a un grupo de cobertura que está configurado con un valor de **Código de cobertura** de *Punto de desacoplo*. Por tanto, el primer paso en el proceso de configuración de DDMRP es decidir qué grupos de cobertura debe implementar para su estrategia de DDMRP y luego crearlos siguiendo estos pasos.

1. Vaya **Planificación maestra \> Configurar \> Cobertura \> Grupos de cobertura**.
1. En el Panel de acciones, haga clic en **Nuevo** para crear un grupo de cobertura.
1. Indique información que identifique al grupo de cobertura y, a continuación, seleccione el calendario que se debe utilizar.
1. En la pestaña **General**, configure el campo **Código de cobertura** en *Punto de desacoplo*. Esta configuración hará que todos los elementos que pertenecen a este grupo de cobertura se traten como puntos de desacoplo para DDMRP. También habilita todas las configuraciones de DDMRP para este grupo, como se describe más adelante en este procedimiento.
1. En la pestaña **Otro**, en la sección **Parámetros de DDMRP**, establezca los siguientes campos:

    - **Factor de plazo de entrega**: especifique un factor (como un valor decimal entre 0 y 1) para controlar el impacto que debe tener el plazo de entrega cuando se calculan los niveles mínimo y máximo de existencias para artículos en este grupo de cobertura. En general, cuanto mayor sea el plazo de entrega de un artículo, menor debería ser su factor de plazo de entrega. Un factor de plazo de entrega más bajo produce niveles de existencias mínimos y máximos más bajos y, por lo tanto, provoca pedidos más pequeños y más frecuentes. La metodología DDMRP recomienda un valor entre 0,20 y 0,40 para artículos con plazos de entrega prolongados, entre 0,41 y 0,60 para artículos con plazos de entrega medios y entre 0,61 y 1,00 para artículos con plazos de entrega cortos. Para obtener más información, consulte [Perfil y niveles de búfer](ddmrp-buffer-profile-and-levels.md).
    - **Factor de variabilidad**: especifique un factor (como un valor decimal entre 0 y 1) para controlar el impacto que debe tener la demanda variable cuando se calcula el nivel mínimo de existencias para artículos en este grupo de cobertura. En general, cuanto más variable es la demanda de un artículo, mayor debe ser su factor de variabilidad. Un factor de variabilidad más alto produce un nivel mínimo de existencias más alto. La metodología DDMRP recomienda un valor entre 0,00 y 0,40 para artículos que tienen baja variabilidad, entre 0,41 y 0,60 para artículos con variabilidad media y entre 0,61 y 1,00 para artículos con alta variabilidad. Para obtener más información, consulte [Perfil y niveles de búfer](ddmrp-buffer-profile-and-levels.md).
    - **Mínimo, máximo y período del punto de hacer nuevo pedido**: especifique con qué frecuencia calcular los valores del búfer (*Diariamente* o *Semanalmente*).

1. En la pestaña **Otro**, en la sección **Uso diario promedio**, establezca los siguientes campos:

    - **Uso diario promedio basado en**: seleccione en qué períodos de tiempo debe basarse el cálculo del uso diario promedio (ADU). Seleccione uno de los siguientes valores:

        - *Pasado*: mira solo el uso anterior para la cantidad de días que se especifican en el campo **Período pasado (días)**. El ADU se calcula como demanda total de un artículo durante el período de cálculo (en unidades de inventario) dividida por el número de días del período de cálculo.
        - *Adelante*: mira solo el uso futuro proyectado (incluidas previsiones) para el número de días que se especifican en el campo **Período futuro (días)**. El ADU se calcula como demanda total de un artículo durante el período de cálculo (en unidades de inventario) dividida por el número de días del período de cálculo. 
        - *Mezcla*: se mira el uso pasado y futuro. Se aplican configuraciones para el campo **Período pasado (días)**, el campo **Período futuro (días)** y las opciones de fusión. 

            *ADU combinado* = (\[*Ponderación pasada* × *ADU pasado*\] + \[*Peso futuro* × *ADU futuro*\]) ÷ (*Peso pasado* + *Peso futuro*)

    - **Período pasado (días)**: introduzca el número de días pasados (hasta el día de hoy incluido) que el sistema debe considerar cuando calcula el ADU de artículos en este grupo de cobertura. Esta configuración se aplica solo cuando el campo **Uso diario promedio basado en** se establece en *Pasado* o *Mezcla*.
    - **Período futuro (días)**: introduzca el número de días futuros (desde hoy y hasta el día especificado) que el sistema debe considerar cuando calcula el ADU de artículos en este grupo de cobertura. Esta configuración se aplica solo cuando el campo **Uso diario promedio basado en** se establece en *Futuro* o *Mezcla*.
    - **Peso relativo del período anterior para el uso diario promedio combinado**: ingrese el peso (como porcentaje) para aplicar al período pasado cuando se calcula el ADU combinado. Esta configuración se aplica solo cuando el campo **Uso diario promedio basado en** se establece en *Mezcla*.
    - **Peso relativo del período futuro para el uso diario promedio combinado**: ingrese el peso (como porcentaje) para aplicar al período futuro cuando se calcula el ADU combinado. Esta configuración se aplica solo cuando el campo **Uso diario promedio basado en** se establece en *Mezcla*.

1. Para todas las demás pestañas y campos, introduzca la configuración detallada utilizada para calcular los requisitos de los artículos vinculados al grupo de cobertura.

### <a name="set-an-item-as-a-decoupling-point"></a>Establecer un artículo como punto de desacoplo

Para establecer un elemento como punto de desacoplo, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Busque y seleccione un artículo liberado que desee configurar para DDMRP.
1. En el panel de acciones, en la pestaña **Plan**, seleccione **Cobertura de artículos**.
1. En la página **Cobertura de artículos**, es posible que ya se hayan enumerado varios registros de cobertura de artículos, cada uno de los cuales se aplica a una combinación diferente de almacenamiento y dimensiones del producto. Puede seleccionar un registro de cobertura de artículos existente que se aplique a las dimensiones en las que desea crear un punto de desacoplo. Alternativamente, puede seleccionar **Nuevo** en el Panel de acciones para crear un nuevo registro de cobertura de artículos.
1. Configure el registro de cobertura de artículos como de costumbre. Como mínimo, debe especificar el sitio y el almacén donde se aplicará el punto de desacoplo.
1. Mientras el registro apropiado todavía está seleccionado, seleccione la pestaña **General**.
1. Seleccione la casilla **Usar configuraciones específicas**.
1. Establezca el campo **Grupo de cobertura** en un grupo de cobertura que esté configurado para crear puntos de desacoplo (como se describe en la sección anterior).
1. El artículo ahora está configurado como un punto de desacoplo. Por lo general, cuando usa DDMRP, también configurará aquí los ajustes que afectan los tamaños de búfer y la cantidad de nuevo pedido. Sin embargo, puede completar esa configuración más adelante. Para más información sobre la configuración, vea [Configurar búferes para un elemento de punto de desacoplo](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

> [!NOTE]
> Para planificar artículos que no son puntos de desacoplo, siga los mismos pasos que sigue cuando se utiliza la planificación estándar de requisitos de material (MRP).
