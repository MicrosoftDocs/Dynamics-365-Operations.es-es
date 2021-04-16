---
title: Informes duales
description: Este tema le guía a través de un ejemplo que muestra cómo puede cumplir con los requisitos para la presentación de informes de la Norma Internacional de Información Financiera (IFRS) y la presentación de informes legales en el arrendamiento de activos.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c9f2bae330e688e1e941277d46ddcbd38916f8c8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815989"
---
# <a name="dual-reporting"></a><span data-ttu-id="bc559-103">Informes duales</span><span class="sxs-lookup"><span data-stu-id="bc559-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bc559-104">Este tema le guía a través de un ejemplo que muestra cómo puede cumplir con los requisitos para la presentación de informes de la Norma Internacional de Información Financiera (IFRS) y la presentación de informes legales en el arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="bc559-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="bc559-105">Es necesaria la familiaridad con las capas de registro en Microsoft Dynamics 365 Finance y facilitará la comprensión del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bc559-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="bc559-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc559-106">Example</span></span>

<span data-ttu-id="bc559-107">El siguiente ejemplo contabiliza un arrendamiento según la información legal italiana utilizando tanto el método de base de efectivo como los métodos de informes IFRS.</span><span class="sxs-lookup"><span data-stu-id="bc559-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="bc559-108">La empresa debe establecer tres libros para dar cuenta tanto de los requisitos legales italianos como de los requisitos del IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="bc559-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="bc559-109">Se requiere un libro para IFRS 16, un libro para los requisitos legales y un libro para revertir automáticamente las contabilizaciones legales.</span><span class="sxs-lookup"><span data-stu-id="bc559-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="bc559-110">Los libros se configuran como se muestra en las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="bc559-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="bc559-111">**Libro IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="bc559-111">**IFRS 16 book**</span></span>

<span data-ttu-id="bc559-112">El libro IFRS 16 está configurado de manera que cumpla con el estándar contable IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="bc559-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="bc559-113">Todas las entradas que se publican en este libro se publicarán en una capa personalizada.</span><span class="sxs-lookup"><span data-stu-id="bc559-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="bc559-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="bc559-114">Name</span></span>                                    | <span data-ttu-id="bc559-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc559-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="bc559-116">Tipo de libro</span><span class="sxs-lookup"><span data-stu-id="bc559-116">Book type</span></span>                               | <span data-ttu-id="bc559-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="bc559-117">IFRS 16</span></span>        |
| <span data-ttu-id="bc559-118">Descripción del libro</span><span class="sxs-lookup"><span data-stu-id="bc559-118">Book description</span></span>                        | <span data-ttu-id="bc559-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="bc559-119">IFRS 16</span></span>        |
| <span data-ttu-id="bc559-120">Capa de registro</span><span class="sxs-lookup"><span data-stu-id="bc559-120">Posting Layer</span></span>                           | <span data-ttu-id="bc559-121">Capa personalizada 1</span><span class="sxs-lookup"><span data-stu-id="bc559-121">Custom layer 1</span></span> |
| <span data-ttu-id="bc559-122">Tipo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-122">Lease Type</span></span>                              | <span data-ttu-id="bc559-123">Finance</span><span class="sxs-lookup"><span data-stu-id="bc559-123">Finance</span></span>        |
| <span data-ttu-id="bc559-124">Marco de contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-124">Accounting Framework</span></span>                    | <span data-ttu-id="bc559-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="bc559-125">IFRS 16</span></span>        |
| <span data-ttu-id="bc559-126">Configuración del plazo del arrendamiento/vida útil</span><span class="sxs-lookup"><span data-stu-id="bc559-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="bc559-127">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-127">0.00</span></span>           |
| <span data-ttu-id="bc559-128">Configuración del valor actual/valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="bc559-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="bc559-129">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-129">0.00</span></span>           |
| <span data-ttu-id="bc559-130">Umbral a corto plazo</span><span class="sxs-lookup"><span data-stu-id="bc559-130">Short-term threshold</span></span>                    | <span data-ttu-id="bc559-131">12</span><span class="sxs-lookup"><span data-stu-id="bc559-131">12</span></span>             |
| <span data-ttu-id="bc559-132">Umbral de valor bajo</span><span class="sxs-lookup"><span data-stu-id="bc559-132">Low Value Threshold</span></span>                     | <span data-ttu-id="bc559-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-133">5,000.00</span></span>       |
| <span data-ttu-id="bc559-134">Pagar a proveedor</span><span class="sxs-lookup"><span data-stu-id="bc559-134">Pay to Vendor</span></span>                           | <span data-ttu-id="bc559-135">N.º</span><span class="sxs-lookup"><span data-stu-id="bc559-135">No</span></span>             |

<span data-ttu-id="bc559-136">**Libro legal**</span><span class="sxs-lookup"><span data-stu-id="bc559-136">**Statutory book**</span></span>

<span data-ttu-id="bc559-137">El libro legal es un libro de efectivo en el que la empresa contabilizará los gastos de arrendamiento como la cantidad de efectivo que se paga cada mes por el alquiler.</span><span class="sxs-lookup"><span data-stu-id="bc559-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="bc559-138">Este libro no producirá un activo por derecho de uso (ROU) ni un pasivo por arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="bc559-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="bc559-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="bc559-139">Name</span></span>                                    | <span data-ttu-id="bc559-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc559-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="bc559-141">Tipo de libro</span><span class="sxs-lookup"><span data-stu-id="bc559-141">Book type</span></span>                               | <span data-ttu-id="bc559-142">Legal</span><span class="sxs-lookup"><span data-stu-id="bc559-142">Statutory</span></span>   |
| <span data-ttu-id="bc559-143">Descripción del libro</span><span class="sxs-lookup"><span data-stu-id="bc559-143">Book description</span></span>                        | <span data-ttu-id="bc559-144">GAAP local</span><span class="sxs-lookup"><span data-stu-id="bc559-144">Local GAAP</span></span>  |
| <span data-ttu-id="bc559-145">Capa de registro</span><span class="sxs-lookup"><span data-stu-id="bc559-145">Posting Layer</span></span>                           | <span data-ttu-id="bc559-146">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-146">Current</span></span>     |
| <span data-ttu-id="bc559-147">Tipo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-147">Lease Type</span></span>                              | <span data-ttu-id="bc559-148">Automático</span><span class="sxs-lookup"><span data-stu-id="bc559-148">Automatic</span></span>   |
| <span data-ttu-id="bc559-149">Marco de contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-149">Accounting Framework</span></span>                    | <span data-ttu-id="bc559-150">Base en efectivo</span><span class="sxs-lookup"><span data-stu-id="bc559-150">Cash basis</span></span>  |
| <span data-ttu-id="bc559-151">Configuración del plazo del arrendamiento/vida útil</span><span class="sxs-lookup"><span data-stu-id="bc559-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="bc559-152">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-152">0.00</span></span>        |
| <span data-ttu-id="bc559-153">Configuración del valor actual/valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="bc559-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="bc559-154">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-154">0.00</span></span>        |
| <span data-ttu-id="bc559-155">Umbral a corto plazo</span><span class="sxs-lookup"><span data-stu-id="bc559-155">Short-term threshold</span></span>                    | <span data-ttu-id="bc559-156">0</span><span class="sxs-lookup"><span data-stu-id="bc559-156">0</span></span>           |
| <span data-ttu-id="bc559-157">Umbral de valor bajo</span><span class="sxs-lookup"><span data-stu-id="bc559-157">Low Value Threshold</span></span>                     | <span data-ttu-id="bc559-158">0</span><span class="sxs-lookup"><span data-stu-id="bc559-158">0</span></span>           |
| <span data-ttu-id="bc559-159">Pagar a proveedor</span><span class="sxs-lookup"><span data-stu-id="bc559-159">Pay to Vendor</span></span>                           | <span data-ttu-id="bc559-160">N.º</span><span class="sxs-lookup"><span data-stu-id="bc559-160">No</span></span>          |

<span data-ttu-id="bc559-161">**Libro de revocación legal**</span><span class="sxs-lookup"><span data-stu-id="bc559-161">**Statutory reversal book**</span></span>

<span data-ttu-id="bc559-162">El libro de revocación legal se configura de la misma manera que el libro legal.</span><span class="sxs-lookup"><span data-stu-id="bc559-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="bc559-163">Nombre</span><span class="sxs-lookup"><span data-stu-id="bc559-163">Name</span></span>                                    | <span data-ttu-id="bc559-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc559-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="bc559-165">Tipo de libro</span><span class="sxs-lookup"><span data-stu-id="bc559-165">Book type</span></span>                               | <span data-ttu-id="bc559-166">Legal: revocación</span><span class="sxs-lookup"><span data-stu-id="bc559-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="bc559-167">Descripción del libro</span><span class="sxs-lookup"><span data-stu-id="bc559-167">Book description</span></span>                        | <span data-ttu-id="bc559-168">Libro para revocar el libro legal</span><span class="sxs-lookup"><span data-stu-id="bc559-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="bc559-169">Capa de registro</span><span class="sxs-lookup"><span data-stu-id="bc559-169">Posting Layer</span></span>                           | <span data-ttu-id="bc559-170">Capa personalizada 1</span><span class="sxs-lookup"><span data-stu-id="bc559-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="bc559-171">Tipo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-171">Lease Type</span></span>                              | <span data-ttu-id="bc559-172">Automático</span><span class="sxs-lookup"><span data-stu-id="bc559-172">Automatic</span></span>                      |
| <span data-ttu-id="bc559-173">Marco de contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-173">Accounting Framework</span></span>                    | <span data-ttu-id="bc559-174">Base en efectivo</span><span class="sxs-lookup"><span data-stu-id="bc559-174">Cash basis</span></span>                     |
| <span data-ttu-id="bc559-175">Configuración del plazo del arrendamiento/vida útil</span><span class="sxs-lookup"><span data-stu-id="bc559-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="bc559-176">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-176">0.00</span></span>                           |
| <span data-ttu-id="bc559-177">Configuración del valor actual/valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="bc559-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="bc559-178">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-178">0.00</span></span>                           |
| <span data-ttu-id="bc559-179">Umbral a corto plazo</span><span class="sxs-lookup"><span data-stu-id="bc559-179">Short-term threshold</span></span>                    | <span data-ttu-id="bc559-180">0</span><span class="sxs-lookup"><span data-stu-id="bc559-180">0</span></span>                              |
| <span data-ttu-id="bc559-181">Umbral de valor bajo</span><span class="sxs-lookup"><span data-stu-id="bc559-181">Low Value Threshold</span></span>                     | <span data-ttu-id="bc559-182">0</span><span class="sxs-lookup"><span data-stu-id="bc559-182">0</span></span>                              |
| <span data-ttu-id="bc559-183">Pagar a proveedor</span><span class="sxs-lookup"><span data-stu-id="bc559-183">Pay to Vendor</span></span>                           | <span data-ttu-id="bc559-184">N.º</span><span class="sxs-lookup"><span data-stu-id="bc559-184">No</span></span>                             |

<span data-ttu-id="bc559-185">Para este ejemplo, se ha creado un arrendamiento con la siguiente configuración en las pestañas **General** y **Líneas de programación de pagos**.</span><span class="sxs-lookup"><span data-stu-id="bc559-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="bc559-186">**Pestaña General**</span><span class="sxs-lookup"><span data-stu-id="bc559-186">**General tab**</span></span>

| <span data-ttu-id="bc559-187">Campo</span><span class="sxs-lookup"><span data-stu-id="bc559-187">Field</span></span>                      | <span data-ttu-id="bc559-188">Valor</span><span class="sxs-lookup"><span data-stu-id="bc559-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="bc559-189">Tipo de interés incremental del endeudamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-189">Incremental borrowing rate</span></span> | <span data-ttu-id="bc559-190">5%</span><span class="sxs-lookup"><span data-stu-id="bc559-190">5%</span></span>               |
| <span data-ttu-id="bc559-191">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="bc559-191">Commencement date</span></span>          | <span data-ttu-id="bc559-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="bc559-192">1/1/2020</span></span>         |
| <span data-ttu-id="bc559-193">Grupo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-193">Lease group</span></span>                | <span data-ttu-id="bc559-194">Edificios</span><span class="sxs-lookup"><span data-stu-id="bc559-194">Buildings</span></span>        |
| <span data-ttu-id="bc559-195">Proveedor</span><span class="sxs-lookup"><span data-stu-id="bc559-195">Vendor</span></span>                     | <span data-ttu-id="bc559-196">1001</span><span class="sxs-lookup"><span data-stu-id="bc559-196">1001</span></span>             |
| <span data-ttu-id="bc559-197">Valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="bc559-197">Fair value of the asset</span></span>    | <span data-ttu-id="bc559-198">245,000</span><span class="sxs-lookup"><span data-stu-id="bc559-198">245,000</span></span>          |
| <span data-ttu-id="bc559-199">Vida útil del activo</span><span class="sxs-lookup"><span data-stu-id="bc559-199">Asset useful life</span></span>          | <span data-ttu-id="bc559-200">120</span><span class="sxs-lookup"><span data-stu-id="bc559-200">120</span></span>              |
| <span data-ttu-id="bc559-201">Tipo de anualidad</span><span class="sxs-lookup"><span data-stu-id="bc559-201">Annuity type</span></span>               | <span data-ttu-id="bc559-202">Anualidad ordinaria</span><span class="sxs-lookup"><span data-stu-id="bc559-202">Ordinary annuity</span></span> |
| <span data-ttu-id="bc559-203">Intervalo de composición</span><span class="sxs-lookup"><span data-stu-id="bc559-203">Compounding interval</span></span>       | <span data-ttu-id="bc559-204">Mensual</span><span class="sxs-lookup"><span data-stu-id="bc559-204">Monthly</span></span>          |

<span data-ttu-id="bc559-205">**Pestaña Líneas de programación de pagos**</span><span class="sxs-lookup"><span data-stu-id="bc559-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="bc559-206">Campo</span><span class="sxs-lookup"><span data-stu-id="bc559-206">Field</span></span>             | <span data-ttu-id="bc559-207">Valor</span><span class="sxs-lookup"><span data-stu-id="bc559-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="bc559-208">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="bc559-208">Start date</span></span>        | <span data-ttu-id="bc559-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="bc559-209">1/1/2020</span></span>   |
| <span data-ttu-id="bc559-210">Intervalo del período</span><span class="sxs-lookup"><span data-stu-id="bc559-210">Period interval</span></span>   | <span data-ttu-id="bc559-211">Meses</span><span class="sxs-lookup"><span data-stu-id="bc559-211">Months</span></span>     |
| <span data-ttu-id="bc559-212">Períodos</span><span class="sxs-lookup"><span data-stu-id="bc559-212">Periods</span></span>           | <span data-ttu-id="bc559-213">24</span><span class="sxs-lookup"><span data-stu-id="bc559-213">24</span></span>         |
| <span data-ttu-id="bc559-214">Fecha final</span><span class="sxs-lookup"><span data-stu-id="bc559-214">End date</span></span>          | <span data-ttu-id="bc559-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="bc559-215">12/31/2020</span></span> |
| <span data-ttu-id="bc559-216">Frecuencia de pago</span><span class="sxs-lookup"><span data-stu-id="bc559-216">Payment frequency</span></span> | <span data-ttu-id="bc559-217">Mensual</span><span class="sxs-lookup"><span data-stu-id="bc559-217">Monthly</span></span>    |
| <span data-ttu-id="bc559-218">Importe del pago</span><span class="sxs-lookup"><span data-stu-id="bc559-218">Payment amount</span></span>    | <span data-ttu-id="bc559-219">1.000</span><span class="sxs-lookup"><span data-stu-id="bc559-219">1,000</span></span>      |

<span data-ttu-id="bc559-220">Para contabilizar este arrendamiento en dos marcos, use una capa de registro actual y una capa de registro personalizada.</span><span class="sxs-lookup"><span data-stu-id="bc559-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="bc559-221">La siguiente tabla muestra un ejemplo de cada entrada de diario que requiere representar correctamente las finanzas bajo cada estándar de informes.</span><span class="sxs-lookup"><span data-stu-id="bc559-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="bc559-222">Posteriormente se proporciona una descripción detallada de cada movimiento del diario correspondiente al primer mes del arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="bc559-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="bc559-223">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="bc559-224">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc559-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="bc559-225">Libro legal (capa actual)</span><span class="sxs-lookup"><span data-stu-id="bc559-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="bc559-226">Total de la capa actual</span><span class="sxs-lookup"><span data-stu-id="bc559-226">Current layer total</span></span></th>
<th><span data-ttu-id="bc559-227">Libro de revocación (capa personalizada)</span><span class="sxs-lookup"><span data-stu-id="bc559-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="bc559-228">Libro IFRS 16 (capa personalizada)</span><span class="sxs-lookup"><span data-stu-id="bc559-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="bc559-229">Capa actual + Total de capa personalizada</span><span class="sxs-lookup"><span data-stu-id="bc559-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="bc559-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="bc559-230">JE-100</span></span></th>
<th><span data-ttu-id="bc559-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="bc559-231">JE-110</span></span></th>
<th><span data-ttu-id="bc559-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="bc559-232">JE-120</span></span></th>
<th><span data-ttu-id="bc559-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="bc559-233">JE-130</span></span></th>
<th><span data-ttu-id="bc559-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="bc559-234">JE-140</span></span></th>
<th><span data-ttu-id="bc559-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="bc559-235">JE-150</span></span></th>
<th><span data-ttu-id="bc559-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="bc559-236">JE-160</span></span></th>
<th><span data-ttu-id="bc559-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="bc559-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="bc559-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bc559-246">1</span><span class="sxs-lookup"><span data-stu-id="bc559-246">1</span></span></td>
<td><span data-ttu-id="bc559-247">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-247">Lease expense</span></span></td>
<td><span data-ttu-id="bc559-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-249">1,000.00</span></span></td>
<td><span data-ttu-id="bc559-250">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="bc559-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-251">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-252">2</span><span class="sxs-lookup"><span data-stu-id="bc559-252">2</span></span></td>
<td><span data-ttu-id="bc559-253">Comisión bancaria</span><span class="sxs-lookup"><span data-stu-id="bc559-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-254">3.00</span><span class="sxs-lookup"><span data-stu-id="bc559-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-255">3.00</span><span class="sxs-lookup"><span data-stu-id="bc559-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-256">3.00</span><span class="sxs-lookup"><span data-stu-id="bc559-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-257">3</span><span class="sxs-lookup"><span data-stu-id="bc559-257">3</span></span></td>
<td><span data-ttu-id="bc559-258">Gasto de iVA</span><span class="sxs-lookup"><span data-stu-id="bc559-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-259">5.00</span><span class="sxs-lookup"><span data-stu-id="bc559-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-260">5.00</span><span class="sxs-lookup"><span data-stu-id="bc559-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-261">5.00</span><span class="sxs-lookup"><span data-stu-id="bc559-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-262">4</span><span class="sxs-lookup"><span data-stu-id="bc559-262">4</span></span></td>
<td><span data-ttu-id="bc559-263">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="bc559-263">Clearing account</span></span></td>
<td><span data-ttu-id="bc559-264">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="bc559-264">-1,000.00</span></span></td>
<td><span data-ttu-id="bc559-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-266">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-266">0.00</span></span></td>
<td><span data-ttu-id="bc559-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-268">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="bc559-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-269">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-270">5</span><span class="sxs-lookup"><span data-stu-id="bc559-270">5</span></span></td>
<td><span data-ttu-id="bc559-271">Proveedores</span><span class="sxs-lookup"><span data-stu-id="bc559-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="bc559-272">-1,008.00</span></span></td>
<td><span data-ttu-id="bc559-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="bc559-273">1,008.00</span></span></td>
<td><span data-ttu-id="bc559-274">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-275">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-276">6</span><span class="sxs-lookup"><span data-stu-id="bc559-276">6</span></span></td>
<td><span data-ttu-id="bc559-277">Activo por derecho de uso</span><span class="sxs-lookup"><span data-stu-id="bc559-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-278">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="bc559-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="bc559-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-281">7</span><span class="sxs-lookup"><span data-stu-id="bc559-281">7</span></span></td>
<td><span data-ttu-id="bc559-282">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="bc559-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-283">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="bc559-284">-22,794.00</span></span></td>
<td><span data-ttu-id="bc559-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-285">1,000.00</span></span></td>
<td><span data-ttu-id="bc559-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="bc559-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="bc559-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-288">8</span><span class="sxs-lookup"><span data-stu-id="bc559-288">8</span></span></td>
<td><span data-ttu-id="bc559-289">Gastos de intereses</span><span class="sxs-lookup"><span data-stu-id="bc559-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-290">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-291">94.97</span><span class="sxs-lookup"><span data-stu-id="bc559-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-292">94.97</span><span class="sxs-lookup"><span data-stu-id="bc559-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-293">9</span><span class="sxs-lookup"><span data-stu-id="bc559-293">9</span></span></td>
<td><span data-ttu-id="bc559-294">Efectivo</span><span class="sxs-lookup"><span data-stu-id="bc559-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="bc559-295">-1,008.00</span></span></td>
<td><span data-ttu-id="bc559-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="bc559-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="bc559-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-298">10</span><span class="sxs-lookup"><span data-stu-id="bc559-298">10</span></span></td>
<td><span data-ttu-id="bc559-299">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="bc559-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-300">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-301">949.75</span><span class="sxs-lookup"><span data-stu-id="bc559-301">949.75</span></span></td>
<td><span data-ttu-id="bc559-302">949.75</span><span class="sxs-lookup"><span data-stu-id="bc559-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-303">11</span><span class="sxs-lookup"><span data-stu-id="bc559-303">11</span></span></td>
<td><span data-ttu-id="bc559-304">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="bc559-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-305">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="bc559-306">-949.75</span></span></td>
<td><span data-ttu-id="bc559-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="bc559-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bc559-308">Como muestra la tabla anterior, se requieren tres libros para informar tanto según los informes legales como según los informes IFRS.</span><span class="sxs-lookup"><span data-stu-id="bc559-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="bc559-309">El libro legal registra el pago del arrendamiento de acuerdo con las reglas para la contabilidad de efectivo en la capa actual.</span><span class="sxs-lookup"><span data-stu-id="bc559-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="bc559-310">El libro de revocación legal revierte los asientos del diario legal.</span><span class="sxs-lookup"><span data-stu-id="bc559-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="bc559-311">El libro IFRS 16 crea los asientos de diario que se requieren según IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="bc559-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="bc559-312">Debe introducir cada arrendamiento solo una vez.</span><span class="sxs-lookup"><span data-stu-id="bc559-312">You must enter a lease only one time.</span></span> <span data-ttu-id="bc559-313">A continuación, puede abrir la página **Libros** para ver todos los libros asociados con el arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="bc559-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="bc559-314">Cuando crea los libros, los tres deben estar asociados con el mismo registro de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="bc559-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="bc559-315">La primera entrada de diario registra el gasto de arrendamiento en el libro legal.</span><span class="sxs-lookup"><span data-stu-id="bc559-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="bc559-316">Puede crear los pagos en un lote o seleccionando la programación de pagos en el libro legal.</span><span class="sxs-lookup"><span data-stu-id="bc559-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="bc559-317">Para este ejemplo, se produce el siguiente movimiento de diario para el libro legal a partir de la programación de pagos.</span><span class="sxs-lookup"><span data-stu-id="bc559-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="bc559-318">Pago de arrendamiento - 31/1/2020 - JE 100</span><span class="sxs-lookup"><span data-stu-id="bc559-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="bc559-319">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-319">Account type</span></span> | <span data-ttu-id="bc559-320">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-320">Account number</span></span> | <span data-ttu-id="bc559-321">Capa</span><span class="sxs-lookup"><span data-stu-id="bc559-321">Layer</span></span>   | <span data-ttu-id="bc559-322">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-322">Account description</span></span> | <span data-ttu-id="bc559-323">Débito</span><span class="sxs-lookup"><span data-stu-id="bc559-323">Debit</span></span>    | <span data-ttu-id="bc559-324">Crédito</span><span class="sxs-lookup"><span data-stu-id="bc559-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="bc559-325">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-325">Ledger</span></span>       | <span data-ttu-id="bc559-326">1</span><span class="sxs-lookup"><span data-stu-id="bc559-326">1</span></span>              | <span data-ttu-id="bc559-327">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-327">Current</span></span> | <span data-ttu-id="bc559-328">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-328">Lease expense</span></span>       | <span data-ttu-id="bc559-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-329">1,000.00</span></span> |          |
| <span data-ttu-id="bc559-330">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-330">Ledger</span></span>       | <span data-ttu-id="bc559-331">4</span><span class="sxs-lookup"><span data-stu-id="bc559-331">4</span></span>              | <span data-ttu-id="bc559-332">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-332">Current</span></span> | <span data-ttu-id="bc559-333">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="bc559-333">Clearing account</span></span>    |          | <span data-ttu-id="bc559-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-334">1,000.00</span></span> |

<span data-ttu-id="bc559-335">Un empleado de la sección de proveedores utiliza la funcionalidad estándar de Dynamics 365 para crear una factura para pagar el arrendamiento por fuera del arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="bc559-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="bc559-336">Sin embargo, en lugar de seleccionar **Gastos de arrendamiento** como cuenta de débito, el empleado de la sección de proveedores selecciona una cuenta de compensación para generar la siguiente entrada.</span><span class="sxs-lookup"><span data-stu-id="bc559-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="bc559-337">Proceso AP - 31/1/2020 - JE 110</span><span class="sxs-lookup"><span data-stu-id="bc559-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="bc559-338">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-338">Account type</span></span> | <span data-ttu-id="bc559-339">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-339">Account number</span></span> | <span data-ttu-id="bc559-340">Capa</span><span class="sxs-lookup"><span data-stu-id="bc559-340">Layer</span></span>   | <span data-ttu-id="bc559-341">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-341">Account description</span></span> | <span data-ttu-id="bc559-342">Débito</span><span class="sxs-lookup"><span data-stu-id="bc559-342">Debit</span></span>    | <span data-ttu-id="bc559-343">Crédito</span><span class="sxs-lookup"><span data-stu-id="bc559-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="bc559-344">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-344">Ledger</span></span>       | <span data-ttu-id="bc559-345">4</span><span class="sxs-lookup"><span data-stu-id="bc559-345">4</span></span>              | <span data-ttu-id="bc559-346">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-346">Current</span></span> | <span data-ttu-id="bc559-347">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="bc559-347">Clearing account</span></span>    | <span data-ttu-id="bc559-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-348">1,000.00</span></span> |          |
| <span data-ttu-id="bc559-349">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-349">Ledger</span></span>       | <span data-ttu-id="bc559-350">2</span><span class="sxs-lookup"><span data-stu-id="bc559-350">2</span></span>              | <span data-ttu-id="bc559-351">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-351">Current</span></span> | <span data-ttu-id="bc559-352">Comisión bancaria</span><span class="sxs-lookup"><span data-stu-id="bc559-352">Bank fee</span></span>            | <span data-ttu-id="bc559-353">3.00</span><span class="sxs-lookup"><span data-stu-id="bc559-353">3.00</span></span>     |          |
| <span data-ttu-id="bc559-354">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-354">Ledger</span></span>       | <span data-ttu-id="bc559-355">3</span><span class="sxs-lookup"><span data-stu-id="bc559-355">3</span></span>              | <span data-ttu-id="bc559-356">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-356">Current</span></span> | <span data-ttu-id="bc559-357">Gasto de iVA</span><span class="sxs-lookup"><span data-stu-id="bc559-357">VAT expense</span></span>         | <span data-ttu-id="bc559-358">5.00</span><span class="sxs-lookup"><span data-stu-id="bc559-358">5.00</span></span>     |          |
| <span data-ttu-id="bc559-359">Proveedor</span><span class="sxs-lookup"><span data-stu-id="bc559-359">Vendor</span></span>       | <span data-ttu-id="bc559-360">5</span><span class="sxs-lookup"><span data-stu-id="bc559-360">5</span></span>              | <span data-ttu-id="bc559-361">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-361">Current</span></span> | <span data-ttu-id="bc559-362">Proveedores</span><span class="sxs-lookup"><span data-stu-id="bc559-362">Accounts payable</span></span>    |          | <span data-ttu-id="bc559-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="bc559-363">1,008.00</span></span> |

<span data-ttu-id="bc559-364">Cuando se envía el estado de cuenta al proveedor, se sigue el proceso de pago habitual.</span><span class="sxs-lookup"><span data-stu-id="bc559-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="bc559-365">Durante este proceso, se genera la siguiente entrada de diario.</span><span class="sxs-lookup"><span data-stu-id="bc559-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="bc559-366">Pago en efectivo - 31/1/2020 - JE 120</span><span class="sxs-lookup"><span data-stu-id="bc559-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="bc559-367">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-367">Account type</span></span> | <span data-ttu-id="bc559-368">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-368">Account number</span></span> | <span data-ttu-id="bc559-369">Capa</span><span class="sxs-lookup"><span data-stu-id="bc559-369">Layer</span></span>   | <span data-ttu-id="bc559-370">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-370">Account description</span></span> | <span data-ttu-id="bc559-371">Débito</span><span class="sxs-lookup"><span data-stu-id="bc559-371">Debit</span></span>    | <span data-ttu-id="bc559-372">Crédito</span><span class="sxs-lookup"><span data-stu-id="bc559-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="bc559-373">Proveedor</span><span class="sxs-lookup"><span data-stu-id="bc559-373">Vendor</span></span>       | <span data-ttu-id="bc559-374">5</span><span class="sxs-lookup"><span data-stu-id="bc559-374">5</span></span>              | <span data-ttu-id="bc559-375">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-375">Current</span></span> | <span data-ttu-id="bc559-376">Proveedores</span><span class="sxs-lookup"><span data-stu-id="bc559-376">Accounts Payable</span></span>    | <span data-ttu-id="bc559-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="bc559-377">1,008.00</span></span> |          |
| <span data-ttu-id="bc559-378">Banco</span><span class="sxs-lookup"><span data-stu-id="bc559-378">Bank</span></span>         | <span data-ttu-id="bc559-379">9</span><span class="sxs-lookup"><span data-stu-id="bc559-379">9</span></span>              | <span data-ttu-id="bc559-380">Actuales</span><span class="sxs-lookup"><span data-stu-id="bc559-380">Current</span></span> | <span data-ttu-id="bc559-381">Efectivo</span><span class="sxs-lookup"><span data-stu-id="bc559-381">Cash</span></span>                |          | <span data-ttu-id="bc559-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="bc559-382">1,008.00</span></span> |

<span data-ttu-id="bc559-383">En este punto, ha contabilizado completamente este contrato de arrendamiento según los requisitos de informes legales y puede generar un balance de prueba utilizando la capa actual.</span><span class="sxs-lookup"><span data-stu-id="bc559-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="bc559-384">El sistema devuelve un saldo de comprobación que tiene las siguientes cifras.</span><span class="sxs-lookup"><span data-stu-id="bc559-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="bc559-385">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="bc559-386">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc559-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="bc559-387">Libro legal (capa actual)</span><span class="sxs-lookup"><span data-stu-id="bc559-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="bc559-388">Total de la capa actual</span><span class="sxs-lookup"><span data-stu-id="bc559-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="bc559-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="bc559-389">JE-100</span></span></th>
<th><span data-ttu-id="bc559-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="bc559-390">JE-110</span></span></th>
<th><span data-ttu-id="bc559-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="bc559-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="bc559-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="bc559-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="bc559-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bc559-395">1</span><span class="sxs-lookup"><span data-stu-id="bc559-395">1</span></span></td>
<td><span data-ttu-id="bc559-396">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-396">Lease expense</span></span></td>
<td><span data-ttu-id="bc559-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-399">2</span><span class="sxs-lookup"><span data-stu-id="bc559-399">2</span></span></td>
<td><span data-ttu-id="bc559-400">Comisión bancaria</span><span class="sxs-lookup"><span data-stu-id="bc559-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-401">3.00</span><span class="sxs-lookup"><span data-stu-id="bc559-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-402">3.00</span><span class="sxs-lookup"><span data-stu-id="bc559-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-403">3</span><span class="sxs-lookup"><span data-stu-id="bc559-403">3</span></span></td>
<td><span data-ttu-id="bc559-404">Gasto de iVA</span><span class="sxs-lookup"><span data-stu-id="bc559-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-405">5.00</span><span class="sxs-lookup"><span data-stu-id="bc559-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-406">5.00</span><span class="sxs-lookup"><span data-stu-id="bc559-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-407">4</span><span class="sxs-lookup"><span data-stu-id="bc559-407">4</span></span></td>
<td><span data-ttu-id="bc559-408">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="bc559-408">Clearing account</span></span></td>
<td><span data-ttu-id="bc559-409">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="bc559-409">-1,000.00</span></span></td>
<td><span data-ttu-id="bc559-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-411">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-412">5</span><span class="sxs-lookup"><span data-stu-id="bc559-412">5</span></span></td>
<td><span data-ttu-id="bc559-413">Proveedores</span><span class="sxs-lookup"><span data-stu-id="bc559-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="bc559-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="bc559-414">-1,008.00</span></span></td>
<td><span data-ttu-id="bc559-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="bc559-415">1,008.00</span></span></td>
<td><span data-ttu-id="bc559-416">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-417">6</span><span class="sxs-lookup"><span data-stu-id="bc559-417">6</span></span></td>
<td><span data-ttu-id="bc559-418">Activo por derecho de uso</span><span class="sxs-lookup"><span data-stu-id="bc559-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-419">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-420">7</span><span class="sxs-lookup"><span data-stu-id="bc559-420">7</span></span></td>
<td><span data-ttu-id="bc559-421">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="bc559-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-422">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-423">8</span><span class="sxs-lookup"><span data-stu-id="bc559-423">8</span></span></td>
<td><span data-ttu-id="bc559-424">Gastos de intereses</span><span class="sxs-lookup"><span data-stu-id="bc559-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-425">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-426">9</span><span class="sxs-lookup"><span data-stu-id="bc559-426">9</span></span></td>
<td><span data-ttu-id="bc559-427">Efectivo</span><span class="sxs-lookup"><span data-stu-id="bc559-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="bc559-428">-1,008.00</span></span></td>
<td><span data-ttu-id="bc559-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="bc559-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-430">10</span><span class="sxs-lookup"><span data-stu-id="bc559-430">10</span></span></td>
<td><span data-ttu-id="bc559-431">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="bc559-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-432">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bc559-433">11</span><span class="sxs-lookup"><span data-stu-id="bc559-433">11</span></span></td>
<td><span data-ttu-id="bc559-434">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="bc559-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="bc559-435">0,00</span><span class="sxs-lookup"><span data-stu-id="bc559-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bc559-436">Si desea utilizar las cifras IFRS 16 para ejecutar el mismo saldo de comprobación, los asientos del diario contable legal deben revertirse y los asientos del diario de IFRS 16 deben contabilizarse.</span><span class="sxs-lookup"><span data-stu-id="bc559-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="bc559-437">Para revertir las entradas de diario legales, este ejemplo incluye un libro de revocación legal que tiene la misma configuración que el libro legal pero un perfil de contabilización opuesto.</span><span class="sxs-lookup"><span data-stu-id="bc559-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="bc559-438">Por ejemplo, el libro legal *adeuda* una cuenta de gastos de arrendamiento, pero el libro de revocación *abona* esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="bc559-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="bc559-439">Estas relaciones se definen fácilmente en las cuentas de contabilización de arrendamiento de activos en la página **Parámetros de arrendamiento de activos** (**Arrendamiento de activos \> Configurar \> Parámetros de arrendamiento de activos**).</span><span class="sxs-lookup"><span data-stu-id="bc559-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="bc559-440">Cuando se utiliza el mismo proceso que se utilizó para el libro legal para el libro de revocación, se produce el siguiente asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="bc559-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="bc559-441">La diferencia es que el libro de revocación registra las entradas de revocación del libro legal.</span><span class="sxs-lookup"><span data-stu-id="bc559-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="bc559-442">Las entradas de revocación también se realizan en la capa personalizada.</span><span class="sxs-lookup"><span data-stu-id="bc559-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="bc559-443">Cuando se ejecuta un saldo de comprobación en la capa actual, las entradas del diario de revocación no se incluyen.</span><span class="sxs-lookup"><span data-stu-id="bc559-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="bc559-444">Pago de arrendamiento - 31/1/2020 - JE 130</span><span class="sxs-lookup"><span data-stu-id="bc559-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="bc559-445">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-445">Account type</span></span> | <span data-ttu-id="bc559-446">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-446">Account number</span></span> | <span data-ttu-id="bc559-447">Capa</span><span class="sxs-lookup"><span data-stu-id="bc559-447">Layer</span></span>  | <span data-ttu-id="bc559-448">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-448">Account description</span></span> | <span data-ttu-id="bc559-449">Débito</span><span class="sxs-lookup"><span data-stu-id="bc559-449">Debit</span></span>    | <span data-ttu-id="bc559-450">Crédito</span><span class="sxs-lookup"><span data-stu-id="bc559-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="bc559-451">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-451">Ledger</span></span>       | <span data-ttu-id="bc559-452">4</span><span class="sxs-lookup"><span data-stu-id="bc559-452">4</span></span>              | <span data-ttu-id="bc559-453">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-453">Custom</span></span> | <span data-ttu-id="bc559-454">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="bc559-454">Clearing account</span></span>    | <span data-ttu-id="bc559-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-455">1,000.00</span></span> |          |
| <span data-ttu-id="bc559-456">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-456">Ledger</span></span>       | <span data-ttu-id="bc559-457">1</span><span class="sxs-lookup"><span data-stu-id="bc559-457">1</span></span>              | <span data-ttu-id="bc559-458">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-458">Custom</span></span> | <span data-ttu-id="bc559-459">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-459">Lease expense</span></span>       |          | <span data-ttu-id="bc559-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-460">1,000.00</span></span> |

<span data-ttu-id="bc559-461">Ahora que ha eliminado las entradas del diario legal, registrará todas las entradas de diario que requiere IFRS 16 en el libro de IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="bc559-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="bc559-462">Estas entradas incluyen el reconocimiento inicial del activo por derecho de uso y el pasivo de ROU, y el registro de intereses y depreciación.</span><span class="sxs-lookup"><span data-stu-id="bc559-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="bc559-463">Reconocimiento inicial - 1/1/2020 - JE 140</span><span class="sxs-lookup"><span data-stu-id="bc559-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="bc559-464">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-464">Account type</span></span> | <span data-ttu-id="bc559-465">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-465">Account number</span></span> | <span data-ttu-id="bc559-466">Capa</span><span class="sxs-lookup"><span data-stu-id="bc559-466">Layer</span></span>  | <span data-ttu-id="bc559-467">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-467">Account description</span></span>      | <span data-ttu-id="bc559-468">Débito</span><span class="sxs-lookup"><span data-stu-id="bc559-468">Debit</span></span>     | <span data-ttu-id="bc559-469">Crédito</span><span class="sxs-lookup"><span data-stu-id="bc559-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="bc559-470">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-470">Ledger</span></span>       | <span data-ttu-id="bc559-471">6</span><span class="sxs-lookup"><span data-stu-id="bc559-471">6</span></span>              | <span data-ttu-id="bc559-472">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-472">Custom</span></span> | <span data-ttu-id="bc559-473">Activo por derecho de uso</span><span class="sxs-lookup"><span data-stu-id="bc559-473">ROU Asset</span></span>                | <span data-ttu-id="bc559-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="bc559-474">22,793.90</span></span> |           |
| <span data-ttu-id="bc559-475">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-475">Ledger</span></span>       | <span data-ttu-id="bc559-476">7</span><span class="sxs-lookup"><span data-stu-id="bc559-476">7</span></span>              | <span data-ttu-id="bc559-477">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-477">Custom</span></span> | <span data-ttu-id="bc559-478">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="bc559-478">Finance lease obligation</span></span> |           | <span data-ttu-id="bc559-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="bc559-479">22,793.90</span></span> |

<span data-ttu-id="bc559-480">El pago del arrendamiento se contabiliza como los demás pagos de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="bc559-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="bc559-481">La razón para utilizar la cuenta de compensación es garantizar que el efectivo se abone solo una vez.</span><span class="sxs-lookup"><span data-stu-id="bc559-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="bc559-482">Pago de arrendamiento - 31/1/2020 - JE 150</span><span class="sxs-lookup"><span data-stu-id="bc559-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="bc559-483">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-483">Account type</span></span> | <span data-ttu-id="bc559-484">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-484">Account number</span></span> | <span data-ttu-id="bc559-485">Capa</span><span class="sxs-lookup"><span data-stu-id="bc559-485">Layer</span></span>  | <span data-ttu-id="bc559-486">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-486">Account description</span></span>      | <span data-ttu-id="bc559-487">Débito</span><span class="sxs-lookup"><span data-stu-id="bc559-487">Debit</span></span>    | <span data-ttu-id="bc559-488">Crédito</span><span class="sxs-lookup"><span data-stu-id="bc559-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="bc559-489">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-489">Ledger</span></span>       | <span data-ttu-id="bc559-490">7</span><span class="sxs-lookup"><span data-stu-id="bc559-490">7</span></span>              | <span data-ttu-id="bc559-491">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-491">Custom</span></span> | <span data-ttu-id="bc559-492">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="bc559-492">Finance lease obligation</span></span> | <span data-ttu-id="bc559-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-493">1,000.00</span></span> |          |
| <span data-ttu-id="bc559-494">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-494">Ledger</span></span>       | <span data-ttu-id="bc559-495">4</span><span class="sxs-lookup"><span data-stu-id="bc559-495">4</span></span>              | <span data-ttu-id="bc559-496">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-496">Custom</span></span> | <span data-ttu-id="bc559-497">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="bc559-497">Clearing account</span></span>         |          | <span data-ttu-id="bc559-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="bc559-498">1,000.00</span></span> |

<span data-ttu-id="bc559-499">El asiento de diario de gasto por intereses se genera a partir de la programación de amortización del pasivo.</span><span class="sxs-lookup"><span data-stu-id="bc559-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="bc559-500">Gastos de intereses - 31/1/2020 - JE 160</span><span class="sxs-lookup"><span data-stu-id="bc559-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="bc559-501">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-501">Account type</span></span> | <span data-ttu-id="bc559-502">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-502">Account number</span></span> | <span data-ttu-id="bc559-503">Capa</span><span class="sxs-lookup"><span data-stu-id="bc559-503">Layer</span></span>  | <span data-ttu-id="bc559-504">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-504">Account description</span></span>      | <span data-ttu-id="bc559-505">Débito</span><span class="sxs-lookup"><span data-stu-id="bc559-505">Debit</span></span> | <span data-ttu-id="bc559-506">Crédito</span><span class="sxs-lookup"><span data-stu-id="bc559-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="bc559-507">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-507">Ledger</span></span>       | <span data-ttu-id="bc559-508">8</span><span class="sxs-lookup"><span data-stu-id="bc559-508">8</span></span>              | <span data-ttu-id="bc559-509">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-509">Custom</span></span> | <span data-ttu-id="bc559-510">Gastos de intereses</span><span class="sxs-lookup"><span data-stu-id="bc559-510">Interest expense</span></span>         | <span data-ttu-id="bc559-511">94.97</span><span class="sxs-lookup"><span data-stu-id="bc559-511">94.97</span></span> |        |
| <span data-ttu-id="bc559-512">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-512">Ledger</span></span>       | <span data-ttu-id="bc559-513">7</span><span class="sxs-lookup"><span data-stu-id="bc559-513">7</span></span>              | <span data-ttu-id="bc559-514">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-514">Custom</span></span> | <span data-ttu-id="bc559-515">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="bc559-515">Finance lease obligation</span></span> |       | <span data-ttu-id="bc559-516">94.97</span><span class="sxs-lookup"><span data-stu-id="bc559-516">94.97</span></span>  |

<span data-ttu-id="bc559-517">El asiento de diario de gasto por depreciación se genera a partir de la programación de depreciación de activos.</span><span class="sxs-lookup"><span data-stu-id="bc559-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="bc559-518">Gasto de depreciación - 31/1/2020 - JE 170</span><span class="sxs-lookup"><span data-stu-id="bc559-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="bc559-519">Tipo de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-519">Account type</span></span> | <span data-ttu-id="bc559-520">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-520">Account number</span></span> | <span data-ttu-id="bc559-521">Capa</span><span class="sxs-lookup"><span data-stu-id="bc559-521">Layer</span></span>  | <span data-ttu-id="bc559-522">Descripción de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-522">Account description</span></span>      | <span data-ttu-id="bc559-523">Débito</span><span class="sxs-lookup"><span data-stu-id="bc559-523">Debit</span></span>  | <span data-ttu-id="bc559-524">Crédito</span><span class="sxs-lookup"><span data-stu-id="bc559-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="bc559-525">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-525">Ledger</span></span>       | <span data-ttu-id="bc559-526">10</span><span class="sxs-lookup"><span data-stu-id="bc559-526">10</span></span>             | <span data-ttu-id="bc559-527">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-527">Custom</span></span> | <span data-ttu-id="bc559-528">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="bc559-528">Depreciation expense</span></span>     | <span data-ttu-id="bc559-529">949.75</span><span class="sxs-lookup"><span data-stu-id="bc559-529">949.75</span></span> |        |
| <span data-ttu-id="bc559-530">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="bc559-530">Ledger</span></span>       | <span data-ttu-id="bc559-531">11</span><span class="sxs-lookup"><span data-stu-id="bc559-531">11</span></span>             | <span data-ttu-id="bc559-532">Personalizado</span><span class="sxs-lookup"><span data-stu-id="bc559-532">Custom</span></span> | <span data-ttu-id="bc559-533">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="bc559-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="bc559-534">949.75</span><span class="sxs-lookup"><span data-stu-id="bc559-534">949.75</span></span> |

<span data-ttu-id="bc559-535">Después de crear y publicar todas estas entradas del diario, verá los siguientes valores de "capa personaliada 1".</span><span class="sxs-lookup"><span data-stu-id="bc559-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="bc559-536">Tenga en cuenta que la última columna incluye la comisión bancaria, el gasto del impuesto sobre el valor añadido (IVA) y la reducción de efectivo de la capa anterior, pero no incluye los asientos del diario de informes legales.</span><span class="sxs-lookup"><span data-stu-id="bc559-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="bc559-537">Por lo tanto, logrará verdaderas capacidades de informes dobles.</span><span class="sxs-lookup"><span data-stu-id="bc559-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="bc559-538">En este momento, la empresa solo tiene que ejecutar su saldo de comprobación y combinar la capa actual y la capa personalizada para crear un saldo de comprobación IFRS.</span><span class="sxs-lookup"><span data-stu-id="bc559-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="bc559-539">Número de cuenta</span><span class="sxs-lookup"><span data-stu-id="bc559-539">Account No</span></span> | <span data-ttu-id="bc559-540">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc559-540">Description</span></span>              | <span data-ttu-id="bc559-541">Libro legal\-Capa actual\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="bc559-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="bc559-542">Libro legal\-Capa actual\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="bc559-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="bc559-543">Libro legal\-Capa actual\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="bc559-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="bc559-544">Capa actual \- Totales</span><span class="sxs-lookup"><span data-stu-id="bc559-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="bc559-545">Libro de revocación\-Capa personalizada\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="bc559-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="bc559-546">Libro IFRS 16\-Capa personalizada\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="bc559-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="bc559-547">Libro IFRS 16\-Capa personalizada\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="bc559-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="bc559-548">Libro IFRS 16\-Capa personalizada\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="bc559-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="bc559-549">Libro IFRS 16\-Capa personalizada\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="bc559-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="bc559-550">Capa actual \+ Capa personalizada \- Totales</span><span class="sxs-lookup"><span data-stu-id="bc559-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="bc559-551">1</span><span class="sxs-lookup"><span data-stu-id="bc559-551">1</span></span>          | <span data-ttu-id="bc559-552">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="bc559-552">Lease expense</span></span>            | <span data-ttu-id="bc559-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="bc559-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-554">1,000\.00</span></span>               |   | <span data-ttu-id="bc559-555">\-1.000</span><span class="sxs-lookup"><span data-stu-id="bc559-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="bc559-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-556">0\.00</span></span>                                   |
| <span data-ttu-id="bc559-557">2</span><span class="sxs-lookup"><span data-stu-id="bc559-557">2</span></span>          | <span data-ttu-id="bc559-558">Comisión bancaria</span><span class="sxs-lookup"><span data-stu-id="bc559-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="bc559-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="bc559-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="bc559-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-561">3\.00</span></span>                                   |
| <span data-ttu-id="bc559-562">3</span><span class="sxs-lookup"><span data-stu-id="bc559-562">3</span></span>          | <span data-ttu-id="bc559-563">Gasto de iVA</span><span class="sxs-lookup"><span data-stu-id="bc559-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="bc559-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="bc559-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="bc559-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-566">5\.00</span></span>                                   |
| <span data-ttu-id="bc559-567">4</span><span class="sxs-lookup"><span data-stu-id="bc559-567">4</span></span>          | <span data-ttu-id="bc559-568">Cuenta de compensación</span><span class="sxs-lookup"><span data-stu-id="bc559-568">Clearing account</span></span>         | <span data-ttu-id="bc559-569">\-1.000\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="bc559-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="bc559-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-571">0\.00</span></span>                   |   | <span data-ttu-id="bc559-572">1.000</span><span class="sxs-lookup"><span data-stu-id="bc559-572">1,000</span></span>                                           |                                                | <span data-ttu-id="bc559-573">\-1.000</span><span class="sxs-lookup"><span data-stu-id="bc559-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="bc559-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-574">0\.00</span></span>                                   |
| <span data-ttu-id="bc559-575">5</span><span class="sxs-lookup"><span data-stu-id="bc559-575">5</span></span>          | <span data-ttu-id="bc559-576">Proveedores</span><span class="sxs-lookup"><span data-stu-id="bc559-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="bc559-577">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="bc559-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-578">1,008\.00</span></span>                                         | <span data-ttu-id="bc559-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="bc559-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-580">0\.00</span></span>                                   |
| <span data-ttu-id="bc559-581">6</span><span class="sxs-lookup"><span data-stu-id="bc559-581">6</span></span>          | <span data-ttu-id="bc559-582">Activo por derecho de uso</span><span class="sxs-lookup"><span data-stu-id="bc559-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="bc559-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="bc559-584">22,794</span><span class="sxs-lookup"><span data-stu-id="bc559-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="bc559-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="bc559-585">22,793\.90</span></span>                              |
| <span data-ttu-id="bc559-586">7</span><span class="sxs-lookup"><span data-stu-id="bc559-586">7</span></span>          | <span data-ttu-id="bc559-587">Obligación de arrendamiento financiero</span><span class="sxs-lookup"><span data-stu-id="bc559-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="bc559-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="bc559-589">\-22.794</span><span class="sxs-lookup"><span data-stu-id="bc559-589">\-22,794</span></span>                                       | <span data-ttu-id="bc559-590">1.000</span><span class="sxs-lookup"><span data-stu-id="bc559-590">1,000</span></span>                                          | <span data-ttu-id="bc559-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="bc559-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="bc559-592">\-21.888\.87</span><span class="sxs-lookup"><span data-stu-id="bc559-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="bc559-593">8</span><span class="sxs-lookup"><span data-stu-id="bc559-593">8</span></span>          | <span data-ttu-id="bc559-594">Gastos de intereses</span><span class="sxs-lookup"><span data-stu-id="bc559-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="bc559-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="bc559-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="bc559-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="bc559-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="bc559-597">94\.97</span></span>                                  |
| <span data-ttu-id="bc559-598">9</span><span class="sxs-lookup"><span data-stu-id="bc559-598">9</span></span>          | <span data-ttu-id="bc559-599">Efectivo</span><span class="sxs-lookup"><span data-stu-id="bc559-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="bc559-600">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="bc559-601">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="bc559-602">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="bc559-603">10</span><span class="sxs-lookup"><span data-stu-id="bc559-603">10</span></span>         | <span data-ttu-id="bc559-604">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="bc559-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="bc559-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="bc559-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="bc559-606">949\.75</span></span>                                        | <span data-ttu-id="bc559-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="bc559-607">949\.75</span></span>                                 |
| <span data-ttu-id="bc559-608">11</span><span class="sxs-lookup"><span data-stu-id="bc559-608">11</span></span>         | <span data-ttu-id="bc559-609">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="bc559-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="bc559-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="bc559-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="bc559-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="bc559-611">\-949\.75</span></span>                                      | <span data-ttu-id="bc559-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="bc559-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]