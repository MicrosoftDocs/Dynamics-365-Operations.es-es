---
title: Editar y auditar transacciones de tienda
description: En este tema se describe la funcionalidad de editar y auditar transacciones de tienda.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: 97211ee36dbaa704d3a967e9b742ff1cae708707
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004398"
---
# <a name="edit-and-audit-retail-store-transactions"></a>Editar y auditar transacciones de tienda

[!include [banner](includes/banner.md)]



Los clientes de Dynamics 365 Commerce usan aplicaciones de punto de venta (PDV) de primera entidad así como de terceros. Con la aplicación de PDV de primera entidad, las transacciones de tienda se incluyen en Headquarters desde los canales a través de un proceso por lotes. Con aplicaciones de terceros, las transacciones se incluyen en Headquarters mediante la integración. En ambos casos, después de que las transacciones se incluyan en Headquarters, se debe ejecutar un proceso de comprobación de coherencia que ejecute varias validaciones en las transacciones para que solo las transacciones validadas correctamente se incluyan en el extracto que se registrará en Headquarters. 

Las transacciones de Commerce producen un error en la validación por varios motivos. Por ejemplo, un error en el código de integración o un error en la aplicación de PDV puede producir datos incoherentes, o un error de usuario, como la eliminación de un producto después de sincronizarse al canal o el cierre de un período fiscal sin registrar las transacciones para ese período puede producir datos incoherentes.

Aunque estas transacciones se marcan y excluyen de los extractos, las transacciones pueden interrumpir el proceso diario de un cliente de registrar las ventas diarias en las operaciones financieras.

En Commerce, podrá editar las transacciones comerciales específicas que causaron un error en la validación durante el mantenimiento de la auditoría de todos los cambios. 

## <a name="edit-and-audit-transactions"></a>Edición y auditar transacciones

En Retail versión 10.0.5, las transacciones de pago al contado sin entrega al domicilio como ventas y devoluciones son las únicas transacciones que se pueden editar. No se admite la edición de pedidos de cliente o en línea. En Retail versión 10.0.6 y posterior, también se admite la edición de transacciones de gestión de efectivo.

1. Instale el complemento de Excel de Dynamics.

2. Vaya al espacio de trabajo **Operaciones financieras de tienda**. La ventana **Errores de validación de transacciones** ofrece una vista previamente filtrada del formulario de transacción que generó un error en una o más de las reglas de validación.
 
3. Abra el formulario. Haga clic en el registro que generó un error en la validación, haga clic en **Complemento de Office** y, a continuación, en **Editar transacción seleccionada**. Se abre un archivo de Excel con los detalles de la transacción seleccionada, con las siguientes hojas de cálculo:

    - Líneas: esta hoja de cálculo tiene las líneas de productos y encabezado y los datos relacionados para la transacción.
    - Pagos: esta hoja de cálculo tiene los detalles de las líneas de pago para la transacción.
    - Descuentos: esta hoja de cálculo tiene los detalles relacionados con descuentos para la transacción.
    - Impuestos: esta hoja de cálculo tiene los detalles relacionados con impuestos para la transacción.
    - Gastos: esta hoja de cálculo tiene los detalles relacionados con gastos para la transacción.

4. En el archivo de Excel, modifique los campos adecuados y, a continuación, cargue los datos de nuevo en Headquarters usando la funcionalidad de publicación del complemento de Excel de Dynamics. Una vez publicados, los cambios se reflejarán en el sistema. Durante la publicación, no se realizará ninguna validación en los cambios que hagan los usuarios.

5. Para ver una traza de auditoría completa de los cambios, haga clic en **Ver traza de auditoría** en el encabezado **Transacción comercial** para los cambios de nivel de encabezado y en la sección y el registro pertinentes de la página de transacción adecuada. Por ejemplo, todos los cambios relativos a las líneas de ventas serán visibles en la página **Transacciones de venta**, los cambios relativos a los pagos serán visibles en la página **Transacciones de pago**, etc. Los detalles de auditoría que se mantienen para los cambios son los siguientes:

   - Fecha y hora de modificación
   - Campo 
   - Valor anterior
   - Nuevo valor
   - Modificado por

6. Después de que se realicen y se publiquen los cambios, ejecute la opción **Validar transacciones de la tienda** de nuevo para validar que los cambios realizados son coherentes y válidos.

> [!NOTE]
> Solo puede editar las transacciones que generaron un error de validación. Si desea editar las transacciones que pasaron la validación, cambie el estado de la validación de la transacción que desee cambiar a **Error** o **Ninguno** y, a continuación, podrá editarlo. 


## <a name="bulk-edit-transactions"></a>Edición en masa de transacciones

En Retail versión 10.0.6 y posterior, se admite la opción de edición masiva de transacciones en un nivel de extracto. 

1. Use el complemento de Excel para abrir un extracto que tenga transacciones que desee modificar con los pasos del 1 al 3 anteriores.

2. Elija una de las opciones siguientes:

    - **Editar transacciones de pago al contado sin entrega a domicilio**. Esta opción le permite editar todas las transacciones de pago al contado sin entrega a domicilio incluidas en el extracto. Las siguientes hojas de cálculo Excel están disponibles.
    
       - **Transacción**: esta hoja de cálculo tiene toda la información de nivel de encabezado para las transacciones de ventas.
       - **Transacción de venta**: esta hoja de cálculo tiene toda la información de nivel de líneas para las transacciones de ventas.
       - **Transacciones de pago**: esta hoja de cálculo tiene toda la información de líneas de pago para las transacciones de ventas.
       - **Transacciones de descuento**: esta hoja de cálculo tiene toda la información de líneas de pago para las transacciones de ventas.
       - **Transacciones de impuestos**: esta hoja de cálculo tiene toda la información de líneas de impuestos para las transacciones de ventas.
       - **Transacciones de gastos**: esta hoja de cálculo tiene toda la información de líneas de gastos para las transacciones de ventas.

    - **Editar transacciones de administración de flujos de efectivo**. Esta opción le permite editar todas las transacciones de administración de flujos de efectivo incluidas en el extracto. Las siguientes hojas de cálculo Excel están disponibles.
     
       - **Transacción**: esta hoja de cálculo tiene toda la información de nivel de encabezado para las transacciones de administración de flujos de efectivo.
       - **Transacciones bancarias de forma de pago realizadas**: esta hoja de cálculo tiene todos los detalles de transacción de ingreso bancario.
       - **Transacciones de forma de pago en caja fuerte**: esta hoja de cálculo tiene todos los detalles de transacción de ingreso seguro.
       - **Declaración por forma de pago**: esta hoja de cálculo tiene todos los detalles de declaración por forma de pago.
       - **Transacción de ingresos y gastos**: esta hoja de cálculo tiene todos los detalles de línea de transacción de ingresos y gastos.
       - **Transacciones de pago**: esta hoja de cálculo tiene toda la información relacionada con pagos para la operación **Pagar factura** así como la transacción de ingresos y gastos.

3.  Las validaciones no se realizan al publicar transacciones editadas de forma masiva. Debe asegurarse que todas las ediciones son precisas y de que se mantiene la fidelidad de los datos en todas las hojas de cálculo. Por ejemplo, si desea cambiar la fecha de transacción para administrar los escenarios donde el período fiscal o de inventario para las transacciones abiertas está cerrado, debe cambiar la fecha en todas las hojas de cálculo de Excel que tienen la columna **Fecha de negocio**. Para validar transacciones después de que se hayan editado, puede usar la página **Revalidar transacciones** en la página **Extractos**.
