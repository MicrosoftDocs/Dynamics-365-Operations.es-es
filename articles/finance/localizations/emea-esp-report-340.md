---
title: Informe 340 para España
description: En este tema se ofrece información acerca de cómo configurar y generar el informe 340 para España.
author: anasyash
ms.date: 07/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Spain
ms.author: epodkolz
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a7c4559559fefde2bd4041ded82be390c862c7d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818341"
---
# <a name="report-340-for-spain"></a>Informe 340 para España

[!include [banner](../includes/banner.md)]

El informe 340 contiene información sobre todas las facturas e impuestos relacionados con las facturas que una empresa emitió o recibió durante un período específico. El informe 340 debe enviarse a las autoridades fiscales durante los primeros 20 días después el período de notificación. El período de notificación puede ser un mes o un trimestre, en función del tamaño de la empresa. El informe se puede cargar en la página web de las autoridades fiscales o se puede enviar mediante un paquete de software que está disponible de forma gratuita por parte de las autoridades fiscales.

El formato de archivo del informe 340 consta de dos tipos de registro basados en la estructura del archivo.

-   **Tipo 1**: este tipo de registro contiene la información de encabezado acerca de la entidad jurídica que genera el informe.
-   **Tipo 2**: este tipo de registro contiene información sobre los artículos y servicios que una entidad jurídica compra y vende durante un período concreto.

## <a name="entries-that-are-included-in-report-340"></a>Entradas que se incluyen en el informe 340

El informe 340 incluye las siguientes entradas:

-   **Entradas de ventas**: líneas de informes de impuesto sobre el valor añadido (IVA) que corresponden a facturas de ventas y facturas de proyectos.
-   **Notas de crédito de ventas (facturas correctivas)**: entradas de líneas de informes de IVA que corresponden a facturas de ventas.
-   **Entradas de compra**: líneas de informes de IVA que corresponden a facturas de compra.
-   **Notas de crédito de compras**: entradas de líneas de informes de IVA que corresponden a facturas de compras.
-   **Facturas automáticas y notas de crédito automáticas**: líneas de informes de IVA que corresponden a facturas y notas de crédito que se crean automáticamente cuando los bienes o servicios son prestados por un proveedor de la Unión Europea (UE).
-   **Facturas que incluyen cargo de equivalencia**: el cargo de equivalencia es un tipo de impuesto español.
-   **Facturas que incluyen varios IVA% o porcentaje de cargo de equivalencia (CE%)**: facturas que tienen más de un porcentaje de IVA o porcentaje de cargo de equivalencia.
    
## <a name="generate-a-spanish-vat-book-and-export-the-report-340-ascii-file"></a>Generar un libro de IVA español y exportar el archivo ASCII del informe 340

1.  En [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), en la Biblioteca de activos compartidos, descargue la últimas versión de las configuraciones de informes electrónicos (ER) para el siguiente formato de declaración de IVA:

-   Libro de registro de IVA (ES)

Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  Vaya a **Impuestos \> Configuración \> Impuestos \> Libros de IVA españoles**.

![Página de libros de impuestos españoles](media/1_Spanish_VAT_book.png)

3.  En los campos **Libro de IVA** y **Descripción**, introduzca un nombre y una descripción para el libro de IVA.
4.  En el campo **Tipo de libro** seleccione un tipo de libro: **Impuestos repercutidos**, **Impuestos soportados** o **Todos los libros**.
5.  En el campo **Código de secuencia numérica**, seleccione un código de secuencia numérica.
6.  En la ficha desplegable **Preparar**, seleccione **Añadir**, y luego configure los siguientes campos para configurar los códigos de impuestos que deben incluirse en el libro de IVA.

| **Campo**               | **Descripción**                                                                                                                                                                                                                                                                                                                          |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Código de impuestos          | Seleccione un código de impuestos.                                                                                                                                                                                                                                                                                                                 |
| Código de cargo de equivalencia | Seleccione un código de impuesto para el cargo de equivalencia, si el cargo de equivalencia es de aplicación.                                                                                                                                                                                                                                                     |
| IVA no deducible      | Seleccione la casilla de verificación para activar el IVA no deducible para el código de impuesto. Si el importe del IVA no es deducible, los compradores no pueden deducirlo.                                                                                                                                                                                 |
| Cargo invertido          | Seleccione la casilla de verificación para activar los cargos invertidos para el código de impuestos. Los cargos invertidos forman parte de la ley de IVA. En algunos casos, los bienes o servicios se compran en una empresa extranjera. Si se activan cargos invertidos, el IVA de estos bienes y servicios lo paga la empresa destinataria, no la empresa extranjera compradora. |

7.  Seleccione **Informes de IVA españoles** para abrir la página **Informes de IVA españoles**.
8.  Seleccionar **Crear nuevo** para crear un informe nuevo.
9.  En el cuadro de diálogo **Lista de IVA español**, establezca los campos siguientes.

| Campo                                                   | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|---------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Libro de IVA                                                | Seleccione un libro de IVA.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Descripción                                             | Especifique una descripción del libro de IVA.                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Período de liquidación                                     | Permite seleccionar un período de liquidación.                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Desde fecha                                             | Especifique fecha inicial del período de liquidación de impuestos.                                                                                                                                                                                                                                                                                                                                                                                                                |
| Método de numeración                                   | Seleccione un método de finalización:<br>- **Código de secuencia numérica**: el número de la línea del informe de IVA es igual al número de factura.<br>- **Código de secuencia numérica**: el número de la línea del informe de IVA se toma de la secuencia numérica que se define en el campo **Código de secuencia numérica** en la página **Libros de IVA españoles**.<br>- **Secuencia 340**: las líneas de informe de IVA se numeran por separado para compras y ventas. En ambos casos, los números de línea comienzan desde 1.  |
| Comenzar a numerar (en la sección **Numeración manual**) | Especifique el primer número de línea.                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Plantilla (en la sección **Numeración manual**)        | Especifique la plantilla ara el número de línea. Por ejemplo, escriba #####.                                                                                                                                                                                                                                                                                                                                                                                                       |
| Declaración sustitutiva                               | Establezca esta opción en **Sí** para reemplazar la declaración anterior.                                                                                                                                                                                                                                                                                                                                                                                                         |
| Número declaración anterior                          | Especifique el número de 13 dígitos de la declaración anterior. Este campo solo se puede editar si la opción **Declaración sustitutiva** se establece en **Sí**.                                                                                                                                                                                                                                                                                                                     |
| Cuenta de pago mínimo en efectivo                       | Especifique el importe de pago de efectivo mínimo que se debería notificarse en la declaración.                                                                                                                                                                                                                                                                                                                                                                                       |

10.  Seleccione **Aceptar** para crear una línea en la página **Informes de IVA español**, según los criterios que definió en el paso anterior.
11.  Revise la línea que se crea.

![Página Informes de impuestos españoles](media/2_Spanish_VAT_report.png)

> [!NOTE]
> No puede modificar los valores de los campos **Período de liquidación**, **Método de numeración** y **Desde fecha** en la página **Informes de IVA españoles**.

12.  En la pestaña **General**, establezca los campos siguientes:

| Campo                                | Descripción                                                                                                                                                                                                                                                                                         |
|--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tipo de presentación                  | Seleccione el tipo de soporte a usar para el archivo exportado:<br>- **Telemático**: cargue el informe en el sitio web de las autoridades fiscales o envíe el informe mediante el software gratuito provisto por las autoridades fiscales.<br>- **CD-R**: envía el informe a las autoridades fiscales en un CD-ROM. |
| Notificado                             | Establezca esta opción en **Sí** para indicar que la declaración ha sido notificada. El campo **Fecha de presentación** se establecerá en la fecha actual y el campo **Notificado por** se establecerá en el identificador del usuario.                                                                                   |
| Persona de contacto                     | Especifique el nombre de la persona de contacto.                                                                                                                                                                                                                                                             |
| Teléfono                            | Especifique el número de teléfono de la persona de contacto.                                                                                                                                                                                                                                                |
| Número de documento de la declaración. | Especifique el número de cuatro dígitos del documento. <br>Si especifica un número que contiene menos de cuatro dígitos, se agregan ceros iniciales para crear un número de cuatro dígitos. Por ejemplo, si especifica **1**, el sistema convierte automáticamente el valor **0001** y guarda el nuevo valor.              |
| Código electrónico                    | Especifique el código electrónico de 16 dígitos. Este número es obligatorio y lo proporciona las autoridades fiscales.                                                                                                                                                                                              |

13.  Seleccione **Líneas de informes de IVA** para abrir la página **Líneas de informes de IVA** . En esta página, puede ver los detalles de las transacciones de IVA que se transfieren al informe de IVA. Si alguna de las líneas que se transfieren automáticamente no tienen que notificarse, puede editarlas o eliminarlas.

![Página de líneas de informe de IVA](media/3_VAT_report_lines.png)

14.  Seleccione **Impuesto registrado** para abrir la página **Impuesto registrado**. En esta página, puede revisar las transacciones de impuestos registrados.
15.  Cierre las páginas **Impuesto registrado** y **Líneas de informe de IVA**.
16.  En la página **Informes de IVA español**, seleccione **Totales** para abrir la página **Totales**. En esta página, puede ver los siguientes valores:

- **Número de operaciones**: el número total de ventas (o IVA repercutido) en la sección **Entregas** y el número total de compras (IVA soportado) en la sección **Adquisiciones**.
- **Importe**: el importe total de ventas (o IVA repercutido) en la sección **Entregas** y el número total de compras (IVA soportado) en la sección **Adquisiciones**.

17.  Seleccione **Resultado \> Exportar a archivo ASCII** para abrir el cuadro de diálogo **Exportar a archivo ASCII**.
18.  En el campo **Nombre de archivo**, especifique un nombre para el archivo y, después, seleccione **Aceptar**.
19.  Seleccione **Resultado \> Imprimir** para abrir el cuadro de diálogo **Libro de registro de IVA español**.
20.  En el campo **Asignación de formato**, seleccione el formato **Libro de registro de IVA (ES)** que descargó anteriormente y luego seleccione **Aceptar**.

## <a name="example"></a>Ejemplo

1.  En el panel de exploración, vaya a **Impuesto \> Impuestos indirectos \> Impuestos \> Códigos de impuestos** y cree los códigos siguientes.

| **Código de impuestos** | **Porcentaje** | **Descripción**                                                                                                                |
|--------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------|
| IVA21              | 21             | Ventas nacionales a un tipo del 21 por ciento.                                                                                        |
| IVA10              | 10             | Ventas nacionales a un tipo del 10 por ciento.                                                                                        |
| IVA4               | 4              | Ventas nacionales a un tipo del 4 por ciento.                                                                                         |
| EUP21              | 21             | Compras en la UE con una tasa del 21 por ciento.                                                                                          |
| EUP-21             | \-21           | Compras de la UE a un tipo del 21 por ciento, donde la opción **Intracomunitario** en la página **Grupos de impuestos** está configurada en **Sí**. |
| EUP10              | 10             | Compras en la UE con una tasa del 10 por ciento.                                                                                          |
| EUP-10             | \-10           | Compras de la UE a un tipo del 10 por ciento, donde la opción **Intracomunitario** en la página **Grupos de impuestos** está configurada en **Sí**. |
| EUP4               | 4              | Compras en la UE con una tasa del 4 por ciento.                                                                                           |
| EUP-4              | \-4            | Compras de la UE a un tipo del 4 por ciento, donde la opción **Intracomunitario** en la página **Grupos de impuestos** está configurada en **Sí**.  |
| EUS                | 0              | Ventas en la UE donde la opción **Exento** está establecida en **Sí**.                                                                        |

> [!NOTE]
> Para códigos con porcentaje de impuestos negativo, en la ficha desplegable **Cálculo**, establezca la opción **Permitir porcentaje de impuestos negativo a las ventas** en **Sí**.

2.  Configure los impuestos de ventas. Para instrucciones, vea [Descripción general del impuesto](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/general-ledger/indirect-taxes-overview.md).
3.  Configurar el IVA intracomunitario para compras en la UE. Para instrucciones, vea [IVA intracomunitario para España](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/localizations/emea-esp-intra-community-vat.md).

4.  Publique las siguientes transacciones.

    Por ejemplo, para facturas de clientes, vaya a **Clientes \> Facturas \> Todas las facturas de servicios**. Para las facturas de proveedores, vaya a **Proveedores \> Facturas \> Diario de facturas**.

| **Fecha**        | **Factura** | **NIF** | **Tipo de transacción** | **Importe neto** | **Importe de IVA** | **Código de impuestos** |
|-----------------|-------------|-----------------------|----------------------|----------------|----------------|--------------------|
| 1 de enero de 2020 | FTI-000007  | 01396364B             | Factura de cliente     | 500            | 0              | EUS                |
| 1 de enero de 2020 | FTI-000008  | 01396365B             | Factura de cliente     | 300            | 30             | IVA10              |
| 1 de enero de 2020 | 1           | FR123321123           | Factura del proveedor       | 1000           | 210            | EUP21 EUP-21       |

5.  Vaya a **Impuestos \> Configuración \> Impuestos \> Libros de IVA españoles**.
6.  Seleccione **Nuevo** para crear un libro de IVA español.
7.  En la ficha desplegable **Configuración**, agregue los siguientes códigos de impuestos:

-   EUP21
-   EUP-21
-   EUS
-   IVA 10

![Página de libros de IVA en español, ficha desplegable Configuración](media/4_Spanish_VAT_book.png)

8.  Seleccione **Informes de IVA español**.
9.  Seleccione **Crear nuevo**.
10.  En el cuadro de diálogo **Lista de IVA español**, establezca los valores de los campos y, a continuación, seleccione **Aceptar**:

-   **Libro de IVA:** ESP
-   **Período de liquidación**: Men
-   **Desde fecha**: 1/1/2020

11.  Seleccione **Líneas de informe de IVA** y revise los datos generados.

![Datos generados en la página de líneas de informe de IVA](media/5_VAT_report_lines.png)

12.  Seleccione **Resultado \> Imprimir**.
13.  En el campo **Asignación de formato**, seleccione el formato **Libro de registro de IVA (ES)** que descargó anteriormente.
14.  Seleccione **Aceptar**, abra el archivo descargado y revise los datos.

![Datos del libro de registro de IVA español](media/6_Spanish_VAT_register_book.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]