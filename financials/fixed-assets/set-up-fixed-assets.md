---
title: Configurar Activos fijos
description: "Este tema proporciona información general de la Configuración del módulo Activos fijos."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b41901d573e977a89fcd1a7c1ebf7185e162c654
ms.openlocfilehash: dde8053df96d03c8c8e52fa6d2fdf7f74e95ec92
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-fixed-assets"></a>Configurar Activos fijos

[!include[banner](../includes/banner.md)]


Este tema proporciona información general de la Configuración del módulo Activos fijos.

<a name="overview"></a>Visión general
--------
Los parámetros controlan el comportamiento general de los Activos fijos.

Los grupos de activos fijos le permiten agrupar los activos y especificar los atributos predeterminados para cada activo que se asigna a un grupo. Los libros se asignan a grupos de activos fijos. Los libros siguen al valor financiero de un activo fijo con el tiempo mediante la configuración de la depreciación que se define en el perfil de depreciación.

Los activos fijos se asignan a un grupo cuando se crean. De forma predeterminada, los libros que se asignan al grupo de activos fijos se asignan después al activo fijo. Los libros que se configuran para registrarse en la contabilidad general se asocian a un perfil de publicación. Las cuentas del libro mayor se definen por libro en el perfil de publicación y se usan cuando se publican las transacciones de activos fijos. 

![FixedAssetsComponentsImage](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Métodos de depreciación
Debe configurar los perfiles de depreciación primero. En el perfil de depreciación, configure cómo se deprecia el valor de un activo en el tiempo. Debe definir el método de depreciación, el año de depreciación (año natural o año fiscal) y la frecuencia de depreciación.

## <a name="books"></a>Libros
Tras configurar los perfiles de depreciación, debe crear los libros necesarios para sus activos. Cada libro sigue el ciclo de vida financiera independiente de un activo. Los libros se pueden configurar para publicar transacciones asociadas a la contabilidad general. Esta configuración es la configuración predeterminada porque se usa normalmente para el informe financiero corporativo. Los libros que no se registran en la contabilidad general se publican solo en el libro mayor auxiliar de activos fijos y se utilizan normalmente para informes tributarios.

A cada libro se asigna un perfil de depreciación principal. Los libros también tienen un perfil de depreciación alternativo o de conversión, si se puede aplicar este tipo de perfil. Para incluir automáticamente el libro de activos fijos en ejecuciones de depreciación, debe habilitar la opción Calcular la depreciación. Si esta opción no está seleccionada para un activo, la propuesta de depreciación omite el activo.

También puede configurar los libros derivados. Las transacciones derivadas especificadas se publican como una copia exacta de la transacción principal con los libros derivados. Por lo tanto, las transacciones derivadas se configuran normalmente para las adquisiciones y las cancelaciones, no para las transacciones de depreciación.

## <a name="fixed-asset-posting-profiles"></a>Perfiles de contabilización de activos fijos
Una vez configura los libros, puede crear el perfil de publicación. El perfil de publicación se debe definir por el libro, pero también puede definirse a un nivel más detallado. Por ejemplo, puede definir el perfil de publicación para la combinación de un libro y un grupo de activos fijos, o incluso para un libro de activo fijo individual. De forma predeterminada, las cuentas del libro mayor se definen para las transacciones de activos fijos.

Debe definir las cuentas del libro mayor que se usan durante los procesos de disposición, las ventas de preparación y las piezas de cancelación. En el momento de la cancelación, las transacciones de activos fijos registradas anteriormente se invierten fuera de las cuentas de originales, y los importes netos se desplazan a la cuenta adecuada de pérdidas y ganancias para la cancelación del activo. Para ayudar a garantizar que las transacciones se invierten correctamente, debe configurar cuentas para cada tipo de transacción que utiliza en su negocio. La cuenta principal debe ser la cuenta original que establece en el perfil de publicación para el tipo de transacción, mientras que la cuenta de contrapartida deben ser las pérdidas y ganancias de cuenta de cancelación. La excepción es el valor neto del libro. En este caso, la cuenta principal y la cuenta de contrapartida deben establecerse a las pérdidas y ganancias de la cuenta de cancelación.

## <a name="fixed-asset-groups"></a>Grupos de activos fijos
El grupo de activos fijos es el único campo necesario cuando crea un activo fijo. El valor de este campo determina el valor predeterminado de varios campos informativos para el activo. Los libros se configuran para asignar un libro predeterminado a cada activo de un grupo. Después puede establecer los atributos de los libros que son específicos para un grupo de activos, como el Tiempo de vida y la Convención de depreciación.

También puede definir los métodos de amortización por depreciación especial o la bonificación de dicha depreciación para una combinación específica de un grupo de activos fijos y un libro. Debe asignar una prioridad al método de amortización por depreciación especial para especificar el orden en que se calculan los permisos cuando se asignan varios métodos a un libro.

## <a name="fixed-asset-parameters"></a>Parámetros del activo fijo
El último paso es actualizar los parámetros de activos fijos.

El campo Umbral de capitalización determina los activos que se deprecian. Si se selecciona una línea de compra como activo fijo pero no coincide con el umbral de capitalización especificado, todavía se crea o se actualiza un activo fijo, pero la opción de Cálculo de la depreciación se establece en No. Por lo tanto, el activo no se depreciará automáticamente como parte de las propuestas de depreciación.

Una opción importante es Crear importes de ajuste de depreciación automáticamente con la cancelación. Cuando establece esta opción en Sí, la depreciación de activos se ajusta automáticamente en función de los ajustes de depreciación en el momento de la cancelación del activo. Otra opción le permite deducir descuentos de efectivo del importe de adquisición al adquirir activos fijos mediante una factura de proveedor.

En la ficha desplegable de Pedidos de compra, puede configurar cómo se crean los activos como parte del proceso de compra. La primera opción es Permitir la adquisición de activos desde Compras. Si establece esta opción en Sí, la adquisición de activos aparece cuando se registra la factura. Si establece esta opción en No, aún podrá configurar un activo fijo en un pedido de compra y en una factura, pero la adquisición no se registrará. El registro se debe realizar como paso independiente del diario de activos fijos. La opción de Crear el activo durante la recepción de producto o la publicación de la factura le permite crear un nuevo activo simultáneamente durante el registro, no para tener que configurarlo como un activo fijo antes de la transacción. La última opción, Comprobar la creación de activos fijos durante la entrada de línea, solo se aplica a las solicitudes de compra.

Puede configurar los códigos de motivo para que sean necesarios para los cambios a un activo fijo o para transacciones de activos fijos concretos.

Finalmente, en la ficha de Secuencias numéricas, se definen las secuencias numéricas de los activos fijos. La secuencia del número de activo fijo se puede anular mediante la secuencia numérica del grupo de activos fijos si se ha especificado.




