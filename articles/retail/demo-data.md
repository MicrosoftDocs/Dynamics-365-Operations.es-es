---
title: "Los diseños de pantalla de datos de demostración en MPOS/CPOS"
description: "Este tema proporciona información sobre los diseños de pantalla que se incluyen con el conjunto de datos de demostración para las experiencias de punto de venta (PDV) en Microsoft Dynamics 365 for Retail."
author: zlinster
manager: AnnBe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: zlinster
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 563c89c75e2136294f8f841bec094c2aeb85d580
ms.openlocfilehash: b758b48230e8d9fabdccbe267a6ad6b9e74af0ff
ms.contentlocale: es-es
ms.lasthandoff: 10/17/2017

---

# <a name="demo-data-screen-layouts-in-mposcpos"></a>Diseños de pantalla de datos de demostración en MPOS/CPOS

[!include[banner](includes/banner.md)]

Este tema proporciona información sobre los diseños de pantalla que se incluyen con el conjunto de datos de demostración para las experiencias de punto de venta (PDV) en Microsoft Dynamics 365 for Retail.

## <a name="overview"></a>Información general

Los diseños de pantalla de ejemplo que se incluyen con datos de demostración de Retail proporcionan contenido que está optimizado para distintos segmentos de venta minorista, roles del trabajador en la tienda, y dispositivos. Un solo diseño puede contener varias combinaciones de y tamaños de diseño de cuadrículas de botones, para ayudar a garantizar la cobertura cuando los trabajadores se desplazan entre dispositivos y estaciones. En este tema se destacan las diferencias entre estos diseños, las operaciones que proporcionan y las experiencias totales que brindan.

![Diseños de datos de demostración interdispositivo](../retail/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a>Anatomía de un identificador de diseño de pantalla

Para encontrar diseños de pantalla en Retail, vaya a **Venta minorista** > **Configuración del canal** > **Configuración de PDV** > **PDV** > **Diseños de pantalla**.

![Página de diseños de pantalla en Retail](../retail/media/demo-screen-layouts-fig-2-1.png)

Los id. de diseño de pantalla pueden tener un máximo de 10 caracteres. El identificador es una cadena que constas de tres datos, en este orden:

1. Compañía
2. Versión del diseño
3. Rol

### <a name="company"></a>Compañía

| Carta | Compañía         |
|--------|-----------------|
| C      | Adventure Works |
| F      | Fabrikam        |
| C      | Contoso         |

### <a name="layout-version"></a>Versión del diseño

| Número de versión | Descripción                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| 3              | La versión base que admite varios tamaños de pantalla para distintos dispositivos y relaciones de aspecto |
| 3.1            | La versión base que tiene soporte adicional para el panel **Productos recomendados**        |

### <a name="persona"></a>Rol

| Abreviatura | Rol       | Contenido |
|--------------|---------------|----------|
| CSH          | Cajero       | Los diseños de cajero incluyen todas las operaciones relacionadas con transacciones, como pedidos de cliente, devoluciones, descuentos, anulaciones y tarjetas regalo. Estos diseños también incluyen tareas diarias para administración de inventario, como comprobaciones de precios, consultas de inventario y los recuentos de existencias. La administración básica de turnos también se proporciona para importes iniciales, turnos suspendidos y reloj de tiempo. |
| MGR          | Encargado de tienda | Los diseños de Encargado de tienda incluyen todas las operaciones relacionadas con transacciones que se encuentren en los diseños de cajero pero también incluyen anulaciones de impuestos. Estos diseños también incluyen tareas diarias para administración de inventario, como comprobaciones de precios, consultas de inventario y los recuentos de existencias. Se suministra gestión de turnos para iniciar, suspender y cerrar turnos. Además, los diseños incluyen las operaciones de caja registradora para entradas, retiradas, declaraciones por forma de pago e ingresos seguros y bancarios. Por último, estos diseños incluye acceso a informes de rendimiento, y permiten imprimir informes X y Z. |
| STK          | Reponedor   | Los diseños de Reponedor se optimizan para la gestión de inventario. Incluyen acceso a tareas diarias para comprobaciones de precio, consultas de inventario, picking y recepción, recuentos de existencias, y desensamblado del kit. Estos diseños también proporcionan operaciones básicas de turnos para turnos suspendidos y reloj de tiempo. Aunque estos diseños están pensados principalmente para tareas de oficina administrativa, los reponedores tienen las mismas operaciones que los cajeros para las pantallas de transacción. |

### <a name="example-layout"></a>Diseño de ejemplo

A continuación se ofrece un ejemplo de un identificador de diseño de pantalla para la empresa Fabrikam, versión de diseño 3, y el rol Encargado de tienda:

F3MGR

La ilustración siguiente muestra un ejemplo de la pantalla de bienvenida para un encargado de tienda de Fabrikam.

![Pantalla de bienvenida para el encargado de tienda de Fabrikam](../retail/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a>Tamaños de diseño

### <a name="full-vs-compact-layouts"></a>Diseños completo y compactos

Un diseño de pantalla puede tener configuraciones de dispositivos completos y compactos. Por tanto, se puede asignar a un usuario un diseño monopantalla que funcionará con diferentes tamaños y factores de formulario en la tienda.

- **Modern POS - Completo** - Normalmente, los diseños completos se emplean mejor para pantallas grandes como monitores de PC o tabletas. Los usuarios pueden seleccionar los elementos de la interfaz de usuario que el diseño incluye, especificar el tamaño y la posición de esos elementos y configurar sus propiedades detalladas. Los diseños completos admiten la configuración vertical y horizontal.
- **Modern POS - Compact** – Normalmente, los diseños compactos se emplean mejor para teléfonos o tabletas pequeñas. Las posibilidades de diseño en los dispositivos compactos son limitadas. Los usuarios pueden configurar las columnas y los campos para los paneles de totales y de recepción.

### <a name="screen-resolutions-that-are-provided"></a>Resoluciones de pantalla que se ofrecen

En la tabla siguiente se muestran los tamaños de diseño que se ofrecen para resoluciones de pantalla habituales.

| Tipo de diseño | Resolución | Relación de aspecto | Pantalla de destino          |
|-------------|------------|--------------|-------------------------|
| Compactar\*   | 480 × 853  | 16:9         | Teléfonos                  |
| Completo        | 1024 × 768 | 4:3          | Tabletas                 |
| Completo\*      | 1280 × 720 | 16:9         | Tabletas                 |
| Completo        | 1366 × 768 | 16:9         | Tabletas, pantallas más grandes |
| Completo        | 1440 × 960 | 3:2          | Tabletas, pantallas más grandes |

\* Estos tamaños de diseño adicionales solo están disponibles en los diseños de Adventure Works y de Fabrikam.


>[!TIP]
> PDV selecciona automáticamente los tamaños de diseño, en función del tamaño más cercano disponible para la resolución de pantalla de la ventana de la aplicación actual. Para buscar el identificador de diseño de pantalla y la resolución de diseño que se usan actualmente, en Retail Modern POS (MPOS) o Retail Cloud POS (CPOS), abra la página **Valores** , y busque en la sección **Información sobre la sesión**. También puede ver la resolución real de la ventana para la aplicación o el marco del explorador actual. Cuando tenga esta información, puede buscar el origen del contenido de diseño en Retail yendo a **Configuración de canal** > **Configuración de PDV** > **PDV** > **Diseños de pantalla**.


![Diseños de pantalla y resoluciones/tamaños del diseño en Retail y PDV](../retail/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a>Empresas y marcas

Cada compañía ficticia está dirigida a un segmento de venta minorista distinto e incluye catálogos de productos que están adaptados al mercado de la empresa. Cada empresa tiene una marca visual única que acompaña a sus productos. Los elementos de marca incluyen el color de acento, tema oscuro o claro y fotos que acompañan que proporcionan experiencias realistas.

### <a name="company-segment-and-visual-characteristics"></a>Segmento de empresa y características visuales

| Compañía         | Ubicación | Segmento        | Énfasis | Tema |
|-----------------|----------|----------------|--------|-------|
| Adventure Works | Seattle  | Artículos deportivos | Azul   | Oscuro  |
| Fabrikam        | Houston  | Moda        | Verde  | Claro |
| Contoso         | Boston   | Electrónica    | Rojo    | Oscuro  |


>[!NOTE]
> Adventure Works y Fabrikam son las dos marcas insignia. Contoso está disponible, pero no se han proporcionado todos los diseños.


Las siguientes ilustraciones muestran ejemplos de la página de bienvenida y la página de transacción para las tres empresas ficticias.

### <a name="adventure-works"></a>Adventure Works

![Página de bienvenida de datos de demostración para Adventure Works](../retail/media/demo-screen-layouts-fig-4-1a.png)

![Página de transacción de datos de demostración para Adventure Works](../retail/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a>Fabrikam

![Página de bienvenida de datos de demostración para Fabrikam](../retail/media/demo-screen-layouts-fig-4-2a.png)

![Página de transacción de datos de demostración para Fabrikam](../retail/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a>Contoso

![Diseños de datos de demostración para Contoso](../retail/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a>Matriz de inicio de sesión del usuario

Se han proporcionado usuarios para los distintos diseños de pantalla. Mediante la tabla siguiente, debe poder obtener acceso a cualquiera de las pantallas. Inicie sesión mediante un identificador de operador adecuado.

| Compañía         | Id. de diseño de pantalla | Rol          | Id. de operador           |
|-----------------|------------------|---------------   |------------------------|
| Adventure Works | A3MGR            | Encargado de tienda    | 000154, 000137, 000073 |
| Adventure Works | A3CSH            | Cajero          | 000150, 000175, 000165 |
| Adventure Works | A3STK            | Reponedor      | 000155, 000181, 000152 |
| Fabrikam        | F3MGR            | Encargado de tienda    | 000160, 000168, 000163 |
| Fabrikam        | F3CSH            | Cajero          | 000161, 000113, 000114 |
| Fabrikam        | F3STK            | Reponedor      | 000164, 000112, 000123 |
| Contoso         | C3MGR            | Encargado de tienda    | 000100, 000111         |
| Contoso         | C3CSH            | Cajero          | 000110, 000120         |
| Contoso         | No aplicable   | Reponedor      | No aplicable         |


>[!TIP]
> Para obtener los mejores resultados, active un registro en la ubicación de tienda correspondiente, y establezca la empresa como la empresa del rol que planea usar al iniciar sesión. De esta manera, usted ayuda a garantizar que el perfil visual y las imágenes de marca están alineadas en toda la experiencia. Por ejemplo, si está interesado en ver un diseño Fabrikam para un cajero, debe activar un registro en la tienda de Houston.


<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail > Channel setup > POS setup > POS > Images**. -->

<!-- ![Images in Dynamics 365 for Retail](../retail/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../retail/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->

