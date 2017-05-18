---
title: "Publicar líneas de diario y documentos de Excel"
description: "En este tema se explica cómo introducir y publicar las líneas para diarios generales desde Microsoft Excel. Incluye información sobre las distintas plantillas que se pueden utilizar, dependiendo del tipo de transacciones que esté introduciendo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 9726c61b69f79bdd56803ced4c06044dd517ac13
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publicar líneas de diario y documentos de Excel

[!include[banner](../includes/banner.md)]


En este tema se explica cómo introducir y publicar las líneas para diarios generales desde Microsoft Excel. Incluye información sobre las distintas plantillas que se pueden utilizar, dependiendo del tipo de transacciones que esté introduciendo.

Los usuarios pueden introducir y publicar líneas de diarios financieros desde Microsoft Excel. Después de que un usuario cree un diario, el botón **Abrir líneas en Excel** muestra las plantillas disponibles. Las plantillas están diseñadas para admitir determinados escenarios; sin embargo, no todas las combinaciones de tipo de cuenta se admiten en el diario. La tabla siguiente muestra las plantillas disponibles y los tipos de cuentas que admiten.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Plantilla**             | **Tipos de cuenta admitidos**                                                                                             | **Cómo acceder a la plantilla**                                                          |
| Líneas de diario de contabilidad     | Cuenta: Libro mayor, Cliente, Proveedor, Cuenta de contrapartida de Banco: se admite Libro mayor, Cliente, Proveedor, Empresas vinculadas de Banco.       | Diario general                                                                         |
| Registro de facturas         | Cuenta: Cuenta de contrapartida del proveedor: Libro mayor empresas vinculadas no se admite.                                                    | Registro de facturas de proveedores                                                                     |
| Diario de facturas          | Cuentas: Cuenta de contrapartida del proveedor: Libro mayor empresas vinculadas se admite.                                                      | Diario de facturas de proveedores                                                                      |
| Factura del proveedor           |                                                                                                                         | Factura del proveedor                                                                          |
| Diario de facturas del cliente | Cuenta: Cuenta de contrapartida del cliente: Libro mayor empresas vinculadas se admite.                                                     | Diario general                                                                         |
| Factura de servicios        |                                                                                                                         | En la página **Factura de servicios**, haga clic en **Abrir en Excel** (el icono Microsoft Office). |
| Diario de activos fijos     | Activo a libro mayor, banco, cliente o proveedor. No se admiten empresas vinculadas.                                               | Diario de activos fijos                                                                     |
| Diario de pagos a proveedores   | Cuenta: Cuenta de contrapartida del proveedor: se admite Libro mayor, Banco empresas vinculadas.                                                 | Diario de pagos a proveedores                                                                  |
| Diario de pagos de clientes | Cuenta: Cuenta de contrapartida del cliente: se admite Libro mayor, Banco empresas vinculadas.                                               | Diario de pagos de clientes                                                                |
| Diario de gastos de proyecto  | Cuenta: Proyecto, Libro mayor, Cliente, Cuenta de contrapartida de proveedor: se admite Proyecto, Libro mayor, Cliente, Empresas vinculadas de proveedor. | Gasto de diario general (bajo Administración de proyectos y contabilidad)                       |

Cuando se publican las líneas, se validan para asegurarse de que cumplen con las reglas definidas en las revistas financieras. Después de publicarse las líneas, los usuarios pueden editar o registrar asientos de Microsoft Dynamics 365 for Operations. 

Para agregar dimensiones financieras a una plantilla, se necesitan otros cambios adicionales. Para obtener más información, consulte [Agregar dimensiones a la plantilla de Microsoft Excel](/dynamics365/operations/dev-itpro/financial/add-dimensions-excel-templates). Después de agregar dimensiones a la entidad, quedarán disponibles en el diseñador de Excel y pueden agregarse a la plantilla.






