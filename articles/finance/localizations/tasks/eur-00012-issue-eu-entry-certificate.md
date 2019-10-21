---
title: EUR-00012 Emisión de un certificado de entrada de la UE
description: Este procedimiento le muestra cómo habilitar un certificado de entrada de la UE, cómo configurar una cuenta de cliente para usar certificados de entrada y emitir un certificado.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 735331fd399ba9501031084e236b88c0e11bb179
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183570"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a>EUR-00012 Emisión de un certificado de entrada de la UE

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo habilitar un certificado de entrada de la UE, cómo configurar una cuenta de cliente para usar certificados de entrada y emitir un certificado. Este procedimiento se creó con los datos de demostración de la empresa DEMF.


## <a name="enable-entry-certificate-management"></a>Habilitar administración de certificados de entrada
1. Vaya a Clientes > Configuración > Parámetros de clientes.
2. Haga clic en la ficha Envíos.
3. Expanda la sección Certificado de entrada.
4. Seleccione Sí en el campo Habilitar administración de certificados de entrada.
5. Seleccione Sí en el campo Habilitar emisión de certificados de entrada.
6. Haga clic en la ficha Secuencias numéricas.
7. En la lista, busque y seleccione Fila de certificado de entrada.
8. En el campo Código de secuencia numérica, especifique o seleccione un valor.

## <a name="set-up-a-customer"></a>Configuración de un cliente
1. Vaya a Clientes > Clientes > Todos los clientes.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Cuenta, por el valor "DE-015".
3. Abra los detalles de la cuenta del cliente.
4. Haga clic en Editar.
5. Expanda la sección Factura y entrega.
6. Seleccione Sí en el campo Se necesita certificado de entrada.
7. Seleccione Sí en el campo Emitir certificado de entrada.
8. Haga clic en Guardar.

## <a name="create-an-eu-entry-certificate-automatically"></a>Creación automática de un certificado de entrada de la UE
1. Vaya a Clientes > Pedidos > Todos los pedidos de venta.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, especifique o seleccione un valor.
4. Haga clic en Aceptar
5. En el campo Número de artículo, especifique o seleccione un valor.
6. Haga clic en Guardar.
7. En el panel de acciones, haga clic en Seleccionar y empaquetar.
8. Haga clic en Registrar albarán.
9. Expanda la sección Parámetros.
10. En el campo Cantidad, seleccione 'Todo'.
11. Quite la marca de la casilla Emitir certificado de entrada.
    * Un certificado de entrada se puede emitir al registrar un albarán o al facturar un pedido. Deje la casilla Emitir certificado de entrada sin marcar para emitirlo más adelante.  
12. Haga clic en Aceptar
13. Haga clic en Aceptar
14. En el panel de acciones, haga clic en Factura.
15. Haga clic en Factura.
    * Compruebe que las casillas Se necesita certificado de entrada y Emitir certificado de entrada en la sección Visión general estén marcadas.  También puede seleccionar la casilla Imprimir certificado de entrada para permitir imprimir el certificado.  
16. Haga clic en Aceptar
17. Haga clic en Aceptar
18. En el panel de acciones, haga clic en Factura.
19. Haga clic en Factura.
20. En el panel de acciones, haga clic en Factura.
21. Haga clic en Ver certificados de entrada emitidos.
22. Haga clic en Imprimir.
23. Cierre la página.
24. Haga clic en Cambiar estado.
25. En el campo Nuevo estado, seleccione una opción.
26. Haga clic en Aceptar
27. Cierre la página.

## <a name="create-an-eu-entry-certificate-manually"></a>Creación manual de un certificado de entrada de la UE
1. En el panel de acciones, haga clic en Factura.
2. Haga clic en Crear certificado de entrada.
3. Haga clic en Aceptar
4. En el panel de acciones, haga clic en Factura.
5. Haga clic en Ver certificados de entrada emitidos.

