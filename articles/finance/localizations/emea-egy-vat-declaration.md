---
title: Declaración de IVA para Egipto
description: Este tema explica cómo configurar y generar el formulario de devolución de IVA para Egipto.
author: sndray
manager: AnnBe
ms.date: 03/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7859d5a5e3273cd6e55edd1c1ce9fc4699d7ab33
ms.sourcegitcommit: a3052f76ad71894dbef66566c07c6e2c31505870
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "5574347"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>Declaración de IVA para Egipto (EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

En este tema se explica cómo configurar y generar el formulario de devolución de IVA y los libros de compra y venta para entidades legales en Egipto.

El formulario de devolución de IVA para Egipto es el documento oficial que resume el importe total del impuesto del IVA repercutido adeudado, el importe total del impuesto del IVA soportado recuperable y el importe del impuesto del IVA correspondiente. El formulario se utiliza para todo tipo de contribuyentes y debe completarse manualmente a través del portal de la autoridad tributaria. El formulario de devolución de IVA se conoce comúnmente como presentación de devolución de IVA.

El formulario de devolución de IVA en Dynamics 365 Finance incluye los siguientes informes:

- Formulario de devolución de IVA número 10, que proporciona un desglose de importes, ajustes e importe de IVA por elemento de línea en el formulario de devolución de IVA, como se describe en la legislación.
- Libro de transacciones de venta
- Libro de transacciones de compras

## <a name="prerequisites"></a>Requisitos previos
La dirección principal de la entidad jurídica debe estar en Egipto.
En el espacio de trabajo **Administración de funciones**, habilite la característica siguiente:

   - (Egipto) Jerarquía de categorías del informe de impuestos sobre las ventas y las compras.

Para obtener más información acerca de cómo habilitar características, consulte [Visión general de la administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

En el espacio de trabajo **Informes electrónicos**, importe los siguientes formatos de informes electrónicos desde el repositorio:

- Excel de declaración de IVA (EG)

> [!NOTE]
> El formato anterior se basa en el **Modelo de declaración de impuestos** y usa la **Asignación de modelos de declaración de impuestos**. Se importarán automáticamente configuraciones adicionales.

Para obtener más información sobre cómo importar configuraciones de informes electrónicos, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Descargar configuraciones de informes electrónicos

La implementación de los formularios de devolución de IVA para Egipto se basa en configuraciones de informes electrónicos (ER). Para obtener más información sobre las capacidades y los conceptos de los informes configurables, consulte [Informes electrónicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Para ambientes de producción y pruebas de aceptación del usuario (UAT), consulte [Descargar configuraciones de informes electrónicos desde Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Para generar el formulario de devolución de IVA y los informes relacionados en una entidad jurídica de Egipto, cargue las siguientes configuraciones:

- Declaración de impuestos model.version.70.xml o versión posterior
- Modelo de declaración de impuestos mapping.version.70.120.xml o versión posterior
- Excel de declaración de IVA (EG).version.70.32 o versión posterior

Una vez que haya descargado las configuraciones ER desde Lifecycle Services (LCS) o el repositorio global, complete los siguientes pasos.

1. Vaya al espacio de trabajo **Informes electrónicos** y seleccione el mosaico **Configuraciones de informes** .
1. En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange** > **Cargar desde archivo XML**.
1. Cargue los archivos en el orden en que aparecen anteriormente. Una vez cargadas todas las configuraciones, el árbol de configuración debe estar presente en Finance.

## <a name="set-up-application-specific-parameters"></a>Configurar parámetros específicos de la aplicación

Los parámetros específicos de la aplicación le permiten establecer los criterios de cómo se clasificarán y calcularán las transacciones fiscales en cada línea cuando se genere el informe. La determinación se basa en la configuración del grupo de impuestos de artículos, el grupo de impuestos, el código de impuestos y otros criterios establecidos en la definición de búsqueda.

Los informes del libro de compras y ventas para Egipto incluyen un conjunto de columnas que corresponden a clasificaciones de transacciones específicas, como tipos de operaciones, productos y documentos que son específicos para Egipto. En lugar de incluir estas nuevas clasificaciones como nuevos datos de entrada cuando se publican las transacciones, las clasificaciones se determinarán en función de las diferentes búsquedas introducidas en **Configuraciones** > **Configurar parámetros específicos de la aplicación** > **Configuración** para cumplir con los requisitos de los informes de IVA para Egipto. 

![Página de parámetros específicos de la aplicación](media/egypt-vat-declaration-setup1.png)

Las siguientes configuraciones de búsqueda se utilizan para clasificar las transacciones en los informes de libros de IVA de compras y ventas:

- **PurchaseItemTypeLookup** > Columna O: tipo de artículo
- **VATRateTypeLookup** > Columna B: tipo de impuesto
- **VATRateTypeLookup** > Columna C: tipo de elemento de tabla
- **PurchaseOperationTypeLookup** > Columna A: tipo de documento
- **SalesOperationTypeLookup** > Columna N: tipo de operación
- **SalesItemTypeLookup** > Columna O: tipo de artículo

Complete los siguientes pasos para configurar las diferentes búsquedas utilizadas para generar la declaración de IVA y los informes de libros relacionados. 

1. En el espacio de trabajo **Informes electrónicos**, seleccione **Configuraciones** > **Configuración** para configurar las reglas para identificar la transacción de impuestos en el cuadro relacionado del formulario de devolución de IVA.
2. Seleccione la versión actual y en la ficha desplegable **Búsquedas**, seleccione el nombre de búsqueda. Por ejemplo, **SalesItemTypeLookup**. Esta búsqueda identifica la lista de clasificaciones en el libro de IVA de ventas que requiere la autoridad fiscal.
3. En la ficha desplegable **Condiciones**, seleccione **Agregar** y, en la nueva línea de la columna **Resultado de la búsqueda**, seleccione la línea relacionada que representa la clasificación en la **Columna O**.
4. En la columna **Grupo de impuestos**, seleccione el grupo de impuestos que se utiliza para identificar la clasificación. Por ejemplo, **Factura de venta nacional**. También puede utilizar el grupo de impuestos de artículos, el código de impuestos o la combinación de atributos de árbol si la configuración se define de otra manera. 
5. En la columna **Nombre**, seleccione la clasificación de transacción fiscal.
6. Repita los pasos 3-5 para todas las búsquedas disponibles.
7. Seleccione **Agregar** para incluir la línea de registro final y, en la columna **Resultado de la búsqueda**, seleccione **No aplicable**. 
8. En las columnas restantes, seleccione **No en blanco**. 

> [!NOTE]
> Cuando agrega el último registro, **No aplicable**, define la siguiente regla: cuando el grupo de impuestos, el grupo de impuestos del artículo, el código de impuestos y el nombre que se pasa como argumento no satisfacen ninguna de las reglas anteriores, las transacciones no se incluyen en el libro de IVA diferido. Aunque esta regla no se usa al generar el informe, la regla ayuda a evitar errores en la generación del informe cuando falta una configuración de regla.

Las siguientes tablas representan un ejemplo de configuración sugerida para las configuraciones de búsqueda descritas. 

**SalesItemTypeLookup**

| Resultado de la búsqueda         | Línea | Grupo de impuestos    | Grupo de impuestos de artículos    | Código de impuestos (código) | Nombre                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| Nacional              | 1    | VAT_LOCAL          | *Completado*             | *Completado*     | Sales                 |
| Nacional              | 2    | VAT_LOCAL          | *Completado*             | *Completado*     | SalesCreditNote       |
| Nacional              | 3    | VAT_FINALC         | *Completado*             | *Completado*     | Sales                 |
| Nacional              | 4    | VAT_FINALC         | *Completado*             | *Completado*     | SalesCreditNote       |
| Nacional              | 5    | VAT_PUBLIO         | *Completado*             | *Completado*     | Sales                 |
| Nacional              | 6    | VAT_PUBLIO         | *Completado*             | *Completado*     | SalesCreditNote       |
| Exportar                | 7    | VAT_EXPORT         | *Completado*             | *Completado*     | Sales                 |
| Exportar                | 8    | VAT_EXPORT         | *Completado*             | *Completado*     | SalesCreditNote       |
| Máquina y equipo | 9    | *Completado*        | VAT_M&E                 | *Completado*     | Sales                 |
| Máquina y equipo | 10   | *Completado*        | VAT_M&E                 | *Completado*     | SalesCreditNote       |
| Piezas de máquinas        | 11   | *Completado*        | VAT_PARTS               | *Completado*     | Sales                 |
| Piezas de máquinas        | 12   | *Completado*        | VAT_PARTS               | *Completado*     | SalesCreditNote       |
| Exenciones            | 13   | VAT_EXE            | *No en blanco*           | *Completado*     | SaleExempt            |
| Exenciones            | 14   | VAT_EXE            | *No en blanco*           | *Completado*     | SalesExemptCreditNote |
| No aplicable        | 15   | *En blanco*            | *En blanco*                 | VAT_ADJ         | *Completado*           |
| No aplicable        | 16   | *Completado*        | *Completado*             | *Completado*     | *Completado*           |

 **SalesOperationTypeLookup**

| Resultado de la búsqueda  | Línea | Grupo de impuestos de artículos    | Código de impuestos    | Nombre                  |
|----------------|------|-------------------------|-------------|-----------------------|
| Mercancías          | 1    | VAT_GOODS               | *Completado* | Sales                 |
| Mercancías          | 2    | VAT_GOODS               | *Completado* | SalesCreditNote       |
| Mercancías          | 3    | VAT_GOODS               | *Completado* | SaleExempt            |
| Mercancías          | 4    | VAT_GOODS               | *Completado* | SalesExemptCreditNote |
| Servicios       | 5    | VAT_SERV                | *Completado* | Sales                 |
| Servicios       | 6    | VAT_SERV                | *Completado* | SalesCreditNote       |
| Servicios       | 7    | VAT_SERV                | *Completado* | SaleExempt            |
| Servicios       | 8    | VAT_SERV                | *Completado* | SalesExemptCreditNote |
| Ajustes    | 9    | *En blanco*                 | VAT_ADJ     | Sales                 |
| Ajustes    | 10   | *En blanco*                 | VAT_ADJ     | Compra              |
| No aplicable | 11   | *Completado*             | *Completado* | *Completado*           |

**PurchaseItemTypeLookup**

| Resultado de la búsqueda          | Línea | Grupo de impuestos de artículos    | Código de impuestos    | Nombre                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| Mercancías                  | 1    | VAT_GOODS               | *Completado* | Compra                 |
| Mercancías                  | 2    | VAT_GOODS               | *Completado* | PurchaseCreditNote       |
| Servicios               | 3    | VAT_SERV                | *Completado* | Compra                 |
| Servicios               | 4    | VAT_SERV                | *Completado*  | PurchaseCreditNote       |
| Máquina y equipo  | 5    | VAT_M&E                 | *Completado* | Compra                 |
| Máquina y equipo  | 6    | VAT_M&E                 | *Completado* | PurchaseCreditNote       |
| Piezas de máquinas         | 7    | VAT_PARTS               | *Completado* | Compra                 |
| Piezas de máquinas         | 8    | VAT_PARTS               | *Completado* | PurchaseCreditNote       |
| Exenciones             | 9    | VAT_EXE                 | *No banco*  | PurchaseExempt           |
| Exenciones             | 10   | VAT_EXE                 | *Completado* | PurchaseExemptCreditNote |
| No aplicable         | 11   | *En blanco*                 | VAT_ADJ     | *Completado*              |
| No aplicable         | 12   | *Completado*             | *Completado* | *Completado*              |
| No aplicable         | 13   | *En blanco*                 | *Completado* | *Completado*              |

**PurchaseOperationTypeLookup**

| Resultado de la búsqueda  | Línea | Grupo de impuestos  | Código de impuestos    | Nombre                     |
|----------------|------|------------------|-------------|--------------------------|
| Nacional       | 1    | VAT_LOCAL        | *Completado* | Compra                 |
| Nacional       | 2    | VAT_LOCAL        | *Completado* | PurchaseCreditNote       |
| Nacional       | 3    | VAT_LOCAL        | *Completado* | PurchaseExempt           |
| Nacional       | 4    | VAT_LOCAL        | *Completado* | PurchaseExemptCreditNote |
| Importado       | 5    | VAT_IMPORT       | *Completado* | Compra                 |
| Importado       | 6    | VAT_IMPORT       | *Completado* | PurchaseCreditNote       |
| Importado       | 7    | VAT_IMPORT       | *Completado* | PurchaseExempt           |
| Importado       | 8    | VAT_IMPORT       | *Completado* | PurchaseExemptCreditNote |
| Ajustes    | 9    | *En blanco*          | VAT_ADJ     | PurchaseCreditNote       |
| Ajustes    | 10   | *En blanco*          | VAT_ADJ     | Compra                 |
| No aplicable | 11   | *Completado*      | *Completado* | *Completado*              |

**VATRateTypeLookup**

| Resultado de la búsqueda  | Línea | Código de impuestos (código) |
|----------------|------|-----------------|
| GeneralGoods   | 1    | VAT_ST          |
| GeneralGoods   | 2    | VAT_RD          |
| FirstTable     | 3    | *Completado*     |
| SecondTable    | 4    | *Completado*     |
| No aplicable | 5    | *Completado*     |


## <a name="set-up-general-ledger-parameters"></a>Configurar los parámetros de Contabilidad general

Para generar los informes del formulario de devolución de IVA en Microsoft Excel, defina un formato ER en la página **Parámetros del libro mayor**.

1. Vaya a **Impuesto** > **Configuración** > **Parámetros del libro mayor**.
2. En la pestaña **Impuesto**, en la sección **Opciones de impuestos**, en el campo **Asignación de formato de declaración de IVA**, seleccione **Excel de declaración de IVA (EG)**. Si deja el campo en blanco, el informe estándar de impuestos sobre las ventas se generará en formato SSRS.
3. Seleccione la **Jerarquía de categoría**. Esta categoría habilita el código de la mercancía en las transacciones de la pestaña Comercio exterior para permitir a los usuarios seleccionar y clasificar bienes y servicios. La descripción de esta clasificación se detalla en los informes de transacciones de compra y venta. Esta configuración es opcional.

![Formulario de declaración](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>Generar un informe de devolución de iVA
El proceso para preparar y enviar un informe de devolución de IVA para un período se basa en las transacciones de pago de impuestos que se registraron durante el trabajo Liquidar y registrar impuestos. Para obtener más información sobre liquidación de informes e impuestos, consulte [Descripción general de impuestos](../general-ledger/indirect-taxes-overview.md).

Complete los pasos siguientes para generar un informe de declaración de impuestos.

1. Vaya a **Impuestos** > **Declaraciones** > **Impuesto** > **Informe de impuestos para el período de liquidación** o **Liquidación y registro de impuestos**.
2. Seleccione el **Período de liquidación**.
3. Seleccione la fecha de inicio y luego seleccione la versión de pago de impuestos.
5. Seleccione **Aceptar**. 
6. Ingrese la cantidad de crédito del período anterior, si corresponde, o deje la cantidad en cero.
7. En el campo **Detalles de informe**, seleccione una de las opciones disponibles siguientes. 
   - **Libro de IVA soportado**: genere el informe de detalles de transacciones de impuestos sobre compras.
   - **Libro de IVA diferido**: genere el informe de detalles de transacciones de impuestos sobre ventas.
   - **Declaración de IVA**: genere solo el formulario de devolución de declaración de IVA.
8. Introduzca el nombre de la persona que está registrada para asignar el formulario.
9. Seleccione el idioma. Todos los informes se traducen en **en-us** y **ar-eg**.
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


