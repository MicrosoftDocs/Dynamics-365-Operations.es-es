--- 
title: EUR-00011 Generar el informe de lista de ventas de la UE
description: "Este procedimiento le guía por la generación del informe de la lista de ventas de la UE."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 9fcafa2beca5d998b2556ba73e9f3cc2bdd314ba
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a>EUR-00011 Generar el informe de lista de ventas de la UE

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le guía por la generación del informe de la lista de ventas de la UE. Esto incluye la transferencia de las transacciones comerciales intracomunitarias a la lista de ventas de la UE y la ejecución del informe. Este procedimiento también incluye la creación de una transacción comercial intracomunitaria para fines de demostración. Para obtener más información acerca de los informes de la lista de ventas de la UE, incluidos requisitos previos necesarios, remítase a la Ayuda de Dynamics 365 for Finance and Operations.

Este procedimiento se aplica a todos los países o regiones europeos. El procedimiento se creó con la empresa de datos de demostración DEMF y, por tanto, Alemania como país o región nacional de ejemplo. El procedimiento también utiliza Portugal como país o región de la UE de ejemplo. Para poder completar este procedimiento, debe configurar los informes de listas de ventas de la UE.

Este procedimiento está pensado para contables.


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a>Crear una transacción de ventas intracomunitaria para fines de demostración
1. Vaya a Clientes > Pedidos > Todos los pedidos de venta.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, escriba "PRT-001".
4. Haga clic en Aceptar
5. En el campo Código de artículo, escriba 'D0001'.
6. Expanda la sección Detalles de línea.
7. Haga clic en la ficha Configurar.
8. En el campo Grupo de impuestos de artículos, escriba "FULL".
9. Haga clic en Agregar línea.
10. En el campo Código de artículo, escriba 'D0003'.
11. En el campo Grupo de impuestos de artículos, escriba "RED".
12. Haga clic en Guardar.
13. En el panel de acciones, haga clic en Factura.
14. Haga clic en Factura.
15. Expanda la sección Parámetros.
16. En el campo Cantidad, seleccione 'Todo'.
17. Expanda la sección Configuración.
18. En el campo Fecha de factura, establezca la fecha en "11/01/2016".
19. Haga clic en Aceptar
20. Haga clic en Aceptar

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a>Transferir transacciones intracomunitarias a la lista de ventas de la UE
1. Vaya a Impuestos > Declaraciones > Comercio exterior > Lista de ventas de la UE.
2. Haga clic en Transferir.
3. Seleccione Sí en el campo Artículo para transferir transacciones de artículos.
4. Seleccione Sí en el campo Servicio para transferir transacciones de servicio.
    * También puede especificar filtros adicionales en transacciones comerciales intracomunitarias para transferencia.  
5. Haga clic en Transferir.
    * Compruebe que la transacción de ventas intracomunitaria se transfiere correctamente a la lista de ventas de la UE.  

## <a name="generate-the-eu-sales-list-report"></a> Generar el informe de lista de ventas de la UE
1. Haga clic en Informes.
2. En el campo Período de notificación, seleccione "Mensual".
3. En el campo Fecha inicial, defina la fecha en "01/01/2016".
4. Seleccione Sí en el campo Generar archivo.
5. Seleccione Sí en el campo Generar informe.
6. En el campo Nombre de archivo, escriba "EUSalesList".
7. En el campo Nombre de archivo de informe, escriba "EUSalesList".
8. En el campo Id. de registro de lista de ventas de la UE, escriba "123".
    * Este campo solo está disponible para Alemania.  
    * También puede especificar filtros adicionales en transacciones comerciales intracomunitarias para incluirlas en el informe.  
9. Haga clic en Aceptar
    * Compruebe que las ventanas emergentes aparecen para confirmar que se están descargando el archivo y el informe de control.  

## <a name="mark-eu-sales-list-lines-as-reported"></a>Marcar las líneas de la lista de ventas de la UE como notificadas
1. Haga clic en Marcar.
2. Haga clic en Marcar como notificado.
3. En la lista, seleccione la fila para el campo Fecha de factura.
4. En el campo Criterios, escriba "01/01/2016..01/31/2016".
5. En la lista, seleccione la fila para el campo Estado de notificación.
6. En el campo Criterios, seleccione "Incluido".
    * También puede especificar filtros adicionales en transacciones comerciales intracomunitarias para marcarlas como notificadas.  
7. Haga clic en Aceptar
8. En el campo Selección, seleccione "Notificado".

## <a name="mark-eu-sales-list-lines-as-closed"></a>Marcar las líneas de la lista de ventas de la UE como cerradas
1. Haga clic en Marcar.
2. Haga clic en Marcar como cerrado.
3. En la lista, marque la fila para el campo Fecha de factura.
4. En el campo Criterios, escriba "01/01/2016..01/31/2016".
5. En la lista, marque la fila para el campo Estado de notificación.
6. En el campo Criterios, seleccione "Notificado".
    * También puede especificar filtros adicionales en transacciones comerciales intracomunitarias para marcarlas como cerradas.  
7. Haga clic en Aceptar
8. En el campo Selección, seleccione "Cerrado".


