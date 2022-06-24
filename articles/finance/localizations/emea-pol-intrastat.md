---
title: Intrastat polaco
description: Este artículo contiene información sobre los informes Intrastat en Polonia.
author: andosip
ms.date: 11/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: ''
ms.openlocfilehash: 45bd1d3c90d0a8a8ad5db6d0b80c5eed0aa489e8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871112"
---
# <a name="polish-intrastat"></a>Intrastat polaco

[!include[banner](../includes/banner.md)]

La página **Intrastat** se usa para generar y presentar información sobre el comercio entre los países de la Unión Europea (UE). La declaración Intrastat polaca contiene información sobre el comercio de mercancías para declarar.

La declaración Intrastat polaca incluye los siguientes campos. Todos los campos están incluidos en llegadas y envíos excepto para **RodzajTransportu** (el modo de transporte) y **KrajPochodzenia** (el país o región de origen) que no están incluidos en los envíos, y **IdKontrahenta** (el número de IVA extranjero del cliente) que no se incluye en las llegadas.

| Nombre de campo | Description |
|-------------------------|-------------------------|
| Datos de Deklaracja | La fecha en la que se crea el documento. |
| Miesiac | El mes de referencia de la declaración. |
| Rok | El año de referencia de la declaración. |
| Numer | El número de declaración en el período de referencia. |
| Wersja | El número de versión de la declaración. |
| NrWlasny | El identificador de la declaración. El valor se genera automáticamente. |
| Typ | La dirección del informe.</br><li>Para las llegadas, se imprime "P".</li><li>Para los envíos, se imprime "W".</li> |
| Rodzaj | El tipo de declaración. El valor indica si el informe es la declaración original o una declaración de corrección. |
| UC | El código de unidad al que se dirige la declaración de Intrastat. El valor se especifica en el campo **Número de identificación fiscal** en la sección **Impuestos** en la pestaña **Agente** de la página **Parámetros de comercio exterior**. |
| Nazwa | El nombre de la empresa. |
| Miejscowosc, UlicaNumer, KodPocztowy | La dirección completa de la entidad jurídica. |
| Nip | El número de identificación fiscal polaco (identificación del impuesto sobre el valor agregado [IVA]). |
| Regon | El número de identificación estadístico polaco (número de empresa). |
| LacznaWartoscFaktur | La suma de los valores de la factura. |
| LacznaWartoscStatystyczna | La suma de valores estadísticos. |
| LacznaLiczbaPozycji | El número total de artículos de productos. |
| PozId | El número consecutivo de un artículo de productos determinado. |
| OpisTowaru | El nombre comercial de la mercancía. |
| KrajPochodzeniaWysylki | El código de la Organización internacional para la estandarización (ISO) para el país o región de la contrapartida. |
| WarunkiDostawy | El código de Intrastat para las condiciones de entrega. |
| RodzajTransakcji | El código que indica la naturaleza de la transacción. Las empresas polacas utilizan códigos de transacción de dos dígitos. |
| KodTowarowy | El código de mercancía de ocho dígitos según la nomenclatura combinada. |
| RodzajTransportu | El código de Intrastat para el modo de transporte. |
| KrajPochodzenia | El código ISO del país o región donde se produjeron o fabricaron los productos básicos. |
| MasaNetto | La masa neta en kilogramos completos. |
| IloscUzupelniajacaJm | La cantidad en la unidad de medida suplementaria, en números enteros. |
| WartoscFaktury | El valor de factura de todas las transacciones que están cubiertas por un artículo. |
| WartoscStatystyczna | El valor estadístico. |
| Wypelniajacy: NazwiskoImie, Telefon, Faks, Email | El nombre y apellidos, número de teléfono, número de fax y dirección de correo electrónico de la persona que presenta la declaración. |
| IdKontrahenta | El número de IVA extranjero del cliente en un estado miembro de la UE. |


## <a name="set-up-intrastat"></a>Configurar Intrastat

Desde el repositorio global, importe la última versión de las siguientes configuraciones de Informes electrónicos (ER):

   - Modelo intrastat
   - Informe intrastat
   - Intrastat (PL)

Para obtener más información, consulte [Descargue las configuraciones de ER del repositorio global del servicio de configuración](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configure un ID de IVA y un número de empresa para su empresa

### <a name="create-registration-types-for-company-codes"></a>Crear tipos de registro para códigos de empresa

Debe crear dos tipos de registro para códigos de empresa: uno para el número de identificación fiscal (código NIP) y otro para el número de empresa (código Regon).

1. Vaya a **Administración de la organización** > **Libreta de direcciones global** > **Tipos de registro** > **Tipos de registro**.
2. En el panel de acciones, seleccione **Nuevo** para crear un tipo de registro para el ID de IVA.
3. En el cuadro de diálogo **Escribir detalles del tipo de registro**, en el campo **Nombre** introduzca un nombre para el nuevo tipo de registro. Por ejemplo, escriba **NIP**.
4. En el campo **País/región**, seleccione **POL**.
5. Seleccione **Crear**.
6. En el Panel de acciones, seleccione **Nuevo** para crear un tipo de registro para el número de empresa.
7. En el cuadro de diálogo **Escribir detalles del tipo de registro**, en el campo **Nombre** introduzca un nombre para el nuevo tipo de registro. Por ejemplo, especifique **Regon**.
8. En el campo **País/región**, seleccione **POL**.
9. Seleccione **Crear**.

### <a name="match-the-registration-types-with-registration-categories"></a>Asociar los tipos de registro con las categorías de registro

1. Vaya a **Administración de la organización** > **Libreta de direcciones global** > **Tipos de registro** > **Categorías de registro**.
2. En el Panel de acciones, seleccione **Nuevo** para crear un vínculo entre cada tipo de registro que creó y una categoría de registro.

    - Para el tipo de registro para el ID de IVA (código NIP), seleccione la categoría de registro **ID de IVA**.
    - Para el tipo de registro para el número de empresa (código Regon), seleccione la categoría de registro **ID de empresa (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configure un ID de IVA y un número de empresa para su empresa

1. Vaya a **Administración de la organización** > **Organizaciones** > **Entidades jurídicas**.
2. En la cuadrícula, seleccione su empresa.
3. En el Panel de acciones, seleccione **Id. de registro**.
4. En la ficha desplegable **Id. de registro**, seleccione **Agregar**.
5. En el campo **Tipo de registro**, seleccione uno de los tipos de registro que creó anteriormente.
6. Ingrese el ID de IVA de su empresa (código NIP) o el número de empresa (código Regon), según el tipo de registro que seleccionó en el paso anterior.
7. Repita los pasos 4 a 6 para el otro tipo de registro que creó anteriormente.

## <a name="set-up-a-company-address"></a>Configurar una dirección de empresa

1. Vaya a **Administración de la organización** > **Organizaciones** > **Entidades jurídicas**.
2. En la cuadrícula, seleccione su empresa.
3. En la pestaña **Direcciones**, seleccione **Editar**.
4. En el cuadro de diálogo **Editar dirección**, en el campo **Código postal**, seleccione el código postal de su empresa.
5. En el campo **Calle**, escriba su dirección.
6. En el campo **Ciudad** seleccione su ciudad.

## <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

1. Vaya a **Impuestos** > **Configuración** > **Parámetros de comercio exterior**.
2. En la pestaña **Intrastat**, en la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Intrastat (PL)**.
3. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat**.
4. En la ficha desplegable **Jerarquía de códigos de bienes**, en el campo **Jerarquía de categorías**, seleccione **Intrastat**.
5. En el campo **Codigo de transacción**, seleccione el código de transacción para transferencias de propiedad. Use este código para transacciones que provoquen transferencias de propiedad reales o planificadas a cambio de una compensación (financieras o de otro tipo). Úselo también para correcciones. Las empresas polacas utilizan códigos de transacción de dos dígitos.
6. En el campo **Nota de abono**, seleccione el código de transacción para la devolución de mercancías.
7. En la pestaña **Propiedades de país o región**, en el campo **País o región**, enumere todos los países o regiones con los que su organización hace negocios. Para cada país o región que forma parte de la UE, seleccione **UE** en el campo **Tipo de país o región**,para que el país o la región aparezca en su informe de Intrastat. Para Polonia, seleccione **Nacional** en el campo **Tipo de país o región**.
8. En la pestaña **Agente**, en la ficha desplegable **Agente**, en la sección **Impuestos**, en el campo **Número de identificación fiscal**, ingrese **420000** para indicar el código de unidad al que se dirige la declaración de Intrastat.
9. En la pestaña **Contacto**, escriba el nombre, número de teléfono, número de fax y dirección de correo electrónico de la persona que presenta la declaración.
10. En la pestaña **Secuencias numéricas**, en el campo **Código de secuencia numérica** para la referencia **Número de archivo XML**, especifique una secuencia numérica no continua que tenga un máximo de nueve caracteres. Este campo se utiliza para generar automáticamente un valor para el campo **Identificador de declaración** en el informe de Intrastat.

## <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Configurar parámetros del producto para la declaración de Intrastat

1. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
2. En la cuadrícula, seleccione un producto.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione el código de mercancía. El nombre de la mercancía se imprimirá en el campo **Descripción de mercancías** en el informe de Intrastat.
4. En la sección **Origen**, en el campo **País / región**, seleccione el país o la región de origen del producto.
5. En la ficha desplegable **Administrar inventario**, en el campo **Peso neto**, introduzca el peso del producto en kilogramos.

## <a name="set-up-compression-of-intrastat"></a>Configurar la compresión de Intrastat

-   Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Compresión de Intrastat** y seleccione los campos que se deben comparar cuando se resume la información de Intrastat. Para el Intrastat polaco, seleccione los siguientes campos:

    - Código Intrastat de la mercancía
    - Código de transacción
    - País o región de origen
    - Transporte
    - Condiciones de entrega
    - País/región de remitente
    - País o región
    - Corrección
    - Número de identificación fiscal
    - Dirección
    - Factura

## <a name="set-up-the-transport-method-and-delivery-terms"></a>Configurar el método de transporte y los plazos de entrega

1.  Configure códigos de transporte.

    1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Método de transporte**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el campo **Transporte**, especifique un código único. Las empresas polacas utilizan códigos de transporte de un dígito.

2.  Configure códigos Intrastat del modo de entrega.

    1. Vaya a **Adquisición y abastecimiento** > **Configuración** > **Distribución** > **Condiciones de entrega**.
    2. En la cuadrícula, seleccione un conjunto de condiciones de entrega.
    3. En la ficha desplegable **General**, en el campo **Código intrastat**, escriba el código único.

## <a name="intrastat-transfer"></a>Transferencia intrastat

En la página **Intrastat**, en el panel de acciones, puede seleccionar **Transferir** para transferir automáticamente la información sobre el comercio intracomunitario de sus órdenes de venta, facturas de servicios, órdenes de compra, facturas de proveedores, recibos de productos de proveedores, facturas de proyectos y órdenes de transferencia. Solo se transferirán los documentos que tengan un país de la UE como país o región de destino o consignación.

También puede introducir transacciones manualmente seleccionando **Nuevo** en el Panel de acciones.

### <a name="generate-an-intrastat-report"></a>Genere un informe Intrastat

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Salida** &gt; **Informe**.
3. En el cuadro de diálogo **Informe Intrastat**, establezca los campos siguientes.

    | Campo | Description |
    |-------------------------|-------------------------|
    | Fecha de inicio | Seleccione la fecha inicial del informe. |
    | Generar archivo | Establezca esta opción en **Sí** para generar un archivo .xml para el informe de Intrastat. |
    | Nombre de archivo | Especifique el nombre del archivo .xml. |
    | Generar informe | Establezca esta opción en **Sí** para generar un archivo .xlsx para el informe de Intrastat. |
    | Nombre de archivo del informe | Especifique el nombre del archivo .xlsx. |
    | Dirección | Seleccione **Llegadas** para un informe sobre llegadas intracomunitarias.</br>Seleccione **Envíos** para un informe sobre los envíos intracomunitarios. |
    | Identificador de la declaración | La identificación del documento se genera automáticamente y se puede actualizar. |
    | Tipo de declaración | Seleccione **Declaración** para una declaración original.</br>Seleccione **Declaración sustitutiva - sustitución** para una declaración sustitutiva que esté destinada a reemplazar completamente una declaración original o sustitutiva existente presentada anteriormente. |
    | Ciudad de creación de documentos | Ingrese el valor que debe imprimirse en el campo **Miejscowosc** en la declaración de Intrastat. |
    | Fecha de creación de documentos | Ingrese el valor que debe imprimirse en el campo **Deklaracja Data** en la declaración de Intrastat. |
    | Número de documento | Ingrese el valor que debe imprimirse en el campo **Numer** en la declaración de Intrastat. |
    | Versión de documento | Ingrese el valor que debe imprimirse en el campo **Wersja** en la declaración de Intrastat. |

4. Seleccione **Aceptar** y revise los informes generados.

## <a name="example"></a>Ejemplo

Este ejemplo muestra cómo registrar llegadas y envíos para Intrastat utilizando la entidad legal **DEMF**.

### <a name="preliminary-setup"></a>Configuración preliminar

Importe la versión más reciente de las siguientes configuraciones de ER:

   - Modelo intrastat
   - Informe intrastat
   - Intrastat (PL)

### <a name="set-up-a-company-address"></a>Configurar una dirección de empresa

1. Vaya a **Administración de la organización** > **Libreta de direcciones global** > **Direcciones** > **Configuración de direcciones**.
2. En la pestaña **Ciudad**, seleccione **Nuevo**.
3. En el campo **País/región**, seleccione **POL**.
4. En el campo **Ciudad**, especifique **Warsaw**.
5. En la pestaña **Código postal**, seleccione **Nuevo**.
6. En el campo **País/región**, seleccione **POL**.
7. En el campo **Ciudad** seleccione **Warsaw**.
8. En el campo **Código postal**, ingrese **00-844**.
9. Vaya a **Administración de la organización** > **Organización** > **Entidades jurídicas** y seleccione la entidad jurídica **DEMF**.
10. En la ficha desplegable **Direcciones**, seleccione **Editar**.
11. En el campo **País/región**, seleccione **POL**.
12. En el campo **Código postal**, seleccione **31-111**.
13. En el campo **Calle**, escriba **Statystyczna 22/1**.
14. En el campo **Ciudad** seleccione **Warsaw**.
15. Seleccione **Aceptar**.

## <a name="set-up-a-vat-id-and-an-enterprise-number-code-for-your-company"></a>Configure un ID de IVA y un código de número de empresa para su empresa

### <a name="create-registration-types-for-company-codes"></a>Crear tipos de registro para códigos de empresa

1. Vaya a **Administración de la organización** > **Libreta de direcciones global** > **Tipos de registro** > **Tipos de registro**.
2. En el panel de acciones, seleccione **Nuevo** para crear un tipo de registro para el ID de IVA (código NIP).
3. En el cuadro de diálogo **Escribir detalles del tipo de registro**, en el campo **Nombre**, escriba **NIP**.
4. En el campo **País/región**, seleccione **POL**.
5. Seleccione **Crear**.
6. En el Panel de acciones, seleccione **Nuevo** para crear un tipo de registro para el número de empresa (código Regon).
7. En el cuadro de diálogo **Escribir detalles del tipo de registro**, en el campo **Nombre**, escriba **Regon**.
8. En el campo **País/región**, seleccione **POL**.
9. Seleccione **Crear**.

### <a name="match-the-registration-types-with-registration-categories"></a>Asociar los tipos de registro con las categorías de registro

1. Vaya a **Administración de la organización** > **Libreta de direcciones global** > **Tipos de registro** > **Categorías de registro**.
2. En el Panel de acciones, seleccione **Nuevo** para crear un vínculo entre cada tipo de registro que creó y una categoría de registro.

    - Para el tipo de registro **NIP**, seleccione la categoría de registro **ID de IVA**.
    - Para el tipo de registro **Regon**, seleccione la categoría de registro **ID de empresa (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configure un ID de IVA y un número de empresa para su empresa

1. Vaya a **Administración de la organización** > **Organizaciones** > **Entidades jurídicas**.
2. En la cuadrícula, seleccione **DEMF**.
3. En el Panel de acciones, seleccione **Id. de registro**.
4. En la ficha desplegable **Id. de registro**, seleccione **Agregar**.
5. En el campo **Tipo de registro**, seleccione **NIP**.
6. En el campo **Número de registro**, escriba **1234567890**.
7. Seleccione **Agregar**.
8. En el campo **Tipo de registro**, seleccione **Regon**.
9. En el campo **Número de registro**, escriba **12345678901234**.

### <a name="set-up-a-number-sequence-code"></a>Configurar un código de secuencia numérica

1. Vaya a **Administración de la organización** > **Secuencias numéricas** > **Secuencias numéricas**.
2. En el panel de acciones, en la ficha **Número de secuencia**, en el grupo **Nuevo**, seleccione **Número de secuencia**.
3. En la ficha desplegable **Identificación**, en el campo **Código de secuencia numérica**, ingrese **archivo XML\_**.
4. En la ficha desplegable **Parámetros del ámbito**, en el campo **Ámbito**, seleccione **Empresa**.
5. En el campo **Empresa**, seleccione **DEMF**.
6. En la ficha desplegable **Segmentos**, en el campo **Longitud** campo para el segmento **Alfanumérico**, ingrese **4**.
7. En la ficha desplegable **General**, en la sección **Configuración**, establezca la opción **Continua** en **No**.
8. En la sección **Asignación numérica**, en el campo **Más grande**, ingrese **9999**.

### <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

1. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
2. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Código de** **transacción**, seleccione **11**.
3. En la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Intrastat (PL)**.
4. En el campo **Asignación de formato de informe**, seleccione **Informe de Intrastat**.
5. En la ficha desplegable **Jerarquía de códigos de mercancías**, compruebe que el campo **Jerarquía de categorías** está establecido como **Intrastat**.
6. En la pestaña **Propiedades de país/región**, seleccione **Nueva**.
7. En el campo **País/región de tercero**, seleccione **POL**. A continuación, en el campo **Tipo de país/región**, seleccione **Nacional**.
8. En el campo **País/región de tercero**, seleccione **DEU**. Luego en el campo **Tipo de país/región**, seleccione **EU**.
9. En la pestaña **Agente**, en la ficha desplegable **Agente**, en la sección **Impuesto de ventas**, en el campo **Número de identificación fiscal**, escriba **420000**.
10. En la pestaña **Contacto**, en el campo **Nombre**, introduzca **Manish Chopra**.
11. En el campo **Teléfono**, escriba **425-555-5068**.
12. En el campo **Número de fax**, escriba **425-555-5049**.
13. En el campo **Correo electrónico**, ingrese **manishc@contoso.com**.
14. En la pestaña **Secuencias numéricas**, en el campo **Código de secuencia numérica** para la referencia **Número de archivo XML**, seleccione **Archivo XML\_**.

### <a name="set-up-product-information"></a>Configurar información de productos

1. Vaya a **Gestión de información de productos** > **Productos** > **Productos** **emitidos**.
2. En la cuadrícula, seleccione **D0001**.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione **100 200 30**.
4. En la ficha desplegable **Administrar inventario**, en la sección **Medidas de peso**, en el campo **Peso neto**, introduzca **2**.
5. En el panel Acciones, seleccione **Guardar**.
6. En la cuadrícula, seleccione **D0003**.
7. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione **100 200 30**.
8. En la sección **Origen**, en el campo **País o región**, seleccione **DEU**.
9. En la ficha desplegable **Administrar inventario**, en la sección **Medidas de peso**, en el campo **Peso neto**, introduzca **5**.
10. En el panel Acciones, seleccione **Guardar**.

### <a name="change-the-site-address"></a>Cambiar la dirección del sitio

1. Vaya a **Gestión de almacenes** > **Configurar** > **Almacén** > **Sitios**.
2. En la cuadrícula, seleccione **1**.
3. En la ficha desplegable **Direcciones**, seleccione **Editar**.
4. En el cuadro de diálogo **Editar dirección**, en el campo **País/región**, seleccione **POL**.
5. Seleccione **Aceptar**.

### <a name="set-up-a-transport-method"></a>Configure un método de transporte

1. Cree un método de transporte.

    1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Método de transporte**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el campo **Transporte**, escriba **3**.
    4. En el campo **Descripción**, escriba **Transporte por carretera**.

2. Asigne el nuevo método de transporte a un modo de entrega. De esta manera, configura los valores predeterminados que se utilizan para el método de transporte cuando se selecciona el modo de entrega correspondiente.

    1. Vaya a **Adquisiciones y abastecimiento** > **Configuración** > **Distribución** > **Modos de entrega**.
    2. En la cuadrícula, seleccione **10**.
    3. En la ficha desplegable **Comercio exterior**, en el campo **Transporte**, seleccione **3**.

3. Seleccione el modo de entrega predeterminado para un cliente.

    1. Vaya a **Clientes** > **Clientes** > **Todos los clientes**.
    2. En la cuadrícula, seleccione **DE-016**.
    3. En la ficha desplegable **Factura y entrega**, en la sección **Modo de entrega**, seleccione **10**.

4. Seleccione el modo de entrega predeterminado para un proveedor.

    1. Vaya a **Proveedores** > **Proveedores** > **Todos los proveedores**.
    2. En la cuadrícula, seleccione **DE-001**.
    3. En la ficha desplegable **Factura y entrega**, en la sección **Modo de entrega**, seleccione **10**.

### <a name="set-up-codes-for-terms-of-delivery"></a>Configurar códigos para condiciones de entrega

1. Configure un código de Intrastat para las condiciones de entrega.

    1. Vaya a **Adquisición y abastecimiento** > **Configuración** > **Distribución** > **Condiciones de entrega**.
    2. En la cuadrícula, seleccione **CIF**.
    3. En la ficha desplegable **General**, en el campo **Código intrastat**, escriba **CIF**.

2. Seleccione las condiciones de entrega predeterminadas para un cliente.

    1. Vaya a **Clientes** > **Clientes** > **Todos los clientes**.
    2. En la cuadrícula, seleccione **DE-016**.
    3. En la ficha desplegable **Factura y entrega**, en el campo **Condiciones de entrega**, seleccione **CIF**.

3. Seleccione las condiciones de entrega predeterminadas para un proveedor.

    1. Vaya a **Proveedores** > **Proveedores** > **Todos los proveedores**.
    2. En la cuadrícula, seleccione **DE-001**.
    3. En la ficha desplegable **Factura y entrega**, en el campo **Condiciones de entrega**, seleccione **CIF**.

### <a name="verify-an-eu-customers-tax-exempt-number-code"></a>Comprobar el número de identificación fiscal del cliente de la UE

1. Vaya a **Clientes** > **Clientes** > **Todos los clientes**.
2. En la cuadrícula, seleccione **DE-016**.
3. En la ficha desplegable **Factura y entrega**, en la sección **Impuesto de ventas**, compruebe que el campo **Número de identificación fiscal** está establecido como **DE9012**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Crear un pedido de ventas con un cliente de la UE

1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de ventas**, en la ficha desplegable **Cliente**, en la sección **Cliente**, en el campo **Cuenta de cliente**, seleccione **DE-016**.
4. En la ficha desplegable **General**, en la sección **Dimensiones de almacenamiento**, en el campo **Sitio**, seleccione **1**.
5. En el campo **Almacén**, seleccione **11**.
6. En la pestaña **Dirección**, verifique que el campo **Dirección** está configurado en **Teichgasse 12, Kiel, 24103, DEU**, porque el cliente es de Alemania.
7. Seleccione **Aceptar**.
8. En la pestaña **Encabezado**, en la ficha desplegable **Entrega**, verifique que el campo **Condiciones de entrega** está configurado en **CIF**, y el campo **Modo de entrega** está configurado en **10**.
9. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de ventas**, en el campo **Número de artículo**, seleccione **D0001**. Después, en el campo **Cantidad**, especifique **8**.
10. En la ficha desplegable **Detalles de línea**, en la pestaña **Comercio exterior**, verifique que el campo **Código de transacción** está configurado en **11**, el campo **Mercancía** está configurado en **100 200 30**, y el campo **País/región de origen** está configurado en **POL**.
11. En el panel Acciones, seleccione **Guardar**.
12. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
13. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todos**.
14. En la ficha desplegable **Configuración**, en el campo **Fecha de la factura**, seleccione **10/18/2021** (18 de octubre de 2021).
15. Seleccione **Aceptar** para registrar la factura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transferir la transacción al diario de Intrastat y revisar el resultado

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Transferir**.
3. En el cuadro de diálogo **Intrastat (transferencia)**, en la sección **Parámetros**, configure la opción **Factura del cliente** a **Sí**.
4. Seleccione **Filtro**.
5. En el cuadro de diálogo **Filtro de Intrastat**, en la pestaña **Rango**, seleccione la primera línea y asegúrese de que el campo **Campo** esté establecido en **Fecha**.
6. En el campo **Criterio**, seleccione la fecha actual.
7. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Filtro de Intrastat**.
8. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Intrastat (Transferir)** y revise el resultado. La línea representa el pedido de ventas que creó antes.

    ![Línea que representa el pedido de ventas en la página de Intrastat](media/intrastat_pl_1.png)

9. Seleccione la línea de transacción y luego seleccione la pestaña **General** para ver más detalles.

    ![Detalles del pedido de ventas en la pestaña General de la página de Intrastat](media/intrastat_pl_2.png)

10. En el panel de acciones, seleccione **Salida** > **Informe**.
11. En el cuadro de diálogo **Informe de Intrastat**, en la ficha desplegable **Parámetros**, en la sección **Fecha**, en el campo **Fecha de inicio**, seleccione el primer día del mes actual.
12. En la sección **Opciones de** **exportación**, establezca la opción **Generar archivo** en **Sí**. Después, en el campo **Nombre de archivo**, especifique el nombre necesario.
13. Establezca la opción **Generar informe** en **Sí**. Después, en el campo **Nombre de archivo del informe**, especifique el nombre necesario.
14. En el campo **Dirección**, seleccione **Envíos**.
15. En la sección **Asignación de formato de archivo**, verifique que el campo **Tipo de declaración** está configurado en **Declaración**.
16. En el campo **Ciudad de creación de documentos**, ingrese **Cracovia**.
17. En el campo **Fecha de creación del documento**, seleccione **10/19/2021** (19 de octubre de 2021).
18. En el campo **Numero de documento**, especifique **11**.
19. En el campo **Versión del documento**, especifique **22**.
20. Seleccione **Aceptar** y revise el informe en formato XML que se genera. En la tabla siguiente se muestran los valores en el informe de ejemplo.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nombre del campo</strong></p>
    </td>
    <td>
    <p><strong>Descripción del campo</strong></p>
    </td>
    <td>
    <p><strong>Valor</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Información relativa al documento</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Datos de Deklaracja</p>
    </td>
    <td>
    <p>La fecha en la que se creó el documento.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>La ciudad en la que se creó el documento.</p>
    </td>
    <td>
    <p>Cracovia</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>El número total de artículos.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>El valor estadístico total.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>El valor total de la factura.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>El código de unidad.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>El tipo de declaración.</p>
    </td>
    <td>
    <p>B</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>La versión del documento.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>El número de documento.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="330">
    <p>El mes de referencia.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="330">
    <p>El año de referencia.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="330">
    <p>La dirección del informe.</p>
    </td>
    <td>
    <p>X</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="330">
    <p>El identificador de la declaración.</p>
    </td>
    <td>
    <p>21ISTDEMF-0001</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Información relativa a la empresa</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="330">
    <p>La ciudad en la que se encuentra la empresa.</p>
    </td>
    <td>
    <p>Varsovia</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="330">
    <p>Código Regon de la empresa.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>Código NIP de la empresa.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Código postal de la empresa.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>La calle en la que se encuentra la empresa.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>El nombre de la empresa.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Alemania</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Información sobre el producto</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>El valor estadístico.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Valor de la factura.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Masa neta.</p>
    </td>
    <td>
    <p>16</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>IdKontrahenta</p>
    </td>
    <td>
    <p>Número de IVA del cliente.</p>
    </td>
    <td>
    <p>DE9012</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>El código de mercancía.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Código de transacción.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Las condiciones del modo de entrega.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>El código del país o región de distribución/destino.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>Descripción de las mercancías.</p>
    </td>
    <td>
    <p>Hardware</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Número de artículo.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Información de contacto</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Correo</p>
    </td>
    <td>
    <p>La dirección de correo electrónico del remitente.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Número de fax del remitente.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Número de teléfono del remitente.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Nombre del remitente.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

21. Revise el informe en formato Excel que se genera.

    ![Informe de Intrastat sobre envíos](media/intrastat_pl_3.png)

### <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Proveedores** > **Pedidos de compra** > **Todos los pedidos de compra**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de compra**, en el campo **Cuenta de proveedor**, seleccione **DE-001**.
4. En el campo **Sitio**, seleccione **1**.
5. En el campo **Almacén**, seleccione **11**.
6. Seleccione **Aceptar**.
7. En la pestaña **Encabezado**, en la ficha desplegable **Entrega**, verifique que el campo **Modo de entrega** está configurado en **10**, y el campo **Condiciones de entrega** está configurado en **CIF**.
8. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de compra**, en el campo **Número de artículo**, seleccione **D0003**. Después, en el campo **Cantidad**, especifique **6**.
9. En la ficha desplegable **Detalles de línea**, en la pestaña **Comercio exterior**, verifique que el campo **Código de transacción** está configurado en **11**, el campo **Transporte** está configurado en **3**, el campo **Producto** está configurado en **100 200 30**, y el campo **País/región de origen** está configurado en **DEU**.
10. En el panel de acciones, en la ficha **Compra**, en el grupo **Acciones**, seleccione **Confirmar**.
11. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
12. En el Panel de acciones, seleccione **Valor predeterminado de origen** y luego, en el campo **Cantidad predeterminada para líneas**, seleccione **Cantidad pedida**. A continuación seleccione **Aceptar**.
13. En la ficha desplegable **Encabezado de factura de proveedor**, en la sección **Identificación de factura**, en el campo **Número**, escriba **00010**.
14. En la sección **Fechas de factura**, en el campo **Fecha de la factura**, seleccione la fecha actual. Esta fecha se utilizará para la transferencia Intrastat.
15. En el campo **Recibir fecha de documento**, seleccione **10/18/2021** (18 de octubre de 2021).
16. En el panel de acciones, seleccione **Registrar** para registrar la factura.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Crear una declaración de Intrastat para las llegadas

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Transferir**.
3. En el cuadro de diálogo **Intrastat (Transferir)**, establezca la opción **Factura de proveedor** en **Sí**.
4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat.

    ![Línea que representa el pedido de compra en la página de Intrastat](media/intrastat_pl_4.png)

5. Revise la información de la pestaña **General** de la orden de compra.

    ![Detalles del pedido de compra en la pestaña General de la página de Intrastat](media/intrastat_pl_5.png)

6. En el panel de acciones, seleccione **Salida** > **Informe**.
7. En el cuadro de diálogo **Informe de Intrastat**, en la ficha desplegable **Parámetros**, en la sección **Fecha**, en el campo **Fecha de inicio**, seleccione el primer día del mes actual.
8. En la sección **Opciones de** **exportación**, establezca la opción **Generar archivo** en **Sí**. Después, en el campo **Nombre de archivo**, especifique el nombre necesario.
9. Establezca la opción **Generar informe** en **Sí**. Después, en el campo **Nombre de archivo del informe**, especifique el nombre necesario.
10. En el campo **Dirección**, seleccione **Llegadas**.
11. En la sección **Asignación de formato de archivo**, verifique que el campo **Tipo de declaración** está configurado en **Declaración**.
12. En el campo **Ciudad de creación de documentos**, ingrese **Cracovia**.
13. En el campo **Fecha de creación del documento**, seleccione **10/19/2021** (19 de octubre de 2021).
14. En el campo **Numero de documento**, especifique **11**.
15. En el campo **Versión del documento**, especifique **22**.
16. Seleccione **Aceptar** y revise el informe en formato XML que se genera. En la tabla siguiente se muestran los valores en el informe de ejemplo.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nombre del campo</strong></p>
    </td>
    <td>
    <p><strong>Descripción del campo</strong></p>
    </td>
    <td>
    <p><strong>Valor</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Información relativa al documento</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Datos de Deklaracja</p>
    </td>
    <td>
    <p>La fecha en la que se creó el documento.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>La ciudad en la que se creó el documento.</p>
    </td>
    <td>
    <p>Cracovia</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>El número total de artículos.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>El valor estadístico total.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>El valor total de la factura.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>El código de unidad.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>El tipo de declaración.</p>
    </td>
    <td>
    <p>B</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>La versión del documento.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>El número de documento.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="332">
    <p>El mes de referencia.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="332">
    <p>El año de referencia.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="332">
    <p>La dirección del informe.</p>
    </td>
    <td>
    <p>C</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="332">
    <p>El identificador de la declaración.</p>
    </td>
    <td>
    <p>21ISTDEMF-0002</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Información relativa a la empresa</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="332">
    <p>La ciudad en la que se encuentra la empresa.</p>
    </td>
    <td>
    <p>Varsovia</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="332">
    <p>Código Regon de la empresa.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>Código NIP de la empresa.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Código postal de la empresa.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>La calle en la que se encuentra la empresa.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>El nombre de la empresa.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Alemania</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Información sobre el producto</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>El valor estadístico.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Valor de la factura.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Masa neta.</p>
    </td>
    <td>
    <p>30</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzenia</p>
    </td>
    <td>
    <p>El código del país o región de origen.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransportu</p>
    </td>
    <td>
    <p>Código del modo de transporte.</p>
    </td>
    <td>
    <p>3</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>El código de mercancía.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Código de transacción.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Las condiciones del modo de entrega.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>El código del país o región de distribución/destino.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>Descripción de las mercancías.</p>
    </td>
    <td>
    <p>Hardware</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Número de artículo.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Información de contacto</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Correo</p>
    </td>
    <td>
    <p>La dirección de correo electrónico del remitente.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Número de fax del remitente.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Número de teléfono del remitente.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Nombre del remitente.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

17. Revise el informe en formato Excel que se genera.

    ![Informe de llegadas de Intrastat](media/intrastat_pl_6.png)
