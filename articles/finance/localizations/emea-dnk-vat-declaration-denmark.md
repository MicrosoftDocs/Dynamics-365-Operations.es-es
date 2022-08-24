---
title: Declaración de IVA (Dinamarca)
description: Este artículo describe cómo configurar y generar una declaración anticipada del impuesto al valor agregado (IVA) para Dinamarca.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: a47b2b98d86daf50876c783f879362ec1addb579
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272152"
---
# <a name="vat-declaration-denmark"></a>Declaración de IVA (Dinamarca)

[!include [banner](../includes/banner.md)]

Este artículo describe cómo configurar el impuesto al valor agregado (IVA) para Dinamarca y ver la versión preliminar en Microsoft Excel.

Para generar automáticamente el informe, primero cree suficientes códigos de impuestos sobre las ventas para mantener una contabilidad de IVA separada para cada casilla en la declaración de IVA anticipada. Además, en los parámetros específicos de la aplicación del formato de informes electrónicos (ER) para la declaración de IVA anticipada, asocie los códigos de impuestos sobre las ventas con el resultado de búsqueda de las búsquedas de las casillas de la declaración de IVA.

Para Dinamarca, debe configurar **Búsqueda de campos de informe**. Para obtener más información sobre cómo configurar parámetros específicos de la aplicación, consulte la sección [Configurar parámetros específicos de la aplicación para campos de declaración de IVA](#set-up-application-specific-parameters) más adelante en este artículo.

En la siguiente tabla, la columna "Resultado de la búsqueda" muestra el resultado de la búsqueda que está preconfigurado para una fila de declaración de IVA específica en el formato de declaración de IVA. Utilice esta información para asociar correctamente los códigos de impuestos sobre las ventas con el resultado de la búsqueda y luego con la fila de la declaración de IVA.

### <a name="vat-declaration-overview"></a>Resumen de la declaración de IVA

La declaración de IVA en Dinamarca contiene la siguiente información.

**VAT repercutidos**

| Description                                                  | Base fiscal/Cantidad fiscal | Resultado de la búsqueda/Total                                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IVA diferido                                                   | Importe de impuestos          | **OutputVAT**</br> **DomesticVATUseTax** (también informado en el cuadro "IVA soportado")                                                                                                                                                                                                                                                                       |
| IVA sobre bienes, etc. Comprado en el extranjero                           | Importe de impuestos          | **PurchaseGoodsAbroad**</br>**PurchaseGoodsAbroadUseTax** (también informado en el cuadro "IVA soportado")</br>**PurchaseGoodsEU** (La base imponible se informa en la "Casilla A - adquisición de bienes").</br>**PurchaseGoodsEUUseTax** (La cantidad de impuestos también aparece en el cuadro "IVA soportado". La base imponible se informa en la "Casilla A - adquisición de bienes").                   |
| IVA sobre los servicios comprados en el extranjero sujetos a un cargo invertido | Importe de impuestos          | **PurchaseServicesAbroad**</br> **PurchaseServicesAbroadUseTax** (también informado en el cuadro "IVA soportado")</br>**PurchaseServicesEU** (La base imponible se informa en la "Casilla A - adquisición de servicios").</br>**PurchaseServicesEUUseTax** (La cantidad de impuestos también aparece en el cuadro "IVA soportado". La base imponible se informa en la "Casilla A - adquisición de servicios"). |
| Total a pagar                                                | Importe de impuestos          | Total de las tres cajas anteriores                                                                                                                                                                                                                                                                                                            |

**Deducciones**

| Description                                                                               | Base fiscal/Cantidad fiscal | Resultado de la búsqueda/Total                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IVA soportado                                                                                 | Importe de impuestos          | **InputVAT**</br> **DomesticVATUseTax** (también informado en el cuadro "IVA diferido")</br>**PurchaseGoodsAbroadUseTax** (también informado en el cuadro "IVA soportado en mercancías etc. comprado en el extranjero")</br>**PurchaseServicesAbroadUseTax** (también informado en el recuadro "IVA sobre servicios comprados en el extranjero sujetos a cobro revertido")</br>**PurchaseGoodsEUUseTax** (también informado en el cuadro "IVA soportado en mercancías etc. comprado en el extranjero")</br> **PurchaseServicesEUUseTax** (también informado en el recuadro "IVA sobre servicios comprados en el extranjero sujetos a cobro revertido") |
| Aranceles de gasolina y gas envasado                                                                  | Importe de impuestos          | **OilGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Aranceles de gas natural y gas de ciudad                                                             | Importe de impuestos          | **NaturalTownGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Aranceles de carbono                                                                               | Importe de impuestos          | **CarbonDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CO2Duty                                                                                   | Importe de impuestos          | **CO2Duty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Cargo de agua                                                                              | Importe de impuestos          | **WaterCharge**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Deducciones totales                                                                          | Importe de impuestos          | Total de las seis cajas anteriores                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Importe total de aranceles (importe positivo = realizar pago, importe negativo = recibir devolución) | Importe de impuestos          | "Total a pagar" – "Total de deducciones"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

**Información complementaria**

| Description                                                                                                                                                                                                                                | Base fiscal/Cantidad fiscal | Resultado de la búsqueda/Total                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------|
| Casilla A - adquisición de bienes. El valor sin IVA de la adquisición de bienes dentro de la Unión.                                                                                                                                                   | Base imponible            | **PurchaseGoodsEU PurchaseGoodsEUUseTax**       |
| Casilla A - adquisición de servicios. El valor sin IVA de la adquisición de servicios dentro de la Unión.                                                                                                                                             | Base imponible            | **PurchaseServicesEU PurchaseServicesEUUseTax** |
| Casilla B - suministro de bienes - a informar a "EU-ventas sin IVA"/DK VIES. El valor sin IVA del suministro de bienes dentro de la Unión                                                                                                           | Base imponible            | **SalesGoodsEU**                                |
| Casilla B - suministros - no informar a "EU-ventas sin IVA"/DK VIES. El valor sin IVA de determinados suministros dentro de la Unión, por ejemplo, de instalación, montaje, ventas a distancia y nuevos medios de transporte a personas que no sean sujetos pasivos. | Base imponible            | **SalesInstallationAssemblyEtcEU**              |
| Casilla B - prestación de servicios. El valor sin IVA de la prestación de servicios dentro de la Unión por la que el comprador está obligado a pagar el IVA como sujeto pasivo también debe declararse en "Ventas en la UE sin IVA"/DK VIES.                          | Base imponible            | **SalesServicesEU**                             |
| Casilla C - otros suministros. Valor del suministro de otros bienes y servicios que se suministren sin IVA en el territorio de Dinamarca, a otros Estados miembros de la UE y a terceros países o terceros territorios.                                     | Base imponible            | **OtherSuppliesWithoutVAT**                     |

#### <a name="purchase-reverse-charge-vat"></a>IVA de cargo invertido de compras

Si configura códigos de impuestos sobre ventas para registrar IVA de cargo invertido entrante mediante el uso del impuesto sobre uso, asocie sus códigos de impuestos sobre las ventas con el resultado de búsqueda de **Búsqueda de campos de informe** que contiene "UseTax" en el nombre.

Como alternativa, puede configurar dos códigos de impuestos sobre las ventas independientes: uno para el IVA adeudado y otro para la deducción del IVA. Luego asocie cada código con los resultados de búsqueda correspondientes de **Búsqueda de campos de informe**.

Por ejemplo, para adquisiciones intracomunitarias sujetas a impuestos, configure el código de impuesto sobre las ventas **UT_S_EU** con el impuesto sobre el uso y asociarlo con el resultado de la búsqueda de **PurchaseGoodsEUUseTax** de **Búsqueda de campos de informe**. En este caso, las cantidades de impuestos que utilizan el código de impuestos sobre las ventas **UT_S_EU** se reflejan en las casillas "IVA en bienes etc. comprados en el extranjero" e "IVA soportado". Las bases imponibles se reflejan en la "Casilla A - adquisición de bienes".

Alternativamente, puede configurar dos códigos de impuestos sobre las ventas:

- **VAT_S_EU**, que tiene una tasa impositiva de -25 por ciento
- **InVAT_S_EU**, que tiene una tasa impositiva de 25 por ciento

Luego asocie los códigos con los resultados de búsqueda de **Búsqueda de campos de informe** de este modo:

- Asocie **VAT_S_EU** con el resultado de la búsqueda **PurchaseGoodsEU**.
- Asocie **InVAT_S_EU** con el resultado de la búsqueda **InputVAT**.

En este caso, las cantidades de impuestos que utilizan el código de impuestos sobre las ventas **VAT_S_EU** se reflejan en las casillas "IVA en bienes etc. Comprada en el extranjero" y "Casilla A - adquisición de bienes". Los importes que utilizan el código de impuestos sobre las ventas **InVAT_S_EU** se reflejan en la casilla "IVA soportado".

Para obtener más información sobre cómo configurar IVA de cargo invertido, consulte [Cargos invertidos](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configurar parámetros del sistema

Para generar una declaración de IVA, debe configurar el número de IVA.

1. Vaya a **Administración de la organización** > **Organizaciones** > **Entidades jurídicas**.
2. Seleccione la entidad jurídica y, a continuación, seleccione **Id. de registro**.
3. Seleccione o cree la dirección en Dinamarca y luego, en la ficha desplegable **Identificación de registro**, seleccione **Agregar**.
4. En el campo **Tipo de registro**, seleccione el tipo de registro que está dedicado a Dinamarca y que utiliza la categoría de registro **Identificación de IVA**.
5. En el campo **Número de registro**, escriba el número de impuesto.
6. En la pestaña **General**, en el campo **Vigencia**, ingrese la fecha en que el número entra en vigencia.

Para obtener más información sobre cómo configurar categorías de registro y tipos de registro, consulte [Id. de registro](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-preview-for-denmark"></a>Configurar una vista previa de declaración de IVA para Dinamarca

### <a name="import-er-configurations"></a>Importar configuraciones de ER

Abra el espacio de trabajo **Informes electrónicos** espacio de trabajo e importe el formato ER **Declaración de IVA Excel (DK)**.

Para obtener más información, consulte [Descargue las configuraciones de ER del repositorio global del servicio de configuración](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters"></a>Configurar parámetros específicos de la aplicación para campos de declaración de IVA

> [!NOTE]
> Le recomendamos, que habilite la característica **Usar parámetros específicos de la aplicación de versiones anteriores de formatos de informes electrónicos** en el espacio de trabajo **Administración de características**. Cuando esta función está habilitada, los parámetros configurados para la versión anterior de un formato ER se aplican automáticamente a la versión posterior del mismo formato. Si esta característica no está habilitada, debe configurar los parámetros específicos de la aplicación explícitamente para cada versión de formato. La característica **Usar parámetros específicos de la aplicación de versiones anteriores de formatos de informes electrónicos** está disponible en el espacio de trabajo **Administración de características** a partir de la versión 10.0.23 de Finance. Para obtener más información sobre cómo configurar los parámetros de un formato ER para cada entidad jurídica, consulte [Configurar los parámetros de un formato de ER por entidad jurídica](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Para generar automáticamente una declaración de IVA, asocie los códigos de impuestos sobre las ventas en la aplicación y los resultados de búsqueda en la configuración de ER.

Siga estos pasos para definir qué códigos de impuestos sobre las ventas generan qué casillas en la declaración de IVA.

1. Vaya a **Espacios de trabajo** > **Informes electrónicos** y seleccione **Configuraciones de informes**.
2. Seleccione la configuración **Excel de declaración de IVA (DK)** y luego seleccione **Configuraciones \> Configuración de parámetros específicos de la aplicación**.
3. En la página **Parámetros específicos de la aplicación**, en la ficha desplegable **Búsquedas**, seleccione **Búsqueda de campos de informe**.
4. En la ficha desplegable **Condiciones**, configure los siguientes campos para asociar los códigos de impuestos sobre las ventas y los campos del informe.

    | Campo                  | Description                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Resultado de la búsqueda          | Seleccione el valor del campo del informe. Para obtener más información sobre los valores y su asignación a filas de declaración de IVA, consulte la sección [Resumen de la declaración de IVA](#vat-declaration-overview) anteriormente en este artículo.                                                                                               |
    | Código de impuestos               | Seleccione el código de impuesto sobre las ventas para asociar con el campo del informe. Las transacciones de impuestos registradas que utilizan el código de impuestos sobre las ventas seleccionado se recopilarán en el cuadro de declaración correspondiente. Recomendamos que separe los códigos de impuestos sobre las ventas de tal manera que un código de impuestos sobre las ventas genere importes en un solo cuadro de declaración. |
    | Clasificador de transacciones | Si creó suficientes códigos de impuestos sobre las ventas para determinar un cuadro de declaración, seleccione **\*No en blanco\***. Si no creó suficientes códigos de impuestos sobre las ventas para que un código de impuestos sobre las ventas genere importes en un solo cuadro de declaración, puede configurar un clasificador de transacciones. Están disponibles los siguientes clasificadores de transacción:</br>-   **Compra**</br>-   **PurchaseExempt** (compra exenta de impuestos)</br>-   **PurchaseReverseCharge** (impuesto soportado de un cargo invertido de compra)</br>-   **Ventas**</br>-   **SalesExempt** (venta exenta de impuestos)</br>-   **SalesReverseCharge** (impuesto repercutido a partir de un cargo inverso de compra o un cargo inverso de venta)</br>-   **Impuesto de uso**. </br>Para cada clasificador de transacciones, también está disponible un clasificador para la nota de crédito. Por ejemplo, uno de estos clasificadores es **PurchaseCreditNote** (nota de crédito de compra).</br>Asegúrese de crear dos líneas para cada código de impuesto sobre las ventas: una que tenga el valor del clasificador de transacciones y otra que tenga el clasificador de transacciones para el valor de la nota de crédito. |


    > [!NOTE]
    > Asocie todos los códigos de impuestos sobre ventas con resultados de búsqueda. Si algún código de impuesto sobre ventas no debe generar valores en la declaración de IVA, asócielo con el resultado de la búsqueda **Otro**.

    ![Página de parámetros específicos de la aplicación.](media/7db74920fad66a0db7fad60758698cc0.png)


5. En el campo **Estado**, cambie el valor de **Completado**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Configurar el formato de informe de IVA para los importes de vista previa en Excel

1. En el espacio de trabajo **Administración de características**, busque y seleccione la característica **Informes de formato de declaración de IVA**. característica en la lista, a continuación, seleccione **Habilitar ahora**.
2. Vaya a **Contabilidad general** > **Configuración** > **Parámetros de contabilidad general**.
3. En la pestaña **Impuesto**, en la ficha desplegable **Opciones de impuestos**, en el campo **Asignación de formato de declaración de IVA**, seleccione el formato de ER **Excel de declaración de IVA (DK)**.

   Este formato se imprime cuando ejecuta el informe **Notificar impuestos de venta para periodo de liquidación**. También se imprime cuando selecciona **Imprimir** en la página **Pago de impuestos sobre las ventas**.

4. En la página **Autoridades fiscales**, seleccione la autoridad fiscal y, a continuación, en el campo **Diseño de informe**, seleccione **Predeterminado**.

Si está configurando la declaración de IVA en una entidad legal que tiene [múltiples registros de IVA](emea-reporting-for-multiple-vat-registrations.md), siga estos pasos.

1. Vaya a **Contabilidad general** \> **Configuración** \> **Parámetros de Contabilidad general**.
2. En la pestaña **Impuesto de venta**, en la ficha desplegable **Informes electrónicos para países/regiones**, en la línea para **DEU**, seleccione el formato de ER **Excel de declaración de IVA (DK)**.

## <a name="set-up-electronic-messages"></a>Configurar mensajes electrónicos

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Descargar e importar el paquete de datos que tiene configuraciones de ejemplo para mensajes electrónicos

El paquete de datos contiene configuraciones de mensajes electrónicos que se utilizan para generar la vista previa declaración de IVA en Excel. Puede ampliar esta configuración o crear la suya propia. Para obtener más información sobre cómo trabajar con mensajería electrónica y crear su propia configuración, consulte [Mensajería electrónica](../general-ledger/electronic-messaging.md).

1. En [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), en la biblioteca de activos compartidos, seleccione **Paquete de datos** como tipo de activo y luego descargue **Paquete de declaración de IVA DK**. El nombre del archivo descargado es **DK VAT declaration package.zip**.
2. En Finance, en el espacio de trabajo **Administración de datos**, seleccione **Importación**.
3. En la ficha desplegable **Importar**, en el campo **Nombre de grupo** escriba un nombre para el trabajo.
4. En la ficha desplegable **Entidades seleccionadas**, seleccione **Agregar archivo**.
5. En el cuadro de diálogo **Agregar archivo**, verifique que el campo **Formato de datos de origen** está configurado en **Paquete**, seleccione **Cargar y agregar** y luego seleccione el archivo zip que descargó anteriormente.
6. Seleccione **Cerrar**.
7. Después de cargar las entidades de datos, en el Panel de acciones, seleccione **Importar**.
8. Vaya a **Impuesto** > **Consultas e informes** > **Mensajes electrónicos** > **Mensajes electrónicos** y valide el procesamiento de mensajes electrónicos que importó (**declaración de IVA DK**).

### <a name="configure-electronic-messages"></a>Configurar mensajes electrónicos

1. Vaya a **Impuestos** > **Configuración** > **Mensajes electrónicos** > **Acciones de rellenar registros**.
2. Seleccione la línea para **DK Rellenar registros de devolución de IVA** y luego seleccione **Editar consulta**.
3. Utilice el filtro para especificar los períodos de liquidación que se incluirán en el informe.
4. Si debe notificar transacciones de impuestos de otros períodos de liquidación en una declaración diferente, cree una nueva acción **Rellenar registros** y seleccione los períodos de liquidación adecuados.

## <a name="preview-the-vat-declaration-in-excel"></a>Vista previa de la declaración de IVA en Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a><a name="preview-vat-excel"></a>Obtenga una vista previa de la declaración de IVA en Excel desde la tarea Notificar impuestos de venta para periodo de liquidación

1. Vaya a **Impuesto** > **Taras periódicas** > **Declaraciones** > **Impuestos de venta** > **Notificar impuestos de venta para periodo de liquidación**.
2. En el campo **Período de liquidación**, seleccione un valor.
3. En el campo **Versión de pago del impuesto**, seleccione uno de los siguientes valores:

    - **Original** : Genere un informe para las transacciones de impuestos sobre ventas del pago original del impuesto sobre ventas o antes de que se genere el pago del impuesto sobre ventas.
    - **Correcciones**: Genere un informe para las transacciones de impuestos sobre ventas de todos los pagos de impuestos sobre ventas posteriores del período.
    - **Lista total**: Genere un informe para todas las transacciones de impuestos sobre ventas del periodo, incluidas la original y todas las correcciones.

4. En el campo **Desde fecha**, seleccione la fecha de inicio del periodo de informe.
5. Seleccione **Aceptar** y revise el informe de Excel.

### <a name="settle-and-post-sales-tax"></a>Liquidar y registrar impuestos

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
> El informe se genera solo para la línea seleccionada de pago de impuestos sobre ventas. Si debe generar, por ejemplo, una declaración correctiva que contenga todas las correcciones para el período, o una declaración de reemplazo que contenga los datos originales y todas las correcciones, utilice la tarea periódica **Notificar impuestos de venta para periodo de liquidación**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Genere una declaración de IVA a partir de mensajes electrónicos

Cuando utiliza mensajes electrónicos para generar el informe, puede recopilar datos fiscales de varias entidades legales. Para obtener más información, consulte la sección [Ejecutar una declaración de IVA para varias entidades legales](#run-vat-declaration) más adelante en este artículo.

El siguiente procedimiento se aplica al ejemplo de procesamiento de mensajes electrónicos que importó antes de la biblioteca de activos compartidos de LCS.

1. Vaya a **Impuestos \> Consultas e informes \> Mensajes electrónicos \> Mensajes electrónicos**.
2. En el panel izquierdo, seleccione **DK Declaración de IVA**.
3. En la ficha desplegable **Mensajes**, seleccione **Nuevo** y luego, en el cuadro de diálogo **Ejecutar procesamiento**, seleccione **Aceptar**.
4. Seleccione la línea de mensaje que se crea, ingrese una descripción y luego especifique las fechas de inicio y finalización de la declaración.

   > [!NOTE]
   > Los pasos del 5 al 7 son opcionales.

5. Opcional: en la ficha desplegable **Mensajes**, seleccione **Recopilar datos** y luego seleccione **Aceptar**. Los pagos de impuestos sobre ventas que se generaron anteriormente se agregan al mensaje. Para obtener más información, consulte la sección [Liquidar y registrar impuestos](#settle-and-post-sales-tax) descrita anteriormente en este artículo. Si omite este paso, aún puede generar una declaración de IVA utilizando el campo **Versión de declaración de impuestos** en el cuadro de diálogo **Declaración**.
6. Opcional: en la ficha desplegable **Elementos de mensaje**, revise los pagos de impuestos sobre ventas que se transfieren para su procesamiento. De forma predeterminada se incluyen todos los pagos de impuestos sobre ventas del período seleccionado que no se incluyeron en ningún otro mensaje del mismo procesamiento.
7. Opcional: seleccione **Documento original** para revisar los pagos de impuestos sobre ventas o seleccione **Eliminar** para excluir del procesamiento los pagos de impuestos sobre ventas. Si omite este paso, aún puede generar una declaración de IVA utilizando el campo **Versión de declaración de impuestos** en el cuadro de diálogo **Declaración**.
8. En la ficha desplegable **Mensajes**, seleccione **Actualizar estado**. En el cuadro de diálogo **Actualizar estado**, seleccione **Listo para generar** y luego seleccione **Aceptar**. Verifique que el estado del mensaje cambie a **Listo para generar**.
9. Seleccione **Generar informe**. Para obtener una vista previa de los importes de la declaración de IVA, en el cuadro de diálogo **Ejecutar procesamiento**, seleccione **Vista previa de informe** y luego seleccione **Aceptar**.
10. En el cuadro de diálogo **Parámetros de informes electrónicos**, configure los campos como se describe en la sección [Obtenga una vista previa de la declaración de IVA en Excel desde la tarea periódica Informe de impuestos sobre las ventas para el período de liquidación](#preview-vat-excel) anterior de este artículo y, a continuación, seleccione **Aceptar**.
11. Seleccione el botón **Adjuntos** (símbolo de clip de papel) en la esquina superior derecha de la página y después seleccione **Abrir**. Revise las cantidades en el documento de Excel.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-vat-declaration"></a>Ejecutar una declaración de IVA para varias entidades jurídicas

Para usar los formatos para notificar la declaración de IVA para un grupo de entidades legales, primero debe configurar los parámetros específicos de la aplicación de los formatos ER para códigos de impuestos sobre ventas de todas las entidades legales requeridas.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Configurar mensajes electrónicos para recopilar datos fiscales de varias entidades legales

Siga estos pasos para configurar mensajes electrónicos para recopilar datos de varias entidades legales.

1. Vaya a **Espacios de trabajo** > **Administración de características**.
2. Busque y seleccione la característica **Consultas entre empresas para las acciones de rellenar registros** en la lista y, a continuación, seleccione **Habilitar ahora**.
3. Vaya a **Impuestos** > **Configuración** > **Mensajes electrónicos** > **Acciones de rellenar registros**.
4. En la página **Acción de rellenar registros**, seleccione la línea para **DK Rellenar registros de declaración de IVA**.

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
