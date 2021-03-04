---
title: Administración de la calidad para procesos de almacén
description: Este tema proporciona información acerca de la característica de gestión de calidad para los procesos de almacén. Esta característica amplía las capacidades de gestión de calidad y permite a los usuarios integrar controles de muestreo de artículos en el proceso de recepción del almacén mediante la gestión avanzada de almacenes.
author: Henrikan
manager: tfehr
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-02
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 0f39bd2ffda492fce9b3fe51feafcbc8fd32391c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437129"
---
# <a name="quality-management-for-warehouse-processes"></a>Administración de la calidad para procesos de almacén

La característica _Administración de la calidad para procesos de almacén_ amplía las capacidades de gestión de calidad y permite a los usuarios integrar controles de muestreo de artículos en el proceso de recepción del almacén mediante la gestión avanzada de almacenes. El trabajo de almacén se puede generar automáticamente para mover el inventario a la ubicación de control de calidad, en función de un porcentaje o una cantidad fija, o según cada *n* matrículas. Una vez que se ha completado un pedido de calidad, el trabajo se puede generar automáticamente para mover el inventario a la siguiente ubicación en el proceso, dependiendo de los resultados de calidad.

La característica _Administración de la calidad para procesos de almacén_ amplía las capacidades de la función de gestión de calidad básica. Proporciona la opción de crear pedidos de calidad para el inventario que se envía a la ubicación de control de calidad, aunque no siempre se requieren pedidos de calidad. Por lo tanto, permite un proceso de control de calidad ligero basado en el trabajo de almacén.

## <a name="turn-on-the-quality-management-for-warehouse-processes-feature"></a>Activar la característica Administración de la calidad para procesos de almacén

Antes de poder usar esta función debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la característica aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de característica**: *Administración de la calidad para procesos de almacén*

## <a name="key-benefits"></a>Beneficios clave

La característica _Administración de la calidad para procesos de almacén_ genera automáticamente trabajo como parte del proceso de recepción, para mover la cantidad de inventario que se requiere para el control de calidad a una ubicación de control de calidad. Si la cantidad recibida excede la cantidad requerida para el control de calidad (de acuerdo con la configuración de muestreo del artículo), la cantidad excedente se mueve a una ubicación entrante que se define en la configuración de la directiva de ubicación. Después de validar el pedido de calidad, el trabajo se genera automáticamente para mover la cantidad del pedido de calidad a una nueva ubicación entrante o de retorno, según el resultado de la validación y la configuración de la directiva de ubicación. La generación automática de trabajo que solo tiene la cantidad que se debe mover hacia y desde el control de calidad proporciona una experiencia de proceso integrada.

> [!NOTE]
> Cuando la característica _Administración de la calidad para procesos de almacén_ está activada, aún puede aprovechar el proceso manual. En el proceso manual, el movimiento de inventario y el movimiento mediante plantilla se utilizan para que un trabajador del almacén active la creación de trabajo de almacén para mover el inventario de una ubicación de control de calidad a una nueva ubicación. También puede configurar una directiva de ubicación entrante que mueva el inventario en su totalidad desde una ubicación receptora a una ubicación de control de calidad sin tener en cuenta la configuración de muestreo de artículos.

## <a name="quality-management-and-the-quality-management-for-warehouse-processes-feature"></a>Administración de calidad y la característica Administración de la calidad para procesos de almacén

Cuando la característica _Administración de la calidad para procesos de almacén_ está activada, cambia la configuración de las entidades clave de gestión de almacén y gestión de calidad. La siguiente ilustración proporciona una descripción general de las entidades que permiten pedidos de calidad para procesos de almacén. El texto entre paréntesis indica acciones sugeridas si se realizó gestión de calidad antes de activar la característica _Administración de la calidad para procesos de almacén_.

![Entidades de administración de la calidad](media/quality-management-entity-diagram.png "Entidades de administración de la calidad")

## <a name="enablers-the-quality-item-sampling-and-quality-order-work-order-types"></a>Habilitadores: los tipos de orden de trabajo Muestreo de artículos de calidad y Pedido de calidad

La característica _Administración de la calidad para procesos de almacén_ presenta dos tipos de órdenes de trabajo que permiten el proceso de creación de trabajo:

- **Muestreo de artículos de calidad**: este tipo de orden de trabajo se usa para crear trabajo que mueve el inventario registrado al control de calidad.
- **Pedido de calidad**: este tipo de orden de trabajo se utiliza para crear trabajos que mueven el inventario del control de calidad a una nueva ubicación, según la configuración de la directiva de ubicación.

### <a name="work-classes-location-directives-and-work-templates"></a>Clases de trabajo, directivas de ubicación y plantillas de trabajo

Las directivas de ubicación, las clases de trabajo y las plantillas de trabajo consumen los tipos de órdenes de trabajo _Muestreo de artículos de calidad_ y _Pedido de calidad_.

Antes de que el trabajo de almacén se pueda generar automáticamente para mover el inventario al control de calidad, debe seguir estos pasos para configurar su sistema.

1. Cree clases de trabajo separadas para los tipos de orden de trabajo _Muestreo de artículos de calidad_ y _Pedido de calidad_. De esta manera, se asegura de que el trabajo apropiado se pueda generar automáticamente en función de los dos tipos de orden de trabajo, y que este trabajo se pueda ejecutar utilizando la aplicación de almacén.
1. Configure una plantilla de trabajo para cada tipo de pedido de trabajo:

    - Configure una plantilla de trabajo que use el tipo de orgen de trabajo _Muestreo de artículos de calidad_ para mover automáticamente el inventario registrado a una ubicación de control de calidad.
    - Configure una plantilla de trabajo que use el tipo de orgen de trabajo _Pedido de calidad_ para mover automáticamente el inventario desde una ubicación de control de calidad una vez completado el control de calidad.

1. Para cada tipo de orden de trabajo, configure directivas de ubicación que apliquen las ubicaciones correctas de control de calidad a las que se debe mover el inventario. Después de completar el control de calidad, la directiva de ubicación para el tipo de orden de trabajo _Pedido de calidad_ asegura que se seleccionará una nueva ubicación de destino para que el inventario se pueda mover fuera de la ubicación de control de calidad.
1. Configure los elementos de menú relevantes del dispositivo móvil para admitir el movimiento del inventario recibido a la ubicación de control de calidad y el movimiento del inventario que pasa o falla el control de calidad desde la ubicación de control de calidad a una nueva ubicación.

Para ver un ejemplo paso a paso que muestra cómo completar esta configuración, consulte el [escenario de ejemplo](#example-scenario) al final de este tema.

## <a name="enable-a-warehouse-for-quality-management"></a>Habilitar un almacén para administración de la calidad

Antes de aplicar la característica _Administración de la calidad para procesos de almacén_ a un almacén específico, debe seguir estos pasos para que la función esté disponible para ese almacén.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
1. Seleccione el almacén que desea habilitar para la administración de la calidad.
1. En la ficha desplegable **Almacén**, configure la opción **Habilitar pedidos de calidad para procesos de almacén** como _Sí_. (Tenga en cuenta que esta opción se puede establecer en _Sí_ solo para almacenes que utilizan procesos de gestión de almacenes).

Cuando la opción **Habilitar pedidos de calidad para procesos de almacén** está establecida en _Sí_, la configuración de la asociación de calidad controla si la característica _Administración de calidad para procesos de almacén_ se aplica realmente para el almacén seleccionado. Puede cambiar la configuración de la opción a _No_ en cualquier momento. En ese caso, la función ya no se aplicará al almacén, independientemente de la configuración de la asociación de calidad.

## <a name="quality-control"></a>Control de calidad

La característica _Administración de calidad para procesos de almacén_ controla varias configuraciones clave para asociaciones de calidad y muestreo de artículos.

### <a name="quality-associations"></a>Asociaciones de calidad

Cada [registro de asociación de calidad](enable-quality-management.md) define también el conjunto de pruebas, el nivel de calidad aceptable (NCA) y el plan de muestreo que se aplica a los pedidos de calidad generados. Para configurar un registro de asociación de calidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Asociaciones de calidad**.
1. Cree o seleccione la entrada de asociación de calidad para el artículo o grupo con el que está trabajando, o para todos los artículos.
1. En la ficha desplegable **Condiciones**, configure el campo **Tipo de almacén aplicable** con uno de los siguientes valores:

    - **Administración de la calidad solo para procesos de almacén**: activa la característica _Administración de la calidad para procesos de almacén_. Puede seleccionar este valor solo si el tipo de referencia es *Compra* o *Producción*.
    - **Todo**: desactiva la característica _Administración de la calidad para procesos de almacén_. Seleccione este valor para todos los tipos de referencia excepto *Compra* y *Producción*.

> [!NOTE]
> La característica _Administración de la calidad para procesos de almacén_ solo tiene efecto si el artículo en la línea del documento de origen usa procesos avanzados de administración de almacenes y si la opción **Habilitar pedidos de calidad para procesos de almacén** está establecida en _Sí_ para el almacén en la línea del documento de origen.

A medida que cada elemento se registra (o se notifica como terminado), el sistema determina qué asociaciones de calidad se le aplican.

Cuando la característica _Administración de la calidad para procesos de almacén_ está activada, el tipo de almacén aplicable se inserta lógicamente en el cuarto grupo de búsqueda de la jerarquía de búsqueda de asociación de calidad. La siguiente tabla proporciona una representación lógica de la jerarquía de búsqueda.

| Grupo de búsqueda | Descripción |
|---|---|
| Grupo 1 | Para cada asociación de calidad, verifique los valores **Tipo de referencia**, **Tipo de evento** y **Coincidencia de ejecución** contra el artículo. Si hay una coincidencia con la línea del documento de origen, pase al grupo 2. |
| Grupo 2 | Para cada asociación de calidad, verifique el valor **Código de artículo** (_Tabla_, _Grupo_ o _Todo_) contra el artículo. _Tabla_ es más específico que _Grupo_ y _Grupo_ es más específico que _Todo_. Si hay una coincidencia para _Tabla_ (un elemento específico), se pasa al grupo 3. Si no hay coincidencia para _Tabla_, se busca una coincidencia para _Grupo_. Si no hay coincidencia para _Grupo_, se aplica _Todo_. Si hay una coincidencia, se pasa al grupo 3. |
| Grupo 3 | Para cada asociación de calidad, verifique los valores de **Código de cuenta** y **Código de recurso** contra el artículo. La lógica que se aplica se parece a la lógica que se aplica para el valor **Código de artículo**. |
| Grupo 4 | Para cada asociación de calidad, verifique el valor **Tipo de almacén aplicable** (_Administración de la calidad para procesos de almacén_ o _Todo_) contra el artículo. Si la opción **Habilitar pedidos de calidad para procesos de almacén** está establecida en _Sí_ para el almacén en el documento de origen y el artículo en la línea del documento de origen se establece en _Utilizar procesos de gestión de almacén_, las asociaciones con una coincidencia para _Administración de la calidad solo para procesos de almacén_ y las asociaciones con una coincidencia para _Todo_ serán aplicables en paralelo, si ambas existen. Si la característica **Administración de la calidad para procesos de almacén** se establece en _No_ para el almacén en el documento de origen y el artículo en la línea del documento de origen se establece en _Usar procesos de gestión de almacenes_, solo se aplicará la administración de calidad. |

Por ejemplo, ha definido un almacén donde la opción **Habilitar pedidos de calidad para procesos de almacén** está establecida en _Sí_ y tiene dos asociaciones de calidad definidas para el tipo de referencia *Compra*: uno para todos los artículos y uno para el tipo de evento *Registro*. La única diferencia entre las dos asociaciones de calidad es el valor **Tipo de almacén aplicable**: se establece en _Todas_ para una asociación de calidad y en _Gestión de calidad solo para procesos de almacén_ para la otra. En este caso, ambas asociaciones de calidad son igualmente específicas y ambas serán aplicables.

El valor del campo **Grupo de prueba** para las asociaciones de calidad también es un factor. Este campo define el procedimiento de prueba que debe aplicarse. Si el valor de **Grupo de prueba** es el mismo para ambas asociaciones, solo se creará un pedido de calidad, para la asociación de calidad donde el valor **Tipo de almacén aplicable** sea _Gestión de calidad solo para procesos de almacén_. Si el valor **Grupo de prueba** no es el mismo para ambas asociaciones, se crearán dos pedidos de calidad. El primer pedido de calidad se creará para la asociación de calidad en la que el valor de **Tipo de almacén aplicable** sea _Administración de la calidad solo para procesos de almacén_. El segundo pedido de calidad se creará para la asociación de calidad en la que el valor de **Tipo de almacén aplicable** sea _Todo_.

> [!NOTE]
> El valor _Administración de la calidad solo para procesos de almacén_ se considera más específico que _Todo_ cuando los criterios para las asociaciones de calidad para los grupos 1 y 2 son los mismos, y cuando el grupo de prueba es el mismo. Se crearán dos pedidos de calidad solo cuando los grupos de prueba difieran.

#### <a name="reference-types"></a>Tipos de referencia

Cuando el valor de **Tipo de referencia** es _Compra_ y el **Tipo de almacén aplicable** es _Gestión de calidad solo para procesos de almacén_, el campo **Tipo de evento** de la ficha desplegable **Proceso** debe establecerse en _Registro_. _Registro_ es el único tipo de evento compatible para el tipo de referencia _Compra_ cuando utiliza la característica _Gestión de calidad para procesos de almacén_.

#### <a name="quality-processing-policy"></a>Directiva de procesamiento de calidad

La característica _Gestión de calidad para procesos de almacén_ permite crear trabajos basados únicamente en el muestreo de elementos. Por lo tanto, permite un proceso ligero. El inventario para el que se crea el trabajo depende del muestreo del artículo que está asociado con la asociación de calidad. Cuando se utiliza el proceso ligero, después de que un trabajador coloca la cantidad en la ubicación de control de calidad, el departamento de calidad puede crear manualmente un pedido de calidad, si se requiere un pedido de calidad.

El campo **Política de procesamiento de calidad** en la ficha desplegable **Proceso de pedido de calidad** controla si también se crea un pedido de calidad cuando se crea trabajo para mover un artículo a la ubicación de control de calidad. Este campo se puede establecer en _Crear orden de calidad_ o _Crear solo trabajo_. El valor predeterminado es _Crear pedido de calidad_.

> [!NOTE]
> Independientemente de si crea pedidos de calidad de forma manual o automática, el sistema genera automáticamente trabajo para mover artículos fuera de la ubicación de control de calidad cuando el pedido de calidad se marca como validado.

La creación de trabajo de pedidos de calidad no está relacionada con la configuración de la asociación de calidad. Si existe una plantilla de trabajo que tiene el valor de **Tipo de orden de trabajo** *Orden de calidad* y si se cumplen los criterios de consulta para esa plantilla de trabajo, la validación de un pedido de calidad activará la creación de un trabajo de pedido de calidad.

#### <a name="referenced-item-sampling"></a>Muestreo de elementos referenciados

Cada asociación de calidad debe hacer referencia a un muestreo de artículos. El muestreo de artículos define la cantidad que se enviará para el control de calidad. Se puede configurar de modo que se aplique solo a asociaciones de calidad en las que el valor de **Tipo de almacén aplicable** sea _Administración de la calidad solo para procesos de almacén_. Si el valor de **Alcance de muestreo** para un elemento de muestreo es _Carga_ o _Envío_, o el valor **Especificación de la cantidad** es _Matrícula completa_, el muestreo de artículos solo puede ser referenciado por asociaciones de calidad donde el valor **Tipo de almacén aplicable** sea _Gestión de calidad solo para procesos de almacén_.

Si define un elemento de muestreo que utiliza el tipo de almacén aplicable _Gestión de calidad solo para procesos de almacén_, recibirá un error si intenta hacer referencia a él desde una asociación de calidad que no utiliza la característica _Gestión de calidad para procesos de almacén_.

> [!NOTE]
> El muestreo de artículos que usa bloqueo completo no es compatible con asociaciones de calidad donde el campo **Tipo de almacén aplicable** se establece en _Gestión de calidad solo para procesos de almacén_.

### <a name="item-sampling"></a>Muestreo de artículos

El muestreo de artículos controla con qué frecuencia se envían los artículos para el control de calidad. La característica _Gestión de calidad para procesos de almacén_ introduce el concepto de _alcance de muestreo del artículo_. El sistema utiliza el alcance del muestreo de artículos cuando evalúa si y cómo se deben crear pedidos de calidad y/o trabajo de muestreo de artículos de calidad y trabajo de pedidos de calidad.

Para configurar el muestreo de elementos, vaya a **Gestión del inventario \> Configuración \> Control de calidad \> Muestreo de artículos** y establezca el campo **Alcance de muestreo** en uno de los siguientes valores:

- **Pedido**: la línea del documento de origen será la base para evaluar si y cómo se crean pedidos de calidad y/o trabajo de muestreo de artículos de calidad y trabajo de pedidos de calidad. Este valor es el valor predeterminado y, cuando se selecciona, el sistema funciona de la misma manera que cuando la característica _Gestión de calidad para procesos de almacén_ no está activada.
- **Carga**: las cargas se utilizarán como base para evaluar si se crea un pedido y/o trabajo de calidad y de qué manera se crea. Este valor solo está disponible cuando la función _Gestión de calidad para procesos de almacén_ está activada.
- **Envío**: los envíos se utilizarán como base para evaluar si se crea un pedido y/o trabajo de calidad y de qué manera se crea. Este valor solo está disponible cuando la función _Gestión de calidad para procesos de almacén_ está activada.

> [!NOTE]
> Cuando el campo **Alcance de muestreo** se establece en *Carga* o *Envío*, se utilizarán la entidad de carga y las entidades de envío, si están disponibles. Si no están disponibles, se utilizará la entidad de pedido.

La característica _Gestión de calidad para procesos de almacén_ también presenta el valor *Matrícula completa* para el campo **Especificación de la cantidad**. Este valor respalda la creación de trabajos de pedidos de calidad y trabajos de muestreo de artículos de calidad, basados en placas de matrícula. Cuando selecciona este valor, se producen los siguientes cambios:

- La opción **Desglose por elemento** y el campo **Por enésima matrícula** de la ficha desplegable **Proceso** estarán disponibles.
- El campo **Valor** de la ficha desplegable **Cantidad de muestreo** deja de estar disponible.
- Las opciones **Por cantidad actualizada**, **Ubicación** y **Placa** están configuradas en *Sí* y la configuración no se puede cambiar.

La opción **Desglose por elemento** controla si el recuento de matrículas se evalúa por artículo o en todos los artículos en el alcance del muestreo. Las variantes del producto se tratan como el mismo artículo. Esta opción también controla si el recuento de matrículas se restablece para cada elemento.

El valor del campo **Por enésima matrícula** controla con qué frecuencia se crean pedidos de calidad en relación con el número de artículos que se registran. Por ejemplo, un valor de *3* enviará cada tercer elemento al control de calidad, comenzando por el primer elemento. El valor debe ser mayor que 0 (cero).

Mientras que los trabajadores reciben artículos utilizando la aplicación de almacén, el sistema valida si se configura una asociación de calidad para cada artículo entrante. Si se configura una asociación de calidad, el sistema utiliza el registro de muestreo de artículos configurado para esa asociación de calidad para determinar cómo creará pedidos de calidad, el trabajo de muestreo de artículos de calidad y el trabajo de pedido de compra.

> [!NOTE]
> Cuando el registro de recibo se realiza en el cliente web (mediante el uso de la página de registro pequeña o el diario de llegada de artículos para las líneas de orden de compra), no se crea trabajo de muestreo de artículos de calidad ni de orden de compra, independientemente de la configuración. En cambio, para los artículos que coinciden con una asociación de calidad, el muestreo del artículo referenciado se utiliza para controlar la creación de pedidos de calidad solamente.

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Ejemplos de generación automática de pedidos de calidad

Los siguientes ejemplos muestran cómo la configuración de una asociación de calidad y un muestreo de artículos asociado afecta a la generación de pedidos de calidad cuando el campo **Tipo de almacén aplicable** se establece en _Gestión de calidad solo para procesos de almacén_.

Cuando el valor de **Especificación de la cantidad** es _Matrícula completa_, el campo **Por enésima matrícula** controla para qué placas de matrícula se crea el trabajo de muestreo de artículos de calidad. La primera placa siempre va al control de calidad y luego el valor de este campo especifica que cada *n* matrículas después de esa matrícula también debe ir.

El valor **Tipo de referencia** para los siguientes ejemplos es _Compra_ y el valor de **Tipo de evento** es *Registro*.

| Ámbito de muestreo | Especificación de cantidad | Por cantidad actualizada | Por dimensión de almacenamiento | Desglosar recuento por artículo | Por enésima matrícula | Resultado |
|---|---|---|---|---|---|---|
| Pedido | Matrícula completa | Sí _(bloqueado/no editable)_ | <p>Ubicación: Sí</p><p>Matrícula: sí _(bloqueado/no editable)_</p> | Nº | 3 | <p>**Cantidad de línea de pedido: 100 EA**</p><ol><li>Registrar recibo en la aplicación de almacén para 20 EA, LP1<p>Trabajo de muestreo de artículos de calidad para 20 EA</p><p>Pedido de calidad 1 para 20 EA</p></li><li>Registrar recibo en la aplicación de almacén para 20 EA, LP2<p>Trabajo de pedido de compra para 20 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 20 EA, LP3<p>Trabajo de pedido de compra para 20 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 20 EA, LP4<p>Trabajo de muestreo de artículos de calidad para 20 EA</p></li><li>Registrar recibo en la aplicación de almacén para 20 EA, LP5<p>Trabajo de pedido de compra para 20 EA (ubicación)</p></li></ol> |
| Pedido | Cantidad fija = 1 | Sí | <p>Ubicación: Sí</p><p>Matrícula de entidad de almacén: Sí</p> | Nº | No aplicable | <p>**Cantidad de línea de pedido: 100**</p><ol><li>Registrar recibo en la aplicación de almacén para 20 EA, LP1<p>Trabajo de muestreo de artículos de calidad para 1 EA</p><p>Pedido de calidad 1 para 1 EA</p><p>Trabajo de pedido de compra para 19 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 20 EA, LP2<p>Trabajo de muestreo de artículos de calidad para 1 EA</p><p>Pedido de calidad 1 para 1 EA</p><p>Trabajo de pedido de compra para 19 (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 20 EA, LP3<p>Trabajo de muestreo de artículos de calidad para 1 EA</p><p>Pedido de calidad 1 para 1 EA</p><p>Trabajo de pedido de compra para 19 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 20 EA, LP4<p>Trabajo de muestreo de artículos de calidad para 1 EA</p><p>Pedido de calidad 1 para 1 EA</p><p>Trabajo de pedido de compra para 19 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 20 EA, LP5<p>Trabajo de muestreo de artículos de calidad para 1 EA</p><p>Pedido de calidad 1 para 1 EA</p><p>Trabajo de pedido de compra para 19 EA (ubicación)</p></li></ol> |
| Pedido | Porcentaje = 10 | Nº | <p>Ubicación: No</p><p>Matrícula de entidad de almacén: No</p> | Nº | No aplicable | <p>**Cantidad de línea de pedido: 100 EA**</p><ol><li>Registrar recibo en la aplicación de almacén para 50 EA, LP1<p>Trabajo de muestreo de artículos de calidad para 10 EA</p><p>Pedido de calidad 1 para 10 EA</p><p>Trabajo de pedido de compra para 40 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 50 EA, LP2<p>Trabajo de pedido de compra para 50 EA (ubicación)</p></li></ol> |
| Cargar | Porcentaje = 5 | Sí _(bloqueado/no editable)_ | <p>Ubicación: No</p><p>Matrícula de entidad de almacén: No</p> | Nº | No aplicable | <p>**Cantidad de línea de pedido: 500 EA**</p><p>**Dos cargas: primera carga 200 EA, segunda carga 300 EA**</p><ol><li>Registrar recibo en la aplicación de almacén para la primera carga de 100 EA<p>Trabajo de muestreo de artículos de calidad para 5 EA</p><p>Pedido de calidad 1 para 5 EA</p><p>Trabajo de pedido de compra para 95 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para la primera carga de 100 EA<p>Trabajo de muestreo de artículos de calidad para 5 EA</p><p>Pedido de calidad 1 para 5 EA</p><p>Trabajo de pedido de compra para 95 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para la segunda carga de 300 EA<p>Trabajo de muestreo de artículos de calidad para 15 EA</p><p>Pedido de calidad 1 para 15 EA</p><p>Trabajo de pedido de compra para 285 EA (ubicación)</p></li></ol> |
| Pedido | Porcentaje = 10 | Nº | <p>Ubicación: Sí</p><p>Matrícula de entidad de almacén: Sí</p> | Nº | No aplicable | <p>**Cantidad de línea de pedido: 100**</p><ol><li>Registrar recibo en la aplicación de almacén para 50 EA, LP1<p>Trabajo de muestreo de artículos de calidad para 5 EA</p><p>Pedido de calidad 1 para 5 EA</p><p>Trabajo de pedido de compra para 45 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 50 EA, LP2<p>Trabajo de muestreo de artículos de calidad para 5 EA</p><p>Pedido de calidad 1 para 5 EA</p><p>Trabajo de pedido de compra para 45 (ubicación)</p></li></ol> |
| Cargar | Matrícula completa | Sí _(bloqueado/no editable)_ | <p>Ubicación: Sí</p><p>Matrícula: sí _(bloqueado/no editable)_</p> | Nº | 3 | <p>**Dos artículos:**</p><ul><li>**Cantidad de línea de pedido para el artículo A: 120 EA (4 palés)**</li><li>**Cantidad de línea de pedido para el artículo B: 90 EA (3 palés)**</li></ul><p>**Una carga, dos líneas de carga con cada línea de pedido**</p><ol><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP1<p>Trabajo de muestreo de artículos de calidad para 30 EA</p><p>Pedido de calidad 1 para 30 EA</p></li><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP2<p>Trabajo de pedido de compra para 30 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP3<p>Trabajo de pedido de compra para 30 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP4<p>Trabajo de muestreo de artículos de calidad para 30 EA</p><p>Pedido de calidad 1 para 30 EA</p></li><li>Registrar recibo en la aplicación de almacén para el elemento B, 30 EA, LP5<p>Trabajo de pedido de compra para 30 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para el elemento B, 30 EA, LP6<p>Trabajo de pedido de compra para 30 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP7<p>Trabajo de muestreo de artículos de calidad para 30 EA</p><p>Pedido de calidad 1 para 30 EA</p></li></ol> |
| Cargar | Matrícula completa | Sí _(bloqueado/no editable)_ | <p>Ubicación: Sí</p><p>Matrícula: sí _(bloqueado/no editable)_</p> | Sí | 3 | <p>**Dos artículos:**</p><ul><li>**Cantidad de línea de pedido para el artículo A: 120 EA (4 palés)**</li><li>**Cantidad de línea de pedido para el artículo B: 90 EA (3 palés)**</li></ul><p>**Una carga, dos líneas de carga con cada línea de pedido**</p><ol><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP1<p>Trabajo de muestreo de artículos de calidad para 30 EA</p><p>Pedido de calidad 1 para 30 EA</p></li><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP2<p>Trabajo de pedido de compra para 30 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP3<p>Trabajo de pedido de compra para 30 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP4<p>Trabajo de muestreo de artículos de calidad para 30 EA</p><p>Pedido de calidad 1 para 30 EA</p></li><li>Registrar recibo en la aplicación de almacén para el elemento B, 30 EA, LP5<p>Trabajo de muestreo de artículos de calidad para 30 EA</p><p>Pedido de calidad 1 para 30 EA</p></li><li>Registrar recibo en la aplicación de almacén para el elemento B, 30 EA, LP6<p>Trabajo de pedido de compra para 30 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para el elemento A, 30 EA, LP7<p>Trabajo de pedido de compra para 30 EA (ubicación)</p></li></ol> |
| Cargar | Porcentaje = 10 | Sí _(bloqueado/no editable)_ | <p>Ubicación: No</p><p>Matrícula de entidad de almacén: No</p> | Nº | No aplicable | <p>**Cantidad de línea de pedido: 100 EA**</p><p>**No se crean cargas. Se aplica el alcance del pedido**.</p><ol><li>Registrar recibo en la aplicación de almacén para 50 EA, LP1<p>Trabajo de muestreo de artículos de calidad para 5 EA</p><p>Pedido de calidad 1 para 5 EA</p><p>Trabajo de pedido de compra para 45 EA (ubicación)</p></li><li>Registrar recibo en la aplicación de almacén para 50 EA, LP2<p>Trabajo de muestreo de artículos de calidad para 5 EA</p><p>Pedido de calidad 1 para 5 EA</p><p>Trabajo de pedido de compra para 45 EA (ubicación)</p></li></ol> |

Cuando un trabajador valida uno de los pedidos de calidad que se muestran en la tabla anterior, el sistema genera automáticamente el trabajo de pedidos de calidad para mover el inventario desde la ubicación de control de calidad a la ubicación que se define en la directiva de ubicación para el tipo de orden de trabajo _Pedido de calidad_. Puede configurar cualquier ubicación para este propósito, como una ubicación de devolución o almacenamiento, dependiendo del resultado de la prueba para el pedido de calidad. Para ver un ejemplo de esta configuración, consulte el [escenario de ejemplo](#example-scenario) al final de este tema.

Puede volver a abrir un pedido de calidad que ya ha sido validado, siempre que el trabajo del pedido de calidad relacionado con el traslado del inventario desde la ubicación de control de calidad no tenga un valor de **Situación laboral** *Cerrado* o *En progreso*.

## <a name="process-insights-when-multiple-quality-associations-coexist"></a>Información del proceso cuando coexisten múltiples asociaciones de calidad

Se puede definir y aplicar más de una asociación de calidad a la misma línea del documento de origen y el campo **Tipo de almacén aplicable** se puede establecer en _Gestión de calidad solo para procesos de almacén_ para algunas de esas asociaciones de calidad y en _Todo_ para otras.

En el siguiente ejemplo, el valor **Tipo de referencia** es _Compra_.

1. La primera asociación de calidad se configura de la siguiente manera:

    - **Tipo de almacén aplicable**: *Gestión de calidad solo para procesos de almacén*
    - **Código de artículo**: *A0001*
    - **Código de cuenta**: *Todos*
    - **Grupo de prueba**: *Recinto*
    - **Muestreo de artículos**: *5 uds.*

1. La segunda asociación de calidad se configura de la siguiente manera:

    - **Tipo de almacén aplicable**: *Todos*
    - **Código de artículo**: *Todos*
    - **Código de cuenta**: *Todos*
    - **Grupo de prueba**: *Recinto*
    - **Muestreo de artículos**: *1 uds.*

1. La tercera asociación de calidad se configura de la siguiente manera:

    - **Tipo de almacén aplicable**: *Gestión de calidad solo para procesos de almacén*
    - **Código de artículo**: *Todos*
    - **Código de cuenta**: *104*
    - **Grupo de prueba**: *Impedancia*
    - **Muestreo de artículo**: *Cada segunda matrícula* (esta configuración significa que la primera, tercera, quinta, etc., placas que se reciben crean un pedido de calidad).

1. La cuarta asociación de calidad se configura de la siguiente manera:

    - **Tipo de almacén aplicable**: *Todos*
    - **Código de artículo**: *Todos*
    - **Código de cuenta**: *Todos*
    - **Grupo de prueba**: *Impedancia*
    - **Muestreo de artículos**: *5 uds.*

1. La quinta asociación de calidad se configura de la siguiente manera:

    - **Tipo de almacén aplicable**: *Todos*
    - **Código de artículo**: *Todos*
    - **Código de cuenta**: *Todos*
    - **Grupo de prueba**: *Cono*
    - **Muestreo de artículos**: *10 %*

Ahora se crea una orden de compra para una cantidad de 10 del artículo A0001 para el proveedor 104. Luego, se registra una línea de pedido de compra que tiene una cantidad de 10 como recibida en una matrícula usando la aplicación de almacén. Este es el resultado:

- Hay un pedido de calidad de la primera asociación de calidad para el grupo de prueba *Recinto*. La cantidad es 5. No hay una orden de calidad de la segunda asociación de calidad, porque los criterios para la primera asociación de calidad son más específicos en relación con el grupo de prueba *Recinto*.
- Hay un pedido de calidad para la tercera asociación de calidad para el grupo de prueba *Impedancia*. La cantidad es 10. No hay una orden de calidad de la cuarta asociación de calidad, porque los criterios para la primera asociación de calidad son más específicos en relación con el grupo de prueba *Impedancia*.
- Hay un pedido de calidad para la quinta asociación de calidad para el grupo de prueba *Cono*. La cantidad es 1.

En relación con la creación de un pedido de calidad para cada una de las tres asociaciones de calidad, también se crea un trabajo de muestreo de artículos de calidad. La cantidad registrada es solo 10. Sin embargo, debido a la configuración de muestreo de artículos, la suma de las cantidades de pedido de calidad que se crean para el tipo de almacén *Gestión de calidad solo para procesos de almacén* aplicable es 16, que excede la cantidad física registrada de 10. Por lo tanto, no se creará trabajo para las cantidades de pedido de calidad completa (16), porque solo 10 están físicamente disponibles para moverse a la ubicación de control de calidad. La prioridad que se utiliza para crear trabajos de muestreo de artículos de calidad sigue el orden de creación de pedidos de calidad:

- **Primer pedido de calidad (cantidad = 5)**: el trabajo de muestreo de artículos de calidad se crea para 5. Ahora queda una cantidad de 5 (10 - 5) para la posterior creación de trabajo de muestreo de artículos de calidad.
- **Segundo pedido de calidad (cantidad = 10)**: el trabajo de muestreo de artículos de calidad se crea para 5. Ahora queda una cantidad de 0 (cero) para la posterior creación de trabajo de muestreo de artículos de calidad.
- **Tercer pedido de calidad (cantidad = 1)**: no se crea trabajo de muestreo de artículos de calidad.

Como parte del proceso de creación de pedidos de calidad, se crea un bloqueo de inventario de una cantidad de 10. Se hace referencia a este bloqueo de inventario en cada uno de los tres pedidos de calidad. La suma de las cantidades de pedido de calidad es 16.

Cuando se validan los pedidos de calidad, el sistema intenta crear trabajos de pedidos de calidad para cada pedido de calidad que se valida. Debido a que la suma de las cantidades de pedido de calidad excede la cantidad que está realmente bloqueada y, por lo tanto, disponible para la creación de trabajo, el trabajo de pedido de calidad no se puede crear para las cantidades de pedido de calidad completa, como se muestra aquí. (Este ejemplo continúa el ejemplo anterior de este tema).

1. **Validar el segundo pedido de calidad que se crea (cantidad = 10). El trabajo de pedido de calidad se crea para una cantidad de 4**.

    La creación del trabajo de pedidos de calidad se desencadena por un cambio en la cantidad de bloqueo de inventario. Debido a que la suma de las cantidades de pedidos de calidad fue de 16, la validación de una cantidad de 10 hará que las cantidades de pedidos de calidad restantes se validen como igual a 6. La cantidad de bloqueo de inventario se reduce de 10 a 6. La cantidad reducida de 4 se asigna a la creación de trabajo de orden de calidad.

2. **Validar el primer pedido de calidad que se crea (cantidad = 5). El trabajo de pedido de calidad se crea para una cantidad de 5**.

    La creación del trabajo de pedidos de calidad se desencadena por un cambio en la cantidad de bloqueo de inventario. Debido a que la suma de las cantidades de pedidos de calidad fue de 6, la validación de una cantidad de 5 hará que las cantidades de pedidos de calidad restantes se validen como igual a 1. La cantidad de bloqueo de inventario se reduce de 6 a 1. La cantidad reducida de 5 se asigna a la creación de trabajo de orden de calidad.

3. **Validar el tercer pedido de calidad que se crea (cantidad = 1). El trabajo de pedido de calidad se crea para una cantidad de 1**.

    La creación del trabajo de pedidos de calidad se desencadena por un cambio en la cantidad de bloqueo de inventario. Debido a que la suma de las cantidades de pedidos de calidad fue de 1, la validación de una cantidad de 1 hará que las cantidades de pedidos de calidad restantes se validen como igual a 0 (cero). El bloqueo de inventario se elimina (es decir, la cantidad de bloqueo de inventario se reduce de 1 a 0). La cantidad reducida de 1 se asigna a la creación de trabajo de orden de calidad.

> [!NOTE]
> La creación del trabajo de pedidos de calidad depende de la cantidad de bloqueo de inventario que se hace referencia a uno o más pedidos de calidad. Si la suma de las cantidades de pedido de calidad excede la cantidad de bloqueo de inventario referenciada, el pedido en el que se validan los pedidos de calidad determina la creación del trabajo de pedido de calidad.

## <a name="canceling-quality-item-sampling-work"></a>Cancelar trabajo de muestreo de artículos de calidad

Puede cancelar el trabajo creado para el muestreo de artículos de calidad. Para controlar lo que ocurre cuando se cancela este trabajo, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **General**, en la ficha desplegable **Trabajo**, configure la opción **Anular el registro al cancelar el trabajo** en uno de los siguientes valores:

    - **Sí**: cuando se cancela el trabajo de muestreo de artículos de calidad, el pedido de calidad asociado se elimina y el inventario no se registra.
    - **No**: cuando se cancela el trabajo de muestreo de artículos de calidad, el pedido de calidad asociado no se elimina y no se anula el registro del inventario.

## <a name="cross-docking"></a>Tránsito directo

Puede tener una configuración de asociación de calidad que cree un trabajo de muestreo de elementos. Sin embargo, cuando existe un acoplamiento cruzado en paralelo con una asociación de calidad que crea un trabajo de muestreo de artículos de calidad, si solo hay suficiente cantidad para satisfacer el acoplamiento cruzado, solo se crea el trabajo de muestreo de artículos. Cuando la opción **Habilitar pedidos de calidad para procesos de almacén** está establecida en _Sí_ para el almacén receptor y el campo **Tipo de almacén aplicable** se establece en _Gestión de calidad solo para procesos de almacén_ para una asociación de calidad, la creación de trabajo de muestreo de artículos de calidad tiene prioridad sobre la creación de trabajo de tránsito directo. Si la cantidad excede el requisito de tránsito directo, el sistema todavía crea solo trabajo de muestreo de artículos.

## <a name="destructive-testing"></a>Prueba destructiva

Puede definir un grupo de prueba que realice pruebas destructivas. En el caso de una prueba destructiva, la suposición es que, independientemente del resultado de la prueba, la cantidad del artículo que se prueba se destruirá como parte de la prueba. La forma en la que la característica _Gestión de calidad para procesos de almacén_ admite pruebas destructivas se asemeja a la forma en que la gestión de calidad lo admite cuando la función no está activada. Antes de que se pueda validar el pedido de calidad, el controlador de calidad debe especificar la ubicación de recogida para la cantidad que se ha destruido. Puede registrarse la recogida en la página de pedidos de calidad seleccionando **Inventario \> Recoger** en el panel de acciones. Después de registrar la selección de la cantidad de pedido de calidad, se puede completar la validación.

## <a name="example-scenario"></a>Supuesto de ejemplo

### <a name="prepare-the-scenario"></a>Preparar el escenario

Para resolver este escenario, debe preparar su sistema de la siguiente manera:

- Asegúrese de que los datos de demostración estén instalados en el sistema y seleccione la entidad legal **USMF**.
- Active la característica _Administración de la calidad para procesos de almacén_ en [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Configure el almacén 51 para usar la característica _Gestión de calidad para procesos de almacén_ siguiendo estos pasos:

    1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
    1. Seleccione el almacén 51.
    1. En la ficha desplegable **Almacén**, configure la opción **Habilitar pedidos de calidad para procesos de almacén** como *Sí*.

### <a name="quality-in-setup--move-to-the-quality-control-location"></a>Configuración de calidad de entrada: desplazamiento a la ubicación de control de calidad

Ahora debe preparar una configuración básica que permita que su sistema admita la característica _Gestión de calidad para procesos de almacén_ para el almacén 51. (Los datos de demostración definen una ubicación de gestión de calidad que se denomina *QMS*. Se hace referencia a esa ubicación varias veces en este escenario). Preparará los siguientes elementos, como se describe en las subsecciones de esta sección:

- Clase de trabajo
- Plantilla de trabajo
- directiva de ubicación
- Muestreo de artículos
- Asociación de calidad
- Elementos de menú del dispositivo móvil

#### <a name="work-class-for-quality-in"></a>Clase de trabajo para la calidad de entrada

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.
1. Cree una clase de trabajo y establezca los siguientes valores:

    - **Identificador de la clase de trabajo**: _CalidadEnt_
    - **Descripción**: _Muestreo de artículos de calidad_
    - **Tipo de orden de trabajo**: _Muestreo de artículos de calidad_

#### <a name="work-template"></a>Plantilla de trabajo

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. Establezca el campo **Tipo de orden de trabajo** en _Muestreo de artículos de calidad_.
1. Cree una plantilla de trabajo y establezca los siguientes valores:

    - **Plantilla de trabajo**: _51 calidad_
    - **Descripción de plantilla de trabajo**: _51 calidad_

1. Agregue una línea a la plantilla de trabajo y establezca los siguientes valores:

    - **Tipo de trabajo**: _Recoger_
    - **Identificador de la clase de trabajo**: _CalidadEnt_

1. Agregue una segunda línea a la plantilla de trabajo y establezca los siguientes valores:

    - **Tipo de trabajo**: _Ubicar_
    - **Identificador de la clase de trabajo**: _CalidadEnt_

#### <a name="location-directive"></a>Directiva de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. Establezca el campo **Tipo de orden de trabajo** en _Muestreo de artículos de calidad_.
1. Cree una directiva de ubicación y establezca los siguientes valores:

    - **Nombre**: _51 a calidad_
    - **Tipo de trabajo**: _Ubicar_
    - **Sitio**: 5
    - **Almacén**: _51_

1. Agregue una línea para la directiva de ubicación y establezca los siguientes valores:

    - **Cantidad inicial**: _1_
    - **Cantidad final**: _1000000_

1. Cree una acción de directiva de ubicación y establezca el siguiente valor:

    - **Nombre**: _Calidad_

1. Para la nueva acción de directiva de ubicación, seleccione **Editar consulta** y especifique un registro **Rango** con los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Campo**: _ID de perfil de ubicación_
    - **Criterios**: *QMS*

1. Seleccione **Aceptar** para guardar la consulta y guardar la nueva directiva de ubicación.

A continuación, debe cambiar la secuencia de las directivas de ubicación de pedidos de compra existentes para el almacén 51. Los datos de demostración incluyen dos directivas de ubicación que tienen un valor de **Tipo de orden de trabajo** _Compra_: uno se llama _51 QMS_ y el otro se llama _51 PO directo_. Para asegurar que la característica *Gestión de calidad para procesos de almacén* se aplica para el almacén 51, debe asegurarse de que no se aplica la directiva _51 QMS_. Sin embargo, en lugar de eliminar esa directiva de ubicación (porque es posible que desee usarla en el futuro), puede cambiar la secuencia.

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. Establezca el campo **Tipo de orden de trabajo** en _Pedido de compra_.
1. En la lista de secuencias, seleccione la secuencia número 5, para la directiva de ubicación _51 PO directo_.
1. Mueva la secuencia seleccionada hasta la secuencia número 4.
1. Verifique que el número de secuencia la directiva de ubicación _51 QMS_ ahora sea al menos 5.

#### <a name="item-sampling"></a>Muestreo de artículos

La característica _Gestión de calidad para procesos de almacén_ agrega algunas nuevas capacidades de muestreo de elementos. El valor **Alcance de muestreo** ahora puede ser _Orden_, _Envío_ o _Carga_ y el valor **Cantidad de muestreo** ahora puede ser _Matrícula completa_.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Muestreo de artículos**.
1. Cree un registro de muestreo de elementos y establezca los siguientes valores:

    - **Muestreo de artículo**: _3ª LP_
    - **Descripción**: _Cada tercera matrícula_
    - **Ámbito de muestreo**: _Pedido_

1. En la ficha desplegable **Cantidad de muestreo**, configure el campo **Especificación de la cantidad** como _Matrícula completa_.
1. En la ficha desplegable **Proceso**, configure el campo **Por enésima matrícula** como _3_.
1. En la sección **Por dimensión de almacenamiento**, habilite **Almacén** y **Estado de inventario**.

#### <a name="quality-associations"></a>Asociaciones de calidad

Cree una asociación de calidad que utilice el nuevo muestreo de elementos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Asociaciones de calidad**.
1. Cree un registro de asociación de calidad y establezca los siguientes valores:

    - **Tipo de referencia**: _Compra_
    - **Código de artículo**: _Tabla_
    - **Artículo**: _M9201_
    - **Sitio**: _5_

1. En la ficha desplegable **Proceso**, configure el campo **Tipo de evento** como *Registro*.
1. En la ficha desplegable **Condiciones**, configure el campo **Tipo de almacén aplicable** como *Gestión de calidad solo para procesos de almacén*.
1. En la ficha desplegable **Proceso de pedido de calidad**, configure el campo **Política de procesamiento de calidad** como _Crear orden de calidad_.
1. En la ficha desplegable **Especificaciones**, haga clic con el botón derecho en el campo **Grupo de prueba** y luego seleccione **Ver detalles** para abrir la página **Grupos de prueba**.
1. En la página **Grupos de prueba**, en la ficha **Visión general** de la cuadrícula superior, cree un grupo de prueba y establezca los siguientes valores:

    - **Grupo de prueba**: _QMS_
    - **Descripción**: _prueba QMS_
    - **Cantidad aceptable**: _100_
    - **Muestreo de artículos**: _3ª LP_ (selección)

1. En la pestaña **Visión general** de la cuadrícula inferior, agregue un registro para una prueba y establezca los siguientes valores:

    - **Secuencia**: *1*
    - **Prueba**: *Medición de recinto*

1. En la pestaña **Prueba** de la cuadrícula inferior, establezca los siguientes valores:

    - **Variables de prueba**: *Aprobado/error*
    - **Resultado predeterminado**: *Aprobado*

1. Guarde el nuevo grupo de prueba y cierre la página **Grupos de prueba**.
1. De vuelta en la página **Asociaciones de calidad**, en el campo **Grupo de prueba**, seleccione **QMS**.
1. Guarde el registro.

#### <a name="mobile-device-menu-items-for-quality-in"></a>Elementos del menú del dispositivo móvil para la calidad de entrada

Para completar la configuración para mover mercancías a la ubicación de control de calidad, debe hacer que el trabajo de muestreo de elementos de calidad esté disponible desde un elemento de menú del dispositivo móvil.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. Seleccione el elemento de menú **Ubicación de compra** del dispositivo móvil.
1. En la ficha desplegable **Clases de trabajo**, agregue el ID de clase de trabajo *CalidadEnt*.

#### <a name="summary-your-setup-to-move-goods-to-quality-control"></a>Resumen: su configuración para mover productos al control de calidad

Ahora ha definido una asociación de calidad que utiliza la característica *Gestión de calidad para procesos de almacén* para desencadenar la creación de un pedido de calidad. Ha configurado los datos de trabajo y ubicación para el almacén 51 para garantizar que se cree un trabajo específico cuando se realice el registro de compra para el artículo M9201. Esta configuración garantiza que cada tercera placa que se registre se moverá a una ubicación de calidad (_QMS_) y que se creará un pedido de calidad para la cantidad de matrícula. Todo lo demás se moverá a la ubicación en lugar de la ubicación de control de calidad.

### <a name="process-quality-management-work"></a>Procesar el trabajo de administración de calidad

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Cree un pedido de compra y establezca los siguientes valores:

    - **Cuenta de proveedor**: *104*
    - **Almacén**: *51*

1. Agregue una línea de pedido de compra y establezca los siguientes valores:

    - **Artículo**: *M9201*
    - **Cantidad:** *20*
    - **UdM**: *u*
    - **Almacén**: *51*

1. Anote el número de orden de compra, para que pueda usarlo más tarde.
1. Vaya a un dispositivo móvil o emulador que esté ejecutando la aplicación de almacén e inicie sesión en el almacén 51 utilizando *51* como id. de usuario y *1* como contraseña.
1. Vaya a **Entrante \> Recibir compra** e ingrese los siguientes valores:

    - **N.º PO**: número del pedido de compra que acaba de crear.
    - **Cant.**: *5*
    - **Unidad**: *u*

1. Continúe recibiendo la línea, *5 u* cada vez, hasta que la línea se reciba por completo. (Se crearán un total de cuatro placas).
1. Cierre sesión en la aplicación de almacén.
1. De vuelta en el cliente web, vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Encuentre y abra la orden de compra.
1. En la sección **Líneas de orden de compra**, seleccione la línea para el número de artículo *M9201* y luego seleccione **Líneas de orden de compra \> Detalles del trabajo**.
1. Observe que los encabezados de trabajo segundo y tercero que se crearon son trabajos de almacenamiento regulares, mientras que los encabezados de trabajo primero y cuarto son trabajos de muestreo de elementos de calidad. Este resultado es coherente con la configuración de muestreo de elementos, que está configurada para muestrear cada tercera placa.

#### <a name="move-to-the-quality-control-location"></a>Moverse a la ubicación de control de calidad

Ahora moverá las placas a sus ubicaciones designadas. Las placas primera y cuarta irán a la ubicación de control de calidad, mientras que las placas segunda y tercera irán directamente al almacenamiento.

1. Vaya a un dispositivo móvil o emulador que esté ejecutando la aplicación de almacén e inicie sesión en el almacén 51 utilizando *51* como id. de usuario y *1* como contraseña.
1. Vayaa a **Entrante \> Ubicación de compra** y ubique cada placa del procedimiento anterior hasta que haya cerrado todo el trabajo.

#### <a name="summary-process-quality-management-work"></a>Resumen: procesar el trabajo de administración de calidad

Ahora ha ejecutado el trabajo de muestreo de artículos de calidad para la primera y la cuarta matrículas moviéndolas a la ubicación de control de calidad. También ha guardado la segunda y la tercera matrícula. El siguiente paso es hacer la prueba y el control de la orden de calidad.

### <a name="quality-out-setup-move-from-the-quality-control-location-to-storage-or-return"></a>Configuración de calidad: moverse de la ubicación de control de calidad a almacenamiento o devolución

Cuando los trabajadores informan resultados de pedidos de calidad, el sistema genera automáticamente trabajo.

Ahora continuará con la configuración básica requerida de la clase de trabajo, la plantilla de trabajo y la directiva de ubicación para permitir la gestión de calidad para los procesos de almacén, de modo que se pueda crear el trabajo requerido para mover la cantidad de pedido de calidad desde la ubicación de control de calidad a un lugar designado del almacén.

#### <a name="work-class-for-quality-out"></a>Clase de trabajo para la calidad de salida

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.
1. Cree una clase de trabajo y establezca los siguientes valores:

    - **Identificador de la clase de trabajo**: *CalidadSal*
    - **Descripción**: *Calidad de salida*
    - **Tipo de orden de trabajo**: *Orden de calidad*

#### <a name="work-templates"></a>Plantillas de trabajo

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. Cambie el valor de **Tipo de orden de trabajo** a *Orden de calidad*.
1. Cree una plantilla de trabajo y establezca los siguientes valores:

    - **Plantilla de trabajo**: *51 calidad de salida*
    - **Descripción de plantilla de trabajo**: *51 calidad de salida*

1. Agregue una línea y establezca los siguientes valores:

    - **Tipo de trabajo**: *Recoger*
    - **Identificador de la clase de trabajo**: **CalidadSal**

1. Agregue una segunda línea y establezca los siguientes valores:

    - **Tipo de trabajo**: *Ubicar*
    - **Identificador de la clase de trabajo**: *CalidadSal*

#### <a name="location-directives"></a>Directivas de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. Cambie el valor de **Tipo de orden de trabajo** a *Orden de calidad*.
1. Cree una directiva de ubicación y establezca los siguientes valores:

    - **Nombre**: *51 aprobado*
    - **Tipo de trabajo**: *Ubicar*
    - **Sitio**: *5*
    - **Almacén**: *51*

1. En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas.
1. En la pestaña **Rango**, establezca los siguientes valores:

    - **Tabla**: *Pedidos de calidad*
    - **Campo**: *Estado*
    - **Criterios**: *Aprobado*

1. Seleccione **Aceptar** para guardar la consulta y cerrar el cuadro de diálogo.
1. En la ficha desplegable **Líneas**, agregue una línea y establezca los siguientes valores:

    - **Cantidad inicial**: *1*
    - **Cantidad final**: *1000000*

1. En la ficha desplegable **Acciones de directivas de localización**, agregue una fila y establezca el siguiente valor:

    - **Nombre**: *Aprobado*

1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas.
1. En la pestaña **Rango**, establezca los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Campo**: *ID de zona*
    - **Criterios**: *Masivo*

1. Seleccione **Aceptar** para guardar la consulta y cerrar el cuadro de diálogo.
1. En el panel de acciones, seleccione **Guardar** para guardar la nueva directiva de ubicación.
1. Cree una segunda directiva de ubicación y establezca los siguientes valores:

    - **Nombre**: *51 error*
    - **Tipo de trabajo**: *Ubicar*
    - **Sitio**: *5*
    - **Almacén**: *51*

1. En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas.
1. En la pestaña **Rango**, establezca los siguientes valores:

    - **Tabla**: *Pedidos de calidad*
    - **Campo**: *Estado*
    - **Criterios**: *Error*

1. Seleccione **Aceptar** para guardar la consulta y cerrar el cuadro de diálogo.
1. En la ficha desplegable **Líneas**, agregue una línea y establezca los siguientes valores:

    - **Cantidad inicial**: *1*
    - **Cantidad final**: *1000000*

1. En la ficha desplegable **Acciones de directivas de localización**, agregue una fila y establezca el siguiente valor:

    - **Nombre**: *Error*

1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas.
1. En la pestaña **Rango**, establezca los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Campo**: *ID de zona*
    - **Criterios**: *Devolución*

1. Seleccione **Aceptar** para guardar la consulta y cerrar el cuadro de diálogo.
1. En el panel de acciones, seleccione **Guardar** para guardar la nueva directiva de ubicación.

#### <a name="mobile-device-menu-items-for-quality-out"></a>Elementos del menú del dispositivo móvil para la calidad de salida

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. Seleccione el elemento de menú **Ubicación QMS** del dispositivo móvil.
1. En la ficha desplegable **Clases de trabajo**, agregue el ID de clase de trabajo *CalidadUbic*.

Los trabajadores de almacén ahora podrán elegir trabajos de pedidos de calidad utilizando el elemento de menú **Ubicación QMS**. Las mercancías con errores de control de calidad se pueden colocar en una ubicación de devolución y las mercancías aprobadas se pueden colocar en la ubicación de Bulk-001.

#### <a name="summary-your-setup-to-move-goods-from-quality-control"></a>Resumen: su configuración para mover productos desde control de calidad

Ha configurado los datos de trabajo y ubicación para el almacén 51 para garantizar que se cree un trabajo automáticamente cuando se completen los pedidos de calidad. Esta configuración garantiza que cada matrícula con control de calidad se mueva a una ubicación masiva o a una ubicación de devolución.

### <a name="process-quality-management-work"></a>Procesar el trabajo de administración de calidad

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.
1. Seleccione el primer pedido de calidad para las cantidades que se registraron.
1. Seleccione **Validar**. El estado de la prueba se actualiza como *Error*.
1. Vaya a **Gestión de almacenes \> Todo el trabajo**.
1. Abra el trabajo que acaba de crear y observe que el valor **Tipo de orden de trabajo** es *Orden de calidad*. El trabajo incluye una línea donde la ubicación de colocación es *Devolución* y el estado es *Error*. (Si el estado del pedido de calidad fuera *Aprobado*, la ubicación de venta sería, en su lugar, *Masiva*).
1. Regrese a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.
1. Seleccione el segundo pedido de calidad para los artículos que se registraron.
1. Seleccione **Resultados** encima de la cuadrícula inferior. Actualice el valor de **Cantidad resultante** en *5* y verifique que el valor de **Resultado de la prueba** se cambia a una marca de verificación.
1. Seleccione **Validar** y cierre la página.
1. De vuelta en la página **Pedidos de calidad**, seleccione **Validar** y haga la validación. El estado se actualiza a *Aprobado*.

    > [!NOTE]
    > El evento de validación desencadena la creación del trabajo de orden de calidad para mover la cantidad desde la ubicación de control de calidad a una nueva ubicación.

1. Vaya a **Gestión de almacenes \> Todo el trabajo**.
1. Seleccione el trabajo que acaba de crear y observe que se ha creado un segundo encabezado de trabajo de orden de calidad, donde está la ubicación de colocación *BULK-001*.
1. Vaya a un dispositivo móvil o emulador que esté ejecutando la aplicación de almacén e inicie sesión en el almacén 51 utilizando *51* como id. de usuario y *1* como contraseña.
1. Vaya a **Calidad \> Ubicar desde QMS** y procese cada una de las dos matrículas relacionadas con ambas unidades de trabajo de modo que todo el trabajo esté cerrado.

> [!NOTE]
> Considere agregar la entrada de calidad de salida a un elemento del menú del dispositivo móvil con código de actividad *Mostrar lista de trabajo abierta*. Por ejemplo, vea el elemento del menú del dispositivo móvil que se llama **Lista de trabajo** en los datos de demostración. Primero agregue la clase de trabajo *Orden de calidad* a un elemento de menú dirigido por el usuario, porque esta clase de trabajo es necesaria para que el trabajo se muestre en la lista de trabajo. Luego agregue la clase de trabajo *Orden de calidad* al elemento de menú **Lista de trabajo**. Los usuarios que tienen acceso a la lista de trabajo podrán seleccionar y procesar el trabajo que se genere automáticamente mediante la validación de pedidos de calidad.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]