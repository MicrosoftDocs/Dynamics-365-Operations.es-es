---
title: Tareas periódicas de administración del crédito
description: En este tema se describen las tareas periódicas que son una parte necesaria del proceso de administración de los límites de crédito para los clientes.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 17b4b2f487fdeb9f1aa7d77bf87197885ba60e47
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977944"
---
# <a name="periodic-credit-management-tasks"></a><span data-ttu-id="45254-103">Tareas periódicas de gestión de crédito.</span><span class="sxs-lookup"><span data-stu-id="45254-103">Periodic credit management tasks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45254-104">En este tema se describen las tareas periódicas que son una parte necesaria del proceso de administración de los límites de crédito para los clientes.</span><span class="sxs-lookup"><span data-stu-id="45254-104">This topic describes the periodic tasks that are a necessary part of the process of managing credit limits for customers.</span></span>

## <a name="update-risk-scores"></a><span data-ttu-id="45254-105">Actualizar clasificaciones del riesgo</span><span class="sxs-lookup"><span data-stu-id="45254-105">Update risk scores</span></span>

<span data-ttu-id="45254-106">A medida que las empresas evolucionan y las circunstancias cambian, los riesgos de crédito para un cliente determinado también pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="45254-106">As businesses evolve and circumstances change, the credit risks for a given customer can also change.</span></span> <span data-ttu-id="45254-107">Para ayudar a mantener los límites de crédito apropiados para sus clientes debe revisar periódicamente los criterios para cada puntuación de riesgo y actualizar las puntuaciones para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="45254-107">To help maintain appropriate credit limits for your customers, you must periodically review the criteria for each risk score and update the scores for each customer.</span></span> <span data-ttu-id="45254-108">Puede actualizar las siguientes puntuaciones a través de la página **Actualizar puntajes de riesgo** (**Créditos y cobros \> Tareas periódicas \> Administración de crédito \> Actualizar puntuaciones de riesgo**).</span><span class="sxs-lookup"><span data-stu-id="45254-108">You can update the following scores by using the **Update risk scores** page (**Credit and collections \> Periodic tasks \> Credit management \> Update risk scores**).</span></span> <span data-ttu-id="45254-109">Todos los cálculos definidos por el usuario también se procesan.</span><span class="sxs-lookup"><span data-stu-id="45254-109">All user-defined calculations are also processed.</span></span>

- <span data-ttu-id="45254-110">**Media de días para efectuar el pago**: este puntuación es el número medio de días que un cliente tarda en pagar las facturas.</span><span class="sxs-lookup"><span data-stu-id="45254-110">**Average payment days** – This score is the average number of days that a customer takes to pay invoices.</span></span>
- <span data-ttu-id="45254-111">**Cliente desde**: esta puntuación es el número de años que un cliente ha sido cliente de su organización.</span><span class="sxs-lookup"><span data-stu-id="45254-111">**Customer since** – This score is the number of years that a customer has been a customer of your organization.</span></span>
- <span data-ttu-id="45254-112">**Opera desde**: esta puntuación es el número de años que lleva un cliente en el negocio.</span><span class="sxs-lookup"><span data-stu-id="45254-112">**In business since** – This score is the number of years that a customer has been in business.</span></span> <span data-ttu-id="45254-113">Utiliza el valor del campo **Inicio del negocio** en la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="45254-113">It uses the value of the **Business start** field on the **Customers** page.</span></span>
- <span data-ttu-id="45254-114">**Ventas diarias pendientes**: esta puntuación se basa en el saldo de clientes, los ingresos por ventas y la cantidad de días para el período de 12 meses anterior.</span><span class="sxs-lookup"><span data-stu-id="45254-114">**Days sales outstanding** – This score is based on the accounts receivable balance, sales revenue, and number of days for the previous 12-month period.</span></span>
- <span data-ttu-id="45254-115">**Saldo medio**: esta puntuación se basa en el saldo de clientes del período de 12 meses anterior.</span><span class="sxs-lookup"><span data-stu-id="45254-115">**Average balance** – This score is based on the accounts receivable balance for the previous 12-month period.</span></span>
- <span data-ttu-id="45254-116">**Grupo de administración de crédito**, **Estado de cuenta** y **País**: estas puntuaciones utilizan información del cliente.</span><span class="sxs-lookup"><span data-stu-id="45254-116">**Credit management group**, **Account status**, and **Country** – These scores use information from the customer.</span></span>

## <a name="update-customer-balance-statistics"></a><span data-ttu-id="45254-117">Actualizar las estadísticas de saldo del cliente</span><span class="sxs-lookup"><span data-stu-id="45254-117">Update customer balance statistics</span></span>

<span data-ttu-id="45254-118">Puede ejecutar el proceso **Actualizar las estadísticas de saldo del cliente** para actualizar el cálculo de estadísticas de saldo que se muestra en la página **Consulta de estadísticas de saldo**.</span><span class="sxs-lookup"><span data-stu-id="45254-118">You can run the **Update customer balance statistics** process to update the calculation of balance statistics that is shown on the **Balance statistics inquiry** page.</span></span> <span data-ttu-id="45254-119">Esta información se usa para calcular las puntuaciones de riesgo y los valores que se muestran en los cuadros de datos de estadísticas de crédito en la página **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="45254-119">This information is used to calculate risk scores and the values that are shown in the credit statistics FactBoxes on the **Customer** page.</span></span>

<span data-ttu-id="45254-120">Al ejecutar el proceso, actualiza las estadísticas de saldo de cliente para un solo cliente.</span><span class="sxs-lookup"><span data-stu-id="45254-120">When you run the process, it updates customer balance statistics for a single customer.</span></span> <span data-ttu-id="45254-121">Para configurar un trabajo por lotes con el fin de ejecutar el proceso para varios clientes, puede usar la página **Calcular estadísticas de saldo** (**Administración de crédito \> Tareas periódicas \> Calcular estadísticas de saldo**).</span><span class="sxs-lookup"><span data-stu-id="45254-121">To set up a batch job to run the process for multiple customers, you can use the **Calculate balance statistics** page (**Credit management \> Periodic tasks \> Calculate balance statistics**).</span></span>
