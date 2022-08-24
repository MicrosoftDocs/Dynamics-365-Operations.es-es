---
title: Intrastat francés
description: Este artículo contiene información sobre la declaración Intrastat en Francia.
author: AdamTrukawka
ms.date: 07/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 83af3cf304772085c5a6f0943ab5196fcc0208c9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287029"
---
# <a name="french-intrastat"></a>Intrastat francés

[!include[banner](../includes/banner.md)]

Las empresas en Francia que están registradas para el impuesto sobre el valor añadido (IVA) y que comercian con otros países de la Unión Europea (UE), deben declarar el intercambio de bienes y servicios desde y hacia Francia. La Declaration d'exchanges de biens (declaración de comercio de bienes o DEB), es una combinación de la lista de ventas de la UE y los informes Intrastat. Debe enviar este informe mensualmente para todas las ventas de bienes intracomunitarios.

El informe DEB se puede generar en cualquiera de dos formatos de archivo de texto electrónico: SAISUNIC 330 o INTRACOM.

La siguiente tabla muestra los campos que se incluyen en la declaración Intrastat francesa en formato SAISUNIC 330. La tabla también indica el nivel de informe del campo. El campo puede ser **4** (simplificado), **1** (completo), o ambos.

| **Campo**                   | **Nivel del informe** |
|-----------------------------|------------------|
| Periodo de referencia         | 4, 1              | 
| Número de declaración       | 4, 1              |
| Número de línea                 | 4, 1              |
| Código ISO de país (FR)       | 4, 1              | 
| Código complementario          | 4, 1              | 
| Número de serie                | 4, 1              | 
| IVA Código del cliente        | 4, 1              | 
| Código de dirección              | 4, 1              |
| Tipo de transacción            | 4, 1              | 
| Nivel de obligación            | 4, 1              |
| Código de mercancía              | 1                | 
| NGP Nacional                | 1                | 
| Provincia (departamento)         | 1                |
| Naturaleza de la transacción       | 1                | 
| País de origen      | 1                | 
| País de origen - Importaciones | 1                | 
| Destino final - Exportaciones | 1                | 
| Valor de la factura               | 4, 1              | 
| Valor estadístico           | 1                |
| Peso neto                  | 1                | 
| Unidades adicionales            | 1                |
| Código de transporte              | 1                | 

La siguiente tabla muestra los campos que se incluyen en la declaración Intrastat francesa en formato INTRACOM.
La tabla también indica el nivel de informe del campo. El campo puede ser **4** (simplificado), **1** (completo), o ambos.

| **Campo**                   | **Nivel del informe**   | 
|-----------------------------|--------------------|
| Código                        | 4, 1               | 
| Número de declaración       | 4, 1               |
| Número de línea              | 4, 1               | 
| Sirena                       | 4, 1               |
| Provincia (departamento)         | 1                  |          
| Código de transporte              | 1                  |          
| País de origen           | 1                  |            
| Naturaleza de la transacción       | 1                  |             
| Valor de la factura               | 4, 1               |             
| Modos de entrega           | 1                  |           
| Tipo de transacción            | 4, 1               |            
| Nivel de obligación            | 4, 1               |           
| Código de mercancía              | 1                  |            
| NGP Nacional                | 1                  |            
| Peso neto                  | 1                  |            
| Valor estadístico           | 1                  |            
| Unidades adicionales            | 1                  |            
| País de origen - Importaciones | 1                  |            
| Destino final - Exportaciones | 1                  |            
| IVA Código del cliente        | 4, 1               |            
| Código complementario          | 4, 1               |           
| Periodo de referencia         | 4, 1               |         

### <a name="set-up-intrastat"></a>Configurar Intrastat

1.  En [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), en la Biblioteca de activos compartidos, descargue las últimas versiones de las configuraciones de informes electrónicos (ER) para el siguiente formato de declaración de Intrastat:

    - Modelo intrastat
    - Informe intrastat
    - INTRACOM intrastat (FR)
    - SAISUNIC intrastat (FR)

    Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  En Dynamics 365 Finance, vaya a **Impuesto** > **Configuración** >  **Comercio exterior** > **Parámetros de comercio exterior** y siga estos pasos:

    1. En la pestaña **Intrastat**, en la ficha desplegable **Informes electrónicos** en el campo **Asignación de formato de archivo**, seleccione **Intrastat INTRACOM (FR)** o **Intrastat SAISUNIC (FR)**.
    2. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat**.
    3. En la ficha desplegable **Jerarquía de códigos de bienes**, en el campo **Jerarquía de categorías**, seleccione **Intrastat**.
    4. En la ficha desplegable **General**, en el campo **Código de transacción**, seleccione el código que se utiliza para las transferencias de mercancías.
    5. En el campo **Nota de crédito**, seleccione el código que se utiliza para las devoluciones de mercancías.
    6. En el campo **Nivel de obligación de exportación**, introduzca el nivel de detalle para el informe de exportación. El nivel que seleccione afecta a las líneas que se muestran en el informe. Para obtener más información, consulte las tablas que aparecen al principio de este artículo.

3. Vaya a **Administración de organizaciones** > **Organizaciones** > **Entidades jurídicas**, seleccione su empresa y siga estos pasos:

    1. En la ficha desplegable **Números de registro**, en el campo **Código NAF** campo, introduzca su código NAF. Para obtener más información, consulte [Códigos FR-00003 NAF y números de siret](tasks/fr-00003-naf-codes-siret-numbers.md).
    2. En la ficha desplegable **Comercio exterior y logística**, en la sección **Intrastat**, configure los campos **Número de exención de IVA por exportación** e **Número de exención de IVA por importación**.
    3. En la ficha desplegable **Registrar impuestos**, en el campo **Número de registro de impuestos**, introduzca el número de registro de impuestos de su empresa.

4. Para especificar códigos NAF y números exentos de impuestos para los clientes, vaya a **Clientes** > **Clientes** > **Todos los clientes** y siga estos pasos:

    1. Seleccione un cliente.
    2. En la ficha desplegable **Factura y entrega**, en la sección **Impuesto de ventas**, en el campo **Número de identificación fiscal**, introduzca el número de identificación fiscal del cliente.
    3. En la ficha desplegable **Demografía de ventas**, en el campo **Francés Siret**, introduzca el número de Siret de la compañía.
    4. En el campo **Código NAF**, introduzca el código NAF de la empresa.
    5. Repita estos pasos para otros clientes.

5. Para especificar códigos NAF y números exentos de impuestos para los proveedores, vaya a **Proveedores** > **Proveedores** > **Todos los proveedores** y siga estos pasos:

    1. Seleccione un proveedor.
    2. En la ficha desplegable **Factura y entrega**, en la sección **Impuesto de ventas**, en el campo **Número de identificación fiscal**, introduzca el número de identificación fiscal del proveedor.
    3. En la ficha desplegable **Demografía de compras**, en el campo **Francés Siret**, introduzca el número de Siret de la compañía.
    4. En el campo **Código NAF**, introduzca el código NAF de la empresa.
    5. Repita estos pasos para otros proveedores.

6. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Compresión de Intrastat** y seleccione los campos que se deben comparar cuando se resume la información de Intrastat. Para Intrastat francés, seleccione **Procedimiento estadístico**, **Estado de origen**, **País / región de origen**, **Términos de entrega**, **Transporte**, **Corrección**, **País / región**, **País de origen / destino**, **Dirección**, **País / región del remitente**, **Estado del remitente**, **Estado**, **Código de transacción**, y **Mercancía**.

7. Vaya a **Gestión de almacenes** > **Configuración** > **Almacén** > **Almacenes**, seleccione un almacén y luego siga estos pasos:

    1. En la ficha desplegable **Direcciones**, seleccione **Agregar** o **Editar**.
    2. En el cuadro de diálogo, en el campo **Ciudad**, seleccione la ciudad del almacén. El estado de la ciudad se utilizará como provincia para su informe DEB.

### <a name="ngp-codes"></a>Códigos NGP

En el informe DEB, la codificación de productos consta de los siguientes elementos:

  - El código CN8 de ocho dígitos que representa la nomenclatura arancelaria y estadística de la UE.
  - Si procede, el código de artículo nacional de la Nomenclatura Générale des Produits (NGP) de un dígito.

En 2021, el NGP se aplica solo a tres tipos de productos:

  - Algunos productos de vacas, ovejas y cabras
  - Equipamiento militar
  - Vinos franceses

 Debe configurar los códigos NGP y asignarlos a productos relacionados. El campo **NGP** se establece automáticamente en la página **Diario intrastat**.

#### <a name="set-up-an-ngp-code"></a>Configurar un código NGP

1. Vaya a **Impuesto** > **Configuración** > **Comercio exterior** > **Códigos NGP**.
2. En el panel de acciones, seleccione **Nuevo** para crear un código NGP.
3. En el campo **NGP**, introduzca un código de un solo dígito.
4. En el campo **Descripción**, especifique una descripción para el código.

#### <a name="assign-an-ngp-code-to-a-product"></a>Asigne un código NGP a un producto

1. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
2. En la cuadrícula, seleccione un producto.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **NGP**, seleccione el código NGP apropiado.

## <a name="intrastat-journal"></a>Diario de Intrastat

Vaya a **Impuestos** > **Declaraciones** > **Comercio** **exterior** > **Intrastat** para gestionar sus transacciones aplicables al comercio exterior con países de la UE. Para obtener más información, consulte [Resumen de Intrastat](emea-intrastat.md).

La columna **NGP** es específica de Francia. Muestra el código NGP del producto. Si el NGP no se aplica a un producto, se muestra **0** (cero). Puede ajustar el código NGP. Seleccione la transacción y luego, en la pestaña **General**, en la sección **Códigos**, en el campo **NGP**, seleccione el código NGP requerido.

### <a name="intrastat-transfer"></a>Transferencia intrastat

En la página **Intrastat**, en el panel de acciones, puede seleccionar **Transferir** para transferir automáticamente la información sobre el comercio intracomunitario de sus órdenes de venta, facturas de servicios, órdenes de compra, facturas de proveedores, recibos de productos de proveedores, facturas de proyectos y órdenes de transferencia. Solo se transferirán los documentos que tengan un país de la UE como país o región de destino (para envíos) o consignación (para llegadas).

Dado que el informe DEB es una combinación de la lista de ventas de la UE y el informe de Intrastat, también incluye transacciones *triangulares*, en las que se realiza una entrega directa desde un país de la UE (parte A) a otro país de la UE (parte C), y una entidad jurídica francesa (parte B) se encuentra en medio del trato triangular.

### <a name="generate-a-deb-intrastat-report"></a>Genere un informe DEB (Intratast)

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Salida** > **Informe**.
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

## <a name="example"></a>Ejemplo

El siguiente ejemplo muestra cómo configurar Intrastat francés y crear el informe DEB. Usa la entidad jurídica **DEMF**.

1. En [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), en la Biblioteca de activos compartidos, descargue las últimas versiones de las configuraciones de ER para el siguiente formato de declaración de Intrastat:

    - Modelo intrastat
    - Informe intrastat
    - INTRACOM intrastat (FR)

2. En Finanzas, configure un código de transacción:

    1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Códigos de transacción**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el campo **Código de transacción**, introduzca **11**.
    4. En el campo **Nombre**, introduzca **Compra o ventas**.
    5. En el panel Acciones, seleccione **Guardar**.

3.  Configurar jerarquía de producto:

    1. Vaya a **Gestión de información de productos** > **Configuración** > **Categorías y atributos** > **Jerarquías de categorías**.
    2. En la cuadrícula, seleccione **Intrastat**. Entonces, en el Panel de acciones, en la ficha **Jerarquía de categoría**, en el grupo **Mantener**, haga clic en **Editar**.
    3. En el panel Acciones, seleccione **Nuevo nodo de categoría**.
    4. En el campo **Nombre**, introduzca **Autres Libournais**.
    5. En el campo **Código**, introduzca **2204 21 42**
    6. En el panel Acciones, seleccione **Guardar**.

4. Vaya a **Impuesto** > **Configuración** > **Comercio Exterior** > **Parámetros de comercio exterior** y siga estos pasos:

    1. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Código de transacción** campo, seleccione **11**.
    2. En la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Intrastat INTRACOM (FR)**.
    3. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat**.
    4. En la ficha desplegable **Jerarquía de códigos de bienes**, en el campo **Jerarquía de categorías**, seleccione **Intrastat**.

5. Configurar un código NGP:

    1. Vaya a **Impuesto** > **Configuración** > **Comercio exterior** > **Códigos NGP**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el campo **NGP**, introduzca **8**.
    4. En el campo **Nombre de descripción** introduzca **NGP 8**.
    5. En el panel Acciones, seleccione **Guardar**.

6. Asigne el código NGP a un producto:

    1. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
    2. En la cuadrícula, seleccione **0001**.
    3. En la ficha desplegable **Comercio exterior**, en el campo **NGP**, seleccione **8**.
    4. En el campo , **Mercancía**, seleccione **2204 21 42**.
    5. En el panel Acciones, seleccione **Guardar**.

7. Cree un pedido de cliente que incluya el nuevo producto:

    1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el cuadro de diálogo **Crear** **pedido** **de ventas**, en la sección **Cliente**, en el campo **Cuenta** **de cliente**, seleccione **100001**.
    4. En la sección **Dirección**, en el campo **Dirección de entrega**, seleccione el signo más (**+**) para crear una dirección.
    5. En el cuadro de diálogo **Dirección nueva**, en el campo **Nombre de descripción**, introduzca **Alemania**.
    6. En el campo **País/región**, seleccione **DEU**.
    7. Seleccione **Aceptar**.
    8. En el cuadro de diálogo **Crear pedido de ventas**, seleccione **Aceptar**.
    9. En la ficha desplegable **Líneas de pedido de** **ventas**, en el campo **Número de artículo**, seleccione **0001**.
    10. En el panel Acciones, seleccione **Guardar**.
    11. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
    12. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todos**. Después seleccione **Aceptar** para publicar la factura.

8.  Crear el informe DEB:

    1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**:
    2. En el panel de acciones. Seleccione **Transferir**.
    3. En el cuadro de diálogo **Intrastat (transferencia)**, en la sección **Parámetros**, configure la opción **Factura del cliente** a **Sí**. A continuación seleccione **Aceptar**.
    4. Ordene las transacciones por el campo **Fecha**. La transacción principal es la transacción de resultado. El campo **NGP** se establece automáticamente.
    5. En el panel de acciones, seleccione **Salida** &gt; **Informe**.
    6. En el cuadro de diálogo **Informe Intrastat**, en la ficha desplegable **Parámetros**, en la sección **Fecha**, seleccione el mes del pedido de ventas que creó.
    7. En la sección **Opciones de exportación**, establezca la opción **Generar archivo** a **Sí**.
    8. En el campo **Nombre del archivo**, especifique el nombre requerido.
    9. Seleccione **Aceptar** y revise el informe.

