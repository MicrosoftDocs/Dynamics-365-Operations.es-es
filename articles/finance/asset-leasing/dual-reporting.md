---
title: Informes duales
description: Este tema le guía a través de un ejemplo que muestra cómo puede cumplir con los requisitos para la presentación de informes de la Norma Internacional de Información Financiera (IFRS) y la presentación de informes legales en el arrendamiento de activos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447791"
---
# <a name="dual-reporting"></a><span data-ttu-id="a6afc-103">Informes duales</span><span class="sxs-lookup"><span data-stu-id="a6afc-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6afc-104">Este tema le guía a través de un ejemplo que muestra cómo puede cumplir con los requisitos para la presentación de informes de la Norma Internacional de Información Financiera (IFRS) y la presentación de informes legales en el arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="a6afc-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="a6afc-105">Es necesaria la familiaridad con las capas de registro en Microsoft Dynamics 365 Finance y facilitará la comprensión del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a6afc-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="a6afc-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6afc-106">Example</span></span>

<span data-ttu-id="a6afc-107">El siguiente ejemplo contabiliza un arrendamiento según la información legal italiana utilizando tanto el método de base de efectivo como los métodos de informes IFRS.</span><span class="sxs-lookup"><span data-stu-id="a6afc-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="a6afc-108">La empresa debe establecer tres libros para dar cuenta tanto de los requisitos legales italianos como de los requisitos del IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="a6afc-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="a6afc-109">Se requiere un libro para IFRS 16, un libro para los requisitos legales y un libro para revertir automáticamente las contabilizaciones legales.</span><span class="sxs-lookup"><span data-stu-id="a6afc-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="a6afc-110">Los libros se configuran como se muestra en las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="a6afc-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="a6afc-111">**Libro IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="a6afc-111">**IFRS 16 book**</span></span>

<span data-ttu-id="a6afc-112">El libro IFRS 16 está configurado de manera que cumpla con el estándar contable IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="a6afc-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="a6afc-113">Todas las entradas que se publican en este libro se publicarán en una capa personalizada.</span><span class="sxs-lookup"><span data-stu-id="a6afc-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="a6afc-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="a6afc-114">Name</span></span>                                    | <span data-ttu-id="a6afc-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6afc-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="a6afc-116">Tipo de libro</span><span class="sxs-lookup"><span data-stu-id="a6afc-116">Book type</span></span>                               | <span data-ttu-id="a6afc-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="a6afc-117">IFRS 16</span></span>        |
| <span data-ttu-id="a6afc-118">Descripción del libro</span><span class="sxs-lookup"><span data-stu-id="a6afc-118">Book description</span></span>                        | <span data-ttu-id="a6afc-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="a6afc-119">IFRS 16</span></span>        |
| <span data-ttu-id="a6afc-120">Capa de registro</span><span class="sxs-lookup"><span data-stu-id="a6afc-120">Posting Layer</span></span>                           | <span data-ttu-id="a6afc-121">Capa personalizada 1</span><span class="sxs-lookup"><span data-stu-id="a6afc-121">Custom layer 1</span></span> |
| <span data-ttu-id="a6afc-122">Tipo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-122">Lease Type</span></span>                              | <span data-ttu-id="a6afc-123">Finance</span><span class="sxs-lookup"><span data-stu-id="a6afc-123">Finance</span></span>        |
| <span data-ttu-id="a6afc-124">Marco de contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-124">Accounting Framework</span></span>                    | <span data-ttu-id="a6afc-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="a6afc-125">IFRS 16</span></span>        |
| <span data-ttu-id="a6afc-126">Configuración del plazo del arrendamiento/vida útil</span><span class="sxs-lookup"><span data-stu-id="a6afc-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="a6afc-127">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-127">0.00</span></span>           |
| <span data-ttu-id="a6afc-128">Configuración del valor actual/valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="a6afc-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="a6afc-129">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-129">0.00</span></span>           |
| <span data-ttu-id="a6afc-130">Umbral a corto plazo</span><span class="sxs-lookup"><span data-stu-id="a6afc-130">Short-term threshold</span></span>                    | <span data-ttu-id="a6afc-131">12</span><span class="sxs-lookup"><span data-stu-id="a6afc-131">12</span></span>             |
| <span data-ttu-id="a6afc-132">Umbral de valor bajo</span><span class="sxs-lookup"><span data-stu-id="a6afc-132">Low Value Threshold</span></span>                     | <span data-ttu-id="a6afc-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-133">5,000.00</span></span>       |
| <span data-ttu-id="a6afc-134">Pagar a proveedor</span><span class="sxs-lookup"><span data-stu-id="a6afc-134">Pay to Vendor</span></span>                           | <span data-ttu-id="a6afc-135">N.º</span><span class="sxs-lookup"><span data-stu-id="a6afc-135">No</span></span>             |

<span data-ttu-id="a6afc-136">**Libro legal**</span><span class="sxs-lookup"><span data-stu-id="a6afc-136">**Statutory book**</span></span>

<span data-ttu-id="a6afc-137">El libro legal es un libro de efectivo en el que la empresa contabilizará los gastos de arrendamiento como la cantidad de efectivo que se paga cada mes por el alquiler.</span><span class="sxs-lookup"><span data-stu-id="a6afc-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="a6afc-138">Este libro no producirá un activo por derecho de uso (ROU) ni un pasivo por arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="a6afc-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="a6afc-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="a6afc-139">Name</span></span>                                    | <span data-ttu-id="a6afc-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6afc-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="a6afc-141">Tipo de libro</span><span class="sxs-lookup"><span data-stu-id="a6afc-141">Book type</span></span>                               | <span data-ttu-id="a6afc-142">Legal</span><span class="sxs-lookup"><span data-stu-id="a6afc-142">Statutory</span></span>   |
| <span data-ttu-id="a6afc-143">Descripción del libro</span><span class="sxs-lookup"><span data-stu-id="a6afc-143">Book description</span></span>                        | <span data-ttu-id="a6afc-144">GAAP local</span><span class="sxs-lookup"><span data-stu-id="a6afc-144">Local GAAP</span></span>  |
| <span data-ttu-id="a6afc-145">Capa de registro</span><span class="sxs-lookup"><span data-stu-id="a6afc-145">Posting Layer</span></span>                           | <span data-ttu-id="a6afc-146">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-146">Current</span></span>     |
| <span data-ttu-id="a6afc-147">Tipo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-147">Lease Type</span></span>                              | <span data-ttu-id="a6afc-148">Automático</span><span class="sxs-lookup"><span data-stu-id="a6afc-148">Automatic</span></span>   |
| <span data-ttu-id="a6afc-149">Marco de contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-149">Accounting Framework</span></span>                    | <span data-ttu-id="a6afc-150">Base en efectivo</span><span class="sxs-lookup"><span data-stu-id="a6afc-150">Cash basis</span></span>  |
| <span data-ttu-id="a6afc-151">Configuración del plazo del arrendamiento/vida útil</span><span class="sxs-lookup"><span data-stu-id="a6afc-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="a6afc-152">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-152">0.00</span></span>        |
| <span data-ttu-id="a6afc-153">Configuración del valor actual/valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="a6afc-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="a6afc-154">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-154">0.00</span></span>        |
| <span data-ttu-id="a6afc-155">Umbral a corto plazo</span><span class="sxs-lookup"><span data-stu-id="a6afc-155">Short-term threshold</span></span>                    | <span data-ttu-id="a6afc-156">0</span><span class="sxs-lookup"><span data-stu-id="a6afc-156">0</span></span>           |
| <span data-ttu-id="a6afc-157">Umbral de valor bajo</span><span class="sxs-lookup"><span data-stu-id="a6afc-157">Low Value Threshold</span></span>                     | <span data-ttu-id="a6afc-158">0</span><span class="sxs-lookup"><span data-stu-id="a6afc-158">0</span></span>           |
| <span data-ttu-id="a6afc-159">Pagar a proveedor</span><span class="sxs-lookup"><span data-stu-id="a6afc-159">Pay to Vendor</span></span>                           | <span data-ttu-id="a6afc-160">N.º</span><span class="sxs-lookup"><span data-stu-id="a6afc-160">No</span></span>          |

<span data-ttu-id="a6afc-161">**Libro de revocación legal**</span><span class="sxs-lookup"><span data-stu-id="a6afc-161">**Statutory reversal book**</span></span>

<span data-ttu-id="a6afc-162">El libro de revocación legal se configura de la misma manera que el libro legal.</span><span class="sxs-lookup"><span data-stu-id="a6afc-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="a6afc-163">Nombre</span><span class="sxs-lookup"><span data-stu-id="a6afc-163">Name</span></span>                                    | <span data-ttu-id="a6afc-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6afc-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="a6afc-165">Tipo de libro</span><span class="sxs-lookup"><span data-stu-id="a6afc-165">Book type</span></span>                               | <span data-ttu-id="a6afc-166">Legal: revocación</span><span class="sxs-lookup"><span data-stu-id="a6afc-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="a6afc-167">Descripción del libro</span><span class="sxs-lookup"><span data-stu-id="a6afc-167">Book description</span></span>                        | <span data-ttu-id="a6afc-168">Libro para revocar el libro legal</span><span class="sxs-lookup"><span data-stu-id="a6afc-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="a6afc-169">Capa de registro</span><span class="sxs-lookup"><span data-stu-id="a6afc-169">Posting Layer</span></span>                           | <span data-ttu-id="a6afc-170">Capa personalizada 1</span><span class="sxs-lookup"><span data-stu-id="a6afc-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="a6afc-171">Tipo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-171">Lease Type</span></span>                              | <span data-ttu-id="a6afc-172">Automático</span><span class="sxs-lookup"><span data-stu-id="a6afc-172">Automatic</span></span>                      |
| <span data-ttu-id="a6afc-173">Marco de contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-173">Accounting Framework</span></span>                    | <span data-ttu-id="a6afc-174">Base en efectivo</span><span class="sxs-lookup"><span data-stu-id="a6afc-174">Cash basis</span></span>                     |
| <span data-ttu-id="a6afc-175">Configuración del plazo del arrendamiento/vida útil</span><span class="sxs-lookup"><span data-stu-id="a6afc-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="a6afc-176">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-176">0.00</span></span>                           |
| <span data-ttu-id="a6afc-177">Configuración del valor actual/valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="a6afc-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="a6afc-178">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-178">0.00</span></span>                           |
| <span data-ttu-id="a6afc-179">Umbral a corto plazo</span><span class="sxs-lookup"><span data-stu-id="a6afc-179">Short-term threshold</span></span>                    | <span data-ttu-id="a6afc-180">0</span><span class="sxs-lookup"><span data-stu-id="a6afc-180">0</span></span>                              |
| <span data-ttu-id="a6afc-181">Umbral de valor bajo</span><span class="sxs-lookup"><span data-stu-id="a6afc-181">Low Value Threshold</span></span>                     | <span data-ttu-id="a6afc-182">0</span><span class="sxs-lookup"><span data-stu-id="a6afc-182">0</span></span>                              |
| <span data-ttu-id="a6afc-183">Pagar a proveedor</span><span class="sxs-lookup"><span data-stu-id="a6afc-183">Pay to Vendor</span></span>                           | <span data-ttu-id="a6afc-184">N.º</span><span class="sxs-lookup"><span data-stu-id="a6afc-184">No</span></span>                             |

<span data-ttu-id="a6afc-185">Para este ejemplo, se ha creado un arrendamiento con la siguiente configuración en las pestañas **General** y **Líneas de programación de pagos**.</span><span class="sxs-lookup"><span data-stu-id="a6afc-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="a6afc-186">**Pestaña General**</span><span class="sxs-lookup"><span data-stu-id="a6afc-186">**General tab**</span></span>

| <span data-ttu-id="a6afc-187">Campo</span><span class="sxs-lookup"><span data-stu-id="a6afc-187">Field</span></span>                      | <span data-ttu-id="a6afc-188">Valor</span><span class="sxs-lookup"><span data-stu-id="a6afc-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="a6afc-189">Tipo de interés incremental del endeudamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-189">Incremental borrowing rate</span></span> | <span data-ttu-id="a6afc-190">5%</span><span class="sxs-lookup"><span data-stu-id="a6afc-190">5%</span></span>               |
| <span data-ttu-id="a6afc-191">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="a6afc-191">Commencement date</span></span>          | <span data-ttu-id="a6afc-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="a6afc-192">1/1/2020</span></span>         |
| <span data-ttu-id="a6afc-193">Grupo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-193">Lease group</span></span>                | <span data-ttu-id="a6afc-194">Edificios</span><span class="sxs-lookup"><span data-stu-id="a6afc-194">Buildings</span></span>        |
| <span data-ttu-id="a6afc-195">Proveedor</span><span class="sxs-lookup"><span data-stu-id="a6afc-195">Vendor</span></span>                     | <span data-ttu-id="a6afc-196">1001</span><span class="sxs-lookup"><span data-stu-id="a6afc-196">1001</span></span>             |
| <span data-ttu-id="a6afc-197">Valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="a6afc-197">Fair value of the asset</span></span>    | <span data-ttu-id="a6afc-198">245,000</span><span class="sxs-lookup"><span data-stu-id="a6afc-198">245,000</span></span>          |
| <span data-ttu-id="a6afc-199">Vida útil del activo</span><span class="sxs-lookup"><span data-stu-id="a6afc-199">Asset useful life</span></span>          | <span data-ttu-id="a6afc-200">120</span><span class="sxs-lookup"><span data-stu-id="a6afc-200">120</span></span>              |
| <span data-ttu-id="a6afc-201">Tipo de anualidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-201">Annuity type</span></span>               | <span data-ttu-id="a6afc-202">Anualidad ordinaria</span><span class="sxs-lookup"><span data-stu-id="a6afc-202">Ordinary annuity</span></span> |
| <span data-ttu-id="a6afc-203">Intervalo de composición</span><span class="sxs-lookup"><span data-stu-id="a6afc-203">Compounding interval</span></span>       | <span data-ttu-id="a6afc-204">Mensual</span><span class="sxs-lookup"><span data-stu-id="a6afc-204">Monthly</span></span>          |

<span data-ttu-id="a6afc-205">**Pestaña Líneas de programación de pagos**</span><span class="sxs-lookup"><span data-stu-id="a6afc-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="a6afc-206">Campo</span><span class="sxs-lookup"><span data-stu-id="a6afc-206">Field</span></span>             | <span data-ttu-id="a6afc-207">Valor</span><span class="sxs-lookup"><span data-stu-id="a6afc-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="a6afc-208">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="a6afc-208">Start date</span></span>        | <span data-ttu-id="a6afc-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="a6afc-209">1/1/2020</span></span>   |
| <span data-ttu-id="a6afc-210">Intervalo del período</span><span class="sxs-lookup"><span data-stu-id="a6afc-210">Period interval</span></span>   | <span data-ttu-id="a6afc-211">Meses</span><span class="sxs-lookup"><span data-stu-id="a6afc-211">Months</span></span>     |
| <span data-ttu-id="a6afc-212">Períodos</span><span class="sxs-lookup"><span data-stu-id="a6afc-212">Periods</span></span>           | <span data-ttu-id="a6afc-213">24</span><span class="sxs-lookup"><span data-stu-id="a6afc-213">24</span></span>         |
| <span data-ttu-id="a6afc-214">Fecha final</span><span class="sxs-lookup"><span data-stu-id="a6afc-214">End date</span></span>          | <span data-ttu-id="a6afc-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="a6afc-215">12/31/2020</span></span> |
| <span data-ttu-id="a6afc-216">Frecuencia de pago</span><span class="sxs-lookup"><span data-stu-id="a6afc-216">Payment frequency</span></span> | <span data-ttu-id="a6afc-217">Mensual</span><span class="sxs-lookup"><span data-stu-id="a6afc-217">Monthly</span></span>    |
| <span data-ttu-id="a6afc-218">Importe del pago</span><span class="sxs-lookup"><span data-stu-id="a6afc-218">Payment amount</span></span>    | <span data-ttu-id="a6afc-219">1.000</span><span class="sxs-lookup"><span data-stu-id="a6afc-219">1,000</span></span>      |

<span data-ttu-id="a6afc-220">Para contabilizar este arrendamiento en dos marcos, use una capa de registro actual y una capa de registro personalizada.</span><span class="sxs-lookup"><span data-stu-id="a6afc-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="a6afc-221">La siguiente tabla muestra un ejemplo de cada entrada de diario que requiere representar correctamente las finanzas bajo cada estándar de informes.</span><span class="sxs-lookup"><span data-stu-id="a6afc-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="a6afc-222">Posteriormente se proporciona una descripción detallada de cada movimiento del diario correspondiente al primer mes del arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="a6afc-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="a6afc-223">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="a6afc-224">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6afc-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="a6afc-225">Libro legal (capa actual)</span><span class="sxs-lookup"><span data-stu-id="a6afc-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="a6afc-226">Total de la capa actual</span><span class="sxs-lookup"><span data-stu-id="a6afc-226">Current layer total</span></span></th>
<th><span data-ttu-id="a6afc-227">Libro de revocación (capa personalizada)</span><span class="sxs-lookup"><span data-stu-id="a6afc-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="a6afc-228">Libro IFRS 16 (capa personalizada)</span><span class="sxs-lookup"><span data-stu-id="a6afc-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="a6afc-229">Capa actual + Total de capa personalizada</span><span class="sxs-lookup"><span data-stu-id="a6afc-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a6afc-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="a6afc-230">JE-100</span></span></th>
<th><span data-ttu-id="a6afc-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="a6afc-231">JE-110</span></span></th>
<th><span data-ttu-id="a6afc-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="a6afc-232">JE-120</span></span></th>
<th><span data-ttu-id="a6afc-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="a6afc-233">JE-130</span></span></th>
<th><span data-ttu-id="a6afc-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="a6afc-234">JE-140</span></span></th>
<th><span data-ttu-id="a6afc-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="a6afc-235">JE-150</span></span></th>
<th><span data-ttu-id="a6afc-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="a6afc-236">JE-160</span></span></th>
<th><span data-ttu-id="a6afc-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="a6afc-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a6afc-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a6afc-246">1</span><span class="sxs-lookup"><span data-stu-id="a6afc-246">1</span></span></td>
<td><span data-ttu-id="a6afc-247">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-247">Lease expense</span></span></td>
<td><span data-ttu-id="a6afc-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-249">1,000.00</span></span></td>
<td><span data-ttu-id="a6afc-250">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-251">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-252">2</span><span class="sxs-lookup"><span data-stu-id="a6afc-252">2</span></span></td>
<td><span data-ttu-id="a6afc-253">Comisión bancaria</span><span class="sxs-lookup"><span data-stu-id="a6afc-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-254">3.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-255">3.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-256">3.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-257">3</span><span class="sxs-lookup"><span data-stu-id="a6afc-257">3</span></span></td>
<td><span data-ttu-id="a6afc-258">Gasto de iVA</span><span class="sxs-lookup"><span data-stu-id="a6afc-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-259">5.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-260">5.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-261">5.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-262">4</span><span class="sxs-lookup"><span data-stu-id="a6afc-262">4</span></span></td>
<td><span data-ttu-id="a6afc-263">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="a6afc-263">Clearing account</span></span></td>
<td><span data-ttu-id="a6afc-264">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-264">-1,000.00</span></span></td>
<td><span data-ttu-id="a6afc-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-266">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-266">0.00</span></span></td>
<td><span data-ttu-id="a6afc-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-268">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-269">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-270">5</span><span class="sxs-lookup"><span data-stu-id="a6afc-270">5</span></span></td>
<td><span data-ttu-id="a6afc-271">Proveedores</span><span class="sxs-lookup"><span data-stu-id="a6afc-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-272">-1,008.00</span></span></td>
<td><span data-ttu-id="a6afc-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-273">1,008.00</span></span></td>
<td><span data-ttu-id="a6afc-274">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-275">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-276">6</span><span class="sxs-lookup"><span data-stu-id="a6afc-276">6</span></span></td>
<td><span data-ttu-id="a6afc-277">Activo por derecho de uso</span><span class="sxs-lookup"><span data-stu-id="a6afc-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-278">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="a6afc-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-281">7</span><span class="sxs-lookup"><span data-stu-id="a6afc-281">7</span></span></td>
<td><span data-ttu-id="a6afc-282">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="a6afc-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-283">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-284">-22,794.00</span></span></td>
<td><span data-ttu-id="a6afc-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-285">1,000.00</span></span></td>
<td><span data-ttu-id="a6afc-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="a6afc-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="a6afc-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-288">8</span><span class="sxs-lookup"><span data-stu-id="a6afc-288">8</span></span></td>
<td><span data-ttu-id="a6afc-289">Gastos de intereses</span><span class="sxs-lookup"><span data-stu-id="a6afc-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-290">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-291">94.97</span><span class="sxs-lookup"><span data-stu-id="a6afc-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-292">94.97</span><span class="sxs-lookup"><span data-stu-id="a6afc-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-293">9</span><span class="sxs-lookup"><span data-stu-id="a6afc-293">9</span></span></td>
<td><span data-ttu-id="a6afc-294">Efectivo</span><span class="sxs-lookup"><span data-stu-id="a6afc-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-295">-1,008.00</span></span></td>
<td><span data-ttu-id="a6afc-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-298">10</span><span class="sxs-lookup"><span data-stu-id="a6afc-298">10</span></span></td>
<td><span data-ttu-id="a6afc-299">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="a6afc-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-300">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-301">949.75</span><span class="sxs-lookup"><span data-stu-id="a6afc-301">949.75</span></span></td>
<td><span data-ttu-id="a6afc-302">949.75</span><span class="sxs-lookup"><span data-stu-id="a6afc-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-303">11</span><span class="sxs-lookup"><span data-stu-id="a6afc-303">11</span></span></td>
<td><span data-ttu-id="a6afc-304">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="a6afc-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-305">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="a6afc-306">-949.75</span></span></td>
<td><span data-ttu-id="a6afc-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="a6afc-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a6afc-308">Como muestra la tabla anterior, se requieren tres libros para informar tanto según los informes legales como según los informes IFRS.</span><span class="sxs-lookup"><span data-stu-id="a6afc-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="a6afc-309">El libro legal registra el pago del arrendamiento de acuerdo con las reglas para la contabilidad de efectivo en la capa actual.</span><span class="sxs-lookup"><span data-stu-id="a6afc-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="a6afc-310">El libro de revocación legal revierte los asientos del diario legal.</span><span class="sxs-lookup"><span data-stu-id="a6afc-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="a6afc-311">El libro IFRS 16 crea los asientos de diario que se requieren según IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="a6afc-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="a6afc-312">Debe introducir cada arrendamiento solo una vez.</span><span class="sxs-lookup"><span data-stu-id="a6afc-312">You must enter a lease only one time.</span></span> <span data-ttu-id="a6afc-313">A continuación, puede abrir la página **Libros** para ver todos los libros asociados con el arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="a6afc-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="a6afc-314">Cuando crea los libros, los tres deben estar asociados con el mismo registro de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="a6afc-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="a6afc-315">La primera entrada de diario registra el gasto de arrendamiento en el libro legal.</span><span class="sxs-lookup"><span data-stu-id="a6afc-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="a6afc-316">Puede crear los pagos en un lote o seleccionando la programación de pagos en el libro legal.</span><span class="sxs-lookup"><span data-stu-id="a6afc-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="a6afc-317">Para este ejemplo, se produce el siguiente movimiento de diario para el libro legal a partir de la programación de pagos.</span><span class="sxs-lookup"><span data-stu-id="a6afc-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="a6afc-318">Pago de arrendamiento - 31/1/2020 - JE 100</span><span class="sxs-lookup"><span data-stu-id="a6afc-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="a6afc-319">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-319">Account type</span></span> | <span data-ttu-id="a6afc-320">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-320">Account number</span></span> | <span data-ttu-id="a6afc-321">Capa</span><span class="sxs-lookup"><span data-stu-id="a6afc-321">Layer</span></span>   | <span data-ttu-id="a6afc-322">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-322">Account description</span></span> | <span data-ttu-id="a6afc-323">Débito</span><span class="sxs-lookup"><span data-stu-id="a6afc-323">Debit</span></span>    | <span data-ttu-id="a6afc-324">Crédito</span><span class="sxs-lookup"><span data-stu-id="a6afc-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="a6afc-325">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-325">Ledger</span></span>       | <span data-ttu-id="a6afc-326">1</span><span class="sxs-lookup"><span data-stu-id="a6afc-326">1</span></span>              | <span data-ttu-id="a6afc-327">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-327">Current</span></span> | <span data-ttu-id="a6afc-328">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-328">Lease expense</span></span>       | <span data-ttu-id="a6afc-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-329">1,000.00</span></span> |          |
| <span data-ttu-id="a6afc-330">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-330">Ledger</span></span>       | <span data-ttu-id="a6afc-331">4</span><span class="sxs-lookup"><span data-stu-id="a6afc-331">4</span></span>              | <span data-ttu-id="a6afc-332">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-332">Current</span></span> | <span data-ttu-id="a6afc-333">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="a6afc-333">Clearing account</span></span>    |          | <span data-ttu-id="a6afc-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-334">1,000.00</span></span> |

<span data-ttu-id="a6afc-335">Un empleado de la sección de proveedores utiliza la funcionalidad estándar de Dynamics 365 para crear una factura para pagar el arrendamiento por fuera del arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="a6afc-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="a6afc-336">Sin embargo, en lugar de seleccionar **Gastos de arrendamiento** como cuenta de débito, el empleado de la sección de proveedores selecciona una cuenta de compensación para generar la siguiente entrada.</span><span class="sxs-lookup"><span data-stu-id="a6afc-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="a6afc-337">Proceso AP - 31/1/2020 - JE 110</span><span class="sxs-lookup"><span data-stu-id="a6afc-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="a6afc-338">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-338">Account type</span></span> | <span data-ttu-id="a6afc-339">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-339">Account number</span></span> | <span data-ttu-id="a6afc-340">Capa</span><span class="sxs-lookup"><span data-stu-id="a6afc-340">Layer</span></span>   | <span data-ttu-id="a6afc-341">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-341">Account description</span></span> | <span data-ttu-id="a6afc-342">Débito</span><span class="sxs-lookup"><span data-stu-id="a6afc-342">Debit</span></span>    | <span data-ttu-id="a6afc-343">Crédito</span><span class="sxs-lookup"><span data-stu-id="a6afc-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="a6afc-344">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-344">Ledger</span></span>       | <span data-ttu-id="a6afc-345">4</span><span class="sxs-lookup"><span data-stu-id="a6afc-345">4</span></span>              | <span data-ttu-id="a6afc-346">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-346">Current</span></span> | <span data-ttu-id="a6afc-347">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="a6afc-347">Clearing account</span></span>    | <span data-ttu-id="a6afc-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-348">1,000.00</span></span> |          |
| <span data-ttu-id="a6afc-349">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-349">Ledger</span></span>       | <span data-ttu-id="a6afc-350">2</span><span class="sxs-lookup"><span data-stu-id="a6afc-350">2</span></span>              | <span data-ttu-id="a6afc-351">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-351">Current</span></span> | <span data-ttu-id="a6afc-352">Comisión bancaria</span><span class="sxs-lookup"><span data-stu-id="a6afc-352">Bank fee</span></span>            | <span data-ttu-id="a6afc-353">3.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-353">3.00</span></span>     |          |
| <span data-ttu-id="a6afc-354">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-354">Ledger</span></span>       | <span data-ttu-id="a6afc-355">3</span><span class="sxs-lookup"><span data-stu-id="a6afc-355">3</span></span>              | <span data-ttu-id="a6afc-356">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-356">Current</span></span> | <span data-ttu-id="a6afc-357">Gasto de iVA</span><span class="sxs-lookup"><span data-stu-id="a6afc-357">VAT expense</span></span>         | <span data-ttu-id="a6afc-358">5.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-358">5.00</span></span>     |          |
| <span data-ttu-id="a6afc-359">Proveedor</span><span class="sxs-lookup"><span data-stu-id="a6afc-359">Vendor</span></span>       | <span data-ttu-id="a6afc-360">5</span><span class="sxs-lookup"><span data-stu-id="a6afc-360">5</span></span>              | <span data-ttu-id="a6afc-361">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-361">Current</span></span> | <span data-ttu-id="a6afc-362">Proveedores</span><span class="sxs-lookup"><span data-stu-id="a6afc-362">Accounts payable</span></span>    |          | <span data-ttu-id="a6afc-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-363">1,008.00</span></span> |

<span data-ttu-id="a6afc-364">Cuando se envía el estado de cuenta al proveedor, se sigue el proceso de pago habitual.</span><span class="sxs-lookup"><span data-stu-id="a6afc-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="a6afc-365">Durante este proceso, se genera la siguiente entrada de diario.</span><span class="sxs-lookup"><span data-stu-id="a6afc-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="a6afc-366">Pago en efectivo - 31/1/2020 - JE 120</span><span class="sxs-lookup"><span data-stu-id="a6afc-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="a6afc-367">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-367">Account type</span></span> | <span data-ttu-id="a6afc-368">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-368">Account number</span></span> | <span data-ttu-id="a6afc-369">Capa</span><span class="sxs-lookup"><span data-stu-id="a6afc-369">Layer</span></span>   | <span data-ttu-id="a6afc-370">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-370">Account description</span></span> | <span data-ttu-id="a6afc-371">Débito</span><span class="sxs-lookup"><span data-stu-id="a6afc-371">Debit</span></span>    | <span data-ttu-id="a6afc-372">Crédito</span><span class="sxs-lookup"><span data-stu-id="a6afc-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="a6afc-373">Proveedor</span><span class="sxs-lookup"><span data-stu-id="a6afc-373">Vendor</span></span>       | <span data-ttu-id="a6afc-374">5</span><span class="sxs-lookup"><span data-stu-id="a6afc-374">5</span></span>              | <span data-ttu-id="a6afc-375">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-375">Current</span></span> | <span data-ttu-id="a6afc-376">Proveedores</span><span class="sxs-lookup"><span data-stu-id="a6afc-376">Accounts Payable</span></span>    | <span data-ttu-id="a6afc-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-377">1,008.00</span></span> |          |
| <span data-ttu-id="a6afc-378">Banco</span><span class="sxs-lookup"><span data-stu-id="a6afc-378">Bank</span></span>         | <span data-ttu-id="a6afc-379">9</span><span class="sxs-lookup"><span data-stu-id="a6afc-379">9</span></span>              | <span data-ttu-id="a6afc-380">Actuales</span><span class="sxs-lookup"><span data-stu-id="a6afc-380">Current</span></span> | <span data-ttu-id="a6afc-381">Efectivo</span><span class="sxs-lookup"><span data-stu-id="a6afc-381">Cash</span></span>                |          | <span data-ttu-id="a6afc-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-382">1,008.00</span></span> |

<span data-ttu-id="a6afc-383">En este punto, ha contabilizado completamente este contrato de arrendamiento según los requisitos de informes legales y puede generar un balance de prueba utilizando la capa actual.</span><span class="sxs-lookup"><span data-stu-id="a6afc-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="a6afc-384">El sistema devuelve un saldo de comprobación que tiene las siguientes cifras.</span><span class="sxs-lookup"><span data-stu-id="a6afc-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="a6afc-385">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="a6afc-386">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6afc-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="a6afc-387">Libro legal (capa actual)</span><span class="sxs-lookup"><span data-stu-id="a6afc-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="a6afc-388">Total de la capa actual</span><span class="sxs-lookup"><span data-stu-id="a6afc-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a6afc-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="a6afc-389">JE-100</span></span></th>
<th><span data-ttu-id="a6afc-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="a6afc-390">JE-110</span></span></th>
<th><span data-ttu-id="a6afc-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="a6afc-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a6afc-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a6afc-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a6afc-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a6afc-395">1</span><span class="sxs-lookup"><span data-stu-id="a6afc-395">1</span></span></td>
<td><span data-ttu-id="a6afc-396">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-396">Lease expense</span></span></td>
<td><span data-ttu-id="a6afc-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-399">2</span><span class="sxs-lookup"><span data-stu-id="a6afc-399">2</span></span></td>
<td><span data-ttu-id="a6afc-400">Comisión bancaria</span><span class="sxs-lookup"><span data-stu-id="a6afc-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-401">3.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-402">3.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-403">3</span><span class="sxs-lookup"><span data-stu-id="a6afc-403">3</span></span></td>
<td><span data-ttu-id="a6afc-404">Gasto de iVA</span><span class="sxs-lookup"><span data-stu-id="a6afc-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-405">5.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-406">5.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-407">4</span><span class="sxs-lookup"><span data-stu-id="a6afc-407">4</span></span></td>
<td><span data-ttu-id="a6afc-408">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="a6afc-408">Clearing account</span></span></td>
<td><span data-ttu-id="a6afc-409">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-409">-1,000.00</span></span></td>
<td><span data-ttu-id="a6afc-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-411">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-412">5</span><span class="sxs-lookup"><span data-stu-id="a6afc-412">5</span></span></td>
<td><span data-ttu-id="a6afc-413">Proveedores</span><span class="sxs-lookup"><span data-stu-id="a6afc-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="a6afc-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-414">-1,008.00</span></span></td>
<td><span data-ttu-id="a6afc-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-415">1,008.00</span></span></td>
<td><span data-ttu-id="a6afc-416">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-417">6</span><span class="sxs-lookup"><span data-stu-id="a6afc-417">6</span></span></td>
<td><span data-ttu-id="a6afc-418">Activo por derecho de uso</span><span class="sxs-lookup"><span data-stu-id="a6afc-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-419">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-420">7</span><span class="sxs-lookup"><span data-stu-id="a6afc-420">7</span></span></td>
<td><span data-ttu-id="a6afc-421">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="a6afc-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-422">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-423">8</span><span class="sxs-lookup"><span data-stu-id="a6afc-423">8</span></span></td>
<td><span data-ttu-id="a6afc-424">Gastos de intereses</span><span class="sxs-lookup"><span data-stu-id="a6afc-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-425">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-426">9</span><span class="sxs-lookup"><span data-stu-id="a6afc-426">9</span></span></td>
<td><span data-ttu-id="a6afc-427">Efectivo</span><span class="sxs-lookup"><span data-stu-id="a6afc-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-428">-1,008.00</span></span></td>
<td><span data-ttu-id="a6afc-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-430">10</span><span class="sxs-lookup"><span data-stu-id="a6afc-430">10</span></span></td>
<td><span data-ttu-id="a6afc-431">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="a6afc-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-432">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a6afc-433">11</span><span class="sxs-lookup"><span data-stu-id="a6afc-433">11</span></span></td>
<td><span data-ttu-id="a6afc-434">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="a6afc-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a6afc-435">0,00</span><span class="sxs-lookup"><span data-stu-id="a6afc-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a6afc-436">Si desea utilizar las cifras IFRS 16 para ejecutar el mismo saldo de comprobación, los asientos del diario contable legal deben revertirse y los asientos del diario de IFRS 16 deben contabilizarse.</span><span class="sxs-lookup"><span data-stu-id="a6afc-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="a6afc-437">Para revertir las entradas de diario legales, este ejemplo incluye un libro de revocación legal que tiene la misma configuración que el libro legal pero un perfil de contabilización opuesto.</span><span class="sxs-lookup"><span data-stu-id="a6afc-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="a6afc-438">Por ejemplo, el libro legal *adeuda* una cuenta de gastos de arrendamiento, pero el libro de revocación *abona* esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="a6afc-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="a6afc-439">Estas relaciones se definen fácilmente en las cuentas de contabilización de arrendamiento de activos en la página **Parámetros de arrendamiento de activos** (**Arrendamiento de activos \> Configurar \> Parámetros de arrendamiento de activos**).</span><span class="sxs-lookup"><span data-stu-id="a6afc-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="a6afc-440">Cuando se utiliza el mismo proceso que se utilizó para el libro legal para el libro de revocación, se produce el siguiente asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="a6afc-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="a6afc-441">La diferencia es que el libro de revocación registra las entradas de revocación del libro legal.</span><span class="sxs-lookup"><span data-stu-id="a6afc-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="a6afc-442">Las entradas de revocación también se realizan en la capa personalizada.</span><span class="sxs-lookup"><span data-stu-id="a6afc-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="a6afc-443">Cuando se ejecuta un saldo de comprobación en la capa actual, las entradas del diario de revocación no se incluyen.</span><span class="sxs-lookup"><span data-stu-id="a6afc-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="a6afc-444">Pago de arrendamiento - 31/1/2020 - JE 130</span><span class="sxs-lookup"><span data-stu-id="a6afc-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="a6afc-445">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-445">Account type</span></span> | <span data-ttu-id="a6afc-446">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-446">Account number</span></span> | <span data-ttu-id="a6afc-447">Capa</span><span class="sxs-lookup"><span data-stu-id="a6afc-447">Layer</span></span>  | <span data-ttu-id="a6afc-448">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-448">Account description</span></span> | <span data-ttu-id="a6afc-449">Débito</span><span class="sxs-lookup"><span data-stu-id="a6afc-449">Debit</span></span>    | <span data-ttu-id="a6afc-450">Crédito</span><span class="sxs-lookup"><span data-stu-id="a6afc-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="a6afc-451">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-451">Ledger</span></span>       | <span data-ttu-id="a6afc-452">4</span><span class="sxs-lookup"><span data-stu-id="a6afc-452">4</span></span>              | <span data-ttu-id="a6afc-453">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-453">Custom</span></span> | <span data-ttu-id="a6afc-454">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="a6afc-454">Clearing account</span></span>    | <span data-ttu-id="a6afc-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-455">1,000.00</span></span> |          |
| <span data-ttu-id="a6afc-456">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-456">Ledger</span></span>       | <span data-ttu-id="a6afc-457">1</span><span class="sxs-lookup"><span data-stu-id="a6afc-457">1</span></span>              | <span data-ttu-id="a6afc-458">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-458">Custom</span></span> | <span data-ttu-id="a6afc-459">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-459">Lease expense</span></span>       |          | <span data-ttu-id="a6afc-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-460">1,000.00</span></span> |

<span data-ttu-id="a6afc-461">Ahora que ha eliminado las entradas del diario legal, registrará todas las entradas de diario que requiere IFRS 16 en el libro de IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="a6afc-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="a6afc-462">Estas entradas incluyen el reconocimiento inicial del activo por derecho de uso y el pasivo de ROU, y el registro de intereses y depreciación.</span><span class="sxs-lookup"><span data-stu-id="a6afc-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="a6afc-463">Reconocimiento inicial - 1/1/2020 - JE 140</span><span class="sxs-lookup"><span data-stu-id="a6afc-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="a6afc-464">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-464">Account type</span></span> | <span data-ttu-id="a6afc-465">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-465">Account number</span></span> | <span data-ttu-id="a6afc-466">Capa</span><span class="sxs-lookup"><span data-stu-id="a6afc-466">Layer</span></span>  | <span data-ttu-id="a6afc-467">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-467">Account description</span></span>      | <span data-ttu-id="a6afc-468">Débito</span><span class="sxs-lookup"><span data-stu-id="a6afc-468">Debit</span></span>     | <span data-ttu-id="a6afc-469">Crédito</span><span class="sxs-lookup"><span data-stu-id="a6afc-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="a6afc-470">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-470">Ledger</span></span>       | <span data-ttu-id="a6afc-471">6</span><span class="sxs-lookup"><span data-stu-id="a6afc-471">6</span></span>              | <span data-ttu-id="a6afc-472">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-472">Custom</span></span> | <span data-ttu-id="a6afc-473">Activo por derecho de uso</span><span class="sxs-lookup"><span data-stu-id="a6afc-473">ROU Asset</span></span>                | <span data-ttu-id="a6afc-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="a6afc-474">22,793.90</span></span> |           |
| <span data-ttu-id="a6afc-475">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-475">Ledger</span></span>       | <span data-ttu-id="a6afc-476">7</span><span class="sxs-lookup"><span data-stu-id="a6afc-476">7</span></span>              | <span data-ttu-id="a6afc-477">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-477">Custom</span></span> | <span data-ttu-id="a6afc-478">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="a6afc-478">Finance lease obligation</span></span> |           | <span data-ttu-id="a6afc-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="a6afc-479">22,793.90</span></span> |

<span data-ttu-id="a6afc-480">El pago del arrendamiento se contabiliza como los demás pagos de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="a6afc-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="a6afc-481">La razón para utilizar la cuenta de compensación es garantizar que el efectivo se abone solo una vez.</span><span class="sxs-lookup"><span data-stu-id="a6afc-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="a6afc-482">Pago de arrendamiento - 31/1/2020 - JE 150</span><span class="sxs-lookup"><span data-stu-id="a6afc-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="a6afc-483">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-483">Account type</span></span> | <span data-ttu-id="a6afc-484">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-484">Account number</span></span> | <span data-ttu-id="a6afc-485">Capa</span><span class="sxs-lookup"><span data-stu-id="a6afc-485">Layer</span></span>  | <span data-ttu-id="a6afc-486">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-486">Account description</span></span>      | <span data-ttu-id="a6afc-487">Débito</span><span class="sxs-lookup"><span data-stu-id="a6afc-487">Debit</span></span>    | <span data-ttu-id="a6afc-488">Crédito</span><span class="sxs-lookup"><span data-stu-id="a6afc-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="a6afc-489">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-489">Ledger</span></span>       | <span data-ttu-id="a6afc-490">7</span><span class="sxs-lookup"><span data-stu-id="a6afc-490">7</span></span>              | <span data-ttu-id="a6afc-491">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-491">Custom</span></span> | <span data-ttu-id="a6afc-492">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="a6afc-492">Finance lease obligation</span></span> | <span data-ttu-id="a6afc-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-493">1,000.00</span></span> |          |
| <span data-ttu-id="a6afc-494">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-494">Ledger</span></span>       | <span data-ttu-id="a6afc-495">4</span><span class="sxs-lookup"><span data-stu-id="a6afc-495">4</span></span>              | <span data-ttu-id="a6afc-496">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-496">Custom</span></span> | <span data-ttu-id="a6afc-497">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="a6afc-497">Clearing account</span></span>         |          | <span data-ttu-id="a6afc-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-498">1,000.00</span></span> |

<span data-ttu-id="a6afc-499">El asiento de diario de gasto por intereses se genera a partir de la programación de amortización del pasivo.</span><span class="sxs-lookup"><span data-stu-id="a6afc-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="a6afc-500">Gastos de intereses - 31/1/2020 - JE 160</span><span class="sxs-lookup"><span data-stu-id="a6afc-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="a6afc-501">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-501">Account type</span></span> | <span data-ttu-id="a6afc-502">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-502">Account number</span></span> | <span data-ttu-id="a6afc-503">Capa</span><span class="sxs-lookup"><span data-stu-id="a6afc-503">Layer</span></span>  | <span data-ttu-id="a6afc-504">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-504">Account description</span></span>      | <span data-ttu-id="a6afc-505">Débito</span><span class="sxs-lookup"><span data-stu-id="a6afc-505">Debit</span></span> | <span data-ttu-id="a6afc-506">Crédito</span><span class="sxs-lookup"><span data-stu-id="a6afc-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="a6afc-507">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-507">Ledger</span></span>       | <span data-ttu-id="a6afc-508">8</span><span class="sxs-lookup"><span data-stu-id="a6afc-508">8</span></span>              | <span data-ttu-id="a6afc-509">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-509">Custom</span></span> | <span data-ttu-id="a6afc-510">Gastos de intereses</span><span class="sxs-lookup"><span data-stu-id="a6afc-510">Interest expense</span></span>         | <span data-ttu-id="a6afc-511">94.97</span><span class="sxs-lookup"><span data-stu-id="a6afc-511">94.97</span></span> |        |
| <span data-ttu-id="a6afc-512">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-512">Ledger</span></span>       | <span data-ttu-id="a6afc-513">7</span><span class="sxs-lookup"><span data-stu-id="a6afc-513">7</span></span>              | <span data-ttu-id="a6afc-514">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-514">Custom</span></span> | <span data-ttu-id="a6afc-515">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="a6afc-515">Finance lease obligation</span></span> |       | <span data-ttu-id="a6afc-516">94.97</span><span class="sxs-lookup"><span data-stu-id="a6afc-516">94.97</span></span>  |

<span data-ttu-id="a6afc-517">El asiento de diario de gasto por depreciación se genera a partir de la programación de depreciación de activos.</span><span class="sxs-lookup"><span data-stu-id="a6afc-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="a6afc-518">Gasto de depreciación - 31/1/2020 - JE 170</span><span class="sxs-lookup"><span data-stu-id="a6afc-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="a6afc-519">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-519">Account type</span></span> | <span data-ttu-id="a6afc-520">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-520">Account number</span></span> | <span data-ttu-id="a6afc-521">Capa</span><span class="sxs-lookup"><span data-stu-id="a6afc-521">Layer</span></span>  | <span data-ttu-id="a6afc-522">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-522">Account description</span></span>      | <span data-ttu-id="a6afc-523">Débito</span><span class="sxs-lookup"><span data-stu-id="a6afc-523">Debit</span></span>  | <span data-ttu-id="a6afc-524">Crédito</span><span class="sxs-lookup"><span data-stu-id="a6afc-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="a6afc-525">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-525">Ledger</span></span>       | <span data-ttu-id="a6afc-526">10</span><span class="sxs-lookup"><span data-stu-id="a6afc-526">10</span></span>             | <span data-ttu-id="a6afc-527">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-527">Custom</span></span> | <span data-ttu-id="a6afc-528">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="a6afc-528">Depreciation expense</span></span>     | <span data-ttu-id="a6afc-529">949.75</span><span class="sxs-lookup"><span data-stu-id="a6afc-529">949.75</span></span> |        |
| <span data-ttu-id="a6afc-530">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a6afc-530">Ledger</span></span>       | <span data-ttu-id="a6afc-531">11</span><span class="sxs-lookup"><span data-stu-id="a6afc-531">11</span></span>             | <span data-ttu-id="a6afc-532">Personalizado</span><span class="sxs-lookup"><span data-stu-id="a6afc-532">Custom</span></span> | <span data-ttu-id="a6afc-533">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="a6afc-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="a6afc-534">949.75</span><span class="sxs-lookup"><span data-stu-id="a6afc-534">949.75</span></span> |

<span data-ttu-id="a6afc-535">Después de crear y publicar todas estas entradas del diario, verá los siguientes valores de "capa personaliada 1".</span><span class="sxs-lookup"><span data-stu-id="a6afc-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="a6afc-536">Tenga en cuenta que la última columna incluye la comisión bancaria, el gasto del impuesto sobre el valor añadido (IVA) y la reducción de efectivo de la capa anterior, pero no incluye los asientos del diario de informes legales.</span><span class="sxs-lookup"><span data-stu-id="a6afc-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="a6afc-537">Por lo tanto, logrará verdaderas capacidades de informes dobles.</span><span class="sxs-lookup"><span data-stu-id="a6afc-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="a6afc-538">En este momento, la empresa solo tiene que ejecutar su saldo de comprobación y combinar la capa actual y la capa personalizada para crear un saldo de comprobación IFRS.</span><span class="sxs-lookup"><span data-stu-id="a6afc-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="a6afc-539">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="a6afc-539">Account No</span></span> | <span data-ttu-id="a6afc-540">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6afc-540">Description</span></span>              | <span data-ttu-id="a6afc-541">Libro legal\-Capa actual\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a6afc-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="a6afc-542">Libro legal\-Capa actual\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a6afc-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="a6afc-543">Libro legal\-Capa actual\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a6afc-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="a6afc-544">Capa actual \- Totales</span><span class="sxs-lookup"><span data-stu-id="a6afc-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="a6afc-545">Libro de revocación\-Capa personalizada\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a6afc-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="a6afc-546">Libro IFRS 16\-Capa personalizada\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a6afc-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="a6afc-547">Libro IFRS 16\-Capa personalizada\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a6afc-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="a6afc-548">Libro IFRS 16\-Capa personalizada\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a6afc-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="a6afc-549">Libro IFRS 16\-Capa personalizada\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a6afc-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="a6afc-550">Capa actual \+ Capa personalizada \- Totales</span><span class="sxs-lookup"><span data-stu-id="a6afc-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="a6afc-551">1</span><span class="sxs-lookup"><span data-stu-id="a6afc-551">1</span></span>          | <span data-ttu-id="a6afc-552">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6afc-552">Lease expense</span></span>            | <span data-ttu-id="a6afc-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="a6afc-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-554">1,000\.00</span></span>               |   | <span data-ttu-id="a6afc-555">\-1.000</span><span class="sxs-lookup"><span data-stu-id="a6afc-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="a6afc-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-556">0\.00</span></span>                                   |
| <span data-ttu-id="a6afc-557">2</span><span class="sxs-lookup"><span data-stu-id="a6afc-557">2</span></span>          | <span data-ttu-id="a6afc-558">Comisión bancaria</span><span class="sxs-lookup"><span data-stu-id="a6afc-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="a6afc-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="a6afc-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="a6afc-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-561">3\.00</span></span>                                   |
| <span data-ttu-id="a6afc-562">3</span><span class="sxs-lookup"><span data-stu-id="a6afc-562">3</span></span>          | <span data-ttu-id="a6afc-563">Gasto de iVA</span><span class="sxs-lookup"><span data-stu-id="a6afc-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="a6afc-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="a6afc-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="a6afc-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-566">5\.00</span></span>                                   |
| <span data-ttu-id="a6afc-567">4</span><span class="sxs-lookup"><span data-stu-id="a6afc-567">4</span></span>          | <span data-ttu-id="a6afc-568">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="a6afc-568">Clearing account</span></span>         | <span data-ttu-id="a6afc-569">\-1.000\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="a6afc-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="a6afc-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-571">0\.00</span></span>                   |   | <span data-ttu-id="a6afc-572">1.000</span><span class="sxs-lookup"><span data-stu-id="a6afc-572">1,000</span></span>                                           |                                                | <span data-ttu-id="a6afc-573">\-1.000</span><span class="sxs-lookup"><span data-stu-id="a6afc-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="a6afc-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-574">0\.00</span></span>                                   |
| <span data-ttu-id="a6afc-575">5</span><span class="sxs-lookup"><span data-stu-id="a6afc-575">5</span></span>          | <span data-ttu-id="a6afc-576">Proveedores</span><span class="sxs-lookup"><span data-stu-id="a6afc-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="a6afc-577">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="a6afc-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-578">1,008\.00</span></span>                                         | <span data-ttu-id="a6afc-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="a6afc-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-580">0\.00</span></span>                                   |
| <span data-ttu-id="a6afc-581">6</span><span class="sxs-lookup"><span data-stu-id="a6afc-581">6</span></span>          | <span data-ttu-id="a6afc-582">Activo por derecho de uso</span><span class="sxs-lookup"><span data-stu-id="a6afc-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="a6afc-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="a6afc-584">22,794</span><span class="sxs-lookup"><span data-stu-id="a6afc-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="a6afc-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="a6afc-585">22,793\.90</span></span>                              |
| <span data-ttu-id="a6afc-586">7</span><span class="sxs-lookup"><span data-stu-id="a6afc-586">7</span></span>          | <span data-ttu-id="a6afc-587">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="a6afc-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="a6afc-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="a6afc-589">\-22.794</span><span class="sxs-lookup"><span data-stu-id="a6afc-589">\-22,794</span></span>                                       | <span data-ttu-id="a6afc-590">1.000</span><span class="sxs-lookup"><span data-stu-id="a6afc-590">1,000</span></span>                                          | <span data-ttu-id="a6afc-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="a6afc-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="a6afc-592">\-21.888\.87</span><span class="sxs-lookup"><span data-stu-id="a6afc-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="a6afc-593">8</span><span class="sxs-lookup"><span data-stu-id="a6afc-593">8</span></span>          | <span data-ttu-id="a6afc-594">Gastos de intereses</span><span class="sxs-lookup"><span data-stu-id="a6afc-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="a6afc-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="a6afc-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="a6afc-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="a6afc-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="a6afc-597">94\.97</span></span>                                  |
| <span data-ttu-id="a6afc-598">9</span><span class="sxs-lookup"><span data-stu-id="a6afc-598">9</span></span>          | <span data-ttu-id="a6afc-599">Efectivo</span><span class="sxs-lookup"><span data-stu-id="a6afc-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="a6afc-600">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="a6afc-601">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="a6afc-602">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="a6afc-603">10</span><span class="sxs-lookup"><span data-stu-id="a6afc-603">10</span></span>         | <span data-ttu-id="a6afc-604">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="a6afc-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="a6afc-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="a6afc-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="a6afc-606">949\.75</span></span>                                        | <span data-ttu-id="a6afc-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="a6afc-607">949\.75</span></span>                                 |
| <span data-ttu-id="a6afc-608">11</span><span class="sxs-lookup"><span data-stu-id="a6afc-608">11</span></span>         | <span data-ttu-id="a6afc-609">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="a6afc-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="a6afc-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="a6afc-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="a6afc-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="a6afc-611">\-949\.75</span></span>                                      | <span data-ttu-id="a6afc-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="a6afc-612">\-949\.75</span></span>                               |


