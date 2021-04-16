---
title: Informe del Modelo 347
description: Este tema proporciona información sobre cómo generar el informe del Modelo 347 que está disponible para las personas jurídicas que tienen su domicilio principal en España.
author: Anasyash
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 271523
ms.search.region: Spain
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 386ccb271b830c9902118639583200faa5881c02
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839759"
---
# <a name="declaration-347-report"></a>Informe del Modelo 347
[!include [banner](../includes/banner.md)]

El informe del Modelo 347 debe presentarse electrónicamente a las autoridades fiscales cada año, durante los primeros 20 días de marzo. Debe incluir toda la información del año fiscal anterior (enero a diciembre). Se deben incluir todas las transacciones de más de 3000 euros. Además, se deben incluir los importes de pago en efectivo que excedan los 6000 euros en un año. Las cantidades se dividen por trimestre durante el año.

Puede usar la página del **Modelo 347** para generar el informe del Modelo 347. Todas las facturas se agrupan por número de identificación fiscal y número de cliente o proveedor o solo por número de identificación fiscal. La línea agregada resultante se incluye en la página del **Modelo 347** si la cantidad total de facturas en la línea excede el valor del campo **Importe mínimo** que se establece en el cuadro de diálogo **Modelo 347**. Si algunas facturas se pagan en efectivo, y el importe total de los pagos en efectivo para las facturas en la línea excede el valor del campo **Importe mínimo de pagos en efectivo** en el cuadro de diálogo **Modelo 347**, esta cantidad se mostrará en el campo **Importes en efectivo** del modelo.

## <a name="prerequisites"></a>Requisitos previos

Se deben establecer los siguientes requisitos previos antes de comenzar a trabajar con el informe del Modelo 347.

### <a name="set-up-a-legal-entity"></a>Configurar una entidad jurídica

1.  Vaya a **Administración de organizaciones** \> **Organizaciones** \> **Entidades jurídicas** y seleccione la entidad jurídica.
2.  En la ficha desplegable **Direcciones**, cree una dirección.
3.  En el campo **País o región**, seleccione **España** y marque la dirección como **Principal**.
4.  Complete los componentes restantes de la dirección.
5.  En la ficha desplegable **Registrar impuestos**, en el campo **Número de registro de impuestos**, especifique el número de registro de impuestos de la empresa.

### <a name="set-up-contact-information"></a>Configurar información de contacto

1.  Vaya a **Administración de la organización** \> **Organizaciones** \> **Entidades jurídicas**.
2.  En la pestaña **Información del contacto**, agregue líneas para **Teléfono** y **Correo** y establézcalos en **Principal**.

### <a name="set-up-tax-exempt-numbers"></a>Configurar números de exención fiscal

1.  Vaya a **Impuestos** \> **Configuración** \> **Impuestos** \> **Números de identificación fiscal**.
2.  Para cada número de identificación fiscal (NIF), cree un registro en la página y especifique la información siguiente:

    -   **País o región**: seleccione el país o la región de registro de impuestos de la contrapartida.
    -   **Número de identificación fiscal (NIF):** indique el número de identificación fiscal (NIF) de la contrapartida.
    -   **Nombre de la empresa**: (Opcional) escriba el nombre de la contrapartida.

## <a name="setup"></a>Configurar

1.  En [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), en la Biblioteca de activos compartidos, descargue las últimas versiones de las configuraciones de informes electrónicos (ER) para los siguientes formatos de declaración de IVA:

    -   Formato de exportación del Modelo 347 (ES)
    -   Formato de informes del Modelo 347 (ES)

Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).

2.  Vaya a **Impuestos** \> **Configuración** \> **Impuestos** \> **Cuentas contables de efectivo**.
3.  En la página **Cuentas contables de efectivo**, especifique las cuentas contables de efectivo que se requieren para el Modelo 347.
4.  Vaya a **Impuesto \> Configuración \> Impuesto \> Listas de validación del 347**.
5.  En la página **Lista de validación**, especifique los grupos de impuestos que deben excluirse del Modelo 347.

## <a name="generate-the-declaration-347-report"></a>Generar el informe del Modelo 347

1.  Vaya a **Impuestos \> Declaraciones \> Impuestos \> Modelo 347**.
2.  En la página **Modelo 347**, seleccione **Generar**.
3.  En el cuadro de diálogo **Modelo 347**, establezca los campos siguientes.

| **Campo**                          | **Descripción**                                                                                                               |
|------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| Ejercicio                        | Especifique el ejercicio para el que generar el Modelo 347.                                                                    |
| Apellidos + nombre               | Especifique el apellido y el nombre del representante de la empresa para el Modelo 347.                                             |
| Importe mínimo                     | Indique el importe mínimo a declarar en el modelo.                                                                        |
| Importe mínimo de pagos en efectivo | Indique el importe mínimo del pago en efectivo a declarar en el modelo.                                                           |
| Número de documento de la declaración | Especifique el código exclusivo de identificación de documento de 13 caracteres para la declaración.                                                |
| Declaración sustitutiva            | Establezca esta opción en **Sí** para indicar que la declaración se ha generado como sustitución de la declaración original. |
| Número declaración anterior        | Si configura la opción **Declaración sustitutiva** en **Sí**, especifique el número de documento de la declaración original.          |
| Agrupar solo por NIF    | Establezca esta opción en **Sí** para agrupar todas las transacciones de clientes y proveedores solo por número identificación fiscal.                           |

4.  Seleccione **Aceptar** para generar los datos en la página del **Modelo 347**.
5.  Revise la información en la declaración.

![Página del Modelo 347](media/1_Declaration_347.png)

La ficha **General** tiene los campos siguientes.

| Campo                                | Descripción                                                                                                                                                                                                                                                                                                       |
|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ejercicio                        | El ejercicio del Modelo 347.                                                                                                                                                                                                                                                                        |
| Sustitución                          | Una casilla de verificación seleccionada indica que la declaración es una declaración sustitutiva.<br>Esta casilla de verificación es equivalente a la opción **Declaración sustitutiva** en el cuadro de diálogo **Modelo 347**.                                                                                                          |
| Número de identificación fiscal                  | El número de identificación fiscal de la empresa para la que se genera el Modelo 347.                                                                                                                                                                                                                                 |
| Nombre                                 | El nombre de la empresa para la que se genera el Modelo 347.                                                                                                                                                                                                                                              |
| Notificado                             | Active esta casilla de verificación para indicar que el informe del Modelo 347 está terminado y se ha enviado a las autoridades fiscales españolas. <br>Si la casilla de verificación **Notificado** está seleccionada, no se pueden editar la declaración.                                                                                  |
| Importe mínimo                     | El importe mínimo requerido, en la divisa de la empresa, para generar el Modelo 347. De forma predeterminada, las transacciones que superan los 500 000 euros se incluyen en la declaración.<br>Esta cantidad se completa para el campo **Importe mínimo** del cuadro de diálogo **Modelo 347**.  |
| Importe mínimo de pagos en efectivo | El importe mínimo de pagos en efectivo requerido para informar del importe del pago en efectivo. <br> Esta cantidad se completa para el campo **Importe mínimo de pagos en efectivo** del cuadro de diálogo **Modelo 347**.                                                                                                  |
| Tipo de presentación                  | Seleccione el tipo de medio usado para realizar el Modelo 347:<br>- Telemático<br>- CD-R<br>- Informe<br> El valor predeterminado es **Telemático**.                                                                                                                                                               |
| Fecha de presentación                  | La fecha de generación del informe.                                                                                                                                                                                                                                                                          |
| Notificado por                        | El identificador (Id.) del usuario que generó el informe.                                                                                                                                                                                                                                                       |
| Teléfono                            | El número de teléfono de la persona de contacto. Este valor se transfiere desde la configuración que definió en la sección **Requisitos previos** anterior en este tema.                                                                                                                                               |
| Contacto                              | Especifique el nombre de la persona de contacto.                                                                                                                                                                                                                                                                           |
| Número de documento de la declaración. | El número de documento del Modelo 347. Este número se completa a partir del campo **Número de documento de la declaración** del cuadro de diálogo **Modelo 347**.                                                                                                                                             |
| Número declaración anterior        | El número de documento del Modelo 347 original. Este número se completa a partir del campo **Número de declaración anterior** del cuadro de diálogo **Modelo 347**.                                                                                                                                           |

La pestaña **Totales** muestra el número de operaciones y los importes totales de compras y ventas.

6.  Seleccione **Transacciones** para revisar y modificar la información para las transacciones agregadas de cliente y las transacciones de proveedor antes de generar el informe como archivo ASCII.

![Página Transacciones](media/2_Transactions.png)

7.  En la página **Transacciones**, en la pestaña **General**, revise los siguientes campos.

| Campo                                       | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Clave de operación                                 | La clave de operación que describe el origen de la transacción:<br>- **A - Compra**: esta clave de operación se define automáticamente para las transacciones de compra.<br>- **B - Venta**: esta clave de operación se define automáticamente para las transacciones de venta.<br>-   **C - Pago mediante entidad de crédito**: seleccione este valor si la transacción es un pago realizado a través de una entidad de crédito.<br>- **D - Compras a entidad pública**: seleccione este valor si la transacción es una compra a una entidad pública.<br>- **E - Subvenciones**: seleccione este valor si la transacción es una subvención que se recibe de administraciones públicas o empresas privadas. |
| Número de identificación fiscal                         | El número de identificación fiscal del cliente o del proveedor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Nombre                                        | El nombre del cliente o proveedor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Provincia                                      | El país del cliente o proveedor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| País/región                              | La Organización internacional para la estandarización (ISO) para el país o región del cliente o el proveedor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Importe del primer trimestre                        | La cantidad total de transacciones agregadas que se registraron en el primer trimestre del año.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Importe del segundo trimestre                        | La cantidad total de transacciones agregadas que se registraron en el segundo trimestre del año.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Importe del tercer trimestre                        | La cantidad total de transacciones agregadas que se registraron en el tercer trimestre del año.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Importe del cuarto trimestre                        | La cantidad total de transacciones agregadas que se registraron en el cuarto trimestre del año.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Importe                                      | El importe total de las transacciones agregadas en la divisa de contabilidad.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Importe liquidado                            | Importe en divisa de contabilidad.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Importes en efectivo                           | Los importes pagados en efectivo de la transacción. Este valor se completa solo para transacciones de clientes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Año de la factura del efectivo                      | El año de la factura original asociada a los pagos en efectivo en la línea de la transacción. Este campo se establece si el campo **Importe en efectivo** está establecido.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Arrendamiento                                     | Seleccione esta casilla para indicar que la transacción es una operación de arrendamiento.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Representante                              | Seleccione esta casilla para indicar que la exención de impuestos se asocia a un representante legal del cliente o del proveedor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Operación de seguro                         | Seleccione esta casilla para indicar que la transacción es una operación de seguro.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Régimen especial del contabilidad de efectivo | Seleccione esta casilla para indicar que el método **Régimen especial de contabilidad de caja** está configurado para este período.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Depósito                                     | Seleccione esta casilla para indicar que la transacción es un depósito.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Cargo invertido                            | Seleccione esta casilla para indicar que el cargo invertido se usa para esta transacción.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

8.  Si seleccionó la casilla **Arrendamiento** en la pestaña **General**, seleccione **Inquilinos del Modelo 347** para agregar información sobre los inquilinos.

![Página Inquilinos del Modelo 347](media/3_Declaration347_tenants.png)

9.  En la página **Inquilinos del Modelo 347**, en la pestaña **Descripción general**, configure los campos **Nombre**, **Importe**, **Referencia de inmuebles**, **Provincia**, **País o región**, **Ciudad** y **Calle**.
10.  En la pestaña **General**, configure los campos **Código postal**, **Abreviatura de dirección**, **N.º de callle**, **Entrada**, **Piso**, **Puerta** y **Código de localización** para el edificio o propiedad.
11.  Cierra la página **Inquilinos del Modelo 347** y la página **Transacciones**.
12.  En la página **Modelo 347**, seleccione **Resultado \> Exportar a archivo ASCII**.
13.  En el cuadro de diálogo **Exportar a archivo ASCII**, en el campo **Asignación de formato**, seleccione el formato **Formato de exportación del Modelo 347 (ES)** que descargó anteriormente.
14.  En el campo **Nombre de archivo**, especifique el nombre del archivo y, después, seleccione **Aceptar**.
15.  Seleccione **Resultado \> Imprimir**.
16.  En el cuadro de diálogo **Modelo 347**, en el campo **Asignación de formato**, seleccione el formato **Formato de informe del Modelo 347 (ES)** que descargó anteriormente.
17.  En el campo **Nombre de archivo**, especifique el nombre del archivo y, después, seleccione **Aceptar**. Puede revisar el formato del informe en el ejemplo más adelante en este tema.

## <a name="generate-the-delta-report"></a>Generar el informe delta

Puede crear un nuevo Modelo 347 para el mismo período y usar el informe delta para ver líneas que difieren de las líneas del Modelo 347 original.

1.  Vaya a **Impuesto** \> **Declaraciones** \> **Impuesto** \> **Modelo 347** y seleccione **Generar** para generar el informe que tiene correcciones.
2.  En el cuadro de diálogo **Modelo 347**, establezca la opción **Declaración sustitutiva** en **Sí** identificar esta declaración como una corrección de la declaración original.
3.  En el campo **Número de declaración anterior**, especifique el número de la declaración de la declaración original y haga clic en **Aceptar**.
4.  Seleccione **Resultado \> Informe delta**.
5.  En el cuadro de diálogo **Informe delta**, en el campo **Asignación de formato**, seleccione el formato **Formato de informe del Modelo 347 (ES)** que descargó anteriormente.
6.  En el campo **Nombre de archivo**, especifique el nombre del archivo y, después, seleccione **Aceptar**. Puede revisar el formato del informe en el ejemplo más adelante en este tema.

## <a name="example"></a>Ejemplo

Tenga en cuenta un ejemplo en la entidad jurídica **DEMF**.

### <a name="setup"></a>Configurar

1.  Vaya a **Administración de la organización** \> **Configuración** \> **Organización** \> **Entidades jurídicas**.
2.  En la ficha desplegable **Registro de impuestos**, en el campo **Número de registro de impuestos**, especifique **B80833593**.
3.  Vaya a **Impuesto** \> **Configurar** \> **Impuesto** \> **Cuentas contables de efectivo** y seleccione **Nuevo** para crear una línea.
    
![Página Cuentas contables de efectivo](media/4_Cash_ledger_accounts.png)

4.  Vaya a **Impuesto** \> **Configurar** \> **Impuesto** \> **Número de identificación fiscal** y seleccione **Nuevo** para crear una línea.

![Página Números de identificación fiscal](media/5_Tax_exempt_numbers.png)

### <a name="customer-transactions"></a>Transacciones de clientes

1.  Vaya **Clientes** \> **Clientes** \> **Todos los clientes** y seleccione el cliente **DE-010**.
2.  En la ficha desplegable **Dirección**, establezca **ESP** como el país y luego, en el la ficha desplegable **Factura y entrega**, configure el campo **Número de identificación fiscal** en **01396364B**.
3.  Seleccione **Guardar** y cierre la página.
4.  Seleccione el cliente **DE-011.**
5.  En la ficha desplegable **Dirección**, establezca **ESP** como el país y luego, en el la ficha desplegable **Factura y entrega**, configure el campo **Número de identificación fiscal** en **01396365B**.
6.  Seleccione **Guardar** y cierre la página.
7.  Seleccione el cliente **DE-012.**
8.  En la ficha desplegable **Dirección**, establezca **ESP** como el país y luego, en el la ficha desplegable **Factura y entrega**, configure el campo **Número de identificación fiscal** en **01396366B**.
9.  Seleccione **Guardar** y cierre la página.
10. Seleccione el cliente **DE-014.**
11. En la ficha desplegable **Dirección**, compruebe que **DEU** se estableció como el país y luego, en el la ficha desplegable **Factura y entrega**, compruebe que el campo **Número de identificación fiscal** se estableció en **DE9801**.
12. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**, cree las siguientes cuatro facturas y luego publíquelas.

| **Factura** | **Cliente** | **Fecha**          | **Dirección de entrega** | **Importe** |
|-------------|--------------|-------------------|----------------------|------------|
| FTI-000007  | DE - 012       | 1 de febrero de 2020  | ESP                  | 4,000.00   |
| FTI-000008  | DE - 010       | 3 de febrero de 2020  | ESP                  | 7,000.00   |
| FTI-000009  | DE - 011       | 5 de febrero de 2020  | ESP                  | 8,000.00   |
| FTI-000010  | DE - 014       | 10 de febrero de 2020 | DEU                  | 6,500.00   |

13. Vaya a **Clientes** \> **Pagos** \> **Diario de pagos de clientes**, cree los siguientes cinco pagos y luego publíquelos.

| **Fecha**          | **Cuenta (número de identificación fiscal)** | **Factura liquidada** | **Crédito** | **Tipo de cuenta de contrapartida** | **Cuenta de contrapartida** |
|-------------------|---------------------------------|---------------------|------------|-------------------------|--------------------|
| 20 de febrero de 2020 | DE-012 (01396366B)              | FTI-000007          | 4,000      | Contabilidad                  | 110180             |
| 25 de febrero de 2020 | DE-010 (01396364B)              | FTI-000008          | 7,000      | Contabilidad                  | 110180             |
| 27 de febrero de 2020 | DE-011 (01396365B)              | FTI-000009          | 5,000      | Contabilidad                  | 110180             |
| 1 de marzo de 2020     | DE-011 (01396365B)              | FTI-000009          | 3,000      | Bank                    | DEMF OPER          |
| 3 de marzo de 2020     | DE-014 (DE9801)                 | FTI-000010          | 6,500      | Bank                    | DEMF OPER          |

### <a name="vendor-transactions"></a>Transacciones de proveedor

1.  Vaya a **Proveedores** \> **Proveedores** \> **Todos los proveedores** y seleccione el proveedor **DE-001**.
2.  En la ficha desplegable **Dirección**, establezca **ESP** como el país y luego, en el la ficha desplegable **Factura y entrega**, configure el campo **Número de identificación fiscal** en **03566243B**.
3.  Seleccione **Guardar** y cierre la página.
4.  Seleccione el proveedor **DE-01001**.
5.  En la ficha desplegable **Dirección**, compruebe que **DEU** se estableció como el país y luego, en el la ficha desplegable **Factura y entrega**, establezca el campo **Número de identificación fiscal** en **DE124363748**.
6.  Vaya a **Proveedores** \> **Facturas** \> **Diario de facturas**, cree las siguientes dos facturas y luego publíquelas.

| **Factura** | **Proveedor** | **Fecha**         | **Dirección del proveedor** | **Importe** |
|-------------|------------|------------------|--------------------|------------|
| 1           | DE - 001     | 4 de febrero de 2020 | ESP                | 6,300      |
| 2           | DE - 01001   | 7 de febrero de 2020 | DEU                | 7,100      |

7.  Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos de proveedores**, cree los siguientes dos pagos y luego publíquelos.

| **Fecha**          | **Cuenta** | **Factura** | **Crédito** | **Tipo de cuenta de contrapartida** | **Cuenta de contrapartida** |
|-------------------|-------------|-------------|------------|-------------------------|--------------------|
| 10 de febrero de 2020 | DE - 001      | 1           | 6,300      | Contabilidad                  | 110180             |
| 15 de febrero de 2020 | DE - 01001    | 2           | 7,100      | Bank                    | DEMF OPER          |

### <a name="generate-declaration-347-and-delta-report"></a>Generar el informe del Modelo 347 y delta

1.  Vaya a **Impuesto** \> **Declaraciones** \> **Impuesto** \> **Modelo 347**, seleccione **Generar** y complete los siguientes campos con los siguientes valores:

    -   **Ejercicio**: 2020
    -   **Importe mínimo**: 6000
    -   **Importe mínimo de pagos en efectivo**: 6000

2.  Seleccione **Aceptar**.
3.  Seleccione la línea de declaración que se creó, seleccione **Transacciones** y revise los datos.

![Página Transacciones](media/6_Transactions.png)

Tenga en cuenta los siguientes detalles:

-   La línea para el cliente **DE-012** no se transfirió a la declaración porque ambas cantidades eran inferiores a 6000.
-   En la línea para el cliente **DE-011** (número de identificación fiscal **01396365B**), debido a que el monto del pago en efectivo es inferior a 6000, se restableció a 0 (cero).
-   En la línea para el vendedor **DE-001** (número de identificación fiscal **03566243B**), aunque el pago fue en efectivo, el importe del pago en efectivo es 0 (cero) porque el campo **Importes en efectivo** se completa solo para clientes.

4.  Cierre la página **Transacciones** y luego, en la página **Modelo 347**, seleccione **Generar** para generar el informe que tiene correcciones.
5.  Establezca la opción **Declaración sustitutiva** en **Sí** para identificar esta declaración como una corrección de la declaración original.
6.  En el campo **Número de declaración anterior**, especifique el número de la declaración de la declaración original y haga clic en **Aceptar**.
7.  Seleccione la línea de declaración que se crea, seleccione **Transacciones** y edite la línea para el cliente con número de identificación fiscal **DE9801** de la siguiente manera:

-   El valor en la columna **Cantidad del primer trimestre** pasa a ser 7000 en lugar de 6500.
-   El valor en la columna **Cantidad del segundo trimestre** pasa a ser 3000 en lugar de 0.

![Página Transacciones, columnas de importe del primer y segundo trimestre](media/7_Transactions.png)

8.  Cierre la página **Transacciones**.
9.  Seleccione **Resultado \> Informe delta**.
10.  En el campo **Asignación de formato**, seleccione **Formato del informe del Modelo 347 (ES)**.
11.  En el campo **Nombre de archivo**, especifique el nombre del archivo y, después, seleccione **Aceptar**.
12.  Abra el archivo descargado y revise los datos.

![Datos generados para el formato del informe del Modelo 347 (ES)](media/8_Declaration347.png)

Observe que solo la línea que tiene correcciones se imprime en el informe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]