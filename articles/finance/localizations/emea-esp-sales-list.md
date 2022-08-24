---
title: Lista de ventas de la UE para España (Informe 349)
description: Este artículo proporciona información sobre el informe de lista de ventas de la Unión Europea (UE) para España, también conocido como Informe 349.
author: AdamTrukawka
ms.date: 05/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Spain
ms.author: atrukawk
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 12811
ms.search.form: EUSalesList
ms.openlocfilehash: 114f78441da1b526741388a74696f5d66423215c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283908"
---
# <a name="eu-sales-list-for-spain-report-349"></a>Lista de ventas de la UE para España (Informe 349)

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre el informe de lista de ventas de la Unión Europea (UE) para España, también conocido como Informe 349. El informe de lista de ventas de la UE en español contiene información sobre la compra y venta de bienes y servicios para informar en formato de texto.

Los siguientes campos se incluyen en el informe de lista de ventas de la UE en España:

- **Encabezado de lista de ventas de la UE:**

  - Modelo de declaración
  - Período de notificación
  - Nombre de la empresa
  - CIF de empresa
  - Forma de presentar una declaración
  - Nombre y número de teléfono principal de una persona de contacto
  - Número de declaración
  - Tipo de declaración correctiva
  - Número de declaración reemplazada
  - Número de transacciones
  - Cantidad total de líneas
  - Número de correcciones
  - Importe total de correcciones
  - Existencia de cambios en la periodicidad

- **Líneas de lista de ventas de la UE:**

  - Ejercicio
  - NIF - CIF de la empresa
  - CIF de cliente o proveedor
  - Nombre de cliente o proveedor 
  - Código de entrega
  - El importe total de los artículos
  - El importe total de los servicios
  - Importe total del comercio triangular
  - Período corregido
  - Importe de la corrección

## <a name="setup"></a>Configurar
Para obtener información general sobre la configuración, consulte [Informes de lista de ventas de la UE](emea-eu-sales-list.md).

> [!NOTE]
> El nombre de la empresa y el valor del campo **Número de registro de impuestos** de la ficha desplegable **Registro de impuestos** de las **Entidades legales** se utilizan en el archivo .xlsx para el informe de la lista de ventas de la UE.


### <a name="set-up-company-information"></a>Configurar la información de la empresa
Cree un tipo de registro y asígnelo a la categoría de registro **CIF** para España y todos los países o regiones con los que su empresa hace negocios. Para obtener más información, consulte [Id. de registro](emea-registration-ids.md).

1. En Microsoft Dynamics 365 Finance, vaya a **Administración de la organización** > **Organizaciones** > **Entidades jurídicas**.
2. En la cuadrícula, seleccione su empresa.
3. En el Panel de acciones, seleccione **Id. de registro**.
4. En la ficha desplegable **Id. de registro**, seleccione **Agregar**.
5. En la pestaña **Información general**, en el campo **Tipo de registro**, seleccione el tipo de registro que creó.
6. Introduzca el CIF para el impuesto al valor añadido (IVA) de su empresa
7. Opcional: en la pestaña **General**, en la sección **General** sección, puede cambiar el período para el que se utiliza el CIF.
8. Cierre la página.

> [!NOTE]
> El CIF que creó se usa en el archivo .txt del informe de la lista de ventas de la UE. Si el campo **Exportación de números exentos de IVA** de la sección **Intrastat** de la ficha desplegable **Comercio exterior y logística** está establecido (es decir, no está en blanco), el valor de ese campo se usa en lugar del CIF.

### <a name="import-electronic-reporting-configurations"></a>Importar configuraciones de informes electrónicos
En [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), importe las últimas versiones de las siguientes configuraciones de informes electrónicos (ER) para la lista de ventas de la UE:

  - Modelo de lista de ventas de la UE
  - Informe de lista de ventas de la UE por columnas
  - Informe de lista de ventas de la UE por filas
  - Lista de ventas de la UE (ES)

Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

### <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

1. En Finance, vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
2. En la pestaña **Lista de ventas de la UE**, configure la opción **Transferir compras** en **Sí**.
3. Establezca la opción **Notificar descuento por pronto pago** en **Sí**: si debe incluirse un descuento por pronto pago en el valor cuando una transacción se incluye en la lista de ventas de la UE.
4. En la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Lista de ventas de la UE (ES)**.
5. En el campo **Asignación de formato de informe**, seleccione **Informe de Lista de ventas de la UE por filas** o **Informe de Lista de ventas de la UE por columnas**.
6. En la pestaña **Propiedades de país/región**, seleccione **Nuevo** y especifique la siguiente información:

    •   En la columna **País/región**, seleccione **ESP**.
    •   En la columna **Tipo de país/región**, seleccione **Nacional**.

7. Enumere todos los países o regiones con los que su empresa hace negocios. Para cada país o región que forma parte de la UE, seleccione UE en el campo **Tipo de país o región**, seleccione **UE** mostrar el comercio con los países de la página **Lista de ventas de la UE**.

### <a name="create-a-contact-for-the-person-who-is-responsible-for-the-report"></a>Crear un contacto para la persona responsable del informe

1. Vaya a **Ventas y marketing** > **Relaciones** > **Contactos** > **Todos los contactos**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear contacto**, en el campo **Contacto para**, seleccione su empresa. Luego, seleccione **Seleccionar**.
4. En la ficha desplegable **Detalles**, establezca los campos **Nombre de pila**, **Segundo nombre**, **Prefijo del apellido** y **Apellido**.
5. En la ficha desplegable **Información del contacto**, establezca el campo **Teléfono**. El valor de este campo se establece como **Primario**.
6. Seleccione **Guardar**.

> [!NOTE]
> Los valores de los campos **Nombre de pila** y **Apellido** y el número de teléfono primario del contacto se mostrarán en el archivo .txt del informe de la lista de ventas de la UE.

## <a name="work-with-the-eu-sales-list"></a>Trabajar con la lista de ventas de la UE
Para obtener información general sobre qué tipos de transacciones se incluyen en la lista de ventas de la UE, cómo generar el informe de la lista de ventas de la UE y cómo cerrar el período del informe de la lista de ventas de la UE, consulte [Informes de lista de ventas de la UE](emea-eu-sales-list.md#working-with-the-esl).

Antes de generar el informe de la lista de ventas de la UE, puede agregar la columna **Código de entrega** y seleccionar el código de entrega para la venta de artículos: **E: entrega normal**, **: entrega de bienes provenientes de una importación exenta de impuestos por un representante fiscal oficial** o **: entrega de bienes provenientes de una importación exenta de impuestos**.

> [!NOTE]
> Para los servicios y el comercio triangular, el campo **Código de entrega** no está disponible.

### <a name="generate-the-eu-sales-list-report"></a> Generar el informe de lista de ventas de la UE

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Lista de ventas de la UE**.
2. Transfiera las transacciones.
3. En el panel de acciones, seleccione **Informes**.
4. En el cuadro de diálogo **Informe de lista de ventas de la UE**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    |  Campo  |  Description  |
    |---------|---------------|
    | Período de notificación | Seleccione **Mensual**, **Trimestral** o **Anual**. |
    | A partir de la fecha   | Seleccione la fecha inicial del informe.   |
    | Cambio de periodicidad   | Establezca esta opción en **Sí** para mostrar el cambio de período en el informe.  |
    | Generar archivo  | Establezca esta opción en **Sí** para generar un archivo .txt para la lista de ventas de la UE.   |
    | Nombre de archivo   | Especifique el nombre del archivo .txt.  |
    | Generar informe | Establezca esta opción en **Sí** para generar un archivo .xlsx para la lista de ventas de la UE.   |
    | Nombre de archivo del informe  | Especifique el nombre del archivo .xlsx.  |
    | Número de documento de la declaración    | Introduzca el número de la declaración. El valor consiste en **349** seguido de los 10 dígitos del número.  |
    | Id. de contacto   | Seleccione un contacto para la persona responsable del informe.  |
    | Tipo de presentación   |  Seleccione **Telemática** o **DVD**. |  
   
5. Seleccione **Aceptar** y revise los informes generados.

### <a name="create-a-corrective-eu-sales-list-report"></a>Crear un informe de lista de ventas de la UE correctivo

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Lista de ventas de la UE**.
2. Transfiera las transacciones.
3. Seleccione una línea correctiva y luego cambie a la vista **Corrección**.
4. En el panel Acciones, seleccione **Editar**.
5. Seleccione la opción **Servicios** o **Elementos** en **Sí**, según el tipo de línea que haya seleccionado.
6. En el campo **Ejercicio**, introduzca el año corregido.
7. En el campo **Período de corrección**, seleccione **Mes**, **Cuarto** o **Año**.
8. En el campo **Mes o trimestre de corrección**, campo, introduzca el número que corresponde al mes o trimestre corregido.
9. En el campo **Importe**, introduzca el importe base declarado que está siendo corregido por la línea seleccionada.
10. Cambie a la vista **Información general**.
11. En el campo **Valor de los artículos** o **Valor de los servicios**, introduzca la cantidad corregida, que se calcula utilizando la siguiente fórmula:

    *n = d – (+) o*

     A continuación aparece una explicación de la fórmula:

     - n es el importe corregido que debe introducir manualmente en el campo **Valor de los artículos** o **Valor de los servicios**.
     - d es el importe base declarado del campo **Importe** en la vista **Corrección**.
     - o es la cantidad del campo **Valor de los artículos** o **Valor de los servicios** después de que las transacciones se transfieran a la página **Lista de ventas de la UE**. (En otras palabras, es el importe del documento correctivo).

12. En el panel de acciones, seleccione **Informes**.
13. En el cuadro de diálogo **Informes de lista de ventas de la UE**, en la ficha desplegable **Parámetros**, establezca los siguientes campos, además de los campos generales que se utilizan para generar un informe.

    | Campo | Description |
    |-------|-------------|
    | Corrección | Seleccione **Complementario** o **Reemplazo** para crear un archivo corregido. |
    | Declaración corregida | Ingrese el número de documento de la declaración de lista de ventas de la UE anterior que se está corrigiendo. |

## <a name="example"></a>Ejemplo
Para obtener información general sobre cómo configurar y transferir transacciones, consulte [Ejemplo de lista de ventas de la UE genérica](emea-eu-sales-list-example.md).
Antes de comenzar, cree el CIF de la empresa **ESB12345678** y establezca el número de registro fiscal de la empresa en **222444666**.

Para obtener información sobre cómo configurar compras y crear una factura de proveedor, consulte [Configurar transferencias de compra](emea-eu-sales-list-example.md#set-up-purchase-transfers).

### <a name="create-a-contact-for-the-person-who-is-responsible-for-the-report"></a>Crear un contacto para la persona responsable del informe

1. Vaya a **Ventas y marketing** > **Relaciones** > **Contactos** > **Todos los contactos**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear contacto**, en el campo **Contacto para**, seleccione **Contoso Entertainment System Spain**. Luego, seleccione **Seleccionar**.
4. En el campo **Nombre de pila**, seleccione **Aaren Ekelund**. Luego, seleccione **Seleccionar**.
5. Seleccione **Guardar**.
6. En la cuadrícula, seleccione **Aaren Ekelund**.
7. En la ficha desplegable **Información de contacto**, en la línea donde el campo **Tipo** está establecido en **Teléfono**, introduzca **75 555-5153** en el campo **Número de contacto/dirección**.

### <a name="create-an-eu-sales-list-report"></a>Crear un informe de lista de ventas de la UE

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Lista de ventas de la UE**.
2. Añada la columna **Código de entrega**.
3. En el panel de acciones, seleccione **Informes**.
4. En el cuadro de diálogo **Informe de lista de ventas de la UE**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    - En el campo **Período de informe**, seleccione **Mensual**.
    - En el campo **Fecha inicial**, seleccione **1/8/2021** (1 de agosto de 2021).
    - Establezca la opción **Generar archivo** en **Sí**.
    - En el campo **Nombre de archivo**, introduzca **ES-001F**.
    - Establezca la opción **Generar informe** en **Sí**.
    - En el campo **Nombre de archivo de informe**, introduzca **ES-001R**.
    - En el campo **Número de documento de la declaración**, especifique **3490000000001**.
    - En el campo **Id. de contacto**, seleccione **Aaren Ekelund**.
    - En el campo **Tipo de presentación**, seleccione **Telemática**.

5. Seleccione **Aceptar** y revise el informe en formato de texto que se genera. En las tablas siguientes se muestran los valores en el informe de ejemplo.

   **Encabezado de lista de ventas de la UE**

   | Nombre de campo | Valor de campo | Comentar |
   |------------|-------------|---------|
   |  Tipo de registro    | 1      |  &nbsp; |
   | Modelo de declaración  |  349  |  &nbsp;     |
   | Ejercicio  |  2021   |  &nbsp;     |
   | Número de IVA de la empresa  | B12345678    |  El CIF de la empresa sin el código de país/región.  |
   | Nombre de la empresa  | CONTOSO ENTERTAINMENT SYSTEM SPAIN  |  &nbsp;     |
   | Tipo de medio |  B   | Si el campo **Tipo de presentación** está establecido en **Telemática**, este campo se establece en **T**. De lo contrario, este campo se establece en **C**.   |
   | Teléfono de contacto  | 755555153  |  &nbsp;     |
   | Nombre del contacto  | EKELUND AAREN |  &nbsp;     |
   | Número de declaración  |  3490000000001 |  &nbsp;  |
   | Declaración complementaria | &nbsp;  | Si el campo **Corrección** esta establecido en **Complementario**, este campo se establece en **C**. De lo contrario, este campo está en blanco. |
   | Declaración sustitutiva  | &nbsp; |  Si el campo **Corrección** esta establecido en **Reemplazo**, este campo se establece en **S**. De lo contrario, este campo está en blanco.  |
   | Número de declaración reemplazada  | 000000000000 |  &nbsp; |
   | Período de notificación  | 08  | Si el campo **Período de informe** está establecido en **Mensual**, este campo se establece en un valor de **01** (enero) hasta **12** (diciembre).<br> Si el campo **Período de informe** está establecido en **Trimestral**, este campo se establece en un valor de **1T** (el primer trimestre) hasta **4T** (el cuarto trimestre). <br> Si el campo **Período de informe** está establecido en **Anual**, este campo se establece en **0A**.      |
   | Número de transacciones |  000000002  | El número de filas para artículos, servicios y comercio triangular. Se excluye el número de filas para correcciones. |
   | Importe total de transacciones  | 000000000000360  | El importe total de artículos, servicios y comercio triangular. Se excluye el importe de las correcciones.  |
   | Número de correcciones  |  000000000  |  &nbsp;  |
   | Importe total de las líneas corregidas  | 000000000000000  |  &nbsp; |
   | Cambio de periodicidad  |  &nbsp; | Si la opción **Cambio de periodicidad** esta establecida en **Sí**, este campo se establece en **X**. De lo contrario, este campo está en blanco. |

   **Líneas de lista de ventas de la UE**
   
   | Nombre de campo | Línea 1 | Línea 2 | Comentar |
   |------------|--------|--------|---------|
   | Tipo de registro   |  2  |   2    | &nbsp;  |
   | Modelo de declaración  |  349  |  349  | &nbsp;  |
   | Ejercicio  |  2021  | 2021  | &nbsp;  |
   | Número de IVA de la empresa  | 222444666  | 222444666  | El número de registro de impuestos de la empresa.  |
   | Código de país  |  DE   |  SE  | El código fiscal del país o región.  |
   | Número de IVA de cliente/proveedor   | 100200400  | 100200300400  | El CIF del cliente o proveedor sin el código de país/región.        |
   | Código de operación      | C      |  S     |  Para un registro comercial triangular, el valor es **T**. <br> Para un registro de servicio, el valor es **S** para ventas e **I** para compras. <br> Para un registro de artículo, el valor es **A** para compras. <br> Para ventas, el valor depende del código de entrega: **E** para el código de entrega **E: entrega normal**, **H** para el código de entrega **Entrega de bienes provenientes de una importación exenta de impuestos por un representante fiscal oficial** o **M** para el código de entrega **M: entrega de bienes provenientes de una importación exenta de impuestos**.  |
   | Importe de registro  |  0000000000120  | 0000000000240  |  La suma de todas las facturas por cliente o proveedor.  |

6. Revise el informe en formato Excel que se genera. 

   ![Lista de ventas de la UE para España.](media/eusl-spain-example.png)
   
### <a name="create-a-corrective-eu-sales-list-report"></a>Crear un informe de lista de ventas de la UE correctivo

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Lista de ventas de la UE**.
2. Verifique que haya una línea de servicio y una línea de artículo en la página de lista de ventas de la UE.

  ![Página de lista de ventas de la UE.](media/EUSL_esp_ex.png)
  
3. Seleccione una línea de artículo y luego siga estos pasos:

    1. Cambie a la vista **Corrección**.
    2. En el panel Acciones, seleccione **Editar**.
    3. En el campo **Ejercicio**, introduzca **2021**.
    4. En el campo **Período de corrección**, seleccione **Mensual**.
    5. En el campo **Mes o trimestre de corrección**, introduzca **7**.
    6. En el campo **Importe**, introduzca **333** como el importe base declarado.
    7. Cambie a la vista **Información general**.
    8. En el campo **Valor de artículos**, escriba **213** (= 333 – 120).

4. Seleccione una línea de servicio y luego siga estos pasos:

    1. Cambie a la vista **Corrección**.
    2. En el campo **Ejercicio**, introduzca **2021**.
    3. En el campo **Período de corrección**, seleccione **Mensual**.
    4. En el campo **Mes o trimestre de corrección**, introduzca **7**.
    5. En el campo **Importe**, introduzca **411** como el importe base declarado.
    6. Cambie a la vista **Información general**.
    7. En el campo **Valor de servicios**, escriba **171** (= 411 – 240).

5.  En el panel Acciones, seleccione **Guardar**.
6.  En el panel de acciones, seleccione **Informes**.
7.  En el cuadro de diálogo **Informe de lista de ventas de la UE**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    1. En el campo **Período de informe**, seleccione **Mensual**.
    2. En el campo **Fecha inicial**, seleccione **1/8/2021** (1 de agosto de 2021).
    3. Establezca la opción **Generar archivo** en **Sí**.
    4. En el campo **Nombre de archivo**, introduzca **ES-002c**.
    5. En el campo **Número de documento de la declaración**, especifique **3490000000002**.
    6. En el campo **Id. de contacto**, seleccione el contacto antes creado.
    7. En el campo **Tipo de presentación**, seleccione **Telemática**.

8.  En el campo **Período de corrección**, seleccione **Complementario**.
9.  En el campo **Declaración corregida**, indique **3490000000001**.
10. Seleccione **Aceptar** y revise el informe de corrección en formato de texto que se genera. En las tablas siguientes se muestran los valores en el informe de ejemplo.

    **Encabezado de lista de ventas de la UE**
    
    | Nombre de campo | Valor de campo |
    |------------|-------------|
    | Tipo de registro |  1         |
    | Modelo de declaración           |     349        |
    | Ejercicio          |   2021          |
    | Número de IVA de la empresa            |  B12345678           |
    | Nombre de la empresa           |  CONTOSO ENTERTAINMENT SYSTEM SPAIN           |
    | Tipo de medio          |   B          |
    | Teléfono de contacto           |   755555153          |
    | Nombre del contacto           | EKELUND AAREN            |
    | Número de declaración            | 3490000000002            |
    | Declaración complementaria           |  C           |
    | Número de declaración reemplazada           | 3490000000001            |
    | Período de notificación           |   08          |
    | Número de transacciones           | 000000000            |
    | Importe total de transacciones           | 000000000000000            |
    | Número de correcciones           | 000000002            |
    | Importe total de los importes base rectificados           | 000000000000360            |
    
    **Líneas de lista de ventas de la UE**
    
    | Nombre de campo | Línea 1 | Línea 2 |
    |------------|--------|--------|
    | Tipo de registro  |  2   |  2     |
    | Modelo de declaración   |  349   |  349  |
    | Ejercicio   |  2021  |  2021  |
    | Número de IVA de la empresa   | 222444666  | 222444666   |
    | Código de país    |   DE   |  SE   |
    | Número de IVA de cliente/proveedor    |  100200400   | 100200300400  |
    | Código de operación    |  C   |  S   |
    | Período corregido   |   2021 07  |  2021 07 |
    | Importe base rectificado  | 0000000000213  |  0000000000171   |
    | Importe base declarado (Importe corregido)  |  0000000000333  | 0000000000411  |
  
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
