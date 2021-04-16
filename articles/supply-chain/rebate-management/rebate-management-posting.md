---
title: Configuración de publicación de gestión de devoluciones
description: Este tema describe cómo configurar datos para perfiles de publicación. Los perfiles de contabilización se utilizan para determinar las entradas de contabilización para las líneas de cálculo de la gestión de devoluciones.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: e79feb567a48d08a9063bf20cface3c5c7fe8ecc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831755"
---
# <a name="rebate-management-posting-setup"></a>Configuración de publicación de gestión de devoluciones

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Los perfiles de contabilización de administración de devoluciones se utilizan para determinar las entradas de contabilización para las líneas de cálculo de la gestión de devoluciones. Cuando se selecciona un perfil de contabilización en el encabezado del acuerdo, se aplica a todas las líneas del acuerdo.

Esta función funciona en todas las empresas (entidades jurídicas). Puede especificar la empresa a la que se le devengarán las provisiones y a la que pagará las reclamaciones. También puede configurar diferentes cuentas de débito de provisión y cuentas de crédito de cancelación por empresa de publicación de origen.

Para configurar los perfiles de contabilización de la gestión de descuentos para clientes y proveedores, vaya a **Gestión de devoluciones \> Configuración de contabilización de gestión de devoluciones \> Perfiles de contabilización de gestión de devoluciones**. La página **Perfiles de contabilización de gestión de devoluciones** incluye un panel de lista que muestra todos sus perfiles existentes. Puede utilizar los botones del panel de acciones para añadir perfiles a la lista o eliminarlos.

Las secciones restantes de este tema describen cómo utilizar los campos disponibles al crear o editar un perfil.

## <a name="posting-profile-header"></a>Encabezado de perfil de contabilización

La siguiente tabla describe la configuración que está disponible en la sección de encabezado de cada perfil de contabilización de Gestión de devoluciones.

| Campo | Descripción |
|---|---|
| Perfil de contabilización | Especifique un nombre único para el perfil. |
| Descripción | Especifique una descripción del perfil. |
| Módulo | Seleccione el tipo de devoluciones y regalías al que está asociado el perfil (*Cliente* o *Proveedor*). |
| Tipo | Seleccione el tipo de perfil (*Devolución* o *Regalías*). |
| Tipo de pago | <p>Este campo determina el formato de la salida de devolución contabilizada.<p><p>Cuando el campo **Tipo** está configurado en *Devolución*, los siguientes valores están disponibles:</p><ul><li>*Ninguno*: no hay un tipo de contabilización predeterminada. Por lo tanto, debe definir el tipo cuando realice el procesamiento.</li><li>*Pagar con proveedores*: cuando contabiliza la devolución, se crea una factura de proveedor para el proveedor de remesas que está configurado en el cliente de devolución.</li><li>*Deducciones de clientes*: cuando contabiliza la devolución, se crea un diario de deducción del cliente para el cliente de la devolución.</li><li>*Deducciones de clientes con impuestos*: cuando contabiliza la devolución, se crea una factura de servicios para el cliente de la devolución.</li><li>*Gastos comerciales*: cuando contabiliza la devolución, se crea un diario de deducción del cliente para el cliente de la devolución.</li><li>*Informe*: cuando contabiliza la devolución, se crea un diario de deducción del cliente para el cliente de la devolución.</li></ul><p>Cuando el campo **Tipo** está configurado en *Regalías*, los siguientes valores están disponibles:</p><ul><li>*Ninguno*: no hay un tipo de contabilización predeterminada. Por lo tanto, debe definir el tipo cuando realice el procesamiento.</li><li>*Pagar con proveedores*: cuando contabiliza la devolución, se crea una factura de proveedor para la cuenta de devolución del proveedor.</li><li>*Informes*: cuando contabiliza la devolución, se crea una factura de proveedor para la cuenta de devolución del proveedor.</li></ul><p>Para obtener más información, consulte la sección [Tipos de pago](#payment-types) a continuación. |
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
> - Para ofertas donde el campo **Reconciliar por** está configurado en *Línea*, puede utilizar un perfil de contabilización que se compensa a una cuenta de oferta dinámica en la línea de oferta, porque el cliente se establece por línea de oferta.

## <a name="posting-fasttab"></a>Ficha desplegable contabilización

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **Contabilización** de cada perfil de contabilización de Gestión de devoluciones.

| Campo | Descripción |
|---|---|
| Tipo de crédito | Seleccione si acreditar una cuenta contable, un cliente o un proveedor. |
| Cuenta de cŕedito | La cuenta en la que se contabilizan los importes de crédito cuando se realizan las provisiones de devolución. Esta cuenta también se utilizará como cuenta de débito cuando se registre la devolución para acreditar al cliente. |
| Nombre del diario<br>(En la sección **Aprovisionar**) | Seleccione el nombre del diario que se utilizará para registrar la provisión publicada. |
| Tipo | Seleccione si contabiliza la devolución una cuenta contable o a un cliente o un proveedor. Si el campo **Tipo de pago** en el encabezado está configurado en *Deducciones de clientes de facturas de impuestos*, este campo se establece en *Cliente / Proveedor*. |
| Usar cuenta de origen | <p>Seleccione uno de los siguientes valores:</p><ul><li>*Ninguna*: si selecciona este valor, debe especificar una cuenta en el campo **Cuenta de devolución**.</li><li>*Cuenta de acuerdo*: utilice la cuenta de cliente o proveedor que se especifica en la línea de devolución. Puede seleccionar este valor solo para acuerdos en los que el campo **Reconciliar por** está configurado en *Línea* y líneas de acuerdo donde el campo **Código de cuenta** está configurado en *Tabla*. No se aplica a los perfiles de publicación de regalías de los clientes.</li></ul> |
| Cuenta de devolución | La cuenta en la que se contabilizarán los gastos de devoluciones reales. |
| Nombre del diario<br>(En la sección **Gestión de devoluciones**) | Seleccione el nombre del diario que se utilizará para registrar una nota de crédito por el monto de la devolución para el cliente. Esta campo no está disponible cuando el campo **Tipo de pago** en el encabezado está configurado en *Deducciones de clientes de facturas de impuestos*. |
| Grupo de impuestos de artículos | Especifique si la devolución está sujeta a impuestos. |
| Nombre del diario<br>(En la sección **Cancelar**) | Si la devolución que se registra no es igual a la provisión, se puede cancelar la diferencia. Seleccione el nombre del diario que se utilizará para registrar la cancelación. |

## <a name="posting-by-company-fasttab"></a>Ficha desplegable de contabilización por empresa

La ficha desplegable **Contabilización por empresa** de cada perfil de contabilización de gestión de devoluciones le permite especificar la cuenta de registro que utiliza cada empresa (entidad jurídica) en la cuadrícula.

Use los botones de la barra de herramientas para agregar compañías a la cuadrícula o eliminarlas. Cada vez que agregue una fila a la cuadrícula, use el campo **Empresa** para especificar la entidad jurídica para esa fila. El campo **Nombre** se establecerá automáticamente.

Seleccione la fila para cada empresa y luego introduzca la siguiente información usando los campos debajo de la cuadrícula:

- **Tipo de débito**: seleccione si el débito es para una cuenta contable, un cliente o un proveedor.
- **Cuenta de debito**: introduzca la cuenta en la que se contabiliza el monto del débito cuando se realizan las provisiones de devolución.
- **Cuenta principal**: seleccione la cuenta principal para cancelaciones.
