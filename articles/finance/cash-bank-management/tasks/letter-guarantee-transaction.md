---
title: Transacción de carta de garantía
description: Este procedimiento le muestra el proceso de Carta de garantía.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 786aecf69bae3d07ac80a55b4dc835dd8129bd59
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803974"
---
# <a name="letter-of-guarantee-transaction"></a>Transacción de carta de garantía

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra el proceso de Carta de garantía.



Las siguientes tareas se deben realizar antes de completar este procedimiento:

- Configuración de servicios bancarios y perfiles para una carta de garantía.

- Creación de un contrato de servicios bancarios para una carta de garantía.



Este procedimiento usa la empresa de demostración USMF.


## <a name="create-sales-order-with-letter-of-guarantee"></a>Crear pedido de ventas con carta de garantía
1. Vaya a **Clientes > Pedidos > Todos los pedidos de venta**.
2. Haga clic en **Nuevo**.
3. En el campo **Cuenta de cliente**, especifique o seleccione un valor.
4. Expanda la sección **General**.
5. En el campo **Sitio**, especifique o seleccione un valor.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. En el campo **Almacén**, especifique o seleccione un valor.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo **Tipo de documento bancario**, seleccione **Carta de garantía**.
10. Haga clic en **Aceptar**.
11. En el campo **Número de artículo**, especifique o seleccione un valor.
12. En el campo **Precio unitario**, escriba un número.
13. Expanda la sección **Detalles de línea.**
14. Haga clic en la ficha **Entrega**.

>[!Note] 
>Seleccione **Control de fecha de entrega** = **Ninguno**  

15. En el campo **Fecha de envío solicitada**, especifique una fecha.
16. En el campo **Fecha de envío confirmada**, especifique una fecha.

## <a name="process-letter-of-guarantee_request"></a>Procesar carta de garantía_Solicitar
1. En el Panel de acciones, haga clic en **Gestionar**.
2. Haga clic en **Carta de garantía**.
3. En el Panel de acciones, haga clic en **Carta de garantía**.
4. Haga clic en **Solicitud** para abrir el cuadro de diálogo desplegable.
5. En el campo **Tipo**, especifique o seleccione un valor.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. En el campo **Valor,** especifique un número.
8. En el campo **Fecha de vencimiento**, especifique una fecha y una hora.
9. Haga clic en **Aceptar**.
10. Cierre la página.

## <a name="process-letter-of-guarantee_submit-to-bank"></a>Procesar carta de garantía_Enviar al banco
1. Vaya a **Gestión de efectivo y bancos > Cartas de garantía > Cartas de garantía**.
2. En la lista, busque y seleccione el registro deseado.
3. Haga clic en **Enviar al banco** para abrir el cuadro de diálogo desplegable.
4. En el campo **Cuenta bancaria**, especifique o seleccione un valor.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en **Aceptar**.

## <a name="process-letter-of-guarantee_receive-from-bank"></a>Procesar carta de garantía_Recibir del banco
1. Haga clic en **Recibir del banco** para abrir el cuadro de diálogo desplegable.
2. En el campo **Número del banco**, escriba un valor.
    * Compruebe los valores en los campos **Margen** y **Gasto** calculados.  
3. Haga clic en **Aceptar**.
4. Expanda la sección **Acciones**.
    * Compruebe el registro "Recibir del banco".  
5. Haga clic para seguir el vínculo en el campo **Número de lote de diario**.
6. Haga clic en **Líneas**.
    * Compruebe el registro de entradas del diario.  
7. Cierre la página.

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>Procesar carta de garantía_Entregar a beneficiario
1. Vaya a **Clientes > Pedidos > Todos los pedidos de venta**.
2. En la lista, haga clic en el vínculo de la fila seleccionada.
3. En el Panel de acciones, haga clic en **Gestionar**.
4. Haga clic en **Carta de garantía**.
5. En el Panel de acciones, haga clic en **Carta de garantía**.
6. Haga clic en **Entregar a beneficiario** para abrir el cuadro de diálogo desplegable.
7. Haga clic en **Aceptar**.
8. Vaya a **Gestión de efectivo y bancos > Cartas de garantía > Cartas de garantía**.
9. En la lista, busque y seleccione el registro deseado.
10. Haga clic en **Entregar a beneficiario** para abrir el cuadro de diálogo desplegable.
11. Haga clic en **Aceptar**.
12. Expanda la sección **Acciones**.
    * Valide el registro "Entregar a beneficiario".  

## <a name="process-letter-of-guarantee_increase-value"></a>Procesar carta de garantía_Aumentar valor
1. Vaya a **Clientes > Pedidos > Todos los pedidos de venta**.
2. En la lista, haga clic en el vínculo de la fila seleccionada.
3. En el Panel de acciones, haga clic en **Gestionar**.
4. Haga clic en **Carta de garantía**.
5. En el Panel de acciones, haga clic en **Carta de garantía**.
6. Haga clic en **Aumentar valor** para abrir el cuadro de diálogo desplegable.
7. En el campo **Valor para agregar**, escriba un número.
8. Haga clic en **Aceptar**.
9. Vaya a **Gestión de efectivo y bancos > Cartas de garantía > Cartas de garantía**.
10. En la lista, busque y seleccione el registro deseado.
11. Haga clic en **Aumentar valor** para abrir el cuadro de diálogo desplegable.
12. Haga clic en **Aceptar**.
13. Expanda la sección **Acciones**.
    * Compruebe el registro "Aumentar valor".  
14. En la lista, busque y seleccione el registro deseado.
15. Haga clic para seguir el vínculo en el campo **Número de lote de diario**.
16. Haga clic en **Líneas**.
    * Compruebe las entradas del diario registradas.  

## <a name="process-letter-of-guarantee_liquidate"></a>Procesar carta de garantía_Liquidar
1. Vaya a **Clientes > Pedidos > Todos los pedidos de venta**.
2. En la lista, haga clic en el vínculo de la fila seleccionada.
3. En el Panel de acciones, haga clic en **Gestionar**.
4. Haga clic en **Carta de garantía**.
5. En el Panel de acciones, haga clic en **Carta de garantía**.
6. Haga clic en **Liquidar** para abrir el cuadro de diálogo desplegable.
7. Haga clic en **Aceptar**.
8. Vaya a **Gestión de efectivo y bancos > Cartas de garantía > Cartas de garantía**.
9. En la lista, busque y seleccione el registro deseado.
10. Haga clic en **Liquidar** para abrir el cuadro de diálogo desplegable.
11. Haga clic en **Aceptar**.
12. Expanda la sección **Acciones**.
    * Compruebe el registro "Liquidar".  
13. En la lista, busque y seleccione el registro deseado.
14. Haga clic para seguir el vínculo en el campo **Número de lote de diario**.
15. Haga clic en **Líneas**.
    * Compruebe las entradas del diario registradas.  
16. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
