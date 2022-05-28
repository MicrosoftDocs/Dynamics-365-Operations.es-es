---
title: Descripción general de perfiles de contabilización
description: Este tema explica cómo se se usan los perfiles de contabilización en todas las aplicaciones de Microsoft Dynamics 365.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c29597155e525638e7c2ded7d641017f2189c49
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734587"
---
# <a name="posting-profiles-overview"></a>Descripción general de perfiles de contabilización

En las aplicaciones de Finanzas y Operaciones, el término *perfiles de contabilización* se utiliza para describir las configuraciones que controlan cómo las cuentas del libro mayor auxiliar se convierten en cuentas principales para que puedan usarse en transacciones que se registran en la contabilidad general. Por ejemplo, controlan cómo se convierte el cliente en una cuenta principal de Cliente cuando se registra una factura.

Algunos módulos y características tienen una página que incluye las palabras "perfil de contabilización" en el nombre (por ejemplo, **Perfil de contabilización del cliente** o **Perfil de contabilización del proveedor**). Además, algunos módulos tienen múltiples opciones para configurar la contabilización de la contabilidad general para las transacciones que se generan desde el libro auxiliar. Por ejemplo, en el módulo **Control de producción**, puede configurar la contabilización por grupo de producción, recurso o grupo de recursos.

Tenga en cuenta que, para muchos tipos de transacciones, existe una alternativa a los perfiles de contabilización: las definiciones de contabilización. Para los documentos admitidos, puede usar definiciones de contabilización en lugar de los perfiles de contabilización para clasificar cuentas principales y las dimensiones financieras de asientos contables. Si planea utilizar reservas de gastos o prerreservas de gastos, se requiere una definición de contabilización para definir las cuentas para los asientos contables.

Antes de poder configurar los perfiles de contabilización, las definiciones de contabilización o la página **Cuentas para transacciones automáticas**, debe configurar el catálogo de cuentas en la página **Contabilidad general** en la entidad jurídica que desea configurar.

## <a name="posting-types"></a>Tipos de registro

En las aplicaciones de Finanzas y Operaciones, los tipos de registro se usan para definir una categoría general para un débito o un crédito. Esta categoría es independiente de la cuenta principal en la contabilidad general. Hay tipos de contabilización para cada débito o crédito en la contabilidad general.

Un solo asiento puede tener uno o más tipos de registro. Por ejemplo, una transacción que se registra a través de un diario general donde la cuenta y la cuenta de contrapartida se establecen en **Libro mayor** tendrá un tipo de registro de **Diario contable**, tanto para el débito como para el crédito. Por el contrario, una factura de proveedor tendrá varios tipos de registro. Esos tipos de registro incluirán una línea para el saldo del proveedor y líneas adicionales para la entrada de contrapartida, como **Diario contable**.

Puede ver el tipo de registro en el campo **Tipo de registro** en la pestaña **General** de la página **Transacciones de asiento**.

> [!TIP]
> Puedes usar la barra de herramientas **Personalización** para agregar el campo **Tipo de registro** a la cuadrícula en la pestaña **Descripción general** o para moverla. De esta manera, puede hacer que este campo sea más fácil de acceder o consultar cuando vea los asientos.

## <a name="detail-settings-for-a-posting-profile"></a>Configuración de detalles para un perfil de contabilización 

Cuando configura perfiles de contabilización, el campo **Código de cuenta** define el nivel de la configuración. Las siguientes opciones están disponibles: **Tabla**, **Grupo** y **Todos**. El emparejamiento se detiene después de la primera coincidencia y el orden es del nivel más específico al nivel menos específico. Aunque el campo **Código de cuenta** puede tener un nombre ligeramente diferente en algunos casos, el comportamiento y la función del campo siguen siendo los mismos. Por ejemplo, el perfil de contabilización de inventario incluye un campo de **Código de artículo** y un campo de **Código de cuenta**. Ambos campos tienen los valores **Tabla**, **Grupo** y **Todos**.

Si deja el campo **Cuenta principal** en blanco para un perfil de registro y no ha configurado una cuenta principal en la página **Cuentas para transacciones automáticas** o en una página específica de un módulo o de una característica, recibirá un mensaje de error cuando registre una transacción que utilice el tipo de registro. Por lo general, el mensaje será "La cuenta para el \[tipo de registro\] no se ha encontrado".

### <a name="table-value"></a>Valor de tabla

El valor **Tabla** se refiere al registro maestro que está asociado con el perfil de contabilización. Cada registro de la tabla es específico de un valor. Especifique ese valor en el campo que aparece después del campo **Código de cuenta**. Por lo general, este campo se denomina **Cuenta** o **Número de cuenta/grupo**. El nombre exacto varía según la página donde aparezca.

Por ejemplo, si está trabajando con un perfil de contabilización de cliente, el valor **Tabla** representa a un cliente específico. Por lo tanto, si selecciona **Tabla** en el campo **Código de cuenta**, debe elegir el número del cliente en el campo **Número de grupo/cuenta**.

El valor **Tabla** representa el tipo de registro más específico. El sistema siempre usa este valor, incluso si ha configurado otro registro donde se selecciona el valor **Grupo** o **Todos**. Este valor también anula cualquier valor que haya creado como valores predeterminados en la página **Cuentas para transacciones automáticas**.

No recomendamos utilizar el valor **Tabla** como el mecanismo principal para administrar sus perfiles de contabilización, porque pueden ocurrir problemas de calidad de datos si se mantiene un perfil de contabilización separado para cada registro de datos maestros. También es difícil mantener y conciliar un perfil de contabilización separado para cada registro de datos maestros. En cambio, este valor debe usarse para administrar excepciones en sus perfiles de contabilización.

### <a name="group-value"></a>Valor de grupo

El valor **Grupo** se refiere al registro de grupo que es compatible con el registro maestro que está asociado con el perfil de contabilización. Cada registro de grupo es específico de un valor. Especifique ese valor en el campo que aparece después del campo **Código de cuenta**. Por lo general, este campo se denomina **Cuenta** o **Número de cuenta/grupo**. El nombre exacto varía según la página donde aparezca.

El valor **Grupo** requiere que primero configure un grupo y lo vincule a uno o más registros para la cuenta. El valor **Grupo** es menos específico que el valor **Tabla**, pero más específico que el **Todos**. Si no se ha configurado ningún registro para una tabla, el sistema intenta encontrar un registro para el grupo al que pertenece el mismo.

Por ejemplo, si está trabajando con un perfil de contabilización de cliente y selecciona **Grupo** en el campo **Código de cuenta**, debe seleccionar un grupo de clientes en el campo **Número de cuenta/grupo**. Debe predefinir los grupos de clientes en la página **Grupo de clientes** y debe especificar un grupo de clientes al crear un cliente.

Si debe realizar un seguimiento de varias cuentas principales para un tipo de registro determinado, le recomendamos que utilice el valor **Grupo**. Por ejemplo, tiene tres cuentas comerciales principales de Clientes: una para clientes habituales, otra para empleados y otra para ventas entre empresas. En este caso, le recomendamos que cree tres grupos de clientes para segmentarlos. Luego asigne cada grupo de clientes a la cuenta principal correcta en el perfil de contabilización del cliente. La siguiente tabla muestra los tres grupos de clientes para este ejemplo.

| Grupo de clientes | Name | Description |
|----------------|------|-------------|
| EXT | Cliente externo | Este grupo se utiliza para todos los clientes externos estándar. |
| EMP | Empleados | Este grupo se utiliza para todos los empleados que realizan compras en su organización. |
| INT | Ventas entre empresas | Este grupo se usa para todas las cuentas de clientes de empresas vinculadas que se usan con pedidos de compra y ventas de integración. |

En el perfil de contabilización, configurará tres líneas. En cada línea, seleccione el valor **Grupo** y la cuenta principal relacionada.

### <a name="all-value"></a>Valor Todos

El valor **Todos** indica que la configuración se aplica a todos los registros. Si selecciona el valor **Todos** en el campo **Código de cuenta**, el campo **Número de cuenta/grupo** no está disponible y no puede seleccionar un registro específico para aplicar la configuración.

El valor **Todos** es el valor menos específico. Se usa solo si el sistema no puede encontrar una coincidencia para el valor **Tabla** o **Grupo**. Debe seleccionar el valor **Todos** cuando solo tiene una cuenta principal para un tipo de registro específico.

Por ejemplo, cuando trabaja con un perfil de contabilización de cliente, las cuentas principales que especifica se aplican a todos los demás clientes y grupos de clientes que no tienen un registro para una tabla específica (cliente) o grupo (grupo de clientes).

### <a name="category"></a>Categoría

Los perfiles de contabilización de inventario tienen un valor adicional que es específico de la categoría de ventas o categoría de compras. Este valor se asemeja al valor **Tabla**, en el sentido de que se aplica solo a una categoría específica de ventas o adquisiciones.

### <a name="default-value"></a>Valor predeterminado

Si no crea un registro para un tipo de registro en un perfil de contabilización donde el campo **Código de cuenta** se establece en **Todos** y el sistema no puede encontrar un registro de perfil de contabilización coincidente para el valor **Grupo** o **Tabla**, el sistema vuelve al valor predeterminado que se puede especificar en la página **Cuentas para transacciones automáticas**. Para obtener más información, consulte [Cuentas para transacciones automáticas](accounts-for-auto-transactions.md).

## <a name="clearing-accounts"></a>Cuentas de compensación

El termino *cuenta de compensación* se utiliza a menudo en la contabilidad. Algunos tipos de registro en las aplicaciones de Microsoft Dynamics 365 son cuentas de compensación. En otras palabras, el saldo de la cuenta se liquida o revierte cuando se registra otra transacción. Por ejemplo, cuando registra un recibo de producto de pedido de compra, la suma de los costes estimados de los productos, más impuestos y cualquier cargo en las líneas de pedido de compra, se registra en el tipo de registro de acumulación de compra como un pasivo. Posteriormente, cuando factura el pedido de compra, el saldo se revierte del tipo de registro de acumulación de compras y se mueve a la cuenta comercial de Clientes.

## <a name="additional-resources"></a>Recursos adicionales

Muchos módulos en Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce y Dynamics 365 Project Operations tienen un perfil de contabilización o configuraciones adicionales que controlen cómo funciona la contabilización en la contabilidad general. Utilice los siguientes temas para obtener más información sobre los perfiles de contabilización y las configuraciones de contabilización en cada módulo:

- [Cuentas para transacciones automáticas](accounts-for-auto-transactions.md)
- [Registro de proveedores](accts-payble-posting.md)
- [Contabilización de clientes](accts-recvble-posting.md)
- [Contabilización de arrendamiento de activos](../asset-leasing/set-up-lease-posting-accts.md)
- Contabilización de administración de activos (próximamente)
- Gestión de efectivo y bancos (próximamente)
- Cuentas de contabilización de revalorización de divisa (próximamente)
- Contabilización de administración de gastos (próximamente)
- [Perfil de contabilización de activos fijos](../fixed-assets/tasks/set-up-fixed-asset-posting-profiles.md)
- Contabilización de contabilidad de empresas vinculadas (próximamente)
- Perfil de contabilización de inventario (próximamente)
- [Contabilización de costes en destino](../../supply-chain/landed-cost/costing-parameters-setup.md)
- [Información general de definiciones de contabilización](posting-definitions.md)
- Contabilización de control de producción (próximamente)
- Contabilización en la contabilidad y gestión de proyectos (próximamente)
- Contabilización de administración de servicios (próximamente)
- Contabilización de impuestos (próximamente)
- Contabilización de tiempo y asistencia (próximamente)
- Contabilización de administración de transporte (próximamente)
- Perfiles de contabilización de administración de devoluciones (próximamente)
