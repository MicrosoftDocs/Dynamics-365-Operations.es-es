---
title: Intrastat francés
description: Este artículo contiene información sobre la declaración Intrastat en Francia.
author: anasyash
ms.date: 11/30/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 2076649c7fff9f47b9c1fda62a103168b19bb973
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831815"
---
# <a name="french-intrastat"></a>Intrastat francés

[!include[banner](../includes/banner.md)]

Las empresas en Francia que están registradas para el impuesto sobre el valor añadido (IVA) y que comercian con otros países de la Unión Europea (UE), deben declarar el intercambio de bienes y servicios desde y hacia Francia. La Declaration d'exchanges de biens (declaración de comercio de bienes o DEB), es una combinación de la lista de ventas de la UE y los informes Intrastat. Debe enviar este informe mensualmente para todas las ventas de bienes intracomunitarios.

El informe DEB se puede generar en cualquiera de dos formatos de archivo de texto electrónico: SAISUNIC 330 o INTRACOM.

La siguiente tabla muestra los campos que se incluyen en la declaración Intrastat francesa en formato SAISUNIC 330. La tabla también indica los niveles de informe de cada campo. Un campo puede tener los siguientes niveles de informe:

- **4** – Declaración de impuestos.
- **1** – Respuesta estadística.
- **5** – Respuesta estadística al envío y a la declaración de impuestos, y cumplimentación conjunta.

| Campo                       | Niveles de informe |
|-----------------------------|---------------|
| Periodo de referencia         | 4, 1, 5       |
| Número de declaración       | 4, 1, 5       |
| Número de línea                 | 4, 1, 5       |
| Código ISO de país (FR)       | 4, 1, 5       |
| Código complementario          | 4, 1, 5       |
| Número de serie                | 4, 1, 5       |
| IVA Código del cliente        | 4, 1, 5       |
| Código de dirección              | 4, 1, 5       |
| Tipo de transacción            | 4, 1, 5       |
| Nivel de obligación            | 4, 1, 5       |
| Código de mercancía              | 1, 5          |
| NGP Nacional                | 1, 5          |
| Provincia (departamento)         | 1, 5          |
| Naturaleza de la transacción       | 1, 5          |
| País de origen      | 1, 5          |
| País de origen - Importaciones | 1, 5          |
| Destino final - Exportaciones | 1, 5          |
| Valor de la factura               | 4, 1, 5       |
| Valor estadístico           | 1, 5          |
| Peso neto                  | 1, 5          |
| Unidades adicionales            | 1, 5          |
| Código de transporte              | 1, 5          |

La siguiente tabla muestra los campos que se incluyen en la declaración Intrastat francesa en formato INTRACOM. La tabla también indica los niveles de informe de cada campo. Un campo puede tener los siguientes niveles de informe:

- **4** – Declaración de impuestos.
- **1** – Respuesta estadística.
- **5** – Respuesta estadística al envío y a la declaración de impuestos, y cumplimentación conjunta.

| Campo                       | Niveles de informe |
|-----------------------------|---------------|
| Código de dirección              | 4, 1, 5       |
| Número de declaración       | 4, 1, 5       |
| Número de línea              | 4, 1, 5       |
| Sirena                       | 4, 1, 5       |
| Provincia (departamento)         | 1, 5          |
| Código de transporte              | 1, 5          |
| País de origen           | 1, 5          |
| Naturaleza de la transacción       | 1, 5          |
| Valor de la factura               | 4, 1, 5       |
| Modos de entrega           | 1, 5          |
| Tipo de transacción            | 4, 1, 5       |
| Nivel de obligación            | 4, 1, 5       |
| Código de mercancía              | 1, 5          |
| NGP Nacional                | 1, 5          |
| Peso neto                  | 1, 5          |
| Valor estadístico           | 1, 5          |
| Unidades adicionales            | 1, 5          |
| País de origen - Importaciones | 1, 5          |
| Destino final - Exportaciones | 1, 5          |
| IVA Código del cliente        | 4, 1, 5       |
| Código complementario          | 4, 1, 5       |
| Periodo de referencia         | 4, 1, 5       |

## <a name="set-up-intrastat"></a>Configurar Intrastat

- En [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), en la biblioteca Activos compartidos, descargue las últimas versiones de las configuraciones de informes electrónicos (ER) para la declaración de Intrastat.

    - Modelo intrastat
    - Informe intrastat
    - INTRACOM intrastat (FR)
    - SAISUNIC intrastat (FR)

    Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

### <a name="set-up-vat-ids"></a>Configuración del id. de IVA

#### <a name="set-up-vat-codes-for-your-company"></a>Configurar códigos de IVA para su empresa

1. Vaya a **Impuestos** \> **Configuración** \> **Impuestos** \> **Números de identificación fiscal**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **País/región**, seleccione **FRA**.
4. En el campo **Importación de número de exención fiscal**, introduzca la clave del número de IVA de su empresa.
5. Vaya a **Administración de organizaciones** \> **Organizaciones** \> **Entidades jurídicas** y seleccione su empresa.
6. En la ficha desplegable **Comercio exterior y logística**, en la sección **Intrastat**, configure los campos **Número de exención de IVA por exportación** y **Número de exención de IVA por importación** con el código que creó en el paso 4.
7. En la ficha desplegable **Registrar impuestos**, en el campo **Número de registro de impuestos**, introduzca el número de registro de impuestos de su empresa.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Configurar el CIF para los partners comerciales

##### <a name="create-a-registration-type-for-the-company-code"></a>Crear un tipo de registro para el código de empresa

Debe crear tipos de registro de ID de IVA para todos los países o regiones con los que su empresa hace negocios.

1. Vaya a **Administración de la organización** \> **Libreta de direcciones global** \> **Tipos de registro** \> **Tipos de registro**.
2. En el panel de acciones, seleccione **Nuevo** para crear un tipo de registro para el ID de IVA.
3. En el cuadro de diálogo **Escribir detalles del tipo de registro**, en el campo **Nombre** introduzca un nombre para el nuevo tipo de registro. Por ejemplo, escriba **CIF**.
4. En el campo **País o región**, escriba o seleccione el país o región del partner comercial.
5. Seleccione **Crear**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Asociar el tipo de registro con una categoría de registro

1. Vaya a **Administración de la organización** \> **Libreta de direcciones global** \> **Tipos de registro** \> **Categorías de registro**.
2. En el Panel de acciones, seleccione **Nuevo** para crear un vínculo entre un tipo de registro que creó y una categoría de registro.
3. Para el tipo de registro para el ID de IVA, seleccione la categoría de registro **ID de IVA**.
4. Repita los pasos 2 y 3 para los otros tipos de registro que creó para los países o regiones con los que su empresa hace negocios.

##### <a name="set-up-the-vat-number-of-a-trading-partner"></a>Configurar el número de IVA de un socio comercial

1. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes**.
2. En la cuadrícula, seleccione un cliente.
3. En el panel Acciones, en la pestaña **Cliente**, en el grupo **Registro**, seleccione **Id. de registro**.
4. En la ficha desplegable **ID de registro**, seleccione **Agregar** para crear un ID de registro.
5. En el campo **Tipo de registro**, seleccione el tipo de registro que creó para el código de empresa.
6. En el campo **Número de registro**, escriba el número de IVA de la empresa.
7. En el la panel de acciones, seleccione **Guardar** y después cierre la página.

Para obtener más información, consulte [Id. de registro](emea-registration-ids.md).

### <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

1. Vaya a **Impuestos** \> **Configuración** \> **Comercio exterior** \> **Parámetros de comercio exterior**.
2. En la pestaña **Intrastat**, en la ficha desplegable **Informes electrónicos** en el campo **Asignación de formato de archivo**, seleccione **Intrastat INTRACOM (FR)** o **Intrastat SAISUNIC (FR)**.
3. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat**.
4. En la ficha desplegable **Jerarquía de códigos de bienes**, en el campo **Jerarquía de categorías**, seleccione **Intrastat**.
5. En la ficha desplegable **General**, en el campo **Código de transacción**, seleccione el código que se utiliza para las transferencias de mercancías.
6. En el campo **Nota de crédito**, seleccione el código que se utiliza para las devoluciones de mercancías.
7. En el campo **Trabajador**, seleccione el nombre de la persona de contacto.
8. En la pestaña **Contacto**, agregue información sobre la persona de contacto:

    - En el campo **Teléfono**, introduzca el número de teléfono de la persona de contacto.
    - En el campo **Fax**, introduzca el número de fax de la persona de contacto.

9. En la pestaña **Propiedades de país o región**, en el campo **País o región**, enumere todos los países o regiones con los que su organización hace negocios. Para cada país o región que forma parte de la UE, seleccione **UE** en el campo **Tipo de país o región**,para que el país o la región aparezca en su informe de Intrastat. Para Francia, seleccione **Nacional** en el campo **Tipo de país o región**.

### <a name="set-up-compression-of-intrastat"></a>Configurar la compresión de Intrastat

- Vaya a **Impuestos** \> **Configuración** \> **Comercio Exterior** \> **Compresión de Intrastat** y seleccione los campos que se deben comparar cuando se resume la información de Intrastat. Para el Intrastat francés, seleccione los siguientes campos:
 
    - Procedimiento de las estadísticas
    - País o región de origen
    - Transporte
    - Corrección
    - País/región
    - Provincia de origen o destino
    - Dirección
    - País/región de remitente
    - Código de transacción
    - Código Intrastat de la mercancía

### <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Configurar parámetros del producto para la declaración de Intrastat

1. Vaya a **Gestión de información de productos** \> **Productos** \> **Productos emitidos**.
2. En la cuadrícula, seleccione un producto.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione el código de mercancía. El nombre de la mercancía se imprimirá en el campo **Descripción de mercancías** en el informe de Intrastat.
4. En la sección **Origen**, en el campo **País / región**, seleccione el país o la región de origen del producto.
5. En la ficha desplegable **Administrar inventario**, en el campo **Peso neto**, introduzca el peso del producto en kilogramos.

### <a name="ngp-codes"></a>Códigos NGP

En el informe DEB, la codificación de productos consta de los siguientes elementos:

- El código CN8 de ocho dígitos que representa la nomenclatura arancelaria y estadística de la UE.
- Si procede, el código de artículo nacional de la Nomenclatura Générale des Produits (NGP) de un dígito.

En 2022, el NGP se aplica solo a tres tipos de productos:

- Algunos productos de vacas, ovejas y cabras
- Equipamiento militar
- Vinos franceses

Debe configurar los códigos NGP y asignarlos a productos relacionados. El campo **NGP** se establece automáticamente en la página **Diario intrastat**.

#### <a name="set-up-an-ngp-code"></a>Configurar un código NGP

1. Vaya a **Impuesto** \> **Configuración** \> **Comercio exterior** \> **Códigos NGP**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **NGP**, introduzca un código de un solo dígito.
4. En el campo **Descripción**, especifique una descripción para el código.

#### <a name="assign-an-ngp-code-to-a-product"></a>Asigne un código NGP a un producto

1. Vaya a **Gestión de información de productos** \> **Productos** \> **Productos emitidos**.
2. En la cuadrícula, seleccione un producto.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **NGP**, seleccione el código NGP apropiado.

### <a name="set-up-warehouse-parameters-for-the-intrastat-declaration"></a>Configurar parámetros del almacén para la declaración de Intrastat

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Almacén** \> **Almacenes**.
2. Seleccione un almacén y luego, en la pestaña desplegable **Direcciones**, seleccione **Agregar** o **Editar**.
3. En el cuadro de diálogo, en el campo **Ciudad**, seleccione la ciudad del almacén. El estado o provincia de la ciudad se utilizará como provincia para su informe DEB.

### <a name="set-up-the-transport-method"></a>Configure el método de transporte

1. Vaya a **Impuestos** \> **Configurar** \> **Comercio exterior** \> **Método de transporte**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Transporte**, especifique un código único. Las empresas en Francia utilizan códigos de transporte de un dígito.

### <a name="intrastat-journal"></a>Diario de Intrastat

Vaya a **Impuestos** \> **Declaraciones** \> **Comercio extranjero** \> **Intrastat** para gestionar sus transacciones aplicables al comercio exterior con países de la UE. Para obtener más información, consulte [Resumen de Intrastat](emea-intrastat.md).

La columna **NGP** es específica de Francia y muestra el código NGP del producto. Si el NGP no se aplica a un producto, se muestra **0** (cero). Para ajustar el código NGP, seleccione la transacción y luego, en la pestaña **General**, en la sección **Códigos**, en el campo **NGP**, seleccione el código NGP requerido.

#### <a name="intrastat-transfer"></a>Transferencia intrastat

En la página **Intrastat**, en el panel de acciones, puede seleccionar **Transferir** para transferir automáticamente la información sobre el comercio intracomunitario de sus órdenes de venta, facturas de servicios, órdenes de compra, facturas de proveedores, recibos de productos de proveedores, facturas de proyectos y órdenes de transferencia. Solo se transferirán los documentos que tengan un país de la UE como país o región de destino (para envíos) o consignación (para llegadas).

Dado que el informe DEB es una combinación de la lista de ventas de la UE y el informe de Intrastat, también incluye transacciones *triangulares*, en las que se realiza una entrega directa desde un país de la UE (parte A) a otro país de la UE (parte C), y una entidad jurídica francesa (parte B) se encuentra en medio del trato triangular.

#### <a name="generate-a-deb-intrastat-report"></a>Genere un informe DEB (Intratast)

1. Vaya a **Impuestos** \> **Declaraciones** \> **Comercio exterior** \> **Intrastat**.
2. En el panel de acciones, seleccione **Salida** \> **Informe**.
3. En el cuadro de diálogo **Informe Intrastat**, establezca los campos siguientes.

    | Campo            | Descripción                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Fecha de inicio        | Seleccione la fecha inicial del informe.                                                                                               |
    | Fecha de finalización          | Seleccione la fecha final del informe.                                                                                                 |
    | Generar archivo    | Establezca esta opción en **Sí** para generar un archivo .txt.                                                                                 |
    | Nombre de archivo        | Introduzca el nombre del archivo .txt para su informe Intrastat.                                                                          |
    | Generar informe  | Establezca esta opción en **Sí** para generar un archivo .xml.                                                                                |
    | Nombre de archivo del informe | Especifique el nombre necesario.                                                                                                            |
    | Sólo correcciones | Establezca esta opción a **Sí** para informar solo de las correcciones. Seleccione **No** para informar tanto de transacciones normales como de correcciones.         |
    | Dirección        | Seleccione **Llegadas** para un informe sobre llegadas intracomunitarias. Seleccione **Envíos** para un informe sobre los envíos intracomunitarios. |

4. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Informe Intrastat**.
5. En el cuadro de diálogo **Parámetros de informes electrónicos**, en la ficha desplegable **Parámetros**, en el campo **Nivel de informe**, seleccione el nivel de informe. El nivel del informe puede ser **1 - respuesta estadística**, **4 - declaración de impuestos**, o **5 - respuesta estadística al envío y declaración de impuestos**.

## <a name="example"></a>ejemplo

El siguiente ejemplo muestra cómo configurar Intrastat francés y crear el informe DEB. Usa la entidad jurídica **DEMF**.

### <a name="preliminary-setup"></a>Configuración preliminar

1. En [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), en la Biblioteca de activos compartidos, descargue las últimas versiones de las configuraciones de ER para el siguiente formato de declaración de Intrastat:

    - Modelo intrastat
    - Informe intrastat
    - INTRACOM intrastat (FR)

2. Configurar jerarquía de producto:

    1. Vaya a **Gestión de información de productos** \> **Configuración** \> **Categorías y atributos** \> **Jerarquías de categorías**.
    2. En la cuadrícula, seleccione **Intrastat**.
    3. En el Panel de acciones, en la ficha **Jerarquía de categoría**, en el grupo **Mantener**, haga clic en **Editar**.
    4. En el panel Acciones, seleccione **Nuevo nodo de categoría**.
    5. En el campo **Nombre**, introduzca **Autres Libournais**.
    6. En el campo **Código**, introduzca **2204 21 42**.
    7. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-vat-ids"></a>Configuración del id. de IVA

#### <a name="set-up-vat-codes-for-your-company"></a>Configurar códigos de IVA para su empresa

1. Vaya a **Impuestos** \> **Configuración** \> **Impuestos** \> **Números de identificación fiscal**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **País/región**, seleccione **FRA**.
4. En el campo **Número de identificación fiscal**, introduzca **MS123456**.
5. Vaya a **Administración de la organización** \> **Organización** \> **Entidades jurídicas** y seleccione **DEMF**.
6. En la ficha desplegable **Comercio exterior y logística**, en la sección **Intrastat**, configure los campos **Número de exención de IVA por exportación** y **Número de exención de IVA por importación** con el código que creó en el paso 4.
7. En la ficha desplegable **Registro de impuestos**, en el campo **Número de registro de impuestos**, especifique **123456789**.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Configurar el CIF para los partners comerciales

##### <a name="create-a-registration-type-for-the-company-code"></a>Crear un tipo de registro para el código de empresa

1. Vaya a **Administración de la organización** \> **Libreta de direcciones global** \> **Tipos de registro** \> **Tipos de registro**.
2. En el panel de acciones, seleccione **Nuevo** para crear un tipo de registro para el ID de IVA.
3. En el cuadro de diálogo **Escribir detalles del tipo de registro**, en el campo **Nombre**, escriba **Id. de IVA**.
4. En el campo **País/región**, seleccione **DEU**.
5. Seleccione **Crear**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Asociar el tipo de registro con una categoría de registro

1. Vaya a **Administración de la organización** \> **Libreta de direcciones global** \> **Tipos de registro** \> **Categorías de registro**.
2. En el Panel de acciones, seleccione **Nuevo** para crear un vínculo entre el tipo de registro que creó y la categoría de registro.
3. Para el tipo de registro para el **ID de IVA** del país **DEU**, seleccione la categoría de registro **ID de IVA**.

##### <a name="set-up-the-customers-vat-registration-number"></a>Configure el número de registro de IVA del cliente

1. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes**.
2. En la cuadrícula, seleccione **DE-016**.
3. En el panel Acciones, en la pestaña **Cliente**, en el grupo **Registro**, seleccione **Id. de registro**.
4. En la ficha desplegable **ID de registro**, seleccione **Agregar** para crear un ID de registro.
5. En el campo **Tipo de registro**, seleccione **ID de IVA**.
6. En el campo **Número de registro**, escriba **DE9012**.
7. En el la panel de acciones, seleccione **Guardar** y después cierre la página.
8. En la ficha desplegable **Factura y entrega**, en la sección **Impuesto de ventas**, en el campo **Número de identificación fiscal**, seleccione **DE9012**.

### <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

1. Vaya a **Impuestos** \> **Configuración** \> **Comercio exterior** \> **Parámetros de comercio exterior**.
2. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Código de transacción** campo, seleccione **11**.
3. En la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Intrastat INTRACOM (FR)**.
4. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat**.
5. En la ficha desplegable **Jerarquía de códigos de bienes**, en el campo **Jerarquía de categorías**, seleccione **Intrastat**.
6. Seleccione un registro en el campo **Trabajador**.
7. En la ficha **Contacto**, en el campo **Teléfono**, introduzca el número de teléfono del contacto
8. En el campo **Fax**, introduzca el número de fax del contacto.

### <a name="create-ngp-code"></a>Crear código NGP

1. Vaya a **Impuesto** \> **Configuración** \> **Comercio exterior** \> **Códigos NGP**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **NGP**, introduzca **8**.
4. En el campo **Nombre de descripción** introduzca **NGP 8**.
5. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-product-information"></a>Configurar información de productos

1. Vaya a **Gestión de información de productos** \> **Productos** \> **Productos emitidos**.
2. En la cuadrícula, seleccione **D0001**.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **NGP**, seleccione **8**.
4. En el campo , **Mercancía**, seleccione **2204 21 42**.
5. En la sección **Origen**, en el campo **País o región**, seleccione **FRA**.
6. En la ficha desplegable **Administrar inventario**, en la sección **Medidas de peso**, en el campo **Peso neto**, introduzca **2**.
7. En el la panel de acciones, seleccione **Guardar** y después cierre la página.
8. En la cuadrícula, seleccione **D0003**.
9. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione **100 200 30**.
10. En la sección **Origen**, en el campo **País o región**, seleccione **DEU**.
11. En la ficha desplegable **Administrar inventario**, en la sección **Medidas de peso**, en el campo **Peso neto**, introduzca **5**.
12. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-regime-codes"></a>Configurar códigos de regimen

1. Vaya a **Impuesto** \> **Configurar** \> **Comercio exterior** \> **Procedimiento estadístico**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Procedimiento estadístico**, introduzca **21**.
4. En el campo **Texto 1**, escriba **Código de regimen 21**.

### <a name="change-the-site-address"></a>Cambiar la dirección del sitio

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Almacén** \> **Sitios**.
2. En la cuadrícula, seleccione **1**.
3. En la ficha desplegable **Direcciones**, seleccione **Editar**.
4. En el cuadro de diálogo **Editar dirección**, en el campo **País/región**, seleccione **FRA**.
5. Seleccione **Aceptar**.
6. Vaya a **Warehouse Management** \> **Configuración** \> **Depósito** \> **Almacenes** y seleccione un almacén.
7. En la ficha desplegable **Direcciones**, seleccione **Agregar**.
8. En el cuadro de diálogo **Nueva dirección**, en el campo **País/región**, seleccione **FRA**.
9. En el campo **Ciudad** seleccione **Burdeos**.
10. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

### <a name="set-up-a-transport-method"></a>Configure un método de transporte

1. Vaya a **Impuestos** \> **Configurar** \> **Comercio exterior** \> **Método de transporte**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Transporte**, escriba **3**.
4. En el campo **Descripción**, escriba **Transporte por carretera**.

### <a name="assign-a-transport-mode-to-a-mode-of-delivery"></a>Asignar un modo de transporte a un modo de entrega

1. Vaya a **Adquisiciones y abastecimiento** \> **Configuración** \> **Distribución** \> **Modos de entrega**.
2. En la cuadrícula, seleccione **50**.
3. En la ficha desplegable **Comercio exterior**, en el campo **Transporte**, seleccione **3**.

### <a name="create-a-sales-order-with-an-eu-customer-that-includes-the-new-product"></a>Crear un pedido de cliente con un cliente EU que incluya el nuevo producto

1. Vaya a **Clientes** \> **Pedidos** \> **Todos los pedidos de ventas**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de ventas**, en la sección **Cliente**, en el campo **Cuenta de cliente**, seleccione **DE-016**.
4. En la sección **Dirección**, en el campo **Dirección de entrega**, seleccione el signo más (**+**) para crear una dirección.
5. En el cuadro de diálogo **Dirección nueva**, en el campo **Nombre de descripción**, introduzca **Alemania**.
6. En el campo **País/región**, seleccione **DEU**.
7. Seleccione **Aceptar**.
8. En el cuadro de diálogo **Crear pedido de ventas**, seleccione **Aceptar**.
9. En la ficha desplegable **Líneas de pedido de ventas**, en el campo **Número de artículo**, seleccione **0001**.
10. En la ficha desplegable **Detalles de la línea**, en la pestaña **Comercio exterior**, en el campo **Procedimiento estadístico**, seleccione **21**.
11. En el campo **Estado de origen**, seleccione **AL**.
12. En el panel Acciones, seleccione **Guardar**.
13. En la pestaña **Encabezado**, en la pestaña rápida **Entrega**, en el campo **Modo de entrega**, asegúrese de que **50** esté seleccionado.
14. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
15. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todos**. Después seleccione **Aceptar** para publicar la factura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transferir la transacción al diario de Intrastat y revisar el resultado

1. Vaya a **Impuestos** \> **Declaraciones** \> **Comercio exterior** \> **Intrastat**.
2. En el panel de acciones, seleccione **Transferir**.
3. En el cuadro de diálogo **Intrastat (transferencia)**, en la sección **Parámetros**, configure la opción **Factura del cliente** a **Sí**. A continuación seleccione **Aceptar**.
4. Ordene las transacciones por el campo **Fecha**. La transacción principal es la transacción de resultado.

    ![Línea que representa el pedido de ventas en la página de Intrastat.](media/intrastat_fr_1.png)

5. Seleccione la línea de transacción y luego seleccione la pestaña **General** para ver más detalles.

    ![Detalles del pedido de ventas en la pestaña General de la página de Intrastat.](media/intrastat_fr_2.png)

6. En el panel de acciones, seleccione **Salida** \> **Informe**.
7. En el cuadro de diálogo **Informe Intrastat**, en la ficha desplegable **Parámetros**, en la sección **Fecha**, seleccione el mes del pedido de ventas que creó.
8. En la sección **Opciones de exportación**, establezca la opción **Generar archivo** a **Sí**.
9. En el campo **Nombre del archivo**, especifique el nombre requerido.
10. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Informe Intrastat**.
11. En el cuadro de diálogo **Parámetros de informes electrónicos**, en la ficha desplegable **Parámetros**, en el campo **Nivel de informe**, seleccione **5 - respuesta estadística al envío y declaración de impuestos** y revise el informe.

    ![Informe Intracom de Intrastat sobre envíos.](media/intrastat_fr_3.png)

12. Revise el informe Excel generado.

    ![Informe de Intrastat sobre envíos.](media/intrastat_fr_4.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
