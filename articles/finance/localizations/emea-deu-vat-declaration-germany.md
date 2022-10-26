---
title: Declaración de IVA (Alemania)
description: Este artículo describe cómo configurar y generar una declaración anticipada del impuesto al valor agregado (IVA) para Alemania en el formato XML oficial.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 04c625b554d96f8ed28ceffef9647fe9cbf7fe2f
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689470"
---
# <a name="vat-declaration-germany"></a>Declaración de IVA (Alemania)

[!include [banner](../includes/banner.md)]

Este artículo describe cómo configurar y generar una declaración anticipada del impuesto al valor agregado (IVA) para Alemania en el formato XML oficial. Este artículo también explica cómo obtener una vista previa de la declaración de IVA en formato Microsoft Excel.

Para generar automáticamente el informe, cree suficientes códigos de impuestos sobre las ventas para mantener una contabilidad de IVA separada para cada casilla en la declaración de IVA anticipada. Además, en los parámetros específicos de la aplicación del formato de informes electrónicos (ER) para la declaración de IVA anticipada, asocie los códigos de impuestos sobre las ventas con el resultado de búsqueda de las búsquedas de las casillas de la declaración de IVA.

Para Alemania, debe configurar **Búsqueda de campos de informe**. Para obtener más información sobre cómo configurar parámetros específicos de la aplicación, consulte la sección [Configurar parámetros específicos de la aplicación para campos de declaración de IVA](#set-up-application-specific-parameters-for-vat-declaration-fields) más adelante en este artículo.

En la siguiente tabla, la columna "Resultado de la búsqueda" muestra el resultado de la búsqueda que está preconfigurado para una fila de declaración de IVA específica en el formato de declaración de IVA. Utilice esta información para asociar correctamente los códigos de impuestos sobre las ventas con el resultado de la búsqueda y luego con la fila de la declaración de IVA.

### <a name="vat-declaration-overview"></a><a name="vat-declaration-overview"></a>Resumen de la declaración de IVA

La declaración anticipada de IVA en Alemania contiene la siguiente información.

**SECCIÓN - ENTREGAS Y OTROS SERVICIOS**

**Ventas gravables**

| Fila | Casilla - base imponible | Casilla - importe de impuestos | Description                                                                                                                                      | Resultado de la búsqueda                                                                             |
|-----|----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 20  | 81             | Sin código     | Ventas gravables a un tipo del 19 por ciento.                                                                                                       | 20-TaxableSalesStandard</br>73-BadDebtsWriteOffStandard (81/50) – con signo menos             |
| 21  | 86             | Sin código     | Ventas gravables a un tipo del 7 por ciento.                                                                                                        | 21-TaxableSalesReduced</br>73-BadDebtsWriteOffReduced (86/50) – con signo menos               |
| 22  | 35             | 36               | Ventas sujetas a impuestos con otros tipos impositivos.                                                                                                                | 22-TaxableSalesOtherRates</br>73-BadDebtsWriteOffOtherRates (35/36/50) - con signo menos      |
| 23  | 77             | *Sin importe de impuesto*  | Entregas de empresas agrícolas y forestales de acuerdo con §24 de la Ley de IVA alemana (UStG) a clientes que tienen un número de identificación de IVA. | 23-EUSalesAverageRate24</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50) – con signo menos |
| 24  | 76             | 80               | Ventas por las que se debe pagar un impuesto, según §24 de la UStG (productos de aserradero, bebidas y líquidos alcohólicos).                                | 24-SalesAverageRate24</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50)                    |

**Ventas exentas de impuestos con deducción de impuestos de entrada**

| Fila | Casilla - base imponible | Casilla - importe de impuestos | Description                                                                       | Resultado de la búsqueda                       |
|-----|----------------|------------------|-----------------------------------------------------------------------------------|-------------------------------------|
| 26  | 41             | *Sin importe de impuesto*  | Envíos intracomunitarios a clientes que tengan un Id. de IVA.                       | 26-EUSales                          |
| 27  | 44             | *Sin importe de impuesto*  | Entregas intracomunitarias de vehículos nuevos a compradores que no tienen un Id. de IVA.    | 27-EUSalesNewVehicles               |
| 28  | 49             | *Sin importe de impuesto*  | Entregas intracomunitarias de vehículos nuevos fuera de empresa.                     | 28-EUSalesNewVehiclesOutsideCompany |
| 29  | 43             | *Sin importe de impuesto*  | Otras ventas libres de impuestos que tienen una deducción del impuesto soportado, como las entregas de exportación. | 29-ExportOtherTaxFreeSales          |

**Ventas exentas de impuestos sin deducción de impuestos de entrada**

| Fila | Casilla - base imponible | Casilla - importe de impuestos | Description                                            | Resultado de la búsqueda                           |
|-----|----------------|------------------|--------------------------------------------------------|-----------------------------------------|
| 30  | 48             | *Sin importe de impuesto*  | Ventas libres de impuestos que no tienen una deducción del impuesto soportado. | 30-TaxFreeSalesWithoutInputTaxDeduction |

**Adquisiciones intracomunitarias**

| Fila | Casilla - base imponible | Casilla - importe de impuestos | Description                                                                                                                   | Resultado de la búsqueda                                                    |
|-----|----------------|------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| 33  | 91             | *Sin importe de impuesto*  | Adquisiciones intracomunitarias libres de impuestos de algunos objetos y oro de inversión.                                                    | 33-TaxFreeEUPurchase                                             |
| 34  | 89             | Sin código     | Adquisiciones intracomunitarias sujetas a impuestos a un tipo impositivo del 19 por ciento.                                                             | 34-EUPurchaseStandard</br>34-UseTaxEUPurchaseStandard (89/61)        |
| 35  | 93             | Sin código     | Adquisiciones intracomunitarias sujetas a impuestos a un tipo impositivo del 7 por ciento.                                                              | 35-EUPurchaseReduced</br>35-UseTaxEUPurchaseReduced (93/61)          |
| 36  | 95             | 98               | Adquisiciones intracomunitarias sujetas a impuestos a otros tipos impositivos.                                                                      | 36-EUPurchaseOtherRates</br>36-UseTaxEUPurchaseOtherRates (95/98/61) |
| 37  | 94             | 96               | Adquisiciones intracomunitarias sujetas a impuestos de vehículos nuevos de proveedores que no tengan número de Id. de IVA, al tipo impositivo general. | 37-EUPurchaseVehicles</br>37-UseTaxEUPurchaseVehicles (94/96/61)     |

**SECCIÓN - BENEFICIARIO COMO DEUDOR FISCAL**

| Fila | Casilla - base imponible | Casilla - importe de impuestos | Description                                                                        | Resultado de la búsqueda                                                                                        |
|-----|----------------|------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 40  | 46             | 47               | Otros servicios de un emprendedor, basados en el resto del área de la Comunidad.        | 40-BeneficiaryTaxDebtor</br>40-UseTaxBeneficiaryTaxDebtor (46/47/66)                                                                              |
| 41  | 73             | 74               | Ventas que corresponden a la sección 13b (2) n.º 3 de UStG.                               | 41-BeneficiaryTaxDebtorRealEstateTransfer</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67) |
| 42  | 84             | 85               | Otros servicios que correspondan a la sección 13b (2) n.º 1, 2 y 4 hasta 12 de UStG. | 42-BeneficiaryTaxDebtorOther</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                           |

**SECCIÓN - INFORMACIÓN COMPLEMENTARIA SOBRE VENTAS**

| Fila | Casilla - base imponible  | Casilla - importe de impuestos | Description                                                                                                | Resultado de la búsqueda                                                                                    |
|-----|-----------------|------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| 48  | 42              | *Sin importe de impuesto*  | Entregas del primer cliente en el caso de transacciones triangulares intracomunitarias.                   | 48-DeliveriesFirstCustomerEUTriangular                                                           |
| 49  | 60              | *Sin importe de impuesto*  | Ventas sujetas a impuestos del empresario ejecutante por las que el destinatario del servicio adeude el impuesto. | 49-SalesServicesReverseCharge                                                                    |
| 50  | 21              | *Sin importe de impuesto*  | Otros servicios no tributables.                                                                                | 50-OtherServicesNonTaxable                                                                       |
| 51  | 45              | *Sin importe de impuesto*  | Otras ventas no imponibles cuando el lugar de ejecución no se encuentra en Alemania.                                    | 51-OtherSalesNonTaxable                                                                          |
| 52  | *Sin importe de impuesto* | *Sin importe de impuesto*  | IVA.                                                                                                       | Fila 20 + Fila 21 + Fila 22 + Fila2 4 + Fila 34 + Fila 35 + Fila 36 + Fila 37 + Fila 40 + Fila 41 + Fila 42 |

**SECCIÓN - IMPUESTO SOPORTADO DEDUCIBLE**

| Fila | Casilla - importe de impuestos | Description                                                                                                | Resultado de la búsqueda                                                                                                                                                                |
|-----|------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 55  | 66               | Importes de impuestos de factura soportados de otras empresas, servicios y transacciones triangulares intracomunitarias.     | 55-InputTax 40-UseTaxBeneficiaryTaxDebtor (46/47/66)</br>74-BadDebtsWriteOffInputTax (66/37) – con signo menos                                                                   |
| 56  | 61               | Importes de impuestos de entrada de la adquisición intracomunitaria de bienes.                                           | 56-InputTaxEUPurchase 34-UseTaxEUPurchaseStandard (89/61)</br>35-UseTaxEUPurchaseReduced (93/61)</br>36-UseTaxEUPurchaseOtherRates (95/98/61)</br>37-UseTaxEUPurchaseVehicles (94/96/61) |
| 57  | 62               | Impuesto sobre las ventas de importación incurrido.                                                                                 | 57-InputTaxImport                                                                                                                                                            |
| 58  | 67               | Importes de impuestos soportados por servicios según el significado de §13b de UStG.                                        | 58-InputTaxServices</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67)</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                                                 |
| 59  | 63               | Importes de impuestos soportados que se calculan de acuerdo con los tipos medios generales.                                  | 59-InputTaxAverageRates</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37) – con signo menos                                                                                    |
| 60  | 59               | Deducción del impuesto soportado por entregas intracomunitarias de vehículos nuevos fuera de una empresa y pequeñas empresas. | 60-InputTaxEUPurchaseNewVehicles</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37) – con signo menos                                                                  |
| 61  | 64               | Corrección de la deducción del impuesto soportado.                                                                     | 61-InputTaxCorrection                                                                                                                                                        |
| 62  | \-               | El importe restante.                                                                                      | Fila 52 - Fila 55 - Fila 56 - Fila 57 - Fila 58 - Fila 50 - Fila 60 - Fila 61                                                                                                        |

**SECCIÓN - OTROS IMPUESTOS**

| Fila | Casilla - importe de impuestos | Description                                                                                                                                                                                                                                                         | Resultado de la búsqueda                                 |
|-----|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 64  | 65               | Impuesto debido a un cambio en la forma de imposición e impuesto adicional sobre pagos iniciales gravados debido a un cambio en la tasa impositiva.                                                                                                                                        | 64-AdditionalTaxDueChangeTaxRate              |
| 65  | 69               | Importes de impuestos incorrectos o injustificados que se muestran en facturas e importes de impuestos adeudados de acuerdo con la sección 6a (4), oración 2, sección 17 (1), oración 7, o sección 25b (2) de UStG, o que son adeudados por una empresa de subcontratación o encargado del almacén. | 65-TaxDecreaseCorrection                      |
| 67  | 39               | Deducción del anticipo especial fijo por prórroga permanente. Por lo general, esta fila se completa solo con la última notificación anticipada del período impositivo.                                                                                                  | Parámetro de entrada del usuario en el cuadro de diálogo del informe |
| 68  | 83               | El pago anticipado restante del impuesto sobre ventas y exceso restante. Incluya un signo menos delante del importe.                                                                                                                                                          | Fila 62 + Fila 64 - Fila 65 - Fila 66             |

**SECCIÓN - INFORMACIÓN COMPLEMENTARIA SOBRE DEDUCCIONES**

| Fila | Casilla - base imponible | Casilla - importe de impuestos | Description                                                            | Resultado de la búsqueda                                                                                                                                                                                                    |
|-----|----------------|------------------|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 73  | 50             | \-               | Deducción de la base imponible en las líneas 20 a la 24.                      | 73-BadDebtsWriteOffStandard (81/50)</br>73-BadDebtsWriteOffReduced (86/50)</br>73-BadDebtsWriteOffOtherRates (35/36/50)</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50)</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50) |
| 74  | \-             | 37               | Deducción de los importes deducibles del impuesto soportado en las líneas 55, 59 y 60. | 74-BadDebtsWriteOffInputTax (66/37)</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37)</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37)                                                                     |

#### <a name="purchase-reverse-charge-vat"></a>IVA de cargo invertido de compras

Si configura códigos de impuestos sobre ventas para registrar IVA de cargo invertido entrante mediante el uso del impuesto sobre uso, asocie sus códigos de impuestos sobre las ventas con el resultado de búsqueda de **Búsqueda de campos de informe** que contiene "UseTax" en el nombre.

Como alternativa, puede configurar dos códigos de impuestos sobre las ventas independientes: uno para el IVA adeudado y otro para la deducción del IVA. Luego asocie cada código con los resultados de búsqueda correspondientes de **Búsqueda de campos de informe**.

Por ejemplo, para adquisiciones intracomunitarias sujetas a impuestos con un tipo estándar, configure el código de impuesto sobre las ventas **UT_S_EU** con el impuesto sobre el uso y asociarlo con el resultado de la búsqueda de **34-UseTaxEUPurchaseStandard** de **Búsqueda de campos de informe**. En este caso, las cantidades que utilizan el código de impuestos sobre las ventas **UT_S_EU** se reflejan en las casillas 089 y 061 (filas 34 y 56).

Alternativamente, puede configurar dos códigos de impuestos sobre las ventas:

  - **VAT_S_EU**, que tiene una tasa impositiva de -19 por ciento
  - **InVAT_S_EU**, que tiene una tasa impositiva de 19 por ciento

Luego asocie los códigos con los resultados de búsqueda de **Búsqueda de campos de informe** de este modo:

  - Asocie **VAT_S_EU** con el resultado de la búsqueda **34-EUPurchaseStandard**.
  - Asocie **InVAT_S_EU** con el resultado de la búsqueda **56-InputTaxEUPurchase**.

En este caso, las cantidades que utilizan el código de impuestos sobre las ventas **VAT_S_EU** se reflejan en la casilla 089 (fila 34). Los importes que utilizan el código de impuestos sobre las ventas **InVAT_S_EU** se reflejan en la casilla 061 (fila 56).

Para obtener más información sobre cómo configurar IVA de cargo invertido, consulte [Cargos invertidos](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configurar parámetros del sistema

Para generar una declaración de IVA, debe configurar el número de impuesto (Steuernummer) de su organización.

1. Vaya a **Administración de la organización** > **Organizaciones** > **Entidades jurídicas**.
2. Seleccione la entidad jurídica y, a continuación, seleccione **Id. de registro**.
3. Seleccione o cree la dirección en Alemania y luego, en la ficha desplegable **Identificación de registro**, seleccione **Agregar**.
4. En el campo **Tipo de registro**, seleccione el tipo de registro que está dedicado a Alemania y que utiliza la categoría de registro **Identificación de empresa (COID)**.
5. En el campo **Número de registro**, escriba el número de impuesto.
6. En la pestaña **General**, en el campo **Vigencia**, ingrese la fecha en que el número entra en vigencia.

Para obtener más información sobre cómo configurar categorías de registro y tipos de registro, consulte [Id. de registro](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-germany"></a>Configurar una declaración de IVA para Alemania

### <a name="import-er-configurations"></a>Importar configuraciones de ER

Abra el espacio de trabajo **Informes electrónicos** e importe las siguientes versiones o posteriores de estos formatos de ER:

   - VAT Declaration Excel (DE).version.101.16.12.xml
   - VAT Declaration XML (DE).version.101.16.xml

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>Configurar parámetros específicos de la aplicación para campos de declaración de IVA

Para generar automáticamente una declaración de IVA, asocie los códigos de impuestos sobre las ventas en la aplicación y los resultados de búsqueda en la configuración de ER.

> [!NOTE]
> Le recomendamos, que habilite la característica **Usar parámetros específicos de la aplicación de versiones anteriores de formatos de informes electrónicos** en el espacio de trabajo **Administración de características**. Cuando esta función está habilitada, los parámetros configurados para la versión anterior de un formato ER se aplican automáticamente a la versión posterior del mismo formato. Si esta característica no está habilitada, debe configurar los parámetros específicos de la aplicación explícitamente para cada versión de formato. La característica **Usar parámetros específicos de la aplicación de versiones anteriores de formatos de informes electrónicos** está disponible en el espacio de trabajo **Administración de características** a partir de la versión 10.0.23 de Finance. Para obtener más información sobre cómo configurar los parámetros de un formato ER para cada entidad jurídica, consulte [Configurar los parámetros de un formato de ER por entidad jurídica](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Siga estos pasos para definir qué códigos de impuestos sobre las ventas generan qué casillas en la declaración de IVA.

1. Vaya a **Espacios de trabajo** > **Informes electrónicos** y seleccione **Configuraciones de informes**.
2. Seleccione la configuración **XML de declaración de IVA (DE)** y luego seleccione **Configuraciones \> Configuración de parámetros específicos de la aplicación**.
3. En la página **Parámetros específicos de la aplicación**, en la ficha desplegable **Búsquedas**, seleccione **Búsqueda de campos de informe**.
4. En la ficha desplegable **Condiciones**, configure los siguientes campos para asociar los códigos de impuestos sobre las ventas y los campos del informe.

    | Campo                  | Description                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Resultado de la búsqueda          | Seleccione el valor del campo del informe. Para obtener más información sobre los valores y su asignación a filas de declaración de IVA, consulte la sección [Resumen de la declaración de IVA](#vat-declaration-overview) anteriormente en este artículo.                                                                                               |
    | Código de impuestos               | Seleccione el código de impuesto sobre las ventas para asociar con el campo del informe. Las transacciones de impuestos registradas que utilizan el código de impuestos sobre las ventas seleccionado se recopilarán en el cuadro de declaración correspondiente. Recomendamos que separe los códigos de impuestos sobre las ventas de tal manera que un código de impuestos sobre las ventas genere importes en un solo cuadro de declaración. |
    | Clasificador de transacciones | Si creó suficientes códigos de impuestos sobre las ventas para determinar un cuadro de declaración, seleccione **\*No en blanco\***. Si no creó suficientes códigos de impuestos sobre las ventas para que un código de impuestos sobre las ventas genere importes en un solo cuadro de declaración, puede configurar un clasificador de transacciones. Están disponibles los siguientes clasificadores de transacción:</br>-   **Compra**</br>-   **PurchaseExempt** (compra exenta de impuestos)</br>-   **PurchaseReverseCharge** (impuesto soportado de un cargo invertido de compra)</br>-   **Ventas**</br>-   **SalesExempt** (venta exenta de impuestos)</br>-   **SalesReverseCharge** (impuesto repercutido a partir de un cargo inverso de compra o un cargo inverso de venta)</br>-   **Impuesto de uso**. </br>Para cada clasificador de transacciones, también está disponible un clasificador para la nota de crédito. Por ejemplo, uno de estos clasificadores es **PurchaseCreditNote** (nota de crédito de compra).</br>Asegúrese de crear dos líneas para cada código de impuesto sobre las ventas: una que tenga el valor del clasificador de transacciones y otra que tenga el clasificador de transacciones para el valor de la nota de crédito. |

    > [!NOTE]
    > Asocie todos los códigos de impuestos sobre ventas con resultados de búsqueda. Si algún código de impuesto sobre ventas no debe generar valores en la declaración de IVA, asócielo con el resultado de la búsqueda **Otro**.

    ![Página de parámetros específicos de la aplicación](media/69ecb881f12819259ca166b9b98b8303.jpg)

5. En el campo **Estado**, cambie el valor de **Completado**.
6. En el panel de acciones, seleccione **Exportar** para exportar la configuración de los parámetros específicos de la aplicación.
7. Seleccione la configuración **Excel de declaración de IVA (DE)** configuración y, a continuación, en el panel de acciones, seleccione **Importar** para importar los parámetros que configuró para **XML de declaración de IVA (DE)**.
8. En el campo **Estado**, seleccione **Completado**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Configurar el formato de informe de IVA para los importes de vista previa en Excel

1. En el espacio de trabajo **Administración de características**, busque y habilite la característica **Informes de formato de declaración de IVA**.
2. Vaya a **Contabilidad general** > **Configuración** > **Parámetros de contabilidad general**.
3. En la pestaña **Impuesto**, en la ficha desplegable **Opciones de impuestos**, en el campo **Asignación de formato de declaración de IVA**, seleccione **Excel de declaración de IVA (EG)**.

   Este formato se imprime cuando ejecuta el informe **Notificar impuestos de venta para periodo de liquidación**. También se imprime cuando selecciona **Imprimir** en la página **Pago de impuestos sobre las ventas**.

4. Si debe informar las correcciones, en la sección **Reporte especial**, establezca **Incluir correcciones** en **Sí**.
5. En la página **Autoridades fiscales**, seleccione la autoridad fiscal y, en el campo **Diseño de informe**, seleccione **Predeterminado**.

Si está configurando la declaración de IVA en una entidad legal que tiene [múltiples registros de IVA](emea-reporting-for-multiple-vat-registrations.md), siga estos pasos:

1. Vaya a **Contabilidad general** > **Configuración** > **Parámetros de contabilidad general**.
2. En la pestaña **Impuesto de venta**, en la ficha desplegable **Informes electrónicos para países/regiones**, en la línea para **DEU**, seleccione el formato de ER **Excel de declaración de IVA (DE)**.

## <a name="set-up-electronic-messages"></a>Configurar mensajes electrónicos

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Descargar e importar el paquete de datos que tiene configuraciones de ejemplo para mensajes electrónicos

El paquete de datos contiene configuraciones de mensajes electrónicos que se utilizan para generar la declaración de IVA en formato XML y luego obtener una vista previa en Excel. Puede ampliar esta configuración o crear la suya propia. Para obtener más información sobre cómo trabajar con mensajería electrónica y crear su propia configuración, consulte [Mensajería electrónica](../general-ledger/electronic-messaging.md).

1. En [Microsoft Dynamics Lifecycle Services(LCS)](https://lcs.dynamics.com/v2), en la biblioteca de activos compartidos, seleccione **Paquete de datos** como tipo de activo y luego descargue **Paquete EM de declaración de IVA DE**. El nombre del archivo descargado es **DE VAT declaration EM package.zip**.
2. En Dynamics 365 Finance, en el espacio de trabajo **Administración de datos**, seleccione **Importación**.
3. En la ficha desplegable **Importar**, en el campo **Nombre de grupo** escriba un nombre para el trabajo.
4. En la ficha desplegable **Entidades seleccionadas**, seleccione **Agregar archivo**.
5. En el cuadro de diálogo **Agregar archivo**, verifique que el campo **Formato de datos de origen** está configurado en **Paquete**, seleccione **Cargar y agregar** y luego seleccione el archivo zip que descargó anteriormente.
6. Seleccione **Cerrar**.
7. Después de cargar las entidades de datos, en el Panel de acciones, seleccione **Importar**.
8. Vaya a **Impuesto** > **Consultas e informes** > **Mensajes electrónicos** > **Mensajes electrónicos** y valide el procesamiento de mensajes electrónicos que importó.

### <a name="configure-electronic-messages"></a>Configurar mensajes electrónicos

1. Vaya a **Impuestos** > **Configuración** > **Mensajes electrónicos** > **Acciones de rellenar registros**.
2. Seleccione la línea para **DE Rellenar registros de devolución de IVA** y luego seleccione **Editar consulta**.
3. Utilice el filtro para especificar los períodos de liquidación que se incluirán en el informe.
4. Si debe notificar transacciones de impuestos de otros períodos de liquidación en una declaración diferente, cree una nueva acción **Rellenar registros** y seleccione los períodos de liquidación adecuados.

## <a name="preview-the-vat-declaration-in-excel"></a>Vista previa de la declaración de IVA en Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Obtenga una vista previa de la declaración de IVA en Excel desde la tarea Notificar impuestos de venta para periodo de liquidación

1. Vaya a **Impuesto** > **Taras periódicas** > **Declaraciones** > **Impuestos de venta** > **Notificar impuestos de venta para periodo de liquidación**.
2. En el campo **Período de liquidación**, seleccione un valor.
3. En el campo **Versión de pago del impuesto**, seleccione uno de los siguientes valores:

    - **Original** : Genere un informe para las transacciones de impuestos sobre ventas del pago original del impuesto sobre ventas o antes de que se genere el pago del impuesto sobre ventas.
    - **Correcciones**: Genere un informe para las transacciones de impuestos sobre ventas de todos los pagos de impuestos sobre ventas posteriores del período.
    - **Lista total**: Genere un informe para todas las transacciones de impuestos sobre ventas del periodo, incluidas la original y todas las correcciones.

4. En el campo **Desde fecha**, seleccione la fecha de inicio del periodo de informe.
5. Seleccione **Aceptar** y revise el informe de Excel.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Liquidar y registrar impuestos

1. Vaya a **Impuestos** > **Tareas periódicas** > **Declaraciones** > **Impuestos** > **Liquidar y registrar impuestos**.
2. En el campo **Período de liquidación**, seleccione un valor.
3. En el campo **Versión de pago del impuesto**, seleccione uno de los siguientes valores:

    - **Original**: Genere el pago del impuesto sobre ventas original para el período de liquidación.
    - **Últimas correcciones**: Genere un pago de impuesto sobre ventas de corrección después de que se haya creado el pago del impuesto sobre ventas original para el período de liquidación.

4. En el campo **Desde fecha**, seleccione la fecha de inicio del periodo de informe.
5. Seleccione **Aceptar**.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Obtenga una vista previa de la declaración de IVA en Excel desde un pago de impuestos sobre ventas

1. Vaya a **Impuesto** > **Consultas e informes** > **Consultas de impuestos** > **Pagos de impuestos** y seleccione una línea de pago de impuestos sobre ventas.
2. Seleccione **Imprimir informe** y, después, seleccione **Aceptar**.
3. Revise el archivo de Excel que se genera para la línea de pago de impuestos sobre ventas seleccionada.

    > [!NOTE]
    > El informe se genera solo para la línea seleccionada de pago de impuestos sobre ventas. Si desea generar, por ejemplo, una declaración correctiva que contenga todas las correcciones para el período, o una declaración de reemplazo que contenga los datos originales y todas las correcciones, utilice la tarea periódica **Notificar impuestos de venta para periodo de liquidación**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Genere una declaración de IVA a partir de mensajes electrónicos

Cuando utiliza mensajes electrónicos para generar el informe, puede recopilar datos fiscales de varias entidades legales. Para obtener más información, consulte la sección [Ejecutar una declaración de IVA para varias entidades legales](#run-a-vat-declaration-for-multiple-legal-entities) más adelante en este artículo.

El siguiente procedimiento se aplica al ejemplo de procesamiento de mensajes electrónicos que importó de la biblioteca de activos compartidos de LCS.

1. Vaya a **Impuestos** > **Consultas e informes** > **Mensajes electrónicos** > **Mensajes electrónicos**.
2. En el panel izquierdo, seleccione **DE Declaración de IVA**.
3. En la ficha desplegable **Mensajes**, seleccione **Nuevo** y luego, en el cuadro de diálogo **Ejecutar procesamiento**, seleccione **Aceptar**.
4. Seleccione la línea de mensaje que se crea, ingrese una descripción y luego especifique las fechas de inicio y finalización de la declaración.

    > [!NOTE]
    > Los pasos del 5 al 7 son opcionales.

5. Opcional: en la ficha desplegable **Mensajes**, seleccione **Recopilar datos** y luego seleccione **Aceptar**. Los pagos de impuestos sobre ventas que se generaron anteriormente se agregan al mensaje. Para obtener más información, consulte la sección [Liquidar y registrar impuestos](#settle-and-post-sales-tax) descrita anteriormente en este artículo. Si omite este paso, aún puede generar una declaración de IVA utilizando el campo **Versión de declaración de impuestos** en el cuadro de diálogo **Declaración**.
6. Opcional: en la ficha desplegable **Elementos de mensaje**, revise los pagos de impuestos sobre ventas que se transfieren para su procesamiento. De forma predeterminada se incluyen todos los pagos de impuestos sobre ventas del período seleccionado que no se incluyeron en ningún otro mensaje del mismo procesamiento.
7. Opcional: seleccione **Documento original** para revisar los pagos de impuestos sobre ventas o seleccione **Eliminar** para excluir del procesamiento los pagos de impuestos sobre ventas. Si omite este paso, aún puede generar una declaración de IVA utilizando el campo **Versión de declaración de impuestos** en el cuadro de diálogo **Declaración**.
8. En la ficha desplegable **Mensajes**, seleccione **Actualizar estado**. En el cuadro de diálogo **Actualizar estado**, seleccione **Listo para generar** y luego seleccione **Aceptar**. Verifique que el estado del mensaje cambie a **Listo para generar**.
9. Seleccione **Generar informe**. Para obtener una vista previa de los importes de la declaración de IVA, en el cuadro de diálogo **Ejecutar procesamiento**, seleccione **Vista previa de informe** y luego seleccione **Aceptar**.
10. En el cuadro de diálogo **Parámetros de informes electrónicos**, establezca los siguientes campos y luego seleccione **Aceptar**.

    | **Campo**                                   | **Descripción**                                                                                                                                                                                                              |
    |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Período de liquidación                           | Seleccione el período de liquidación. Si seleccionó **Recopilar datos** en el paso 5, puede dejar este campo en blanco. El informe se generará para las transacciones de impuestos sobre ventas que se incluyen en los pagos de impuestos sobre ventas recaudados. |
    | Versión de declaración de impuestos                     | Seleccione uno de los siguientes valores:</br>-   **Original** – Genere un informe para las transacciones de impuestos sobre ventas del pago original del impuesto sobre ventas o antes de que se genere el pago del impuesto sobre ventas.</br>-   **Correcciones** – Genere un informe para las transacciones de impuestos sobre ventas de todos los pagos de impuestos sobre ventas posteriores del período.</br>-   **Lista total** – Genere un informe para todas las transacciones de impuestos sobre ventas del periodo, incluidas la original y todas las correcciones.|
    | Representante fiscal | Seleccione la parte que es representante fiscal para la declaración de IVA, si corresponde. La información sobre la parte seleccionada se exporta al elemento XML **DatenLieferant**. |
    | Persona de contacto | Seleccione una persona de la organización que sea un proveedor de datos. La información sobre la persona seleccionada se exporta al elemento XML **DatenLieferant**. |
    | Devolución correctiva | Seleccione **Sí** si se trata de una declaración de IVA correctiva. En este caso, el elemento XML KZ10 tendrá un valor de **1**.|
    | Documentos relacionados | Seleccione **Sí** si también envía documentos de respaldo. En este caso, el elemento XML KZ22 tendrá un valor de **1**.|
    | La orden de domiciliación de adeudo directo SEPA se revocará como excepción| Seleccione **Sí** si el mandato de domiciliación bancaria SEPA será revocado como excepción para este período de preinscripción. Por ejemplo, debido a solicitudes de compensación. Cualquier saldo restante se pagará por separado. En este caso, el elemento XML KZ26 tendrá un valor de **1**. |
    | Compensación del importe de reembolso deseado | Seleccione **Sí** si se desea compensar el importe del reembolso o si se ha asignado el importe del reembolso. En este caso, el elemento XML KZ29 tendrá un valor de **1**. |
    | Prórroga permanente de anticipo especial | Introduzca el importe de deducción del anticipo especial fijo por prórroga permanente. Este importe de deducción generalmente solo se completa en la última preinscripción del período impositivo. El importe se exporta en la fila 67 (casilla 39) y el elemento XML KZ39 de la declaración de IVA. |

11. Seleccione **Archivos adjuntos** en la esquina superior derecha de la página y a continuación seleccione **Abrir**.
12. Revise las cantidades en el documento de Excel y luego seleccione **Generar informe**.
13. Para generar una declaración de IVA en formato XML, en el cuadro de diálogo **Ejecutar procesamiento**, seleccione **Generar informe** y luego seleccione **Aceptar**.
14. En el cuadro de diálogo **Parámetros de informes electrónicos**, configure los campos como se describe en el paso 10.
15. Seleccione **Archivos adjuntos** en la esquina superior derecha de la página, descargue el archivo y utilícelo para enviarlo a la autoridad fiscal.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Ejecutar una declaración de IVA para varias entidades jurídicas

Para usar los formatos para notificar la declaración de IVA para un grupo de entidades legales, primero debe configurar los parámetros específicos de la aplicación de los formatos ER para códigos de impuestos sobre ventas de todas las entidades legales requeridas.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Configurar mensajes electrónicos para recopilar datos fiscales de varias entidades legales

Siga estos pasos para configurar mensajes electrónicos que recopilarán datos de varias entidades legales.

1. Vaya a **Espacios de trabajo** > **Administración de características**.
2. Busque y seleccione la característica **Consultas entre empresas para las acciones de rellenar registros** en la lista y, a continuación, seleccione **Habilitar ahora**.
3. Vaya a **Impuestos** > **Configuración** > **Mensajes electrónicos \> Acciones de rellenar registros**.
4. En la página **Acción de rellenar registros**, seleccione la línea para **DE Rellenar registros de declaración de IVA**.

   En la cuadrícula **Configuración de orígenes de datos**, un nuevo campo **Empresa** está disponible. Para los registros existentes, este campo muestra el identificador de la entidad legal actual.

5. En la cuadrícula **Configuración de orígenes de datos**, agregue una línea para cada entidad legal adicional que deba incluirse en los informes. Para cada nueva línea, establezca los siguientes campos.

    | Campo                  | Description                                                                                                                   |
    |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
    | Name                   | Ingrese un valor que le ayude a comprender de dónde proviene este registro. Por ejemplo, ingrese **Pago de IVA de subsidiaria 1**. |
    | Tipo de elemento de mensaje      | Seleccione **Devolución de IVA**. Este valor es el único valor disponible para todos los registros.                                    |
    | Tipo de cuenta           | Seleccione **Todo**.                                                                                                               |
    | Nombre de la tabla principal      | Especifique **TaxReportVoucher** para todos los registros.                                                                             |
    | Campo de número de documento  | Especifique **Vale** para todos los registros.                                                                                      |
    | Campo de fecha de documento    | Especifique **TransDate** para todos los registros.                                                                                    |
    | Campo de cuenta de documento | Especifique **TaxPeriod** para todos los registros.                                                                                    |
    | Empresa                | Seleccione el ID de la entidad jurídica.                                                                                            |
    | Consulta de usuario             | Esta casilla de verificación se selecciona automáticamente cuando define criterios seleccionando **Editar consulta**.                                 |

6. Para cada nueva línea, seleccione **Editar consulta** y especifique un periodo de liquidación relacionado para la entidad jurídica que se especifica en el campo **Empresa** en la línea.

Cuando se completa la configuración, la función **Recopilar datos** de la página **Mensajes electrónicos** recopila los pagos de impuestos sobre ventas de todas las entidades legales que definió.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
