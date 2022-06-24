---
title: Certificación de origen USMCA
description: Esta función le permite imprimir los documentos de certificación de origen requeridos por el Acuerdo Estados Unidos-México-Canadá (USMCA).
author: Weijiesa
ms.date: 10/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 2a87e1aa27085f1b4821d27cece782dffbcd2096
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851373"
---
# <a name="usmca-certification-of-origin"></a>Certificación de origen USMCA

[!include [banner](../includes/banner.md)]

Esta función le permite imprimir los documentos de certificación de origen requeridos por el Acuerdo Estados Unidos-México-Canadá (USMCA).

El *documento de certificación de origen USMCA* contiene los elementos de datos mínimos requeridos para la declaración. Algunos elementos de datos pueden rellenarse previamente antes de imprimir, mientras que otros deben rellenarse manualmente después de la impresión. Para obtener un trato arancelario preferencial, el documento debe estar cumplimentado y en posesión del importador al momento de realizar la declaración. El documento puede ser completado por el importador, exportador o productor.

Puede imprimir el documento para un solo envío desde la página de lista **Todos los envios** o de la página **Detalles del envío**.

Solo se puede acceder al documento cuando el país de la dirección principal de la entidad legal es Estados Unidos.

Dependiendo de la selección de impresión del documento, el documento se puede completar previamente con datos de su sistema. Es posible cambiar o agregar datos al documento impreso exportando el documento impreso a un formato editable, como Microsoft Word. Después de la exportación, puede aplicar los cambios necesarios antes de realizar una declaración.

## <a name="turn-on-the-usmca-feature"></a>Activar la característica USMCA

Antes de poder usar la característica USMCA debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo**: *Administración de transporte*
- **Nombre de la función:** *Documento de certificación de origen USMCA*

## <a name="document-content"></a>Contenido del documento

La certificación de origen de USMCA contiene los siguientes elementos de datos:

- Elementos de dirección
- Papel de la parte certificadora
- Envío único
- Facturas
- Período abierto
- Detalles del artículo
- Firma del certificador
- Número de páginas

Para obtener más información sobre cada uno de estos elementos y cómo se encuentran sus valores, consulte las secciones restantes de este artículo.

## <a name="print-a-usmca-certification-of-origin-document"></a>Imprimir un documento de certificación de origen USMCA

Para imprimir un documento de certificación de origen USMCA para un envío, haga lo siguiente:

1. Realice una de las acciones siguientes:
    - Vaya a **Gestión de transporte > Envíos > Todos los envíos** y seleccione el envío para el que desea imprimir el documento.
    - Abra la página **Detalles del envío** para el envío que desea imprimir el documento (hay varias formas de llegar aquí, incluso desde la página **Todos los envios**).
1. En el panel de acciones, abra la pesetaña **Envíos** y, desde el grupo **Impresión**, seleccione **Certificado de origen USMCA**.
1. Aparece el cuadro de diálogo **Certificado u origen**. Realice los ajustes descritos en las siguientes subsecciones y luego seleccione **Aceptar** para generar el documento.
1. Se abre una vista previa del documento. Utilice los comandos proporcionados en el Panel de acciones para imprimir o exportar el documento según sea necesario.

### <a name="certifying-party"></a>Parte certificadora

Utilice la lista desplegable **Parte certificadora** para identificar el tipo de parte que está imprimiendo el documento. Especifique si la parte certificadora es el *Exportador*, *Exportador y Productor*, *Productor* o *Importador*; o déjelo en blanco si la parte certificadora no es ninguna de estas. La opción que seleccione determina lo que se imprime en las secciones de dirección del documento.

La **Parte certificadora** que elija se incluirá en el documento impreso.

El documento se puede imprimir para envíos entrantes y salientes. Seleccione *Importador* como **Parte certificadora** solo para envíos entrantes.

La siguiente tabla describe los tipos de información que se incluyen en el documento según la **Parte certificadora** que elija.

| Parte&nbsp;certificadora | Descripción |
|---|---|
| *\[En blanco\]* | Agrega los siguientes detalles al documento:<ul><li>**Detalles del certificador**: Utiliza los detalles de la dirección del almacén de envío, si está disponible; de lo contrario, utiliza la dirección del sitio de envío, si está disponible; de lo contrario, utiliza la dirección de la entidad jurídica (empresa) seleccionada en Supply Chain Management.</li><li>**Detalles del exportador**: Blanco</li><li>**Detalles del productor**: Blanco</li><li>**Detalles del importador**: Blanco</li><ul>|
| *Exportador* | Agrega los siguientes detalles al documento:<ul><li>**Detalles del certificador**: Utiliza los detalles de la dirección del almacén de envío, si está disponible; de lo contrario, utiliza la dirección del sitio de envío, si está disponible; de lo contrario, utiliza la dirección de la entidad jurídica (empresa) seleccionada en Supply Chain Management.</li><li>**Detalles del exportador**: Utiliza los detalles de la dirección de la entidad jurídica.</li><li>**Detalles del productor**: Blanco</li><li>**Detalles del importador**: Utiliza la cuenta de factura para el pedido de ventas relacionado.</li><ul>|
| *Exportador y productor* | Agrega los siguientes detalles al documento:<ul><li>**Detalles del certificador**: Utiliza los detalles de la dirección del almacén de envío, si está disponible; de lo contrario, utiliza la dirección del sitio de envío, si está disponible; de lo contrario, utiliza la dirección de la entidad jurídica (empresa) seleccionada en Supply Chain Management.</li><li>**Detalles del exportador**: Utiliza los detalles de la dirección de la entidad jurídica.</li><li>**Detalles del productor**: Utiliza los detalles de la dirección de la entidad jurídica.</li><li>**Detalles del importador**: Utiliza la cuenta de factura para el pedido de ventas relacionado.</li><ul>|
| *Importador* | Agrega los siguientes detalles al documento:<ul><li>**Detalles del certificador**: Utiliza los detalles de la dirección del almacén de envío, si está disponible; de lo contrario, utiliza la dirección del sitio de envío, si está disponible; de lo contrario, utiliza la dirección de la entidad jurídica (empresa) seleccionada en Supply Chain Management.</li><li>**Detalles del exportador**: Blanco</li><li>**Detalles del productor**: Blanco</li><li>**Detalles del importador**: Utiliza los detalles de la dirección de la entidad jurídica.</li><ul>|
| *Productor* | Agrega los siguientes detalles al documento:<ul><li>**Detalles del certificador**: Utiliza los detalles de la dirección del almacén de envío, si está disponible; de lo contrario, utiliza la dirección del sitio de envío, si está disponible; de lo contrario, utiliza la dirección de la entidad jurídica seleccionada en Supply Chain Management.</li><li>**Detalles del exportador**: Blanco</li><li>**Detalles del productor**: Utiliza los detalles de la dirección de la entidad jurídica.</li><li>**Detalles del importador**: Blanco</li><ul>|

### <a name="has-various-producers"></a>Tiene varios productores

La lista desplegable **Parte certificadora** controla el texto que se utilizará para los detalles del productor en el documento. Elija una opción de las siguientes:

- *Varios productores* - Imprime el texto "Varios" en los detalles del productor.
- *Disponible bajo pedido* - Imprime el texto "Disponible a solicitud de las autoridades importadoras" en los detalles del productor.

Cuando **Parte certificadora** se establece en *Exportador y Productor* o *Productor*, entonces la configuración **Tiene varios productores** se anula y los detalles de la dirección del productor serán los mismos que los del certificador.

### <a name="blanket-period"></a>Período abierto

Utilice las configuraciones **Período general desde** y **Período general para** para establecer un período general, durante el cual el documento cubrirá varios envíos de mercancías idénticas, aunque el documento se imprima para un solo envío. Puede establecer las fechas del período general sin ninguna restricción y se agregará al documento. También puede dejar estas configuraciones en blanco o configurarlas en el pasado.

### <a name="is-single-shipment"></a>Es envío único

En el cuadro de diálogo **Certificado de origen**, establezca **Es un solo envío** en uno de los siguientes:

- *Sí* - Agrega "Envío único: Sí" junto al número de factura.
- *No* - No agrega nada.

## <a name="other-information-included-in-the-document"></a>Otra información incluida en el documento

Además de los elementos opcionales que seleccione mediante el cuadro de diálogo **Certificado u origen**, el documento de certificación de origen de USMCA incluirá la información y los campos personalizados resumidos en las siguientes subsecciones. Parte de esta información debe ingresarse manualmente después de generar el documento.

### <a name="invoice-number"></a>Número de factura

Los ID de las facturas de venta relacionadas con los envíos se imprimen en el documento independientemente del período global. Los números de las facturas se imprimen independientemente de la selección **Es un solo envío**.

### <a name="item-details"></a>Detalles del artículo

El documento proporciona varias secciones que enumeran detalles específicos del artículo, que son:

- **Número de SKU**: Imprime el número de artículo del producto publicado.

- **Descripción**: Imprime la descripción o el nombre del producto lanzado. Si existe una descripción en el idioma del usuario, se imprime. Si no existe tal descripción, se imprime el nombre en el idioma del usuario. Si ese nombre no existe, se imprime el nombre del artículo.

- **Clasificación arancelaria del sistema armonizado (SA)**: Imprime el Arancel Armonizado asociado al producto. Puede configurar estos horarios yendo a **Gestión de transporte \> Preparar \> Estándar de transporte \> Listas de tarifas armonizadas**.

- **Criterio de origen:** Debe ingresar datos manualmente en esta sección la primera vez que publique el documento.

- **País de origen:** Imprime el país de origen, que se aplica yendo a **Gestión de información de producto \> Preparar \> Cumplimiento del producto \> País de origen** (ver también [País de origen](../pim/country-of-origin.md)). El código ISO para el país de origen se imprime según el país o región de destino en la dirección de entrega del envío y el artículo. Si no se ha configurado ningún dato del país de origen, este valor vuelve a la configuración encontrada en **Producto lanzado \> Comercio Exterior \> Origen**. Si aún no se encuentran datos del país de origen, debe ingresar manualmente el país de origen después de generar el documento.

### <a name="certifier-signature-and-date"></a>Firma y fecha del certificador

Debe ingresar esto manualmente después de generar el documento.

### <a name="consists-of-number-of-pages"></a>Consta de número de páginas

El usuario que firma la certificación debe ingresar manualmente el número de páginas (para verificación) después de generar el documento.

### <a name="page-numbers"></a>Números de página

Página actual y número de páginas impresas en la parte inferior del documento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]