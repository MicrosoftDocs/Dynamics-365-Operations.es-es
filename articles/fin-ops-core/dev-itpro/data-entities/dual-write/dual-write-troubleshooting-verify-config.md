---
title: Verifique que la doble escritura esté configurada en aplicaciones Finance and Operations y Dataverse
description: Este tema explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finance and Operations y en Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f389bcf133cc7e6a086167d5e26c1b8795d0fa30
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685548"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-dataverse"></a><span data-ttu-id="685fd-103">Verifique que la doble escritura esté configurada en aplicaciones Finance and Operations y Dataverse</span><span class="sxs-lookup"><span data-stu-id="685fd-103">Verify that dual-write is configured in Finance and Operations apps and Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="685fd-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="685fd-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="685fd-105">Específicamente explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finance and Operations y en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="685fd-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Dataverse.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="685fd-106">Verifique que la doble escritura esté configurada en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="685fd-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="685fd-107">Para determinar si los errores que ve cuando intenta guardar filas para la actualización provienen de doble escritura, primero verifique que la doble escritura esté configurada.</span><span class="sxs-lookup"><span data-stu-id="685fd-107">To determine whether the errors that you see when you try to save rows for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="685fd-108">Si tiene privilegios de administrador en la aplicación Finance and Operations, vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="685fd-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="685fd-109">Si se muestran los detalles de los entornos vinculados y la lista de mapas de tablas que se están ejecutando, se configura la escritura doble.</span><span class="sxs-lookup"><span data-stu-id="685fd-109">If the details of the linked environments and the list of table maps that are running are shown, dual-write is configured.</span></span>

    ![Comprobar la conexión de la aplicación Finance and Operations con privilegios de administrador](media/verify_fin_ops_1.png)

+ <span data-ttu-id="685fd-111">Si no tiene privilegios de administrador, aparecerá un mensaje de error: *No se pueden escribir datos en la entidad nombre de la entidad \<entity name\>*.</span><span class="sxs-lookup"><span data-stu-id="685fd-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="685fd-112">En el ejemplo de la siguiente ilustración, no puede crear una fila de cliente en la aplicación Finance and Operations, porque la escritura doble está configurada, pero el grupo de clientes y los datos de referencia de términos de pago no existen en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="685fd-112">In the example in the following illustration, you can't create a customer row in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Dataverse.</span></span>

    ![Verificando la conexión de la aplicación Finance and Operations cuando no tiene privilegios de administrador](media/verify_fin_ops_2.png)

<span data-ttu-id="685fd-114">Para obtener información sobre cómo solucionar problemas al crear datos en aplicaciones Finance and Operations, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="685fd-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a><span data-ttu-id="685fd-115">Verifique que la doble escritura esté configurada en Dataverse</span><span class="sxs-lookup"><span data-stu-id="685fd-115">Verify that dual-write is configured in Dataverse</span></span>

<span data-ttu-id="685fd-116">Cuando crea datos, si ve el campo **Empresa** en páginas en Dataverse, la doble escritura está configurada.</span><span class="sxs-lookup"><span data-stu-id="685fd-116">When you create data, if you see the **Company** field on pages in Dataverse, dual-write is configured.</span></span>

![Verificando la conexión Dataverse](media/verify_cds.png)

<span data-ttu-id="685fd-118">Para obtener información sobre cómo solucionar problemas al crear datos en Dataverse, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="685fd-118">For information about how to fix issues when you create data in Dataverse, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="685fd-119">Para obtener información sobre cómo ver los detalles del error si encuentra algún error mientras crea datos en Dataverse, consulte [Habilitar y ver el inicio de sesión de seguimiento del complemento Dataverse para ver detalles del error](dual-write-troubleshooting.md#enable-view-trace).</span><span class="sxs-lookup"><span data-stu-id="685fd-119">For information about how to view error details if you encounter any errors while you create data in Dataverse, see [Enable and view the plug-in trace log in Dataverse to view error details](dual-write-troubleshooting.md#enable-view-trace).</span></span>
