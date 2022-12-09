---
title: Explorador de origen de contabilidad
description: Este artículo proporciona información acerca de la página Explorador del origen de contabilidad, que puede usar para análisis detallado de la información de origen detrás de asientos contables de la contabilidad general.
author: RyanCCarlson2
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: kfend
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd5580dc0be37ec89e6c7934b47c7d5593d8716
ms.sourcegitcommit: 5f8f042f3f7c3aee1a7303652ea66e40d34216e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2022
ms.locfileid: "9806443"
---
# <a name="accounting-source-explorer"></a>Explorador de origen de contabilidad

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de la página **Explorador del origen de contabilidad**, que puede usar para análisis detallado de la información de origen detrás de asientos contables de la contabilidad general.

La página **Explorador de origen de la contabilidad** muestra la información de origen. Puede usarla como herramienta independiente o analizar los detalles detrás de asientos contables de la contabilidad general. Por ejemplo, puede usar la página para obtener la información de origen detallada para un saldo en saldo de comprobación o para una transacción de asiento. Puede usar la característica **Exportar a MS Excel** para segmentar y desglosar la información en Microsoft Excel (por ejemplo, en una tabla dinámica o un informe de tablas dinámicas).

La página **Explorador de origen de contabilidad** siempre muestra el mismo importe total por cuenta contable que muestra la Contabilidad general (por ejemplo, en un saldo de comprobación). Como en un saldo de comprobación, puede mostrar segmentos en columnas independientes. Solo tiene que seleccionar el conjunto adecuado de dimensiones financieras. 

Puede usar parámetros para definir un intervalo de fechas para el análisis. Esta funcionalidad también es similar a la funcionalidad de saldo de comprobación.

Para todos los documentos que usan el marco del documento de origen, la página **Explorador de origen de contabilidad** muestra información adicional basada en las distribuciones contables y, si procede, en distribuciones contables del proyecto. Esta información incluye los valores de **Tipo de importe monetario**, **Proyecto**, **Actividad**, **Categoría** y **Propiedad de línea**. A continuación se muestran algunos ejemplos del análisis que puede realizar:

- Desviaciones entre los pedidos de compra y las facturas de proveedor, porque cada desviación está representada por un tipo de importe monetario, como la desviación de cargos
- Gastos y horas facturables frente a no facturables por proyecto, unidad de negocio y cuenta principal

Para documentos de origen que usen el concepto de identidades de referencia de documento de origen, la página **Explorador de origen de contabilidad** muestra incluso más detalles, como los valores de **Cliente**, **Proveedor**, **Trabajador**, **Producto**, **Cantidad**, **Texto de unidad** y **Descripción**. A continuación se muestran algunos ejemplos del análisis que puede realizar:

- Los gastos de hotel por unidad de negocio y el marca de hotel para un período fiscal, en función de los informes de gastos
- Descuentos por proveedor, producto, departamento

Para estos documentos, también puede navegar hasta el documento de origen real desde la página **Explorador de origen de contabilidad**.

> [!NOTE]
> A partir de la versión 10.0.31, una nueva característica **Filtrado avanzado del explorador de fuentes de contabilidad** está disponible en Administración de características. Esta característica reemplaza el botón **Actualizar** para brindar una experiencia de consulta avanzada más sólida que se asemeja a lo que está disponible en la página **Transacciones de asiento**. El filtro avanzado le permitirá filtrar campos similares a los que encuentra en la página **Consulta de transacciones de asientos**, como **Cuenta contable**, **Unidad de negocio**, **Centro de costos** y **Departamento**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
