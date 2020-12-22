---
title: Goteo en la creación de pedidos basados en fuente para transacciones de tienda
description: En este tema se describe el goteo de la creación de pedidos basados en fuente para las transacciones de tienda en Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 09/04/2020
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
ms.openlocfilehash: 79f99b9b401de3e3bcca6ec5a13a3b4f7bad6f8c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459893"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a><span data-ttu-id="ff513-103">Goteo en la creación de pedidos basados en fuente para transacciones de tienda</span><span class="sxs-lookup"><span data-stu-id="ff513-103">Trickle feed-based order creation for retail store transactions</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ff513-104">En Dynamics 365 Retail versión 10.0.4 y anteriores, el registro del extracto es una operación de final del día y todas las transacciones se registran en los libros al final del día.</span><span class="sxs-lookup"><span data-stu-id="ff513-104">In Dynamics 365 Retail versions 10.0.4 and earlier, statement posting is an end-of-day operation and all transactions are posted in the books at the end of the day.</span></span> <span data-ttu-id="ff513-105">Las transacciones grandes deben procesarse a continuación en una ventana de tiempo limitada, lo que a veces da lugar a errores de registro de extractos, carga y bloqueos.</span><span class="sxs-lookup"><span data-stu-id="ff513-105">Large transactions must then be processed in a limited time window, sometimes resulting in load and locks and statement posting failures.</span></span> <span data-ttu-id="ff513-106">Los minoristas tampoco pueden reconocer ingresos y pagos en los libros durante todo el día.</span><span class="sxs-lookup"><span data-stu-id="ff513-106">Retailers also can't recognize revenue and payments in their books throughout the day.</span></span>

<span data-ttu-id="ff513-107">Con el goteo de la creación de pedidos basados en fuente introducido en Retail versión 10.0.5, las transacciones se procesan durante todo el día y solo la conciliación financiera de formas de pago y otras transacciones de gestión de efectivo se procesan al final del día.</span><span class="sxs-lookup"><span data-stu-id="ff513-107">With trickle feed-based order creation introduced in Retail version 10.0.5, transactions are processed throughout the day, and only the financial reconciliation of tenders and other cash management transactions are processed at the end of the day.</span></span> <span data-ttu-id="ff513-108">Esta funcionalidad divide la carga de la creación de pedidos de ventas, facturas y pagos durante el día, ofreciendo el mejor rendimiento percibido y a la capacidad de reconocer ingresos y pagos en los libros casi en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="ff513-108">This functionality splits the load of creating sales orders, invoices, and payments throughout the day, providing better perceived performance and the ability to recognize revenue and payments in the books in near real-time.</span></span> 


## <a name="how-to-use-trickle-feed-based-posting"></a><span data-ttu-id="ff513-109">Cómo utilizar el goteo del registro basado en fuente</span><span class="sxs-lookup"><span data-stu-id="ff513-109">How to use trickle feed-based posting</span></span>
  
1. <span data-ttu-id="ff513-110">Para habilitar el goteo del registro basado en fuente de transacciones comerciales, habilite la característica denominada **Extractos comerciales - Fuente de goteo** utilizando la administración de características.</span><span class="sxs-lookup"><span data-stu-id="ff513-110">To enable trickle feed-based posting of retail transactions, enable the feature named **Retail statements - Trickle feed** using Feature management.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ff513-111">Antes de habilitar la característica, asegúrese de que ningún extracto pendiente esté en espera de registrarse.</span><span class="sxs-lookup"><span data-stu-id="ff513-111">Before you enable the feature, make sure that no pending statements are waiting to be posted.</span></span>

2. <span data-ttu-id="ff513-112">El documento de extracto actual se dividirá en dos tipos: extracto transaccional e informe financiero.</span><span class="sxs-lookup"><span data-stu-id="ff513-112">The current statement document will be split into two types: transactional statement and financial statement.</span></span>

      - <span data-ttu-id="ff513-113">El extracto transaccional recogerá todas las transacciones sin registrar y validadas, y creará pedidos de ventas, facturas de ventas, diarios de pagos y descuentos, así como transacciones de ingresos y gastos en la cadencia configurada.</span><span class="sxs-lookup"><span data-stu-id="ff513-113">The transactional statement will pick up all unposted and validated transactions and create sales orders, sales invoices, payment and discount journals, and income-expense transactions at the cadence that you configure.</span></span> <span data-ttu-id="ff513-114">Debe configurar este proceso para su ejecución en una frecuencia alta de manera que se creen documentos cuando se carguen las transacciones en Headquarters mediante el trabajo P.</span><span class="sxs-lookup"><span data-stu-id="ff513-114">You should configure this process to run at a high frequency so that documents are created when the transactions are uploaded into Headquarters through the P-job.</span></span> <span data-ttu-id="ff513-115">Con el extracto transaccional que ya crea pedidos de ventas y facturas de ventas, no es necesario realmente configurar el trabajo por lotes **Registrar inventario**.</span><span class="sxs-lookup"><span data-stu-id="ff513-115">With the transactional statement that already creates sales orders and sales invoices, there is no real need to configure the **Post inventory** batch job.</span></span> <span data-ttu-id="ff513-116">No obstante, puede seguir usándolo para cumplir los requisitos empresariales específicos que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="ff513-116">However, you can still use it to meet specific business requirements that you may have.</span></span>  
      
     - <span data-ttu-id="ff513-117">El informe financiero se ha diseñado para crearse al final del día y solo admite el método de cierre de **Turno**.</span><span class="sxs-lookup"><span data-stu-id="ff513-117">The financial statement is designed to be created at the end of the day and only supports the closing method of **Shift**.</span></span> <span data-ttu-id="ff513-118">Este informe se limitará a la conciliación financiera y solo creará los diarios para los importes de diferencia entre el importe contado y el importe de la transacción para las diferentes formas de pago, junto con los diarios para otras transacciones de administración de flujos de efectivo.</span><span class="sxs-lookup"><span data-stu-id="ff513-118">This statement will be limited to financial reconciliation and will only create the journals for the difference amounts between counted amount and transaction amount for the different tenders, along with journals for other cash management transactions.</span></span>   

3. <span data-ttu-id="ff513-119">Para calcular el extracto transaccional, vaya a **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Calcular extractos transaccionales por lotes**.</span><span class="sxs-lookup"><span data-stu-id="ff513-119">To calculate the transactional statement, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate transactional statements in batch**.</span></span> <span data-ttu-id="ff513-120">Para registrar los extractos transaccionales por lotes, vaya a **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Registrar extractos transaccionales por lotes**.</span><span class="sxs-lookup"><span data-stu-id="ff513-120">To post the transactional statements in batch, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Post transactional statements in batch**.</span></span>

4. <span data-ttu-id="ff513-121">Para calcular el informe financiero, vaya a **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Calcular informes financieros por lotes**.</span><span class="sxs-lookup"><span data-stu-id="ff513-121">To calculate the financial statement, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate financial statements in batch**.</span></span> <span data-ttu-id="ff513-122">Para registrar los informes financieros por lotes, vaya a **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Registrar informes financieros por lotes**.</span><span class="sxs-lookup"><span data-stu-id="ff513-122">To post the financial statements in batch, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Post financial statements in batch**.</span></span>

> [!NOTE]
> <span data-ttu-id="ff513-123">Los elementos de menú **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Calcular extractos por lotes** y **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Registrar extractos por lotes** se eliminan con esta nueva característica.</span><span class="sxs-lookup"><span data-stu-id="ff513-123">The menu items **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate statements in batch** and **Retail and Commerce > Retail and Commerce IT > POS Posting > Post statements in batch** are removed with this new feature.</span></span>

<span data-ttu-id="ff513-124">De manera alternativa, los tipos de informes financieros y transaccionales se pueden crear manualmente.</span><span class="sxs-lookup"><span data-stu-id="ff513-124">Alternately, transactional and financial statement types can be created manually.</span></span> <span data-ttu-id="ff513-125">Vaya a **Retail y Commerce > Canales > Tiendas** y haga clic en **Extractos**.</span><span class="sxs-lookup"><span data-stu-id="ff513-125">Go to **Retail and Commerce > Channels > Stores** and click **Statements**.</span></span> <span data-ttu-id="ff513-126">Haga clic en **Nuevo** y, a continuación, elija el tipo de informe que desea crear.</span><span class="sxs-lookup"><span data-stu-id="ff513-126">Click **New** and then choose the type of statement that you want to create.</span></span> <span data-ttu-id="ff513-127">Los campos de la página **Extractos** y las acciones del **Grupo de extracto** de la página mostrarán datos pertinentes y acciones basadas en el tipo de extracto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ff513-127">Fields on the **Statements** page and actions under the **Statement group** of the page will show relevant data and actions based on the selected statement type.</span></span>
