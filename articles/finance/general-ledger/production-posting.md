---
title: Registrar pedido de producción
description: Este artículo proporciona información sobre los distintos tipos de registros de pedido de producción.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, ProjCategory, CostSheetDesigner
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d41725325a82b24c1e5aa6bd2c1a5322f3078ace
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879635"
---
# <a name="production-postings"></a>Registros de producción

Este artículo proporciona información sobre los distintos tipos de registro en el proceso de pedido.


## <a name="material-consumption"></a>Lista de selección

Los materiales se registran como consumidos durante la producción cuando se registra el diario de lista de selección de producción. Esto crea transacciones que reducen el inventario disponible. En los **Parámetros de producción**, puede especificar si el valor de las materias primas en proceso (llamado WIP), se deben registrar en el libro mayor.

El valor de las materias primas en curso (WIP) se contabiliza en las cuentas **Costo estimado de los materiales consumidos** y **Costo estimado de materiales consumidos, WIP**. El proceso de lista de selección para la orden de producción es una actualización física de las transacciones de inventario relacionadas con la orden de producción. Cuando una orden de producción se registra como finalizada, las transacciones físicas se revierten y las transacciones de inventario relacionadas se actualizan financieramente. Cuando se contabiliza el diario final, los tipos de contabilización **Coste de los materiales consumidos** y **Coste de materiales consumidos, WIP** se utilizan.

La pestaña **Producción** en la página **Perfiles de contabilización de inventario** se utiliza para controlar cómo se contabilizarán los pedidos de venta en el libro mayor. Esto se usa cuando el campo **Registro contable** se establece en **Artículo y recurso** o **Artículo y categoría** en la página **Parámetros de control de producción**. 

Para que un diario de lista de selección se registre en el libro mayor para una orden de producción, se deben cumplir las siguientes condiciones:

-   La casilla **Registrar lista de selección** debe seleccionarse en la página **Parámetros de control de producción**. Esta configuración se puede anular para un sitio específico en la página **Parámetros de control de producción por sitio**.
-   La casilla de verificación **Registrar el inventario físico** debe estar seleccionada en la página **Grupos de modelo de artículo** para el artículo seleccionado en la línea de pedido de compra.
-   Las cuentas principales deben especificarse en la página **Perfil de contabilización de inventario** para los siguientes tipos de contabilización:
    -   **Coste estimado de materiales consumidos**
    -   **Coste estimado de materiales consumidos, trabajo en curso**

## <a name="time-consumption"></a>Consumo de tiempo

El tiempo que los trabajadores invierten en trabajos de producción se registra en el **Diario de tarjeta de ruta** o en el **Diario de tarjeta de trabajo**. Cuando se registran estos diarios, se procesa el registro contable en una cuenta dedicada para recursos en curso (trabajo en curso). Este registro representa el valor de tiempo invertido en el pedido de producción. Después de que el pedido de producción se registre como terminado, se liquidarán las cuentas de trabajo en curso.

Hay tres formas posibles de contabilizar el consumo de tiempo dependiendo de la opción seleccionada en el campo **Registro contable** en la página **Parámetros de control de producción**.

## <a name="reporting-finished-goods-and-error-quantities"></a>Notificación de productos terminados y cantidades de error

Cuando un pedido de producción se **Notifica como terminado**, la cantidad de productos terminados que se haya completado se actualizan en el inventario a través del diario **Notificar como terminado**. Si utiliza contabilidad de WIP, se registra un diario contable para reducir las cuentas de trabajo en curso y para aumentar el inventario de productos terminados. El diario usa el coste estándar definido para el producto. Si la opción **Usar precio de coste estimado** se selecciona en la página **Parámetros de control de producción**, se utilizará el coste estimado de la orden de producción.

El valor de las materias primas en curso (WIP) se contabiliza en las cuentas **Coste estimado de fabricación** y **Costo estimado de facturación, WIP**. El proceso de **Notificado como completado** para la orden de producción es una actualización física de las transacciones de inventario relacionadas con la orden de producción. Cuando una orden de producción finaliza, las transacciones físicas se revierten y las transacciones de inventario relacionadas se actualizan financieramente. Cuando se contabiliza el diario final, los tipos de contabilización **Coste de fabricación** y **Coste de fabricación, WIP** se utilizan.

La pestaña **Producción** en la página **Perfiles de contabilización de inventario** se utiliza para controlar cómo se contabilizarán los pedidos de producción en el libro mayor. Esto se usa cuando el campo **Registro contable** se establece en **Artículo y recurso** o **Artículo y categoría** en la página **Parámetros de control de producción**. La ficha desplegable **Artículos de libro mayor** en la página **Grupos de producción** también se puede utilizar para controlar la publicación de órdenes de producción cuando el campo se establece en **Grupos de producción**.

Para que un diario de **Notificado como completado** se registre en el libro mayor para una orden de producción, se deben cumplir las siguientes condiciones:
-   La casilla **Registrar informe como completado en el libro mayor** debe seleccionarse en la página **Parámetros de control de producción**. Esta configuración se puede anular para un sitio específico en la página **Parámetros de control de producción por sitio**.
-   La casilla de verificación **Registrar el inventario físico** debe estar seleccionada en la página **Grupos de modelo de artículo** para el artículo seleccionado en la línea de pedido de compra.
-   Las cuentas principales deben especificarse en la página **Perfil de contabilización de inventario** para los siguientes tipos de contabilización:
    -   **Coste estimado de artículos fabricados**
    -   **Coste estimado de artículos fabricados, trabajo en curso**

## <a name="ending-the-production-order"></a>Finalización del pedido de producción

Antes de completar un pedido de producción, se calculan los costes reales para la cantidad producida. Todos los costes estimados de material, mano de obra y gastos generales se invierten y sustituyen por los costes reales. El coste total del artículo terminado se carga desde la cuenta de **Coste de manufacturación** y se abona a la cuenta de **Coste de manufacturación, WIP**. Los materiales que se consumieron durante la orden de fabricación se abonan en el **Coste de los materiales consumidos** y con cargo a la cuenta **Coste de materiales, WIP**.

Si activa la casilla de verificación **Cierre final** al ejecutar el cálculo de costes, el estado de pedido de producción cambia a **Finalizado**. Este estado evita que los costes adicional se registren de forma inadvertida para un pedido de producción finalizado. Puede especificar que el valor de las cantidades equivocadas que se notifiquen como terminadas se asigne a las cantidades correctas notificadas como terminadas. También puede especificar que el valor de las cantidades equivocadas se debe registrar en una cuenta residual dedicada. 

Para especificar una cuenta de residuos específica, siga estos pasos:
1.  Vaya a **Control de producción** > **Configurar** > **Parámetros de control de producción**.
2.  Seleccione la pestaña **Actualización estándar**.
3.  En el campo **Método de residuo**, seleccione **Cuenta de residuo**.
4.  En el campo **Cuenta residuo** seleccione la cuenta principal en la que debe contabilizarse el residuo por cantidad de error cuando finaliza la orden de producción. Por ejemplo, seleccione una cuenta de gastos como 510380: Residuos de producción.

Para que el diario final se registre en el libro mayor para una orden de producción, se deben cumplir las siguientes condiciones:
-   Las cuentas principales deben especificarse en la página **Perfil de contabilización de inventario** o **Grupos de producción** para los siguientes tipos de contabilización:
    -   **Coste de materiales consumidos**
    -   **Coste de materiales consumidos, trabajo en curso**
    -   **Coste de artículos fabricados**
    -   **Coste de artículos fabricados, trabajo en curso**
-   Las cuentas principales deben especificarse en la página **Categorías de costes**, **Recursos**, o **Grupos de recursos** para los siguientes tipos:
    -   **Costes de fabricación absorbidos**
    -   **Coste de fabricación consumido, trabajo en curso**

## <a name="indirect-costs-for-production-orders"></a>Costos indirectos para órdenes de producción

Cuando procesa transacciones para una orden de producción, puede configurar costes indirectos para capturar costes generales o tarifas adicionales en su libro mayor. Las transacciones físicas para costes indirectos se reconocen en el inventario cuando registra un diario de lista de selección o informa como diario terminado. Las transacciones financieras por costos indirectos se reconocen en el inventario cuando registra el diario final.

Puede reconocer costes indirectos en su consumo de tiempo relacionados con diarios de **Tarjeta de ruta** o **Tarjeta de trabajo**. Estas transacciones se anulan y contabilizan en las cuentas financieras cuando finaliza la orden de producción. Para obtener más información, consulte [Hojas de costes](/supply-chain/cost-management/costing-sheets.md).

## <a name="controlling-the-level-of-ledger-posting"></a>Control del nivel de registro contable

En la página **Parámetros de control de producción**, puede usar el campo **Registro de libro mayor** para definir el nivel de registro contable para los procesos de producción. 

Están disponibles los siguientes campos:

### <a name="item-and-resource"></a>Artículo y recurso

Cuando selecciona la opción **Artículo y recurso** en el campo **Registro contable**, las cuentas de contabilización provienen del recurso o grupo de recursos en operación en la ruta. Las cuentas en el recurso específico serán la primera opción de publicación. Si no se especifica una cuenta, se usarán las cuentas especificadas en el grupo de recursos. Cada línea de operación en una ruta puede tener un recurso especificado como el **Recurso de coste**. Este recurso se utiliza para determinar la cuenta a utilizar. Esta opción se usa comúnmente cuando una organización asigna costos operativos a los recursos. Los costes suelen ser más altos para los recursos y se utilizan para ayudar a tomar decisiones de "fabricar versus comprar". Esta es la configuración de publicación más detallada y permite el control más granular de las publicaciones y un análisis muy detallado del proceso de producción.

### <a name="item-and-category"></a>Artículo y categoría

Cuando selecciona la opción **Artículo y categoría** en el campo **Registro contable**, las cuentas de contabilización procederán de la página **Categoría de costo** relacionada con cada línea de la ruta. Cada línea de operación en la ruta puede tener tres categorías de coste: tiempo de **Configuración**, tiempo de **Ejecución** y **Cantidad**. Esta opción se usa comúnmente cuando el enfoque principal de su organización está en la eficiencia del proceso y la duración de la actividad. Esta opción es una forma más resumida de contabilización y aún proporciona una forma de agrupar costos en categorías.

### <a name="production-group"></a>Grupo de producción

Cuando selecciona la opción **Grupos de producción** en el campo **Registro contable**, las cuentas contables proceden de la página **Grupos de producción**. **Grupos de producción** se utilizan normalmente cuando más de una línea de producción ejecuta productos similares o tiene equipos similares. Puede utilizar esta opción para comparar los costes entre dos grupos de producción diferentes.  
  
> [!NOTE]
> Si se utiliza el método estándar para calcular el coste del artículo terminado, las transacciones finales lo reflejan. Si los costes reales y los costes calculados utilizando el método estándar varían, las diferencias se registran en la cuenta que muestra las pérdidas o beneficios.

### <a name="route-groups-and-ledger-posting"></a>Grupos de rutas y registros contables

Cada línea de operación en una ruta tiene un **Grupo de ruta** especificado. Los campos **Tiempo de configuración**, **Tiempo de ejecución** y **Cantidad** en el **Grupo de ruta** en el grupo **Estimación y costes** se usan para controlar si el tiempo se usará para los costes al registrar una **Tarjeta de trabajo** o **Diario de tarjeta de ruta** en la orden de producción. Si las opciones están deshabilitadas, no se creará un comprobante en el libro mayor para el consumo de tiempo.

Para que una **Tarjeta de ruta** o **Diario de tarjeta de trabajo** se registre en el libro mayor para una orden de producción, se deben cumplir las siguientes condiciones:

-   El campo **Tiempo de configuración**, **Tiempo de ejecución** o **Cantidad** debe ser seleccionado en el grupo **Estimación y coste** en la página **Grupo de rutas**.
-   Las cuentas principales deben especificarse en la página **Categoría de coste**, **Ruta**, **Grupo de ruta** o **Grupos de producción** para los siguientes tipos de registro:
    -   Coste estimado de fabricación absorbido
    -   Coste estimado de fabricación consumido, trabajo en curso

El siguiente diagrama muestra la relación del grupo de rutas con el cálculo del coste total de cada operación (línea de ruta) en una ruta determinada. Cada línea de ruta tiene un grupo de rutas. El grupo de rutas controla los parámetros para el tiempo de configuración, el tiempo de ejecución y la cantidad. La pestaña **Categoría de coste** tiene tres opciones para **Configuración**, **Ejecución**, y **Cantidad** que están habilitadas en función de la configuración de los grupos de rutas. La ficha desplegable **Horarios** tiene tres campos que se basan en el grupo de rutas.

La fórmula que se usa se basa en si la opción está habilitada en el grupo de rutas. El coste de la categoría de coste seleccionada se multiplica por la cantidad que se ingresó en los tiempos para calcular el coste total.

:::image type="complex" source="media/RouteGroupRelationship.png" alt-text="La relación de los grupos de rutas con el coste total calculado.":::
La relación de los grupos de rutas con el coste total calculado. Cada línea de ruta tiene un grupo de rutas. El grupo de rutas controla los parámetros para el tiempo de configuración, el tiempo de ejecución y la cantidad. La pestaña Categoría de coste tiene tres opciones para Configuración, Ejecución, y Cantidad que están habilitadas en función de la configuración de los grupos de rutas. La ficha desplegable Horarios tiene tres campos que están habilitados y basados en costes en el grupo de rutas. La fórmula que se usa se basa en si la opción está habilitada en el grupo de rutas. El coste de la categoría de coste seleccionada se multiplica por la cantidad que se ingresó en los tiempos para calcular el coste total.
:::image-end:::

## <a name="sample-posting-profile-configuration"></a>Ejemplo de configuración del perfil de publicación

La siguiente tabla muestra ejemplos de los tipos de contabilización predeterminados con ejemplos de cuentas principales y descripciones. 

 - La columna **Débito/Crédito** indica si la transacción suele ser Débito o Crédito o, en algunos casos, puede contabilizarse. 
 - La columna **Cuenta de compensación** indica si el tipo de contabilización es una cuenta de compensación. El importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior. 
 - La columna **F/F** indica **p** para publicación física y **f** para la contabilización financiera. 
 - La columna **Seguir** indica si la cuenta principal para un tipo de publicación específico suele ser la misma que para otro tipo de publicación. El valor de la columna indica el tipo de publicación que se suele utilizar.

> [!NOTE]
> Estas cuentas principales y nombres de cuentas principales son solo sugerencias. Le recomendamos que trabaje con su contador para determinar la mejor configuración para sus necesidades comerciales.


| Tipo de registro  | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal| Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Físico o financiero | Seguir | Description |
|---------------|----------------------|--------------------------|--------------|----------------|------------------|-----------------------|--------|------------|
| Coste estimado de materiales consumidos      | 140100               | Inventario de materiales        | Activo        | Crédito         | Y                | C                     | Coste de materiales consumidos                | Esta cuenta se usa cuando registra un diario de lista de selección para una orden de producción. La compensación a esta cuenta es el Coste estimado de materiales, WIP. El importe registrado en esta cuenta se revierte automáticamente cuando el pedido de producción termina Esta cuenta representa la cuenta de inventario en el balance de situación.       |
| Coste estimado de materiales consumidos, trabajo en curso | 150150               | WIP de producción: materiales | Activo        | Débito          | Y                | C                     | Coste estimado de artículos fabricados, trabajo en curso          | Esta cuenta se usa cuando registra un diario de lista de selección para una orden de producción. La compensación a esta cuenta es el Coste estimado de materiales consumidos. El importe registrado en esta cuenta se revierte automáticamente cuando un pedido de producción termina Esta cuenta representa el WIP en su balance de situación.                  |
| Coste estimado de artículos fabricados               | 140200               | Inventario de bienes terminados   | Activo        | Débito          | Y                | C                     | Coste de artículos fabricados                         | Esta cuenta se usa cuando registra un informe como diario finalizado para una orden de producción. La compensación a esta cuenta es el Coste estimado de fabricación, WIP. El importe registrado en esta cuenta se revierte automáticamente cuando el pedido de producción termina Esta cuenta representa la cuenta de inventario en el balance de situación. |
| Coste estimado de artículos fabricados, trabajo en curso          | 150150               | WIP de producción: materiales | Activo        | Crédito         | Y                | C                     | Coste de artículos fabricados, trabajo en curso                    | Esta cuenta se usa cuando registra un informe como diario finalizado para una orden de producción. La compensación a esta cuenta es el Coste estimado de fabricación. El importe registrado en esta cuenta se revierte automáticamente cuando un pedido de producción termina Esta cuenta representa el WIP en su balance de situación.                     |
| Coste de materiales consumidos                | 140100               | Inventario de materiales        | Activo        | Crédito         | N                 | V                     | Coste estimado de materiales consumidos      | Esta cuenta se utiliza para reconocer los materiales que se consumen en la orden de fabricación durante el proceso final. La compensación a esta cuenta es el Coste de materiales consumidos, WIP.                                                                                                    |
| Coste de materiales consumidos, trabajo en curso           | 150150               | WIP de producción: materiales | Activo        | Débito          | N                 | V                     | Coste estimado de materiales consumidos, trabajo en curso | Esta cuenta se utiliza para reconocer los materiales en WIP que se consumen en la orden de fabricación durante el proceso final. La compensación a esta cuenta es el Coste de materiales consumidos.                                                |
| Coste de artículos fabricados                         | 140200               | Inventario de bienes terminados   | Activo        | Débito          | N                 | V                     | Coste estimado de artículos fabricados               | Esta cuenta se usa para reconocer el costo del bien terminado que se produce mediante una orden de producción cuando finaliza la orden de producción. La compensación a esta cuenta es el Coste de fabricación, cuenta WIP.                                                                  |
| Coste de artículos fabricados, trabajo en curso                    | 150150               | WIP de producción: materiales | Activo        | Crédito         | N                 | V                     | Coste estimado de artículos fabricados, trabajo en curso          | Esta cuenta se usa para reconocer el costo del bien terminado en WIP que se produce mediante una orden de producción cuando finaliza la orden de producción. La compensación a esta cuenta es la Cuenta de Coste de fabricación.                                     |

> [!NOTE]
> El **Recibo WIP del servicio Lean** y **Cuenta de compensación WIP del servicio Lean** se utilizan con contabilización previa de los costes para Lean manufacturing. Para obtener más información, consulte [Contabilización previa de los costes](/supply-chain/cost-management/backflush-costing.md).

