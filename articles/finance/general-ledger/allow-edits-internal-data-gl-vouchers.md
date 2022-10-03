---
title: Permitir ediciones en datos internos para asientos de contabilidad general
description: Este artículo proporciona información sobre cómo editar datos internos en comprobantes del libro mayor.
author: kweekley
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 6e346c6ff881d3a33743196b45247493fd19ed1d
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573261"
---
# <a name="allow-edits-to-internal-data-on-general-ledger-vouchers"></a>Permitir ediciones en datos internos para asientos de contabilidad general

[!include[banner](../includes/banner.md)]


Cuando contabiliza asientos contables en el libro mayor, el campo **Descripción** se utiliza a menudo para almacenar notas internas o documentación. Si la información es incorrecta, puede causar confusión y dificultar el cierre del período. Esta característica le permite al gerente de contabilidad o al supervisor de contabilidad corregir errores editando el campo **Descripción** en los comprobantes contabilizados en el libro mayor.

Los cambios en los comprobantes registrados en el libro mayor se limitan a los datos de naturaleza interna. Esta característica nunca le permitirá editar datos como montos, fechas de publicación, cuentas contables y la moneda de la transacción. Los cambios en esos datos afectarán el informe externo de los estados financieros y deben realizarse solo a través de nuevos comprobantes del libro mayor.

> [!NOTE]
> Para la versión 10.0.29 de Dynamics 365 Finance, esta función se limita a las ediciones en el campo **Descripción**.

## <a name="edit-internal-data-on-general-ledger-vouchers"></a>Editar datos internos para asientos de contabilidad general

Antes de que se puedan editar los datos internos de los comprobantes del libro mayor, debe habilitar la característica **Permitir ediciones de datos internos en comprobantes del libro mayor** en el espacio de trabajo **Gestión de características**.
Una vez habilitada la función, el usuario que editará los comprobantes registrados debe asignarse al rol de Gerente de contabilidad o Supervisor de contabilidad. También puede agregar permisos a otros roles, personalizando los roles de seguridad.

El proceso de edición solo está permitido desde la página de transacciones de Vales.

1. Vaya a **Contabilidad general** > **Consultas e informes** > **Transacciones de asiento**.
2. En el cuadro de diálogo **SysQuery**, ingrese los criterios de búsqueda para seleccionar comprobantes.
3. Seleccione las líneas de los comprobantes que desea editar y luego seleccione **Editar cupón** > **Editar datos de cupones internos**.

    [![Página de transacciones de asiento.](./media/voucher-transactions-page.png)](./media/voucher-transactions-page.png)
    
En la página **Editar datos de comprobantes internos**, se muestran los siguientes datos para cada línea que seleccionó:
  
  - Cuenta contable
  - Nombre de la cuenta
  - Comprobante
  - Descripción actual
  - Nueva descripción

    [![Asiento del diario.](./media/edit-internal-voucher-data.png)](./media/edit-internal-voucher-data.png)
    
> [!NOTE]
> Solo el campo **Nueva descripción** se puede editar. Por defecto, el valor coincide con el valor del campo **Descripción actual**, para que pueda corregir rápidamente pequeños errores en la descripción.

4. Modifique el campo **Nueva descripción** en cada fila, o elimine la descripción de cada fila.

   Alternativamente, si se deben actualizar varias filas con el mismo valor, siga estos pasos:

      1. Seleccione las filas para editar y luego seleccione **Actualización masiva de registros seleccionados**.
      2. En el campo **Campo a editar**, seleccione el campo para editar. Actualmente, la búsqueda incluye solo el campo **Nueva descripción**.
      3. En el campo **Nuevo valor**, especifique una nueva descripción.
      4. Seleccione **Actualizar**. Todos los registros seleccionados se actualizan con el nuevo valor.

      [![Cuadro de diálogo Actualizar masivamente los registros seleccionados](./media/bulk-update-selected-records.png)](./media/bulk-update-selected-records.png)
    
5. En el campo **Motivo de la edición**, ingrese una nota para explicar por qué se realizó la edición. Esta nota se muestra en la página **Pista de auditoría de ediciones de comprobantes**.

   Se pueden realizar varias ediciones en el mismo comprobante y se realizará un seguimiento de cada edición.

## <a name="audit-trail-of-voucher-edits"></a>Traza de auditoría de ediciones de asientos

Se mantiene un seguimiento de auditoría específicamente para realizar un seguimiento de los cambios que se realizan a través de esta función. Puede acceder a la pista de auditoría de las ediciones de comprobantes de dos maneras:

  - Vaya a **Contabilidad general** > **Consultas e informes** > **Transacciones de asiento**. En la página **Consultas sobre vales**, seleccione **Editar cupón** > **Pista de auditoría de ediciones de comprobantes**. La pista de auditoría se muestra solo para el registro de comprobante seleccionado. 
   
    Al abrir la consulta de esta manera, puede concentrarse en todas las ediciones que se realizaron en un solo registro de comprobante.
  
  - Vaya a **Contabilidad general** > **Tareas periódicas** > **Pista de auditoría de ediciones de comprobantes**. En el cuadro de diálogo, ingrese los criterios para especificar los comprobantes para los que desea ver el registro de auditoría de ediciones. Para ver la pista de auditoría de todos los comprobantes, deje los criterios en blanco y seleccione **Aceptar**. 
    
    Al abrir la consulta de esta manera, puede filtrar las ediciones que se realizaron en una fecha específica o por un usuario específico.

La página **Pista de auditoría de ediciones** muestra la siguiente información:

- **Fecha y hora de creación** – La fecha y hora de la edición.
- **Motivo de la edición** – La razón por la que el usuario ingresó para la edición.
- **Creado por**: el usuario que hizo la edición.

Para ver los detalles de cada registro de auditoría, profundice en el valor **Fecha y hora de creación**. La página **Ver las propiedades del cupón editado** muestra la misma información que la página de edición original, incluida la descripción anterior y la descripción actualizada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
