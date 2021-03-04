---
title: Crear un libro de trabajo de Excel para editar transacciones minoristas
description: En este tema se describe cómo crear un libro de Excel para poder editar transacciones minoristas en Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 73a3387d1e7251168002ff683b5b58e0c82a620c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965386"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>Crear un libro de trabajo de Excel para editar transacciones minoristas

[!include [banner](../includes/banner.md)]

En este tema se describe cómo crear un libro de Excel para poder editar transacciones minoristas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Existe una plantilla de Excel predefinida a la que los clientes pueden obtener acceso desde diferentes partes del sistema y utilizar para editar y auditar transacciones minoristas. Sin embargo, los clientes también pueden crear un libro de Excel personalizado para este propósito.

## <a name="create-and-configure-an-excel-workbook"></a>Crear y configurar un libro de Excel

Para crear y configurar un libro de Excel para que pueda editar transacciones minoristas, siga estos pasos.

1. Abra Excel y cree un libro en blanco.
1. En la pestaña **Insertar**, seleccione **Mis complementos**.
1. En el panel derecho, seleccione el vínculo **Agregar información del servidor**.
1. Escriba la dirección URL del servidor y luego seleccione **Aceptar**.
1. Si recibe un mensaje de error "No se encontraron registros de applet", siga estos pasos para resolver el problema:

    1. En Commerce, vaya a **Administración del sistema \> Configuración \> Parámetros de aplicación de Office**.
    1. En la ficha desplegable **Parámetros de aplicación**, seleccione **Inicializar parámetros de aplicación**.
    1. En el cuadro de mensaje de confirmación, seleccione **Aceptar**.
    1. En la ficha desplegable **Applets registrados**, seleccione **Inicializar registro de applet**.
    1. Repita los tres pasos anteriores según sea necesario.

1. Seleccione **Diseño** y, a continuación, **Agregar tabla**.
1. En función de los datos que deben modificarse, seleccione las entidades que se deben agregar al libro de Excel para su edición. Utilice la siguiente tabla como referencia.

    | Tipo de transacción | Entidades de datos que se usarán |
    |------------------|----------------------|
    | Transacciones de pago al contado sin entrega a domicilio, Pedidos en línea, Pedidos de clientes asincrónicos, Ofertas de clientes asincrónicas | Transacción (auditable), Transacción de ventas (auditable), Transacciones de pago (auditables), Transacciones de impuestos (auditables), Transacciones de descuento (auditables), Transacciones de cargos (auditables) |
    | Ingreso bancario | Transacción (auditable), Transacciones de forma de pago bancarias (auditables) |
    | Ingreso en caja fuerte | Transacción (auditable), Transacciones de forma de pago en caja fuerte (auditables) |
    | Declaración por forma de pago | Transacción (auditable), Transacciones de declaración por forma de pago (auditables) |
    | Ingresos, gastos | Transacción (auditable), Transacciones de ingresos/gastos (auditables), Transacciones de pago (auditables) |
    | Declarar importe inicial, Supresión de forma de pago, Entrada flotante, Cambio de la forma de pago, Pago de factura, Depósito del cliente | Transacción (auditable), Transacciones de pago (auditables) |

    > [!NOTE]
    > Es importante que agregue solo una entidad de datos a cada libro de Excel. Además, todos los campos que están marcados con un símbolo de llave deben agregarse al libro correspondiente.

1. Una vez configurado el libro, aplique los filtros necesarios. Asegúrese de aplicar los mismos filtros a todas las hojas de cálculo del archivo. Evite cargar grandes cantidades de datos en el archivo de Excel. De lo contrario, el rendimiento podría verse afectado y Excel y su sistema podrían ralentizarse. Recomendamos que use siempre "Empresa" y "Número de extracto" o "Número de transacción" como filtros para su archivo.
1. Una vez configurados los filtros, seleccione **Actualizar** para cargar los datos.
1. Edite los datos necesarios y luego publíquelos. Si el botón **Publicar** no está disponible, algunos campos clave probablemente no se agregaron al libro de Excel.

## <a name="additional-resources"></a>Recursos adicionales

[Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio](edit-cash-trans.md)

[Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea](edit-order-trans.md)

[Editar dimensiones financieras para transacciones minoristas](edit-financial-dim.md)

[Agregar campos a un libro de trabajo de Excel para editar transacciones minoristas](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]