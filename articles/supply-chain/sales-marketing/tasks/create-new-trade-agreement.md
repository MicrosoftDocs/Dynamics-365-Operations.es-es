---
title: Crear un nuevo acuerdo comercial
description: Este procedimiento muestra cómo crear un acuerdo comercial por el que se registra un nuevo precio de venta acordado con un cliente específico.
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24290ec873da9e871c001bcdc97e14dcad0e3d1e
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111119"
---
# <a name="create-a-new-trade-agreement"></a>Crear un nuevo acuerdo comercial

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear un acuerdo comercial por el que se registra un nuevo precio de venta acordado con un cliente específico. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Si utiliza sus propios datos, antes de comenzar este procedimiento deberá asegurarse de que exista un nombre de diario de acuerdo comercial en el que la relación predeterminada esté establecida en "Precio (ventas)".

## <a name="create-and-post-a-new-trade-agreement-journal"></a>Creación y registro de un diario de acuerdos comerciales nuevos

1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Precios y descuentos > Diarios de acuerdos comerciales**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre**, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En **Panel Acciones**, haga clic en **Líneas**.
6. En el campo **Código de cuenta**, seleccione 'Tabla'.
    
    En este ejemplo, va a actualizar el precio para un cliente específico, por lo que tiene que elegir Tabla. Si fuera a actualizar el precio de lista del producto, seleccionaría 'Todo', de modo que el nuevo precio fuera válido para todos los clientes. Si fuera a diferenciar precios entre distintos segmentos de cliente, seleccionaría Grupo. Para seleccionar Grupo debe haber configurado grupos de precios de cliente.  

7. En el campo **Selección de cuentas**, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, busque y seleccione el registro deseado.
9. En el campo **Código de artículo**, seleccione 'Tabla'.
    
    Al introducir un acuerdo comercial del tipo 'Precio (ventas)', solo se debe seleccionar Tabla en el campo **Código de artículo**. Esto es así porque un precio es un valor absoluto, y no puede ser el mismo para todos los productos o un grupo de productos.
    
10. En el campo **Relación de artículos**, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, seleccione el producto que desee incluir en el acuerdo. Anote el producto que ha seleccionado.  
12. Especifique una cantidad mínima en el campo **Desde**.
    - Si el cliente tiene que pedir una cantidad mínima para poder optar al nuevo precio, deberá especificar la cantidad aquí.  
    - Especifique un valor en el campo **Hasta** para especificar la cantidad máxima por encima de la cual no será válido el precio del acuerdo. Si ofrece precios y descuentos según distintas cantidades por niveles, especifique cada segmento de cantidad como par de cantidades mínima y máxima en los campos **Desde** y **Hasta**, respectivamente.
13. En el **campo Importe en divisa**, escriba un precio.
14. En la sección **Detalles**, en el campo **Fecha inicial**, especifique una fecha desde la cual será válido este acuerdo.
15. Haga clic en **Guardar**.
16. Hacer clic en **Validar**.
17. Haga clic en **Validar las líneas seleccionadas**.
18. Haga clic en **Aceptar**.
19. Haga clic en **Registrar**.
20. Haga clic en **Aceptar**.

## <a name="view-trade-agreements-for-a-product"></a>Visualización de acuerdos comerciales para un producto

1. Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos despachados**.
2. En la lista, busque y seleccione el producto cuyo precio acaba de actualizar.
3. En **Panel de acciones**, haga clic en **Vender**.
4. Haga clic en **Ver acuerdos comerciales**
    
    Revise los detalles del acuerdo comercial de precios que acaba de crear.

5. Cierre la página.

## <a name="additional-resources"></a>Recursos adicionales

### <a name="whitepaper"></a>Notas del producto

Para obtener más información, descargue las siguientes notas del producto (escrito para ser compatible con AX2012, pero aún sirve para Dynamics 365 Supply Chain Management)

- [Acuerdos comerciales](https://download.microsoft.com/download/0/2/9/02972c8b-0159-4936-a3ef-1e64252b2d2f/TradeAgreementsInAX.pdf)

### <a name="community-blogs"></a>Blogs de la comunidad

- [Precios de ventas en finanzas y operaciones](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
