---
title: Determinar la combinación óptima de descuentos superpuestos
description: Cuando los descuentos se superponen, debe determinar la combinación de descuentos superpuestos que generará el total más bajo de la transacción o el descuento total más alto. Cuando el importe de descuento varía en función del precio de los productos que se han comprado, por ejemplo en el descuento comercial habitual “Compre 1 y llévese otro con X por ciento de descuento” (BOGO), este proceso se convierte en un problema de optimización combinatoria.
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount,
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 89643
ms.assetid: 09843c9a-3e19-4e4a-a8ce-80650f2095f9
ms.search.region: global
ms.search.industry: Retail
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 565722da65cbb711acedb5acf7de4edfbd615314
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023997"
---
# <a name="determine-the-optimal-combination-of-overlapping-discounts"></a><span data-ttu-id="694c5-104">Determinar la combinación óptima de descuentos superpuestos</span><span class="sxs-lookup"><span data-stu-id="694c5-104">Determine the optimal combination of overlapping discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="694c5-105">Cuando los descuentos se superponen, debe determinar la combinación de descuentos superpuestos que generará el total más bajo de la transacción o el descuento total más alto.</span><span class="sxs-lookup"><span data-stu-id="694c5-105">When discounts overlap, you must determine the combination of overlapping discounts that will produce the lowest transaction total or the highest total discount.</span></span> <span data-ttu-id="694c5-106">Cuando el importe de descuento varía en función del precio de los productos que se han comprado, por ejemplo en el descuento comercial habitual “Compre 1 y llévese otro con X por ciento de descuento” (BOGO), este proceso se convierte en un problema de optimización combinatoria.</span><span class="sxs-lookup"><span data-stu-id="694c5-106">When the discount amount varies according to the price of the products that are purchased, such as in the common "Buy 1, get 1 X percent off" (BOGO) retail discount, this process becomes an issue of combinatorial optimization.</span></span>

<span data-ttu-id="694c5-107">Este artículo se aplica a Microsoft Dynamics AX 2012 R3 con 3105973 KB (liberado el 2 de noviembre de 2015) o posterior, y Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="694c5-107">This article applies to Microsoft Dynamics AX 2012 R3 with KB 3105973 (released November 2, 2015) or later, and to Dynamics 365 Commerce.</span></span> <span data-ttu-id="694c5-108">Para determinar la combinación de descuentos superpuestos para aplicarlos de manera oportuna, hemos introducido un método de aplicación descuentos superpuestos.</span><span class="sxs-lookup"><span data-stu-id="694c5-108">To determine the combination overlapping discounts to apply in a timely manner, we have introduced a method for applying overlapping discounts.</span></span> <span data-ttu-id="694c5-109">A este nuevo método lo llamamos **clasificación de valor marginal**.</span><span class="sxs-lookup"><span data-stu-id="694c5-109">We call this new method **marginal value ranking**.</span></span> <span data-ttu-id="694c5-110">La clasificación de valor marginal se usa cuando el tiempo necesario para evaluar las combinaciones posibles de descuentos superpuestos supera un umbral que se puede configurar en la página **Parámetros de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="694c5-110">Marginal value ranking is used when the time that is required in order to evaluate the possible combinations of overlapping discounts exceeds a threshold that is configurable on the **Commerce parameters** page.</span></span> <span data-ttu-id="694c5-111">En el método de la clasificación de valor marginal, se calcula un valor para cada descuento superpuesto usando el valor del descuento en los productos compartidos.</span><span class="sxs-lookup"><span data-stu-id="694c5-111">In the marginal value ranking method, a value is calculated for each overlapping discount by using the discount's value on the shared products.</span></span> <span data-ttu-id="694c5-112">Los descuentos superpuestos se aplican desde el valor relativo más alto hasta el más bajo.</span><span class="sxs-lookup"><span data-stu-id="694c5-112">The overlapped discounts are then applied from the highest relative value to the lowest relative value.</span></span> <span data-ttu-id="694c5-113">Para obtener más información sobre el nuevo método, consulte la sección “Valor marginal”, más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="694c5-113">For details about the new method, see the "Marginal value" section, later in this article.</span></span> <span data-ttu-id="694c5-114">La clasificación de valor marginal no se usa cuando los importes de descuento de un producto no se ven afectados por otro producto de la transacción.</span><span class="sxs-lookup"><span data-stu-id="694c5-114">Marginal value ranking isn't used when the discount amounts for a product aren't affected by another product in the transaction.</span></span> <span data-ttu-id="694c5-115">Por ejemplo, este método no se usa para dos descuentos simples o para un descuento simple y un descuento por cantidad de un producto individual.</span><span class="sxs-lookup"><span data-stu-id="694c5-115">For example, this method isn't used for two simple discounts, or for a simple discount and a single product quantity discount.</span></span>

## <a name="discount-examples"></a><span data-ttu-id="694c5-116">Ejemplos de descuentos</span><span class="sxs-lookup"><span data-stu-id="694c5-116">Discount examples</span></span>

<span data-ttu-id="694c5-117">Puede crear un número ilimitado de descuentos en un conjunto habitual de productos.</span><span class="sxs-lookup"><span data-stu-id="694c5-117">You can create an unlimited number of discounts on a common set of products.</span></span> <span data-ttu-id="694c5-118">Sin embargo, dado que no hay límite, pueden producirse problemas de rendimiento si intenta calcular los descuentos que se deben usar en diversos productos.</span><span class="sxs-lookup"><span data-stu-id="694c5-118">However, because there is no limit, performance issues can occur when you try to calculate the discounts that should be used on the various products.</span></span> <span data-ttu-id="694c5-119">Los ejemplos siguientes muestran este problema con más detalle.</span><span class="sxs-lookup"><span data-stu-id="694c5-119">The following examples illustrate this issue in more detail.</span></span> <span data-ttu-id="694c5-120">En el ejemplo 1, comenzamos con dos productos y dos descuentos superpuestos.</span><span class="sxs-lookup"><span data-stu-id="694c5-120">In example 1, we start with two products and two overlapping discounts.</span></span> <span data-ttu-id="694c5-121">A continuación, en el ejemplo 2, mostramos cómo el problema aumenta a medida que se agregan más productos.</span><span class="sxs-lookup"><span data-stu-id="694c5-121">Then, in example 2, we show how the issue evolves as more products are added.</span></span>

### <a name="example-1-two-products-and-two-discounts"></a><span data-ttu-id="694c5-122">Ejemplo 1: Dos productos y dos descuentos</span><span class="sxs-lookup"><span data-stu-id="694c5-122">Example 1: Two products and two discounts</span></span>

<span data-ttu-id="694c5-123">En este ejemplo, se requieren dos productos para poder obtener cada descuento y los descuentos no se pueden combinar.</span><span class="sxs-lookup"><span data-stu-id="694c5-123">In this example, two products are required in order to qualify for each discount, and the discounts can't be combined.</span></span> <span data-ttu-id="694c5-124">Los descuentos en este ejemplo son descuentos **Mejor precio**.</span><span class="sxs-lookup"><span data-stu-id="694c5-124">The discounts in this example are **Best price** discounts.</span></span> <span data-ttu-id="694c5-125">Ambos productos pueden obtener ambos descuentos.</span><span class="sxs-lookup"><span data-stu-id="694c5-125">Both products qualify for both discounts.</span></span> <span data-ttu-id="694c5-126">Aquí están los dos descuentos.</span><span class="sxs-lookup"><span data-stu-id="694c5-126">Here are the two discounts.</span></span>

![Ejemplo de dos mejores precios/descuentos](./media/overlapping-discount-combo-01.jpg)

<span data-ttu-id="694c5-128">En dos productos cualquiera, el mejor de estos dos descuentos depende de los precios de los dos productos.</span><span class="sxs-lookup"><span data-stu-id="694c5-128">For any two products, the better of these two discounts depends on the prices of the two products.</span></span> <span data-ttu-id="694c5-129">Si el precio de ambos productos es igual o casi igual, el descuento 1 es mejor.</span><span class="sxs-lookup"><span data-stu-id="694c5-129">When the price of both products is equal or almost equal, discount 1 is better.</span></span> <span data-ttu-id="694c5-130">Si el precio de un producto es significativamente inferior al precio del otro producto, el descuento 2 es mejor.</span><span class="sxs-lookup"><span data-stu-id="694c5-130">When the price of one product is significantly less than the price of the other product, discount 2 is better.</span></span> <span data-ttu-id="694c5-131">A continuación se indica la regla matemática para evaluar estos dos descuentos entre sí.</span><span class="sxs-lookup"><span data-stu-id="694c5-131">Here is the mathematical rule for evaluating these two discounts against each other.</span></span>

![Regla para evaluar los descuentos](./media/overlapping-discount-combo-02.jpg)

> [!NOTE]
> <span data-ttu-id="694c5-133">Cuando el precio del producto 1 es igual a dos tercios del precio del producto 2, los dos descuentos son iguales.</span><span class="sxs-lookup"><span data-stu-id="694c5-133">When the price of product 1 is equal to two-thirds of the price of product 2, the two discounts are equal.</span></span> <span data-ttu-id="694c5-134">En este ejemplo, el porcentaje de descuento efectivo del descuento 1 varía entre un pequeño porcentaje (cuando los precios de los dos productos son muy diferentes) y un máximo de 25 por ciento (cuando los dos productos tienen el mismo precio).</span><span class="sxs-lookup"><span data-stu-id="694c5-134">In this example, the effective discount percentage for discount 1 varies from a few percent (when the prices of the two products are far apart) to a maximum of 25 percent (when the two products have the same price).</span></span> <span data-ttu-id="694c5-135">El porcentaje de descuento efectivo del descuento 2 es fijo.</span><span class="sxs-lookup"><span data-stu-id="694c5-135">The effective discount percentage for discount 2 is fixed.</span></span> <span data-ttu-id="694c5-136">Siempre es el 20 por ciento.</span><span class="sxs-lookup"><span data-stu-id="694c5-136">It's always 20 percent.</span></span> <span data-ttu-id="694c5-137">Dado que el porcentaje de descuento efectivo del descuento 1 tiene un intervalo que puede ser superior o inferior al descuento 2, el mejor descuento depende de los precios de los dos productos que se deben descontar.</span><span class="sxs-lookup"><span data-stu-id="694c5-137">Because the effective discount percentage for discount 1 has a range that can be more than or less than discount 2, the best discount depends on the prices of the two products that must be discounted.</span></span> <span data-ttu-id="694c5-138">En este ejemplo, el cálculo se completa rápidamente, ya que solo se aplican dos descuentos a solo dos productos.</span><span class="sxs-lookup"><span data-stu-id="694c5-138">In this example, the calculation is completed quickly, because only two discounts are applied on only two products.</span></span> <span data-ttu-id="694c5-139">Solo hay dos combinaciones posibles: una aplicación del descuento 1 o una aplicación del descuento 2.</span><span class="sxs-lookup"><span data-stu-id="694c5-139">There are only two possible combinations: one application of discount 1 or one application of discount 2.</span></span> <span data-ttu-id="694c5-140">No hay permutas que calcular.</span><span class="sxs-lookup"><span data-stu-id="694c5-140">There are no permutations to calculate.</span></span> <span data-ttu-id="694c5-141">El valor de cada descuento se calcula usando ambos productos, y se emplea el mejor descuento.</span><span class="sxs-lookup"><span data-stu-id="694c5-141">The value of each discount is calculated by using both products, and the best discount is used.</span></span>

### <a name="example-2-four-products-and-two-discounts"></a><span data-ttu-id="694c5-142">Ejemplo 2: Cuatro productos y dos descuentos</span><span class="sxs-lookup"><span data-stu-id="694c5-142">Example 2: Four products and two discounts</span></span>

<span data-ttu-id="694c5-143">A continuación, utilizaremos cuatro productos y los mismos dos descuentos.</span><span class="sxs-lookup"><span data-stu-id="694c5-143">Next, we will use four products and the same two discounts.</span></span> <span data-ttu-id="694c5-144">Los cuatro productos pueden obtener ambos descuentos.</span><span class="sxs-lookup"><span data-stu-id="694c5-144">All four products qualify for both discounts.</span></span> <span data-ttu-id="694c5-145">Existen doce combinaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="694c5-145">There are twelve possible combinations.</span></span> <span data-ttu-id="694c5-146">Al final, dos descuentos se aplicarán a la transacción con una de tres combinaciones posibles: dos aplicaciones del descuento 1, dos aplicaciones del descuento 2 o una aplicación del descuento 1 y una del descuento 2.</span><span class="sxs-lookup"><span data-stu-id="694c5-146">In the end, two discounts will be applied to the transaction in one of three combinations: two applications of discount 1, two applications of discount 2, or one application of discount 1 and one application of discount 2.</span></span> <span data-ttu-id="694c5-147">Para mostrar las combinaciones posibles, echaremos un vistazo a dos conjuntos diferentes de cuatro productos que tienen precios diferentes:</span><span class="sxs-lookup"><span data-stu-id="694c5-147">To illustrate the possible combinations, we will look at two different sets of four products that have different prices:</span></span>

- <span data-ttu-id="694c5-148">Los cuatro productos tienen el mismo precio, 15,00 $.</span><span class="sxs-lookup"><span data-stu-id="694c5-148">All four products have the same price, $15.00.</span></span> <span data-ttu-id="694c5-149">En este caso, la mejor combinación del descuento es dos aplicaciones del descuento 1.</span><span class="sxs-lookup"><span data-stu-id="694c5-149">In this case, the best discount combination is two applications of discount 1.</span></span> <span data-ttu-id="694c5-150">Dos productos se venderán al precio completo y dos con un 50 por ciento de descuento.</span><span class="sxs-lookup"><span data-stu-id="694c5-150">Two products will be full price, and two will be 50 percent off.</span></span> <span data-ttu-id="694c5-151">El total descontado de la transacción es 45 $ (15 + 15 + 7,50 + 7,50), que es 15 $ (el 25 por ciento) de descuento del total de 60 $ sin descuento.</span><span class="sxs-lookup"><span data-stu-id="694c5-151">The discounted total for the transaction is $45 (15 + 15 + 7.50 + 7.50), which is $15 (25 percent) off the undiscounted total of $60.</span></span> <span data-ttu-id="694c5-152">El descuento 2 es solo de 12 $(20 por ciento).</span><span class="sxs-lookup"><span data-stu-id="694c5-152">Discount 2 is only $12 (20 percent).</span></span>
- <span data-ttu-id="694c5-153">Los dos productos cuestan 20 $ cada uno, un producto cuesta 15 $ y un producto cuesta 5 $.</span><span class="sxs-lookup"><span data-stu-id="694c5-153">Two products are $20 each, one product is $15, and one product is $5.</span></span> <span data-ttu-id="694c5-154">En este caso, la mejor combinación de descuento es una aplicación del descuento 2 y una aplicación del descuento 1.</span><span class="sxs-lookup"><span data-stu-id="694c5-154">In this case, the best discount combination is one application of discount 2 and one application of discount 1.</span></span> <span data-ttu-id="694c5-155">En las siguientes tablas se muestran los descuentos.</span><span class="sxs-lookup"><span data-stu-id="694c5-155">The following tables illustrates the discounts.</span></span>

<span data-ttu-id="694c5-156">Para leer las tablas, utilice un producto de una fila y un producto de una columna.</span><span class="sxs-lookup"><span data-stu-id="694c5-156">To read the tables, use one product from a row and one product from a column.</span></span> <span data-ttu-id="694c5-157">Por ejemplo, en la tabla del descuento 1, si combina los dos productos de 20 $, recibe un 10 $ de descuento.</span><span class="sxs-lookup"><span data-stu-id="694c5-157">For example, in the table for discount 1, when you combine the two $20 products, you get $10 off.</span></span> <span data-ttu-id="694c5-158">En la tabla del descuento 2, si combina el producto de 15 $ y el de 5 $, recibe un descuento de 4 $.</span><span class="sxs-lookup"><span data-stu-id="694c5-158">In the table for discount 2, when you combine the $15 product and the $5 product, you get $4 off.</span></span>

![Ejemplo que utiliza cuatro productos para los mismos dos descuentos](./media/overlapping-discount-combo-03.jpg)

<span data-ttu-id="694c5-160">Primero, encontramos el descuento más alto disponible de dos productos con cualquiera de los descuentos.</span><span class="sxs-lookup"><span data-stu-id="694c5-160">First, we find the largest discount that is available from any two products by using either discount.</span></span> <span data-ttu-id="694c5-161">Las dos tablas muestran el importe de descuento de todas las combinaciones de los dos productos.</span><span class="sxs-lookup"><span data-stu-id="694c5-161">The two tables show the discount amount for all combinations of the two products.</span></span> <span data-ttu-id="694c5-162">Las partes sombreadas de las tablas representan los casos en los que un producto se empareja consigo mismo (algo imposible) o un emparejamiento inverso de dos productos que genere el mismo importe de descuento y que se puede ignorar.</span><span class="sxs-lookup"><span data-stu-id="694c5-162">The shaded portions of the tables represent either cases where a product is paired with itself, which we can't do, or a reverse pairing of two products that produces the same discount amount and can be ignored.</span></span> <span data-ttu-id="694c5-163">Al mirar las tablas, puede ver que el descuento 1 para los dos artículos de 20 $ es el descuento más alto disponible para cualquiera de los descuentos en los cuatro productos.</span><span class="sxs-lookup"><span data-stu-id="694c5-163">By looking at the tables, you can see that discount 1 for the two $20 items is the largest discount that is available for either discount on all four products.</span></span> <span data-ttu-id="694c5-164">(Este descuento se resalta en verde en la primera tabla.) Nos queda solo el producto de 15 $ y el de 5 $.</span><span class="sxs-lookup"><span data-stu-id="694c5-164">(This discount is highlighted in green in the first table.) That leaves only the $15 product and the $5 product.</span></span> <span data-ttu-id="694c5-165">Al mirar las dos tablas de nuevo, puede ver que, en estos dos productos, el descuento 1 otorga 2,50 $ de descuento, mientras que el descuento 2 otorga 4 $ de descuento.</span><span class="sxs-lookup"><span data-stu-id="694c5-165">By looking at the two tables again, you can see that, for these two products, discount 1 gives a $2.50 discount, whereas discount 2 gives a $4 discount.</span></span> <span data-ttu-id="694c5-166">Por lo tanto, seleccionamos el descuento 2.</span><span class="sxs-lookup"><span data-stu-id="694c5-166">Therefore, we select discount 2.</span></span> <span data-ttu-id="694c5-167">El descuento total es 14 $.</span><span class="sxs-lookup"><span data-stu-id="694c5-167">The total discount is $14.</span></span> <span data-ttu-id="694c5-168">Para poder visualizar esta discusión más fácilmente, aquí tenemos dos tablas adicionales que muestran el porcentaje de descuento efectivo para todas las combinaciones posibles de dos productos tanto para el descuento 1 como para el descuento 2.</span><span class="sxs-lookup"><span data-stu-id="694c5-168">To make this discussion easier to visualize, here are two additional tables that show the effective discount percentage for all possible two-product combinations for both discount 1 and discount 2.</span></span> <span data-ttu-id="694c5-169">Solo se incluye la mitad de la lista de combinaciones para estos dos descuentos y el orden en el que se colocan los dos productos en el descuento no importa.</span><span class="sxs-lookup"><span data-stu-id="694c5-169">Only half the list of combinations is included, because, for these two discounts, the order in which the two products are put into the discount doesn't matter.</span></span> <span data-ttu-id="694c5-170">El descuento efectivo más alto (25 por ciento) está resaltado en verde y el descuento efectivo más bajo (10 por ciento) está resaltado en rojo.</span><span class="sxs-lookup"><span data-stu-id="694c5-170">The highest effective discount (25 percent) is highlighted in green, and the lowest effective discount (10 percent) is highlighted in red.</span></span>

![Porcentaje de descuento efectivo para todas las combinaciones de dos producto para ambos descuentos](./media/overlapping-discount-combo-04.jpg)

> [!NOTE]
> <span data-ttu-id="694c5-172">Si los precios varían y compiten dos o más descuentos, la única forma de garantizar la mejor combinación de descuentos consiste en evaluar ambos descuentos y compararlos.</span><span class="sxs-lookup"><span data-stu-id="694c5-172">When prices vary, and two or more discount compete, the only way to guarantee the best combination of discounts is to evaluate both discounts and compare them.</span></span>

## <a name="total-possible-combinations"></a><span data-ttu-id="694c5-173">Total de combinaciones posibles</span><span class="sxs-lookup"><span data-stu-id="694c5-173">Total possible combinations</span></span>

<span data-ttu-id="694c5-174">Esta sección continúa el ejemplo de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="694c5-174">This section continues the example from the previous section.</span></span> <span data-ttu-id="694c5-175">Agregaremos más productos y otro descuento y veremos cuántas combinaciones deben calcularse y compararse.</span><span class="sxs-lookup"><span data-stu-id="694c5-175">We will add more products and another discount, and see how many combinations must be calculated and compared.</span></span> <span data-ttu-id="694c5-176">En la tabla siguiente muestra el número de combinaciones posibles de descuentos a medida que aumenta la cantidad de producto.</span><span class="sxs-lookup"><span data-stu-id="694c5-176">The following table shows the number of possible discount combinations as the product quantity increases.</span></span> <span data-ttu-id="694c5-177">En la siguiente tabla se muestra lo que ocurre cuando hay dos descuentos superpuestos, como en el ejemplo anterior, y cuando hay tres descuentos superpuestos.</span><span class="sxs-lookup"><span data-stu-id="694c5-177">The table shows what happens both when there are two overlapping discounts, as in the previous example, and when there are three overlapping discounts.</span></span> <span data-ttu-id="694c5-178">El número de combinaciones posibles de descuentos que se deben evaluar supera rápidamente lo que incluso un ordenador rápido puede calcular y comparar con una velocidad aceptable para las transacciones comerciales.</span><span class="sxs-lookup"><span data-stu-id="694c5-178">The number of possible discount combinations that must be evaluated soon exceeds what even a fast computer can calculate and compare quickly enough to be acceptable for retail transactions.</span></span>

![Número de combinaciones posibles de descuentos a medida que aumenta la cantidad de producto.](./media/overlapping-discount-combo-05.jpg)

<span data-ttu-id="694c5-180">Si se aplican cantidades incluso superiores o más descuentos superpuestos, el número total de combinaciones posibles de descuentos llega rápidamente a varios millones y el tiempo necesario para evaluar y seleccionar la mejor combinación posible comienza a notarse.</span><span class="sxs-lookup"><span data-stu-id="694c5-180">When even larger quantities or more overlapping discounts are applied, the total number of possible discount combinations quickly goes into the millions, and the time that is required in order to evaluate and select the best possible combination quickly becomes noticeable.</span></span> <span data-ttu-id="694c5-181">Se han realizado algunas optimizaciones en el motor de precio para reducir el número total de combinaciones que se deben evaluar.</span><span class="sxs-lookup"><span data-stu-id="694c5-181">Some optimizations have been done in the price engine to reduce the total number of combinations that must be evaluated.</span></span> <span data-ttu-id="694c5-182">Sin embargo, dado que el número de descuentos superpuestos y las cantidades en una transacción no están restringidos, se tendrá que evaluar siempre un gran número de combinaciones cuando haya descuentos superpuestos.</span><span class="sxs-lookup"><span data-stu-id="694c5-182">However, because the number overlapping discounts and the quantities in a transaction aren't limited, a large number of combinations will always have to be evaluated whenever there are overlapping discounts.</span></span> <span data-ttu-id="694c5-183">Este problema es al que se enfrenta la clasificación de valor marginal.</span><span class="sxs-lookup"><span data-stu-id="694c5-183">This issue is the issue that the marginal value ranking method addresses.</span></span>

## <a name="marginal-value-method"></a><span data-ttu-id="694c5-184">Método de valor marginal</span><span class="sxs-lookup"><span data-stu-id="694c5-184">Marginal value method</span></span>

<span data-ttu-id="694c5-185">Para resolver el problema de un número de combinaciones que aumenta exponencialmente, existe una optimización que calcula el valor por producto compartido de cada descuento en el conjunto de productos al que se pueden aplicar dos o más descuentos.</span><span class="sxs-lookup"><span data-stu-id="694c5-185">To resolve the issue of an exponentially increasing number of combinations that must be evaluated, an optimization exists that calculates the value per shared product of each discount on the set of products that two or more discounts can be applied to.</span></span> <span data-ttu-id="694c5-186">A este valor lo denominamos **valor marginal** del descuento de los productos compartidos.</span><span class="sxs-lookup"><span data-stu-id="694c5-186">We refer to this value as the **marginal value** of the discount for the shared products.</span></span> <span data-ttu-id="694c5-187">El valor marginal es el aumento medio por producto del importe de descuento total cuando se incluyen productos compartidos en cada descuento.</span><span class="sxs-lookup"><span data-stu-id="694c5-187">The marginal value is the average per product increase in the total discount amount when the shared products are included in each discount.</span></span> <span data-ttu-id="694c5-188">El valor marginal se calcula tomando el importe de descuento total (DTotal), restando el importe de descuento sin los productos compartidos (DMinus\\ Compartido) y dividiendo esa diferencia por el número de productos (ProductosCompartidos).</span><span class="sxs-lookup"><span data-stu-id="694c5-188">The marginal value is calculated by taking the total discount amount (DTotal), subtracting the discount amount without the shared products (DMinus\\ Shared), and dividing that difference by the number of shared products (ProductsShared).</span></span>

![Fórmula para calcular el valor marginal](./media/overlapping-discount-combo-06.jpg)

<span data-ttu-id="694c5-190">Después de calcular el valor marginal de cada descuento en un conjunto de productos compartidos, se aplican los descuentos a los productos compartidos en orden y exhaustivamente desde el valor marginal más alto hasta el más bajo.</span><span class="sxs-lookup"><span data-stu-id="694c5-190">After the marginal value of each discount on a shared set of products is calculated, the discounts are applied to the shared products in order, exhaustively, from highest marginal value to lowest marginal value.</span></span> <span data-ttu-id="694c5-191">En este método todas las posibilidades restantes de descuentos no se comparan cada vez que se aplica una instancia única de un descuento.</span><span class="sxs-lookup"><span data-stu-id="694c5-191">For this method, all remaining discount possibilities aren't compared every time after a single instance of a discount is applied.</span></span> <span data-ttu-id="694c5-192">En su lugar, los descuentos superpuestos se comparan una vez y después se aplican en orden.</span><span class="sxs-lookup"><span data-stu-id="694c5-192">Instead, the overlapping discounts are compared one time and then applied in order.</span></span> <span data-ttu-id="694c5-193">No se realiza ninguna comparación adicional.</span><span class="sxs-lookup"><span data-stu-id="694c5-193">No additional comparisons are done.</span></span> <span data-ttu-id="694c5-194">Puede configurar el umbral para cambiar al método de valor marginal en la ficha **Descuento** de la página **Parámetros de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="694c5-194">You can configure the threshold to switch to the marginal value method on the **Discount** tab of the **Commerce parameters** page.</span></span> <span data-ttu-id="694c5-195">El tiempo aceptable para calcular el descuento total varía en los diferentes sectores minoristas.</span><span class="sxs-lookup"><span data-stu-id="694c5-195">The acceptable time to calculate the total discount varies across retail industries.</span></span> <span data-ttu-id="694c5-196">Sin embargo, este tiempo normalmente va de milésimas de segundo a un segundo.</span><span class="sxs-lookup"><span data-stu-id="694c5-196">However, this time generally falls in the range of tens of milliseconds to one second.</span></span>