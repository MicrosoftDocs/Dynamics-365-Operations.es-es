---
title: Complemento Hoja de ruta (Carta de Porte)
description: Este artículo explica cómo configurar y enviar albaranes y órdenes de transferencia que incluyen el complemento Hoja de ruta (Carta de Porte).
author: AdamTrukawka
ms.date: 03/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: atrukawk
ms.search.validFrom: 2021-08-31
ms.dyn365.ops.version: 10.0.23
ms.search.form: ''
ms.openlocfilehash: 51b665bacfd76c9983cacebb2cba4cd8875474e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267120"
---
# <a name="waybill-carta-de-porte-complement"></a>Complemento Hoja de ruta (Carta de Porte)

[!include [banner](../includes/banner.md)]

Este artículo ofrece información sobre cómo configurar y enviar albaranes y órdenes de transferencia que incluyen el complemento Hoja de ruta (Carta de Porte). A partir del 1 de octubre de 2021, el complemento Hoja de ruta (Carta de Porte) es obligatorio para los contribuyentes que transportan bienes y mercancías en el territorio nacional.

Para generar el complemento Hoja de ruta (Carta de Porte) en documentos de factura electrónica (CFDI), introduzca la información de transporte en la página **Detalles de transporte**. Puede abrir esta página desde cualquiera de los documentos empresariales siguientes:

- **Un registro de pedido de ventas:** estos pedidos de venta incluyen pedidos de venta para el proyecto. Vaya a **Clientes** \> **Pedidos** \> **Todos los pedidos de ventas**. En el panel de acciones, seleccione **Recoger y empaquetar**.
- **Una orden de transferencia:** Vaya a **Gestión del inventario** \> **Pedidos de salida** \> **Orden de transferencia**. En el panel Acciones, seleccione **Enviar**.
- **Un envío:** vaya a **Administración del inventario** \> **pedidos salientes** \> **Envíos**.
- **Requisitos del proyecto**: vaya a **Administración y contabilidad de proyectos** \> **Tareas de elementos** \> **Requisitos del proyecto**. En el panel de acciones, seleccione **Administrar**.

> [!NOTE]
> Puede ver la información de transporte en las páginas de lista **CFDI: facturas electrónicas de albarán** y **CFDI: facturas electrónicas de transferencia de inventario**.

## <a name="transportation-details-page"></a>Página de detalles de transporte

Esta sección proporciona información sobre los campos que son obligatorios en la página **Detalles de transporte**. En la siguiente ilustración, se han resaltado los campos obligatorios.

![Página de detalles de transporte.](media/latam-mx-transportation-details.png)

> [!NOTE]
> A partir de la versión 10.0.23 (compilación 10.0.1037.160) la siguiente funcionalidad está disponible:
>
> - En la ficha desplegable **Cargando** de la página **Detalles de transporte**, introduzca un valor en los campos **Fecha y hora de carga** y **Nombre** (dirección de envío). Si deja el campo **Fecha y hora de carga** en blanco, el sistema selecciona el valor de la transacción. Si deja el campo **Nombre** (dirección de envío) en blanco, el sistema selecciona el valor de la dirección del almacén o sitio.
> - Seleccione un valor en el campo **Peso por unidad**. Antes de la versión 10.0.23, la unidad de peso **XAG** era un valor fijo en un archivo XML. Si deja este campo en blanco, el atributo correspondiente en el archivo XML se completa con **XAG**.
> - Además de los datos de dos conductores, puede completar los actores de transporte seleccionando **Actores del transporte** en el Panel de acciones. Sin embargo, primero debe completar el catálogo de actores yendo a **Administración de la organización** \> **Configuración** \> **Aclaración SAT** \> **Transporte**.

### <a name="general-fasttab"></a>Ficha desplegable General

Los campos siguientes son obligatorios:

- **Tipo de permiso**
- **Id. de permiso de transporte**
- **Distancia**
- **Horas**

### <a name="vehicle-fasttab"></a>Ficha desplegable Vehículo

En la sección **Vehículo**, los siguientes campos son obligatorios:

- **Número de registro**
- **Configuración de transporte de motores federal**
- **Año de modelo**

En la sección **Seguro**, los siguientes campos son obligatorios:

- **Cuenta del proveedor**
- **Número de póliza**

En la sección **Conductor**, los siguientes campos son obligatorios:

- **Número de registro** o **Número RFC**
- **Carné de conducir**
- **País/región**

En la sección **Remolque**, configure los siguientes campos si se utiliza un remolque en el transporte de mercancías:

- **Número de registro de tráiler**
- **Tipo de remolque**

> [!NOTE]
> Si hay un remolque adicional, configure los campos en la sección **Remolque adicional**. Si hay un conductor adicional, configure los campos en la sección **Conductor adicional**.

Todos los campos para un camión, remolque y conductor, excepto el campo **Configuración federal de transporte motorizado**, se pueden rellenar manualmente o utilizando información de activos fijos y registros de trabajadores.

## <a name="posting-packing-slips-and-shipping-transfer-orders-that-include-the-waybill-carta-de-porte-complement"></a>Registro de albaranes y órdenes de transferencia de envío que incluyan el complemento Hoja de ruta (Carta de Porte)

Si selecciona **Habilitar albarán de CFDI** en la página **Registro de albarán** o **Envío**, el parámetro **Generar nota de transporte** se selecciona automáticamente. Sin embargo, puede borrar este parámetro cuando lo necesite. Si se selecciona **Generar nota de transporte**, el complemento Hoja de ruta (Carta de Porte) se incluirá en el archivo XML.

## <a name="setup"></a>Configurar

### <a name="catalogs"></a>Catálogos

Siga estos pasos para configurar los catálogos de las autoridades fiscales mexicanas (SAT) para agregar información a los campos **Tipo de permiso**, **Tipo de remolque** y **Configuración federal de transporte motorizado**.

1. Vaya a **Administración de la organización** \> **Configuración** \> **Factura electrónica** \> **Clasificación SAT** \> **Transporte**.
2. En la página **Transporte**, cree los siguientes catálogos SAT:

    - Para el campo **Tipo de remolque**, el catálogo SAT es **c\_SubTipoRem**.
    - Para el campo **Tipo de permiso**, el catálogo SAT es **c\_TipoPermiso**.
    - Para el campo **Configuración federal de transporte motorizado**, el catálogo SAT es **c\_ConfigAutotransporte**.

### <a name="permission-number"></a>Número de permiso

1. Vaya a **Administración de la organización** \> **Organizaciones** \> **Entidades jurídicas**.
2. En la ficha desplegable **Permisos de transporte**, en el campo **Id. de permiso de transporte**, introduzca el número de permiso que proporciona la Secretaría de Comunicaciones y Transportes de México (SCT).

### <a name="items"></a>Artículos

1. Vaya a **Gestión de información de productos** \> **Productos** \> **Todos los productos emitidos**.
2. Seleccione y abra el registro de artículo con el que desee trabajar.
3. En la ficha desplegable **Administrar inventario**, establezca los campos **Peso neto** y **Peso de tara** si son obligatorios. El campo **Peso bruto** se establece automáticamente.

### <a name="distance-and-time"></a>Distancia y tiempo

Puede definir información sobre la distancia y el tiempo de transporte entre las ubicaciones de entrega del envío por adelantado. Luego, cuando los usuarios introducen la distancia y el tiempo de transporte en la página **Detalles de transporte**, pueden ahorrar tiempo seleccionando valores existentes en lugar de tener que calcular nuevos valores. Siga estos pasos para configurar la información sobre la distancia y el tiempo de transporte entre los puntos de transporte.

1. Vaya a **Administración de la organización** \> **Configurar** \> **Factura electrónica**.
2. En la página **Factura electrónica**, introduzca o seleccione lugares de transporte.
3. Ingrese el tiempo y la distancia entre los dos puntos. Los puntos de transporte son todos los puntos de envío y entrega. Los puntos pueden tener diferentes tipos. A continuación, encontrará algunos ejemplos:

    - Cliente 
    - Almacén
    - Frontera (si las mercancías se entregan en la frontera)
    - Otra

> [!NOTE] 
> Puede omitir este procedimiento. Sin embargo, en ese caso, debe introducir manualmente la distancia y el tiempo de transporte en la página **Detalles de transporte**.

### <a name="fixed-assets"></a>Activos fijos

Si su empresa ha implementado el módulo **Activos fijos**, introduzca información en el registro de activos fijos para vehículos o remolques. Esta información se puede utilizar en la página **Detalles de transporte**. Esta información es necesaria para el complemento de Hoja de ruta (Carta de Porte).

1. Vaya a **Activos fijos** \> **Activos fijos** \> **Activos fijos**.
2. En la ficha desplegable **Información técnica**, establezca los siguientes campos:

    - En la sección **Clasificación SAT**:

        - **Tipo de vehículo**
        - **Configuración federal de transporte motorizado** (solo para camiones)
        - **Tipo de remolque**

    - En la sección **Modelo**:

        - **Año de modelo**
        - **Número de serie**

### <a name="workers"></a>Trabajadores

Siga estos pasos para introducir números de identificación fiscal (RFC), números de registro e información de licencia para conductores. Antes de comenzar, asegúrese de que los tipos de identificación se hayan configurado en **Recursos humanos** \> **Configuración** \> **Tipos de identificación**.

1. Vaya a **Recursos humanos** \> **Trabajadores** \> **Empleados/ Contratistas/Trabajadores**.
2. En el panel de acciones, seleccione **Informacion personal** \> **Números de identificación**.
3. En el campo **Tipo de identificación**, seleccione el tipo correspondiente. Por ejemplo, para un tipo de identificación de permiso de conducir, seleccione **Permiso de conducir**.

## <a name="hazardous-materials"></a>Materiales peligrosos

Si la empresa transporta materiales peligrosos, habilite la característica **Información de productos de materiales peligrosos y documentación de envío** en el espacio de trabajo **Administración de características**. Para más información, consulte [Resumen de administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Después de habilitar la función, siga estos pasos para introducir información adicional sobre materiales peligrosos.

1. Vaya a **Gestión de información de productos** \> **Productos** \> **Todos los productos emitidos**.
2. Abra el registro de artículo y luego, en la ficha desplegable **Administrar inventario**, configure la opción **Materiales peligrosos** en **Sí**.
3. En el panel de acciones, seleccione **Administrar inventario** \> **Cumplimiento**.
4. En la página **Artículos de materiales peligrosos**, en el encabezado, establezca el campo **Código de regulación**.
5. En la ficha desplegable **Gestión de materiales**, en la sección **Grupo de embalaje**, establezca el campo **Grupo de embalaje**.

> [!NOTE]
> Para seleccionar valores para los campos **Código de regulación** y **Grupo de embalaje**, primero complete las tablas **Regulación de materiales peligrosos** y **Grupos de embalaje de materiales peligrosos**, de acuerdo con los catálogos SAT **c\_MaterialPeligroso** y **c\_TipoEmbalaje** que se encuentran en **Gestión de información de producto** \> **Configuración** \> **Documentación de envío de materiales peligrosos**.
>
> A partir de la versión 10.0.23 (compilación 10.0.1037.149), puede trabajar con la opción **Mostrar estado peligroso** al enviar el atributo **matrialPeligrosso** como salida en un archivo XML. Si la opción **Mostrar estado peligroso** está establecida en **Sí**, puede configurar la opción **Materiales peligrosos** a **Sí**.

![Página de artículo de materiales peligrosos.](media/latam-mx-hazardous2.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
