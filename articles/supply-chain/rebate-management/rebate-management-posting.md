---
title: Configuración del registro de la administración de devoluciones
description: Este artículo describe cómo configurar datos para perfiles de publicación. Los perfiles de contabilización se utilizan para determinar las entradas de contabilización para las líneas de cálculo de la gestión de devoluciones.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7a519b7153b307bf7d8cc9093572ca2711432970
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873590"
---
# <a name="rebate-management-posting-setup"></a>Configuración de publicación de gestión de devoluciones

[!include [banner](../includes/banner.md)]

Los perfiles de contabilización de administración de devoluciones se utilizan para determinar las entradas de contabilización para las líneas de cálculo de la gestión de devoluciones. Cuando se selecciona un perfil de contabilización en el encabezado del acuerdo, se aplica a todas las líneas del acuerdo.

Esta función funciona en todas las empresas (entidades jurídicas). Puede especificar la empresa a la que se le devengarán las provisiones y a la que pagará las reclamaciones. También puede configurar diferentes cuentas de débito de provisión y cuentas de crédito de cancelación por empresa de publicación de origen.

Para configurar los perfiles de contabilización de la gestión de descuentos para clientes y proveedores, vaya a **Gestión de devoluciones \> Configuración de contabilización de gestión de devoluciones \> Perfiles de contabilización de gestión de devoluciones**. La página **Perfiles de contabilización de gestión de devoluciones** incluye un panel de lista que muestra todos sus perfiles existentes. Puede utilizar los botones del panel de acciones para añadir perfiles a la lista o eliminarlos.

Las secciones restantes de este artículo describen cómo utilizar los campos disponibles al crear o editar un perfil.

## <a name="posting-profile-header"></a>Encabezado de perfil de contabilización

La siguiente tabla describe la configuración que está disponible en la sección de encabezado de cada perfil de contabilización de Gestión de devoluciones.

| Campo | Descripción |
|---|---|
| Perfil de contabilización | Especifique un nombre único para el perfil. |
| Descripción | Especifique una descripción del perfil. |
| Módulo | Seleccione el módulo con el que están asociadas las devoluciones y regalías del perfil (*Cliente* o *Proveedor*). |
| Tipo | Seleccione el tipo de perfil (*Devolución* o *Regalías*). |
| Tipo de pago | <p>Este campo determina el formato de la salida de devolución contabilizada.<p><p>Cuando el campo **Tipo** está configurado en *Devolución*, los siguientes valores están disponibles:</p><ul><li>*Pagar con proveedores*: cuando contabiliza la devolución de un cliente, se crea una factura de proveedor para el proveedor de devoluciones que está configurado en el cliente de devolución. Cuando contabiliza una devolución de un proveedor, se crea una factura de proveedor para la cuenta de devolución del proveedor.</li><li>*Deducciones de clientes*: cuando contabiliza la devolución, se crea un diario de deducción del cliente para el cliente de la devolución.</li><li>*Deducciones de clientes con impuestos*: cuando contabiliza la devolución, se crea una factura de servicios para el cliente de la devolución.</li><li>*Gastos comerciales*: cuando contabiliza la devolución, se crea un diario de deducción del cliente para el cliente de la devolución.</li><li>*Informe*: cuando contabiliza la devolución, se crea un diario de deducción del cliente para el cliente de la devolución.</li></ul><p>Cuando el campo **Tipo** está configurado en *Regalías*, los siguientes valores están disponibles:</p><ul><li>*Pagar con proveedores*: cuando contabiliza la devolución, se crea una factura de proveedor para la cuenta de devolución del proveedor.</li><li>*Informes*: cuando contabiliza la devolución, se crea una factura de proveedor para la cuenta de devolución del proveedor.</li></ul><p>Para obtener más información, consulte la sección [Tipos de pago](#payment-types) a continuación. |
| Empresa | Seleccione la empresa (entidad jurídica) a la que se le devengarán las provisiones y a la que pagará las reclamaciones. |

### <a name="payment-types"></a>Tipos de pago

La siguiente tabla resume cómo las distintas configuraciones del campo **Tipo de pago** afecta dónde se registran los pagos. Los pagos se pueden contabilizar en una cuenta de cliente, cuenta de proveedor o cuenta de remesas, según la transacción de destino y el tipo de devolución.

| Tipo de pago | Tipo de transacción de destino | Tipo de devolución | Pago a (cuenta de factura) |
|---|---|---|---|
| Pagar mediante Proveedores | Diario de facturas del proveedor | Devolución de clientes | Cuenta de proveedor de remesas del cliente |
| Pagar mediante Proveedores | Diario de facturas del proveedor | Regalías del cliente | Cuenta del proveedor |
| Pagar mediante Proveedores | Diario de facturas del proveedor | Devolución de proveedor | Cuenta del proveedor |
| Deducciones de clientes | Diario | Devolución de clientes | Cuenta de cliente |
| Deducciones de clientes de facturas de impuestos | Factura de servicios | Devolución de clientes | Cuenta de cliente |
| Gastos comerciales | Diario | Devolución de clientes | Cuenta de cliente |
| Notificación | Diario | Devolución de clientes | Cuenta de cliente |
| Notificación | Diario de facturas del proveedor | Regalías del cliente | Cuenta del proveedor |
| Notificación | Diario de facturas del proveedor | Devolución de proveedor | Cuenta del proveedor |

> [!NOTE]
> Tenga en cuenta los siguientes puntos cuando configure [Ofertas de gestión de devoluciones](rebate-management-deals.md):
>
> - Para acuerdos donde el campo **Reconciliar por** está configurado en *Acuerdo*, no puede utilizar la cuenta de oferta dinámica durante la publicación. Debe utilizar una cuenta de cliente o proveedor específica.
> - Para ofertas donde el campo **Reconciliar por** está configurado en *Línea*, puede utilizar un perfil de contabilización que se compensa a una cuenta de oferta dinámica en la línea de oferta, porque el cliente o proveedor se establece por línea de oferta.

## <a name="posting-fasttab"></a>Ficha desplegable contabilización

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **Contabilización** de cada perfil de contabilización de Gestión de devoluciones.

| Campo | Descripción |
|---|---|
| Tipo de crédito | Seleccione si acreditar una cuenta contable o un cliente. Si el campo **Tipo de pago** en el encabezado está configurado en *Deducciones de clientes de facturas de impuestos*, este campo se establece en *Cuenta contable*. Para reembolsos de proveedores, este campo se establece en *Cuenta contable*. |
| Cuenta de cŕedito | Seleccione la cuenta en la que se contabilizan los importes de crédito cuando se realizan las provisiones de devolución. Esta cuenta también se utilizará como cuenta de contrapartida cuando se registre la devolución para acreditar al proveedor. |
| Nombre del diario<br>(En la sección **Aprovisionar**) | Seleccione el nombre del diario que se utilizará para registrar la provisión publicada. |
| Tipo | Seleccione si contabiliza la devolución una cuenta contable o a un cliente o un proveedor. Si el campo **Tipo de pago** en el encabezado está configurado en *Deducciones de clientes de facturas de impuestos*, este campo se establece en *Cliente / Proveedor*. |
| Usar cuenta de origen | <p>Seleccione uno de los siguientes valores:</p><ul><li>*Cuenta fija*: si selecciona este valor, debe especificar una cuenta en el campo **Cuenta de devolución**.</li><li>*Cuenta de línea de acuerdo*: utilice la cuenta de cliente o proveedor que se especifica en la línea de devolución. Puede seleccionar este valor solo para acuerdos en los que el campo **Reconciliar por** está configurado en *Línea* y líneas de acuerdo donde el campo **Código de cuenta** está configurado en *Tabla*. No se aplica a los perfiles de publicación de regalías de los clientes ni a los reembolsos de proveedores que se basan en pedidos de ventas.</li></ul> |
| Cuenta de devolución | La cuenta en la que se contabilizarán los gastos de devoluciones reales. |
| Nombre del diario<br>(En el grupo de campos **Gestión de reembolsos**) | Seleccione el nombre del diario que se utilizará para registrar una nota de crédito por el monto de la devolución para el cliente o proveedor. Esta campo no está disponible cuando el campo **Tipo de pago** en el encabezado está configurado en *Deducciones de clientes de facturas de impuestos*. Para reembolsos de clientes, los nombres de diario del tipo de diario *Diario* estará disponible el tipo de revista. Para regalías de clientes y reembolsos de proveedores, los nombres de diario del *Registro de facturas de proveedores* estará disponible el tipo de revista. |
| Grupo de impuestos de artículos | Especifique si la devolución está sujeta a impuestos. |
| Nombre del diario<br>(En el grupo de campos **Cancelar**) | Si la devolución que se registra no es igual a la provisión, se puede cancelar la diferencia. Seleccione el nombre del diario que se utilizará para registrar la cancelación. |

## <a name="posting-by-company-fasttab"></a>Ficha desplegable de contabilización por empresa

La ficha desplegable **Contabilización por empresa** de cada perfil de contabilización de gestión de devoluciones le permite especificar la cuenta de registro que utiliza cada empresa (entidad jurídica) en la cuadrícula.

Use los botones de la barra de herramientas para agregar compañías a la cuadrícula o eliminarlas. Cada vez que agregue una fila a la cuadrícula, use el campo **Empresa** para especificar la entidad jurídica para esa fila. El campo **Nombre** se establecerá automáticamente.

Seleccione la fila para cada empresa y luego introduzca la siguiente información usando los campos debajo de la cuadrícula:

- **Tipo de débito**: seleccione si el débito es para una cuenta contable o un proveedor. Para reembolsos de clientes y regalías, este campo se establece en *Cuenta contable*.
- **Cuenta de debito**: introduzca la cuenta en la que se contabiliza el monto del débito cuando se realizan las provisiones de devolución.
- **Cuenta principal**: seleccione la cuenta principal para cancelaciones.
