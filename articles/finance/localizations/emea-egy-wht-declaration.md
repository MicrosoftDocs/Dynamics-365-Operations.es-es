---
title: Declaración de retención de impuestos para Egipto
description: Este tema explica cómo configurar y generar las declaraciones de retención de impuestos para Egipto.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8c9aaa3868167806ce3189d724621991ec7e53eb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022820"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>Declaración de retención de impuestos para Egipto (EG-00005)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>Información general
Este tema explica cómo configurar y generar la declaración de retención de impuestos y los formularios 41 y 11 de declaración de retención de impuestos para entidades legales en Egipto 

Todas las entidades egipcias deben preparar el formulario 41 que resume todos los impuestos que se retienen de los proveedores locales y proveedores de servicios. Además del formulario 41, se debe generar el formulario 11 para detallar todos los impuestos retenidos de proveedores extranjeros. 

El informe **Declaración de retención de impuestos** de Dynamics 365 Finance incluye los siguientes informes:

- Número de formulario de declaración. 41
- Número de formulario de declaración. 11
    
    
## <a name="prerequisites"></a>Requisitos previos
La dirección principal de la entidad jurídica debe estar en Egipto.
En el espacio de trabajo **Administración de funciones**, active las siguientes características:

   - **Retención de impuestos global**

Para obtener más información acerca de cómo habilitar características, consulte [Visión general de la Administración de características.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

1. Vaya a **Impuesto** > **Configuración** > **Parámetros** > **Parámetros del libro mayor** y luego, en la pestaña **Retención de impuestos**, establezca **Habilitar la retención de impuestos global** en **Sí**.
2. En el espacio de trabajo **Informes electrónicos**, importe los siguientes formatos de informes electrónicos desde el repositorio:

    - Excel de declaración de WHT (EG)

    > [!NOTE]
    > El formato anterior se basa en el **Modelo de declaración de impuestos** y usa la **Asignación de modelos de declaración de impuestos**. Esta configuración adicional se importa automáticamente.

Para obtener más información sobre cómo importar configuraciones de informes electrónicos, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Descargar configuraciones de informes electrónicos

La implementación de los formularios de declaración WHT para Egipto se basa en configuraciones de informes electrónicos (ER). Para obtener más información sobre las capacidades y los conceptos de los informes configurables, consulte [Informes electrónicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Para entornos de producción y pruebas de aceptación del usuario (UAT), siga las instrucciones del tema, [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Para generar las declaraciones de retención en una entidad jurídica egipcia, debe cargar las siguientes configuraciones:

- Modelo de declaración de impuestos model.version.82.xml o versión posterior
- Modelo de declaración de impuestos mapping.version.82.133.xml o versión posterior
- Excel de declaración WHT (EG).version.82.21 o versión posterior

Una vez que haya terminado de descargar las configuraciones de ER desde Lifecycle Services (LCS) o el repositorio global, complete los siguientes pasos.

1. Vaya al espacio de trabajo **Informes electrónicos** y seleccione el mosaico **Configuraciones de informes** .
1. En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange > Cargar desde archivo XML**.
1. Cargue todos los archivos en el orden en que aparecen en las viñetas anteriores. Una vez cargadas todas las configuraciones, el árbol de configuración debe estar presente en Finance.

## <a name="set-up-application-specific-parameters"></a>Configurar parámetros específicos de la aplicación

La opción de parámetros específicos de la aplicación permite a los usuarios establecer los criterios de cómo se clasificarán y calcularán las transacciones fiscales en cada línea de un informe generado en función de la configuración del **grupo de partidas de retención de impuestos** u otros criterios establecidos en la definición de búsqueda.

El formulario de declaración de retenciones 41 incluye una columna específica donde la transacción de retención de impuestos debe clasificarse de acuerdo con la clasificación de la autoridad tributaria denominada **Tipo de código de descuento**. En lugar de incluir estas nuevas clasificaciones como nuevos datos de entrada cuando se publican las transacciones, las clasificaciones se determinarán en función de las diferentes búsquedas introducidas en **Configuraciones** > **Configurar parámetros específicos de la aplicación** > **Configuración** para cumplir con los requisitos de los informes de retención para Egipto. 

La siguiente configuración se utiliza para clasificar las transacciones en el informe del formulario 41 de declaración de retenciones:

- **DiscountTaxTypeLookup** -> Columna n.º 18 

Complete los siguientes pasos para configurar las diferentes búsquedas utilizadas para generar la declaración WHT y los informes de libros relacionados. 

1. En el espacio de trabajo **Informes electrónicos**, seleccione **Configuraciones** > **Configuración** para configurar las reglas para identificar cómo se clasifican las transacciones en el informe de declaración WHT. 
2. Seleccione la versión actual y en la ficha desplegable **Búsquedas**, seleccione el nombre de búsqueda. Por ejemplo, **DiscountTaxTypeLookup**. Esta búsqueda identifica la lista de tipos de descuento requeridos por la autoridad fiscal.
3. En la ficha desplegable **Condiciones**, seleccione **Agregar** y, en la nueva línea de la columna **Resultado de la búsqueda**, seleccione la línea relacionada que representa la clasificación en la **Columna 18**.
4. En la columna **Grupo de elementos de retención de impuestos**, seleccione el código relacionado que se utiliza para identificar la clasificación. Por ejemplo, **Descuento permitido**.  
5. Repita los pasos 3 y 4 para todas las búsquedas disponibles.
6. Seleccione **Agregar** de nuevo para incluir la línea de registro final y, en la columna **Resultado de la búsqueda**, seleccione **No aplicable**. 
7. En las columnas restantes, seleccione **No en blanco**. 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>Configurar los parámetros de Contabilidad general

Para generar los informes del formulario de declaración WHT en Microsoft Excel, defina un formato ER en la página **Parámetros del libro mayor**.

1. Vaya a **Impuesto** > **Configuración** > **Parámetros del libro mayor**.
2. En la pestaña **Retención de impuestos**, en el campo **Asignación de formato de declaración WHT**, seleccione **Excel de declaración WHT (EG)**. Si deja el campo en blanco, el informe estándar de impuestos sobre las ventas se generará en formato SSRS.


![Formulario de declaración](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>Generar los formularios de declaración de retención
El proceso de preparación y envío de un formulario de declaración de retención para un período específico se basa en las transacciones de retención de impuestos contabilizadas durante el trabajo de liquidación y contabilización de pago de impuestos. Para obtener más información sobre la retención de impuestos global, consulte [Retención global de impuestos](../general-ledger/global-withholding-tax-overview.md).

Complete los pasos siguientes para generar un informe de declaración de impuestos.

1. Vaya a **Impuesto** > **Declaraciones** > **Retención de impuestos** > **Pago de retención de impuestos*.
2. Seleccione el período de liquidación y luego seleccione la fecha de inicio para el informe. 
3. Escriba la fecha de la transacción y luego seleccione **Aceptar**.
4. En el cuadro de diálogo que se abre, seleccione uno o más de los tipos de formulario **Formulario N.º 41**, **Formulario N.º 11** o **Ninguno**. Si selecciona **Ninguno**, se genera el informe estándar. 
5. Seleccione el idioma. Todos los informes se traducen en **en-us** y **ar-eg**.
6. Introduzca la sucursal y el nombre del banco donde se pagará el impuesto.
7. Seleccione el tipo de negocio y luego introduzca los números de cheque y documento. 
8. Introduzca el tipo de entidad. 
9. Introduzca el nombre de la persona registrada para asignar el formulario y seleccione **Aceptar** para confirmar la generación del informe. 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
