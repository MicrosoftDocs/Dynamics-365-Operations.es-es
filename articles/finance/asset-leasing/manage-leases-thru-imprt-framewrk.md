---
title: Gestionar arrendamientos a través del marco de importación de arrendamientos
description: Este tema explica cómo utilizar el marco de importación de arrendamientos para ajustar varios arrendamientos al mismo tiempo.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 26fb195ff18dc0c86d3546b782265043c2c78bf4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819803"
---
# <a name="manage-leases-through-the-lease-import-framework"></a>Gestionar arrendamientos a través del marco de importación de arrendamientos

[!include [banner](../includes/banner.md)]

Este tema explica cómo utilizar el marco de importación de arrendamientos para ajustar varios arrendamientos en un solo paso. Al usar esta capacidad, puede ahorrar tiempo y también puede garantizar ajustes más precisos al reducir la posibilidad de errores humanos. Además, esta capacidad puede conectar Microsoft Dynamics 365 Finance con entidades de datos externas para cargar datos de manera eficiente.

Las siguientes entidades de datos se pueden utilizar para integrar el arrendamiento de activos con sistemas externos:

- Almacenamiento provisional de arrendamiento
- Almacenamiento provisional de contrato de pago
- Almacenamiento provisional de contrato del arrendatario en un arrendamiento de capital

Puede utilizar el proceso de importación para ajustar un arrendamiento, actualizar información no financiera o agregar nuevos arrendamientos. Puede ver y editar los datos de arrendamiento antes de importarlos.

El sistema puede ejecutar los siguientes tres procesos a través del conjunto de aplicaciones de importación de arrendamientos.

| Tipo de proceso  | Descripción |
|---------------|-------------|
| Agregar registro    | Los arrendamientos migrados que tienen este tipo de proceso crean un arrendamiento en el sistema. La programación de pagos debe confirmarse manualmente y la entrada de diario de reconocimiento inicial debe registrarse manualmente después de la migración. |
| Actualizar registro | Los arrendamientos migrados que tienen este tipo de proceso actualizan los valores de campo para los arrendamientos que ya están en el sistema. Solo los campos que se han seleccionado en la página **Actualizar la selección de campos** se actualizan. Se recomienda seleccionar campos no financieros en la página **Actualizar selección de campos**, porque este tipo de proceso no ajusta el arrendamiento. |
| Ajustar registro | Los arrendamientos migrados que tienen este tipo de proceso ajustan el arrendamiento. Este ajuste provoca una modificación del arrendamiento financiero. Una vez que se procesa el arrendamiento, el sistema crea una nueva programación de pago utilizando los nuevos datos del paquete de aplicaciones de importación de arrendamientos. El sistema no confirma la programación de pagos ni contabiliza el movimiento del diario de ajuste. |

Después de cargar la información a través del espacio de trabajo **Administración de datos**, abra la página **Importar encabezado** (**Arrendamiento de activos \> Marco de importación de arrendamientos \> Importar encabezado**). Esta página enumera todas las importaciones de las tres entidades de datos que se enumeraron anteriormente.

Para ver los datos de almacenamiento provisional del arrendamiento antes de ejecutar el procesamiento, seleccione **Datos de almacenamiento provisional**.

La función de comparación le permite comparar un registro que está importando con el registro correspondiente que ya está en su sistema. Para comparar un registro de arrendamiento individual, seleccione un arrendamiento y luego seleccione **Comparar**. Debe completar este paso para generar un informe **Diferencias** antes de migrar los registros de arrendamiento. La función Comparar compara los valores de los datos de almacenamiento provisional con los valores de los arrendamientos que se encuentran actualmente en el sistema.

> [!NOTE]
> La función Comparar no funciona para arrendamientos que tienen el tipo de proceso **Agregar registro**, porque no hay nada que comparar con ese arrendamiento.
>
> Para comparar varios arrendamientos al mismo tiempo, vaya a **Arrendamiento de activos \> Marco de importación de arrendamientos \> Periódico \> Comparar** y seleccione **Comparar**.

Para cada entidad, puede ver las diferencias entre lo que hay actualmente en el sistema y lo que está en las tablas de almacenamiento provisional. Para cada entidad en las tablas de almacenamiento provisional, seleccione **Ver diferencias**. El cuadro de diálogo que aparece muestra el valor actual y el valor de almacenamiento provisional propuesto.

También puede actualizar el valor de almacenamiento provisional cambiándolo en la columna **Nuevo valor** y luego seleccionando **Actualizar almacenamiento provisional**.

Puede validar los arrendamientos para asegurarse de que los registros se puedan incorporar al sistema sin introducir errores. Antes de que se migre un registro de arrendamiento, el sistema ejecuta varias validaciones para garantizar que el registro se importe correctamente. Para validar un arrendamiento individual, seleccione **Validar**.

> [!NOTE]
> Para validar varios arrendamientos al mismo tiempo, vaya a **Arrendamiento de activos \> Marco de importación de arrendamientos \> Periódico \> Validar** y seleccione **Comparar**.

Para procesar un arrendamiento individual, seleccione **Migrar registros de arrendamiento** en la página **Importar encabezado**. Cuando se migra un arrendamiento, el sistema realiza la acción que se especifica en el campo **Tipo de proceso**.

> [!NOTE]
> Para validar varios arrendamientos al mismo tiempo, vaya a **Arrendamiento de activos \> Marco de importación de arrendamientos \> Periódico \> Validar** y seleccione **Comparar**.

Después de comparar los arrendamientos, puede generar un informe para ver las diferencias para cada arrendamiento que se incluye en el id. de importación. Para generar el informe de un arrendamiento, seleccione ese arrendamiento en los datos de almacenamiento provisional y luego seleccione **Comparar y ver informe \> Informe de diferencias**.

> [!NOTE]
> Para validar varios arrendamientos al mismo tiempo, vaya a **Arrendamiento de activos \> Conultas e informes \> Informe de diferencias** y seleccione **Comparar**.

## <a name="set-up-update-fields"></a>Configurar la actualización de campos

Si está utilizando el marco de importación de arrendamientos para actualizar arrendamientos y el tipo de proceso es **Actualizar registro**, puede seleccionar campos específicos a actualizar.

1. Vaya a **Arrendamiento de activos \> Marco de importación de arrendamientos \> Configurar \> Actualizar selección de campos**.
2. En la página que aparece, seleccione los campos a actualizar y luego seleccione la flecha verde para moverlos a la lista **Campos seleccionados**. Solo los campos de la lista **Campos seleccionados** se pueden actualizar utilizando el paquete de aplicaciones de importación de arrendamiento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]