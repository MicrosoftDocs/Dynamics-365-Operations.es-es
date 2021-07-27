---
title: Visión general de conversión de costes estándares
description: Este artículo proporciona una visión general del proceso para ayudarle a configurar y a ejecutar una conversión de coste estándar. Los pasos mostrados están pensados para completarse una vez se hayan completado los requisitos previos para una conversión de coste estándar.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "78212"
- intro-internal
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85f2c623255b8fec17acfcf7da7adbb105e921c7
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "6336544"
---
# <a name="standard-cost-conversion-overview"></a>Visión general de conversión de costes estándares

[!include [banner](../includes/banner.md)]

Este artículo proporciona una visión general del proceso para ayudarle a configurar y a ejecutar una conversión de coste estándar. Los pasos mostrados están pensados para completarse una vez se hayan completado los requisitos previos para una conversión de coste estándar. 

Utilice la página **Conversiones de costes estándar** para convertir el modelo de inventario para un lote de artículos seleccionados del enfoque de gestión de costes real al enfoque de coste estándar. El proceso de conversión implica realizar un cierre de inventario como requisito previo, realizando diversos pasos durante un período de transición, definido por una fecha de inicio de transición y una fecha de conversión planificada y, a continuación realizando la conversión y un cierre de inventario asociado.

-   Cierre de inventario antes del período de transición: el cierre de inventario representa un requisito previo, ya que liquida las transacciones abiertas de un artículo con el método de valoración anterior. Durante el período de transición, puede especificar transacciones con fecha anterior, tales como facturas, para que pueda cerrar el período anterior. El cierre de inventario debe ser un día antes de la fecha inicial de la transición para asegurar una clara separación del método de valoración anterior.
-   Pasos de conversión durante el período de transición: use la página **Conversiones de costes estándar** para crear un registro de conversión que también incluya el identificador definido por el usuario para una nueva versión de gestión de costes. Identifique los artículos que requieren conversión y especifique los costes estándar pendientes de los artículos en la nueva versión de gestión de costes. Realice una comprobación de los artículos seleccionados para identificar problemas que podrían impedir la conversión y soluciónelos, y después realice comprobación. Cuando el resultado de las comprobaciones de los artículos sea satisfactorio, cambie el estado del registro de conversión a **Preparado**. En la fecha de conversión planificada, realice la conversión y opcionalmente incluya un cierre de inventario. Los movimientos de inventario de un artículo durante el período de transición se registran y valoran según el modelo de inventario anterior. A continuación, cuando el proceso de conversión se haya completado correctamente, los movimientos de inventario se vuelven a valorar como costes estándar.
-   Cierre de inventario antes de la conversión: el cierre de inventario se puede incluir como parte de la conversión en la fecha de conversión planificada, o bien antes de la conversión como paso independiente.

Una vez completado correctamente el proceso de conversión, el modelo de inventario para cada artículo estará basado el coste estándar, y se habilitará el coste estándar del artículo. Las transacciones de inventario posteriores se valorarán según el coste estándar del artículo. Además, el sistema convierte las transacciones físicas de inventario del artículo para recepciones y emisiones al coste estándar basándose en la fecha de conversión. El sistema también convierte el inventario disponible financiero del artículo al coste estándar, y registra la diferencia en valor como una reevaluación de inventario. Las transacciones que tengan lugar después de la conversión se valoran según el coste estándar del artículo. No puede introducir transacciones con fecha anterior antes de la fecha de conversión, pues es necesario realizar un cierre de inventario un día antes de la fecha de conversión. Una conversión solo puede realizarse si se realizó un cierre de inventario un día antes. Este cierre de inventario no se puede cancelar.

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a>1. Defina un registro de conversión de coste estándar y la versión de gestión de costes asociada
Use la página **Conversiones de costes estándar** para crear un registro de conversión. Puede crear un registro de conversión nuevo una vez completados los registros de conversión existentes. La duración del período de transición planificado se define mediante la fecha de inicio de la transición y la fecha de conversión planificada. Un período de transición planificado puede ser tan breve como un día. Un período de transición planificado ayuda a garantizar que el proceso de conversión tiene bastante tiempo para completar todos sus pasos. Debe realizarse un cierre de inventario un día antes de la fecha de inicio de la transición, para ayudar a garantizar que se completan las liquidaciones antes de iniciar el proceso de conversión. Para asegurarse de que la fecha de inicio de la transición y la fecha de cierre de inventario están correctamente ajustadas, puede cambiar la fecha de inicio de la transición a un día después de un cierre de inventario existente, o bien realizar un cierre de inventario. Al especificar un registro de conversión, también especifica un identificador definido por el usuario para una nueva versión de gestión de costes que contendrá los costes estándar para los artículos convertidos. La versión de gestión de costes se genera automáticamente al guardar el registro de conversión.

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a>2. Revise y cambie la nueva versión de gestión de costes para el registro de conversión
La nueva versión de gestión de costes está dedicada al registro de conversión, como indica el tipo de gestión de costes **Conversión**. La versión de gestión de costes es similar a una versión de gestión de costes para costes estándar y contiene los registros de coste de artículo para artículos asociados con el registro de conversión. La versión de gestión de costes dedicada para un registro de conversión tiene la siguiente configuración, que deber revisar y modificar en las diferentes pestañas según sea necesario.

-   **Tipo de coste:** este campo se debe establecer en **Coste estándar**.
-   **Versión:** el identificador refleja la información que se especifica en el registro de conversión para el id. de la versión de gestión de costes.
-   **Nombre:** de forma predeterminada, el nombre está en blanco. De forma opcional, puede escribir un nombre.
-   **Bloque:** este campo se debe establecer en **No**. Puede especificar registros de costes en la versión de gestión de costes hasta que el estado del registro de conversión cambie a **Preparado**. El estado de **Preparado** indica que se han comprobado los artículos seleccionados y que no deben permitirse los cambios en los registros de costes.
-   **Bloquear activación:** este campo se debe establecer en **Sí**. No se pueden activar manualmente los registros de costes pendientes en la versión de gestión de costes dedicada. La activación tiene lugar cuando se realiza la conversión.
-   **Desde fecha: :** refleja la fecha de conversión planificada que se introduce en el registro de conversión.
-   **Sitio:** deje este campo en blanco, para que se puedan especificar registros de costes para todos los sitios.
-   **Permitir grupo de campos de tipo de precio:** establezca este campo en **Sí**, de manera que solo se puedan especificar registros de precio de coste.
-   **Principio de reserva:** Este campo se establece en **Ninguno**. Cambie el principio de reserva a **Activo** si necesita información de costes que haya sido activada en otras versiones de gestión de costes. Por ejemplo, la información de costes sobre los componentes, categorías de coste y los costes indirectos puede ser necesaria para calcular los costes de los artículos fabricados.
-   **Versión de gestión de costes de reserva:** Deje este campo en blanco.

La información de coste de artículo dentro de la versión de gestión de costes dedicada solo se puede mantener desde la página **Conversiones de costes estándar**. No puede usar las páginas **Configuración de la versión de gestión de costes** o **Mantenimiento de la versión de gestión de costes** para calcular los costes de la versión de gestión de costes durante la conversión. Sin embargo, puede usar estas páginas para mantener la versión de gestión de costes dedicada después de haber completado el proceso de conversión.

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a>3. Identifique los artículos que se convertirán al coste estándar
Use la página **Conversiones de costes estándar** para identificar los artículos individuales que se deben convertir al coste estándar. Puede agregar varios artículos mediante la página **Agregar artículos a la conversión de coste estándar**. En general, debe incluir todos los artículos fabricados en un único registro de conversión para ayudar a garantizar que los costes se calculen correctamente.

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a>4. Especifique o calcule el coste estándar pendiente para cada artículo que se esté convirtiendo
Use la página **Precio de artículo** para especificar costes estándares pendientes dentro de la versión de gestión de costes dedicada para artículos adquiridos y artículos de transferencia. Los registros de coste son específicos del sitio y se deben introducir los costes pendientes de un artículo para cada sitio. Utilice la página **Precio de artículo** para calcular los costes estándar pendientes para artículos fabricados. Los costes pendientes de un artículo fabricado se deben calcular para cada sitio de fabricación, a menos que el sitio represente un sitio de transferencia. En este caso, los costes pendientes deben especificarse manualmente. Algunos artículos pueden tener dimensiones de producto de color, tamaño o configuración. En la página **Conversiones de costes estándar**, la casilla **Usar precio de coste por variante** muestra el coste estándar para cada combinación de dimensiones de producto. Si esta casilla está desactivada, solo debe especificar un coste pendiente para el artículo.

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a>5. Compruebe si hay algún problema en los artículos que se están convirtiendo y, en su caso, resuélvalos.
Use el informe **Comprobaciones de conversión de coste estándar** para identificar problemas para los artículos que se están convirtiendo. Si un artículo no tiene ningún problema, su estado dentro del registro de conversión cambia a **Comprobado**. Si un artículo tiene problemas, debe solucionarlos y volver a ejecutar el informe hasta que su estado cambie a **Comprobado**. Si no puede solucionar los problemas de un artículo, puede eliminar el artículo del registro de conversión y convertirlo más adelante.

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a>6. Cambie el estado del registro de conversión a Preparado
Cuando el estado del registro de conversión se cambia a **Preparado**, el sistema realiza una comprobación final antes de ejecutar una conversión de coste estándar. El estado solo cambia a **Preparado** si se han cumplido las siguientes condiciones:

-   Todos los artículos del registro de conversión tienen un estado de **Comprobado**.
-   Se realizó un cierre de inventario en una fecha anterior en un día a la de inicio de la transición. Para asegurarse de que la fecha de inicio de la transición y la fecha de cierre de inventario están correctamente ajustadas, puede cambiar la fecha de inicio de la transición a un día después de un cierre de inventario existente, o bien realizar un cierre de inventario.

## <a name="7-back-up-the-database-before-conversion"></a>7. Realice una copia de seguridad de la base de datos antes de la conversión
La copia de seguridad le permite restaurar la base de datos si se encuentran errores durante la conversión.

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a>8. Realice la conversión cuando el registro de conversión tenga un estado Preparado
El proceso de conversión requiere que se realice un cierre de inventario en una fecha anterior en un día a la fecha de conversión planificada. Este requisito ayuda a garantizar que no se puedan introducir transacciones con fecha anterior durante el período de transición. Si no se ha realizado aún ningún cierre de inventario, se le preguntará si desea realizarlo como parte del proceso de conversión. El proceso de conversión gestiona un artículo cada vez. Comienza con los artículos que se encuentran más abajo en una estructura de producto, en función del código de nivel bajo del artículo. Cuando un artículo se ha convertido correctamente, se cambia su estado en el registro de conversión a **Convertido**. Si se interrumpe el proceso de conversión, los artículos que no se hayan convertido correctamente tendrán el estado **Convertido**. La correcta finalización del proceso de conversión tiene los siguientes efectos:

-   El estado del registro de conversión cambia de **Preparado** a **Completado** y el estado de cada artículo seleccionado cambia de **Comprobado** a **Convertido**.
-   El grupo de modelos de artículo para artículos convertidos cambia de modo que refleje un nuevo grupo con un modelo de inventario de coste estándar.
-   Los costes estándares para los artículos convertidos se han habilitado en la versión de gestión de costes dedicada.
-   El tipo de coste de la versión de gestión de costes cambia desde **Conversión** hasta **Coste estándar**, y la versión de gestión de costes es ahora como cualquier otra versión de gestión de costes para costes estándar.

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a>9. Valide y concilie los valores de inventario para los artículos convertidos
El informe **Informe de análisis de desviación** le permite analizar la desviación de revalorización y el informe **Valor de inventario** le permite ver el valor de inventario en una fecha específica.

-   Analice las desviaciones de revalorización. Utilice el informe **Informe de análisis de desviación** para ver desviaciones de revalorización de inventario para los artículos convertidos. También puede usar la página **Transacciones de coste estándar** para ver las transacciones de revalorización de inventario para los artículos convertidos que tienen inventario.
-   Analizar el valor de inventario antes de la fecha de inicio de la transición Utilice el informe **Valor de inventario** para ver valores de inventario para los artículos convertidos. Para la opción Fecha final para el informe, use una fecha que sea un día anterior a la fecha de inicio de la transición.
-   Analice el valor de inventario antes de la fecha de conversión. Utilice el informe **Valor de inventario** para ver valores de inventario para los artículos convertidos. Como Fecha final para el informe, use una fecha refleje un día anterior a la fecha de conversión.
-   Analice el valor de inventario en la fecha de conversión. Utilice el informe **Valor de inventario** para ver los valores de inventario en la fecha de conversión. Tanto la Fecha inicial como la Fecha final para el informe deben coincidir con la fecha de conversión. Los criterios de selección de informe deben reflejar los artículos convertidos.
-   Analizar los movimientos de inventario con fecha anterior Utilice el informe **Valor de inventario** para ver movimientos de inventario con fecha anterior que se hayan introducido después de la conversión. Las fechas desde y hasta del informe deben corresponder con la fecha de inicio de la transición y la fecha de conversión menos un día. Los criterios de selección de informe deben reflejar los artículos convertidos. El informe muestra los movimientos de inventario que se realizaron al coste estándar durante el período de transición.


## <a name="additional-resources"></a>Recursos adicionales

[Requisitos previos para la conversión de costes estándar](prerequisites-standard-cost-conversion.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]