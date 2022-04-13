---
title: Usar el diario de existencias de seguridad para actualizar la cobertura mínima para artículos
description: Este tema describe cómo utilizar el diario de existencias de seguridad para actualizar la cantidad de existencias de seguridad para artículos mediante el cálculo de propuestas de cobertura mínima basadas en transacciones históricas.
author: t-benebo
ms.date: 10/28/2021
ms.topic: article
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, ReqItemTableSetup, ReqItemTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-28
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 391f741ee08eb0624e80f5c297009c527e50c14c
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468563"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage-for-items"></a>Usar el diario de existencias de seguridad para actualizar la cobertura mínima para artículos

[!include [banner](../../includes/banner.md)]

Las existencias de seguridad indican una cantidad adicional de un artículo que se mantiene en el inventario para ayudar a reducir el riesgo de que el artículo se agote. Las existencias de seguridad se usan como reserva en caso de que vengan pedidos de ventas pero el proveedor no pueda entregar los artículos adicionales.

Este tema muestra cómo usar el diario de existencias de seguridad para calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas.

## <a name="overview-of-minimum-coverage-usage"></a>Descripción general del uso de cobertura mínima

Las existencias de seguridad se configuran en la página **Cobertura de artículos** para cada artículo. Los diferentes tipos de reabastecimiento están representados por diferentes códigos de cobertura. (Para más información, vea [Cumplimiento de existencias de seguridad para los artículos](safety-stock-replenishment.md).) Sin embargo, todos los códigos de cobertura utilizan el valor que se establece en el campo **Mínimo** en la página **Cobertura de artículos** para cada artículo. Hay dos enfoques principales para utilizar el campo **Mínimo**:

- **Cantidad mínima para fines mín/máx** - Este enfoque utiliza la cantidad mínima junto con la lógica mínima/máxima. Se aplica cuando el campo **Código de cobertura** está configurado en *Mín/Máx* para el artículo o grupo de cobertura relevante. La cantidad **Mínima** representa el uso diario promedio multiplicado por el tiempo de entrega del artículo.
- **Cantidad mínima para propósitos del plan de inventario** - Este enfoque utiliza la cantidad mínima para representar un plan de inventario en combinación con previsiones de demanda. Se aplica cuando el campo **Código de cobertura** está configurado en *Periodo* o *Requisito* para el artículo o grupo de cobertura relevante. La cantidad **Mínima** representa un plan de inventario que refleja el nivel de servicio al cliente deseado para ayudar a reducir el desabastecimiento, los envíos parciales y los plazos de entrega. La cantidad mínima refleja un porcentaje de precisión de la previsión para un artículo determinado. No representa una posición de inventario deseada.

El valor **Mínimo** se puede establecer de tres formas:

- Manualmente en la página **Cobertura de artículos**
- Mediante el marco de administración de datos (entidades de datos de *Cobertura de artículos*)
- Mediante el cálculo de existencias de seguridad realizado por los diarios de existencias de seguridad.

## <a name="calculate-minimum-coverage-based-on-historical-usage"></a>Calcular la cobertura mínima basada en el uso histórico

Los diarios de existencias de seguridad se utilizan para calcular una cantidad mínima propuesta en función del uso histórico de un artículo, ya sea para fines mínimos/máximos o para fines del plan de inventario. El uso histórico representa todas las transacciones de emisión durante un período específico. Estas transacciones de emisión incluyen transacciones de órdenes de venta y ajustes de inventario. Los cálculos también identifican el impacto de la cantidad mínima propuesta en el valor del inventario y el cambio en el valor del inventario en comparación con las cantidades mínimas actuales.

Cada línea del diario de existencias de seguridad representa un artículo y sus dimensiones de cobertura. Estas líneas de diario se crean y se muestran en la página **Líneas del diario de existencias de seguridad** (**Planificación maestra \> Planificación maestra \> Ejecutar \> Cálculo de existencias de seguridad**). El proceso empresarial para utilizar los diarios de existencias de seguridad para calcular las cantidades mínimas propuestas se describe más adelante en este tema.

El planificador utiliza un diario de existencias de seguridad para calcular las cantidades mínimas propuestas para artículos seleccionados, en función del uso histórico durante los períodos seleccionados. Los mínimos propuestos se pueden reemplazar manualmente según sea necesario, y puede revisar el impacto potencial de los mínimos propuestos en el valor del inventario. Cuando se registra el diario, las cantidades mínimas asociadas en la cobertura del artículo se actualizan automáticamente.

### <a name="create-a-new-safety-stock-journal-name"></a>Puede crear un nuevo nombre de diario de existencias de seguridad.

Debe crear al menos un nombre de diario de existencias de seguridad antes de poder generar este tipo de diario. Por lo general, puede usar varios nombres de diario para ayudar a separar sus cálculos de existencias de seguridad.

1. Vaya a **Planificación maestra \> Configuración \> Nombres de diario de existencias de seguridad**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En la nueva línea, establezca los siguientes campos:

    - **Nombre** – Especifique un nombre breve para el diario.
    - **Descripción** – Proporcione una descripción del diario.
    - **Privado para grupo de usuarios** - Para limitar la audiencia del nombre del diario actual, seleccione un grupo de usuarios.
    - **Eliminar líneas tras registrar** - Seleccione esta casilla de verificación para limpiar las líneas del diario de forma predeterminada a medida que las publica. Bórrelo para mantener todas las líneas registradas.

    El campo **Tipo de diario** es de solo lectura y está preestablecido para *Existencias de seguridad*.

1. Cierre la página.

### <a name="create-a-safety-stock-journal-and-lines"></a>Crear un diario y líneas de existencias de seguridad

Este paso crea un diario y le agrega líneas automáticamente. Cada línea identifica un artículo, sus dimensiones de cobertura y varias cantidades calculadas del historial de uso. Las cantidades calculadas incluyen emisiones promedio por tiempo de entrega del artículo, emisiones promedio por mes y la desviación estándar mensual.

#### <a name="automatically-generate-journal-lines"></a>Generar automáticamente líneas de diario

Se pueden generar automáticamente líneas del diario solo si no existen líneas para el diario que se muestra actualmente.

Siga estos pasos para generar automáticamente líneas de diario.

1. Vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Cálculo de existencias de seguridad**.
1. En el panel de acciones, haga clic en **Nueva**. Se crea un nuevo diario de existencias de seguridad.
1. En la ficha desplegable **Detalles de encabezado de diario**, configure los siguientes campos:

    - **Nombre** - Seleccione el nombre del diario de existencias de seguridad al que agregar la línea.
    - **Descripción** - El valor predeterminado es la descripción del nombre del diario que seleccionó. Sin embargo, puede editar el valor si es necesario.
    - **Eliminar líneas tras registrar** - Seleccione esta casilla de verificación para limpiar las líneas del diario a medida que las publica. Bórrelo para mantener todas las líneas registradas. La configuración se hereda del nombre del diario seleccionado.

    El campo **Diario** es de solo lectura y muestra el número de identificación del diario que está creando y al que está agregando líneas.

1. En la ficha desplegable **Líneas del diario**, seleccione **Crear líneas** en la barra de herramientas.
1. En el cuadro de diálogo **Crear líneas del diario para niveles mínimos de inventario propuestos**, configure los siguientes campos:

    - **Fecha de inicio** - Seleccione la fecha de inicio del período para el que se deben incluir las emisiones en el cálculo.
    - **Fecha de finalización** - Seleccione la fecha de fin del período para el que se deben incluir las emisiones en este cálculo. Debe haber al menos dos meses entre las fechas de inicio y finalización.
    - **Calcular la desviación estándar** - Establezca esta opción en *Sí* para calcular la desviación estándar. Debe configurar esta opción en *Sí* para usar la opción **Usar nivel de servicio** cuando calcule la propuesta (como se describe más adelante en este tema).

1. En la ficha desplegable **Registros para incluir**, puede configurar filtros y restricciones para definir qué artículos se incluyen. (Por ejemplo, puede filtrar por el valor del **Grupo de cobertura**.) Seleccione **Filtrar** para abrir un cuadro de diálogo del editor de consultas estándar, donde puede definir criterios de selección, criterios de ordenación y combinaciones. Los campos funcionan igual que para otros tipos de consultas en Microsoft Dynamics 365 Supply Chain Management.
1. En la ficha desplegable **Ejecutar en segundo plano**, seleccione si el trabajo se debe ejecutar en modo por lotes y/o establezca una programación periódica. Los campos funcionan igual que o hacen para otros tipos de [trabajos en segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar**. Se crean líneas para las dimensiones que tienen transacciones de inventario.

#### <a name="manually-add-or-remove-journal-lines"></a>Agregar o eliminar líneas del diario manualmente

Puede agregar y/o quitar líneas del diario manualmente en cualquier momento (ya sea después o en lugar de generar líneas automáticamente). Utilice los siguientes botones de la barra de herramientas de la ficha desplegable **Líneas del diario**:

- **Nuevo** - Agregar una línea nueva. Luego ingrese un valor en cada columna para definir el producto para calcular y aplicar nuevos mínimos. Dado que los cálculos mínimos propuestos no están disponibles para las líneas agregadas manualmente, no se muestran nuevos valores de **Cantidad mínima calculada** para ellas. Por lo tanto, debe ingresar manualmente los valores de **Nueva cantidad mínima**. Sin embargo, aún puede ver el impacto potencial del valor de **Nueva cantidad mínima** en el valor del inventario y el cambio potencial en el inventario en comparación con el mínimo especificado actualmente.
- **Eliminar** - Elimine la línea seleccionada.
- **Eliminar líneas del diario** - Eliminar todas las líneas del diario.

### <a name="calculate-a-proposal"></a>Calcular una propuesta

Este paso calcula un mínimo propuesto para cada línea del diario y el impacto potencial de la línea en el valor del inventario. (El mínimo propuesto se muestra como valor de **Cantidad mínima calculada**.) Puede hacer el cálculo varias veces, según lo requiera. El cálculo actualiza el valor de **Cantidad mínima calculada** que se muestra para todas las líneas del diario.

Los cálculos que se muestran no afectarán los valores de cantidad mínima real para cada producto hasta que seleccione **Registrar** en el Panel de acciones. En ese momento, los valores de **Nueva cantidad mínima** se aplicarán a cada producto.

1. Vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Cálculo de existencias de seguridad**.
1. Abra el diario para calcular una propuesta. Alternativamente, cree un nuevo diario como se describe anteriormente en este tema.
1. En la ficha desplegable **Líneas del diario**, seleccione **Calcular propuesta** en la barra de herramientas. (No tiene que seleccionar ninguna línea.)
1. En el cuadro de diálogo **Calcular propuesta para nivel mínimo de inventario**, configure los siguientes campos:

    - **Usar el promedio de emisión durante el plazo** - Seleccione esta opción para generar valores de **Cantidad mínima calculada** basados en la emisión promedio durante el período especificado. Luego, en el campo **Factor de multiplicación**, ingrese un valor para ajustar el resultado según sea necesario. Por ejemplo, ingrese *1.0* para utilizar el promedio calculado exacto o *1.1* para agregar una reserva adicional del 10 por ciento.
    - **Usar nivel de servicio** - Seleccione esta opción para calcular un mínimo propuesto basado en el nivel de servicio deseado. Luego, en el campo **Nivel de servicio**, seleccione su nivel de servicio preferido.
    - **Margen de tiempo de entrega** - Ingrese un valor para extender el tiempo de entrega normal (por ejemplo, para permitir la administración).
    - **Usar la cantidad mínima calculada como nueva cantidad mínima** - Establezca esta opción en *Sí* para copiar automáticamente los valores de la columna **Cantidad mínima calculada** a la columna **Nueva cantidad mínima** para todas las líneas después de que se complete el cálculo. Si configura esta opción en *No*, el valor de **Cantidad mínima actual** se copiará en la columna **Nueva cantidad mínima** para todas las líneas. A continuación, tendrá que editar manualmente los valores de **Nueva cantidad mínima** según sea necesario.

1. En la ficha desplegable **Ejecutar en segundo plano**, seleccione si el trabajo se debe ejecutar en modo por lotes y/o establezca una programación periódica. Los campos funcionan igual que o hacen para otros tipos de [trabajos en segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar**. Los resultados del cálculo se muestran en la columna **Cantidad mínima calculada** en la ficha desplegable **Líneas del diario**. Por ahora, los valores son solo valores propuestos que aún no se han aplicado a sus productos.

### <a name="update-minimum-quantity"></a>Actualizar cantidad mínima

Puede seleccionar cualquier línea en un diario de existencias de seguridad y reemplazar manualmente el valor de su campo **Nueva cantidad mínima**.

1. Vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Cálculo de existencias de seguridad**.
1. Abra el diario para editar. Alternativamente, cree un nuevo diario como se describe anteriormente.
1. En la ficha desplegable **Líneas del diario**, busque la línea para ajustar y luego edite el valor en la columna **Nueva cantidad mínima**. Por ejemplo, puede configurar el valor de **Nueva cantidad mínima** para que coincida con el valor de **Cantidad mínima calculada**. Si el valor de **Cantidad mínima calculada** es *0* (cero) puede escribir el valor futuro deseado.

### <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Publicar la nueva cantidad mínima y validar el resultado

Siga esto pasos para registrar la nueva cantidad mínima y validar el resultado.

1. Vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Cálculo de existencias de seguridad**.
1. Abra el diario para registrar nuevas cantidades mínimas. Alternativamente, cree un nuevo diario como se describe anteriormente.
1. En el panel de acciones, seleccione **Registrar**.
1. En el cuadro de diálogo **Publicar diario**, establezca el campo **Transferir todos los errores de registro a un nuevo diario** según sea necesario. Después seleccione **Aceptar** para publicar el diario.
1. Si cambió el valor de **Nueva cantidad mínima** para una línea en la ficha desplegable **Líneas del diario**, puede confirmar el cambio siguiendo estos pasos:

    1. Para la línea que editó, seleccione el enlace en la columna **Número de artículo**.
    1. En el cuadro de diálogo **Información del producto**, seleccione el enlace en el campo **Número de artículo** para abrir el registro de producto publicado relacionado.
    1. En el panel Acciones, en la pestaña **Plan**, en el grupo **Cobertura**, seleccione **Cobertura de artículos**.
    1. Note que el valor **Mínimo** para el sitio y el almacén que ajustó utilizando el diario de existencias de seguridad publicado ahora se ha actualizado para que coincida con su edición.

## <a name="additional-resources"></a>Recursos adicionales

- [Cumplimiento de existencias de seguridad para los artículos](safety-stock-replenishment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
