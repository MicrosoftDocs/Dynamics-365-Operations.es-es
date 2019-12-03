---
title: Goteo en la creación de pedidos basados en fuente para transacciones de tienda
description: En este tema se describe el goteo de la creación de pedidos basados en fuente para las transacciones de tienda en Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: deb8399aa401af16b6fe123a433eb21864e178c6
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693098"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a><span data-ttu-id="c8c8b-103">Goteo en la creación de pedidos basados en fuente para transacciones de tienda (versión preliminar pública)</span><span class="sxs-lookup"><span data-stu-id="c8c8b-103">Trickle feed-based order creation for retail store transactions (Public preview)</span></span>

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="c8c8b-104">En Dynamics 365 Retail versión 10.0.4 y anteriores, el registro del extracto comercial es una operación de final del día y todas las transacciones se registran en los libros al final del día.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-104">In Dynamics 365 Retail versions 10.0.4 and earlier, retail statement posting is an end-of-day operation and all transactions are posted in the books at the end of the day.</span></span> <span data-ttu-id="c8c8b-105">Las transacciones grandes deben procesarse a continuación en una ventana de tiempo limitada, lo que a veces da lugar a errores de registro de extractos, carga y bloqueos.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-105">Large transactions must then be processed in a limited time window, sometimes resulting in load and locks and statement posting failures.</span></span> <span data-ttu-id="c8c8b-106">Los minoristas tampoco pueden reconocer ingresos y pagos en los libros durante todo el día.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-106">Retailers also can't recognize revenue and payments in their books throughout the day.</span></span>

<span data-ttu-id="c8c8b-107">Con la versión preliminar pública del goteo de la creación de pedidos basados en fuente introducido en Retail versión 10.0.5, las transacciones se procesan durante todo el día y solo la conciliación financiera de formas de pago y otras transacciones de gestión de efectivo se procesan al final del día.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-107">With the public preview of trickle feed-based order creation introduced in Retail version 10.0.5, transactions are processed throughout the day, and only the financial reconciliation of tenders and other cash management transactions are processed at the end of the day.</span></span> <span data-ttu-id="c8c8b-108">Esta funcionalidad divide la carga de la creación de pedidos de ventas, facturas y pagos durante el día, ofreciendo el mejor rendimiento percibido y a la capacidad de reconocer ingresos y pagos en los libros casi en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-108">This functionality splits the load of creating sales orders, invoices, and payments throughout the day, providing better perceived performance and the ability to recognize revenue and payments in the books in near real-time.</span></span> 


## <a name="how-to-use-trickle-feed-based-posting"></a><span data-ttu-id="c8c8b-109">Cómo utilizar el goteo del registro basado en fuente</span><span class="sxs-lookup"><span data-stu-id="c8c8b-109">How to use trickle feed-based posting</span></span>
  
1. <span data-ttu-id="c8c8b-110">Para habilitar el goteo del registro basado en fuente de las transacciones comerciales, vaya a **Administración del sistema > Configuración > Configuración de licencias** y deshabilita la clave **Extractos comerciales**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-110">To enable trickle feed-based posting of retail transactions, go to **System administration > Set up > License configuration** and disable the the **Retail statements** key.</span></span>

2. <span data-ttu-id="c8c8b-111">En la misma página, habilite la clave de licencia **Extractos comerciales (fuente de goteo): versión preliminar**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-111">On the same page, enable the **Retail statements (trickle feed) – Preview** license key.</span></span> <span data-ttu-id="c8c8b-112">Al habilitar esta clave, asegúrese de que no haya extractos pendientes en espera de registrarse.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-112">When you enable this key, make sure there are no pending statements waiting to be posted.</span></span> 

> [!Important]
> <span data-ttu-id="c8c8b-113">Antes de habilitar la clave de licencia **Extractos comerciales (fuente de goteo): versión preliminar**, asegúrese de que ninguno de los extractos pendientes están en espera de ser registrados.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-113">Before you enable the **Retail statements (trickle feed) – Preview** license key, make sure that no pending statements are waiting to be posted.</span></span>

3. <span data-ttu-id="c8c8b-114">El documento de extracto actual se dividirá en dos tipos diferentes: extracto transaccional e informe financiero.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-114">The current statement document will be split into two different types; transactional statement and financial statement.</span></span>

      - <span data-ttu-id="c8c8b-115">El extracto transaccional recogerá todas las transacciones comerciales sin registrar y validadas, y creará pedidos de ventas, facturas de ventas, diarios de pagos y descuentos, así como transacciones de ingresos y gastos en la cadencia configurada.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-115">The transactional statement will pick up all unposted and validated retail transactions and create sales orders, sales invoices, payment and discount journals, and income-expense transactions at the cadence that you configure.</span></span> <span data-ttu-id="c8c8b-116">Debe configurar este proceso para su ejecución en una frecuencia alta de manera que se creen documentos cuando se carguen las transacciones comerciales en Retail Headquarters mediante el trabajo P.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-116">You should configure this process to run at a high frequency so that documents are created when the retail transactions are uploaded into Retail Headquarters through the P-job.</span></span> <span data-ttu-id="c8c8b-117">Con el extracto transaccional que ya crea pedidos de ventas y facturas de ventas, no es necesario realmente configurar el trabajo por lotes **Registrar inventario**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-117">With the transactional statement that already creates sales orders and sales invoices, there is no real need to configure the **Post inventory** batch job.</span></span> <span data-ttu-id="c8c8b-118">No obstante, puede seguir usándolo para cumplir los requisitos empresariales específicos que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-118">However, you can still use it to meet specific business requirements that you may have.</span></span>  
      
     - <span data-ttu-id="c8c8b-119">El informe financiero se ha diseñado para crearse al final del día y solo admite el método de cierre de **Turno**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-119">The financial statement is designed to be created at the end of the day and only supports the closing method of **Shift**.</span></span> <span data-ttu-id="c8c8b-120">Este informe se limitará a la conciliación financiera y solo creará los diarios para los importes de diferencia entre el importe contado y el importe de la transacción para las diferentes formas de pago, junto con los diarios para otras transacciones de administración de flujos de efectivo.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-120">This statement will be limited to financial reconciliation and will only create the journals for the difference amounts between counted amount and transaction amount for the different tenders, along with journals for other cash management transactions.</span></span>   

4. <span data-ttu-id="c8c8b-121">Para calcular el extracto transaccional, haga clic en **Venta minorista > TI de venta minorista > Registro de PDV > Calcular extractos transaccionales por lotes**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-121">To calculate the transactional statement, click **Retail > Retail IT > POS Posting > Calculate transactional statements in batch**.</span></span> <span data-ttu-id="c8c8b-122">Para registrar los extractos transaccionales por lotes, haga clic en **Venta minorista > TI de venta minorista > Registro de PDV > Registrar extractos transaccionales por lotes**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-122">To post the transactional statement statements in batch, click **Retail > Retail IT > POS Posting > Post transactional statements in batch**.</span></span>

5. <span data-ttu-id="c8c8b-123">Para calcular el informe financiero, haga clic en **Venta minorista > TI de venta minorista > Registro de PDV > Calcular informes financieros por lotes**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-123">To calculate the financial statement, click **Retail > Retail IT > POS Posting > Calculate financial statements in batch**.</span></span> <span data-ttu-id="c8c8b-124">Para registrar los informes financieros por lotes, haga clic en **Venta minorista > TI de venta minorista > Registro de PDV > Registrar informes financieros por lotes**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-124">To post the financial statements in batch, click **Retail > Retail IT > POS Posting > Post financial statements in batch**.</span></span>

> [!NOTE]
> <span data-ttu-id="c8c8b-125">Los elementos de menú **Venta minorista > TI de venta minorista > Registro de PDV > Calcular extractos por lotes** y **Venta minorista > TI de venta minorista > Registro de PDV > Registrar extractos por lotes** se eliminan con esta nueva característica.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-125">The menu items **Retail > Retail IT > POS Posting > Calculate statements in batch** and **Retail > Retail IT > POS Posting > Post statements in batch** are removed with this new feature.</span></span>

<span data-ttu-id="c8c8b-126">De manera alternativa, los tipos de informes financieros y transaccionales se pueden crear manualmente.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-126">Alternately, transactional and financial statement types can be created manually.</span></span> <span data-ttu-id="c8c8b-127">Vaya a **Venta minorista > Canales > Tiendas** y haga clic en **Extractos comerciales**.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-127">Go to **Retail > Channels > Retail stores** and click **Retail statements**.</span></span> <span data-ttu-id="c8c8b-128">Haga clic en **Nuevo** y, a continuación, elija el tipo de informe que desea crear.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-128">Click **New** and then choose the type of statement that you want to create.</span></span> <span data-ttu-id="c8c8b-129">Los campos de la página **Extractos comerciales** y las acciones del **Grupo de extracto** de la página mostrarán datos pertinentes y acciones basadas en el tipo de extracto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-129">Fields on the **Retail statements** page and actions under the **Statement group** of the page will show relevant data and actions based on the selected statement type.</span></span>
