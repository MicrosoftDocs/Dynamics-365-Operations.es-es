---
title: Almacenamiento de datos de vencimiento de cliente
description: Este tema describe el proceso de uso de almacenamiento externo para datos de vencimiento del cliente. Puede ejecutar el proceso de almacenamiento de datos de vencimiento del cliente para que la salida esté disponible para su exportación a un sistema externo.
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 497d49da84f4df90877908bef3031e079bc36066
ms.sourcegitcommit: d0e99545d722c924db57ae2bd06f72154a1f1f97
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "8557889"
---
# <a name="customer-aging-data-storage"></a>Almacenamiento de datos de vencimiento de cliente

[!include [banner](../includes/banner.md)]


Este tema describe el proceso de uso de almacenamiento externo para datos de vencimiento del cliente. En Microsoft Dynamics 365 Finance, puede ejecutar el proceso de almacenamiento de datos de vencimiento del cliente para que la salida esté disponible para su exportación a un sistema externo. Cuando ejecuta el proceso, las mismas opciones de informes de vencimiento que están disponibles en el sistema están disponibles para sistemas externos. Los detalles siempre se incluyen en los datos exportados.

Puede resultar útil poner los datos de vencimiento de los clientes a disposición de un sistema externo para su almacenamiento en los casos en que la salida contenga muchos clientes y / o muchas transacciones. Si el informe **de vencimientos de clientes** agota el tiempo de espera debido a que tiene demasiados datos para imprimir, esta función proporciona una forma alternativa de obtener los mismos datos.

## <a name="enable-the-customer-aging-data-storage-feature"></a>Habilitar la función de almacenamiento de datos de vencimientos de clientes

Antes de poder usar esta función debe habilitarla en su sistema. Los administradores pueden usar la configuración de gestión de funciones para verificar el estado de la función y habilitarla si es necesario. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** Crédito y cobros
- **Nombre de característica:** Almacenamiento de datos de vencimientos de clientes

## <a name="run-the-customer-aging-data-storage-process"></a>Ejecutar el proceso de almacenamiento de datos de vencimientos de clientes

1. Vaya a **Crédito y cobros \> Consultas e informes \> Cliente \> Almacenamiento de datos de vencimientos de clientes**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, especifique un nombre para el proceso.
4. Configure los parámetros restantes según sus necesidades.

    > [!NOTE]
    > Los detalles de la transacción siempre se incluyen y el procesamiento siempre se realiza en un trabajo por lotes.

5. Seleccione **Aceptar**.
6. Actualice la página **Almacenamiento de datos de vencimientos de clientes** para ver los valores de **Nombre del lote** y **Tiempo de ejecución por lotes** que se muestran junto con el valor de **Estado de procesamiento**. Cuando se completa el trabajo por lotes, el campo **Estado de procesamiento** se configura en **Terminado** y el campo **Número de líneas de vencimiento** está configurado. Si el trabajo por lotes es periódico, el campo **Estado de procesamiento** se configura en **En espera**.
7. Seleccione el botón **Filtrar** junto al campo **Número de líneas de vencimeinto** para revisar los filtros que se han agregado para el trabajo por lotes.

La página **Almacenamiento de datos de vencimiento de clientes** no incluye los resultados. Sin embargo, la entidad de datos **Almacenamiento de datos de vencimiento de clientes** le permite exportar la salida a cualquier formato que admita administración de datos.

> [!NOTE]
> Antes de realizar una exportación, agregue un filtro para limitar los resultados exportados al vencimiento más reciente. Por ejemplo, agregue los siguientes criterios para devolver la ejecución por lotes más reciente:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchName())
>
> También puede agregar los siguientes criterios para devolver la ejecución por lotes más reciente para el usuario actual:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchNameForCurrentUser())
