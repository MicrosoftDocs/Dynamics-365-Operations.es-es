---
title: "Publicar las líneas de diario y documentos de Excel"
description: "Este tema explica cómo especificar y publicar las líneas para los diarios generales de Microsoft Excel. Incluye información acerca de las plantillas diferentes que puede usar, en función del tipo de transacciones que está introduciendo."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
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
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 087339cb3002b42bcb985c2ccfc2d97c752a817c
ms.lasthandoff: 03/31/2017


---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publicar las líneas de diario y documentos de Excel

Este tema explica cómo especificar y publicar las líneas para los diarios generales de Microsoft Excel. Incluye información acerca de las plantillas diferentes que puede usar, en función del tipo de transacciones que está introduciendo.

Los usuarios pueden especificar y publicar las líneas para los diarios financieros de Microsoft Excel. Una vez que un usuario cree un diario, ** líneas abiertas en Excel ** el botón muestra las plantillas disponibles. Las plantillas están diseñados para admitir escenarios de facturación específicos, aunque no admiten a cada combinación de tipo de cuenta en el diario. En la tabla siguiente se muestran las plantillas que están disponibles y los tipos de cuenta que admiten.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Template**             | ** Tipos de cuenta admitidos **                                                                                             | ** Cómo tener acceso a la plantilla **                                                          |
| Líneas de diario de contabilidad     | Cuenta: Libro mayor, cliente, proveedor, cuenta de contrapartida del banco: Se admite el libro mayor, cliente, proveedor, empresas vinculadas del banco.       | Diario general                                                                         |
| Registro de facturas         | Cuenta: Cuenta de contrapartida del proveedor: Las empresas vinculadas de contabilidad no se admiten.                                                    | Registro de facturas de proveedores                                                                     |
| Diario de facturas          | Cuentas: Cuenta de contrapartida del proveedor: Se admiten las empresas vinculadas de contabilidad.                                                      | Diario de facturas de proveedores                                                                      |
| Factura del proveedor           |                                                                                                                         | Factura del proveedor                                                                          |
| Diario de facturas del cliente | Cuenta: Cuenta de contrapartida del cliente: Se admiten las empresas vinculadas de contabilidad.                                                     | Diario general                                                                         |
| Factura de servicios        |                                                                                                                         | En ** factura de servicios ** la página, abra ** clic en Excel (** el icono de Microsoft Office). |
| Diario de activos fijos     | Activo en la contabilidad, al banco, al cliente, o al proveedor. Las empresas vinculadas no se admiten.                                               | Diario de activos fijos                                                                     |
| Diario de pagos a proveedores   | Cuenta: Cuenta de contrapartida del proveedor: Se admite el libro mayor, empresas vinculadas del banco.                                                 | Diario de pagos a proveedores                                                                  |
| Diario de pagos de clientes | Cuenta: Cuenta de contrapartida del cliente: Se admite el libro mayor, empresas vinculadas del banco.                                               | Diario de pagos de clientes                                                                |
| Diario de gastos de proyecto  | Cuenta: Proyecto, contabilidad, cliente, cuenta de contrapartida del proveedor: Se admite el proyecto, contabilidad, cliente, empresas vinculadas del proveedor. | Gasto general del diario (en Gestión de proyectos y contabilidad)                       |

Cuando se publiquen las líneas, se validan para asegurarse de que cumplen con las reglas configuradas en los diarios financieros. Después de que se publiquen las líneas, los usuarios pueden editar o registrar asientos de Microsoft Dynamics 365 para las operaciones. 

Para agregar dimensiones financieras a una plantilla, los cambios adicionales se requieren. Para obtener más información, consulte [agregar dimensiones a la plantilla de Microsoft Excel] (\ revelador - itpro dimensiones financieras \ \ agregar-dimensión-Excel- plantillas). Una vez que las dimensiones se agregan a la entidad, están disponibles en el diseñador de Excel y pueden agregarse a la plantilla.




