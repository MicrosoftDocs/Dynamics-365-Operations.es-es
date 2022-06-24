---
title: Espacio de trabajo de automatización de facturas de proveedor
description: Este artículo explica cómo configurar el espacio de trabajo relacionado con las facturas de proveedores que muestra la información que está disponible a través de Microsoft Power BI.
author: abruer
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2020-09-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2b74731a3283badad941e567e85f8a1644f6ad18
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865812"
---
# <a name="vendor-invoice-automation-workspace"></a>Espacio de trabajo de automatización de facturas de proveedor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artículo explica cómo configurar el espacio de trabajo relacionado con las facturas de proveedores que muestra la información que está disponible a través de Microsoft Power BI. La información de factura de proveedor en este espacio de trabajo se filtra para usuarios específicos y se muestra en un formato gráfico.

## <a name="overview"></a>Información general

El espacio de trabajo **Automatización de facturas de proveedor** muestra la información relacionada con el procesamiento de facturas de proveedor. Este espacio de trabajo incluye un vista **Mi trabajo** y una página **Análisis de todas las empresas**. La vista **Mi trabajo** muestra mosaicos de resumen, cuadrículas de transacciones con proveedores y la información de proveedor relacionada. La página **Análisis de todas las empresas** utiliza la funcionalidad de Microsoft Power BI para mostrar visualizaciones relacionadas con las facturas de proveedor.

## <a name="set-up-the-workspace-to-show-power-bi-content"></a>Configurar el espacio de trabajo para mostrar contenido de Power BI

Debe completar esta configuración para poder mostrar los datos en visualizaciones de Power BI en el espacio de trabajo **Automatización de facturas de proveedor**.

1. En el espacio de trabajo **Administración de características**, filtre la lista para encontrar la característica **Automatización de factura de proveedor**.
3. Seleccione **Habilitar ahora**.
4. Para asegurarse de que las facturas se puedan procesar de principio a fin sin necesidad de intervención manual, configure un flujo de trabajo de factura de proveedor. Para configurar un flujo de trabajo, vaya a **Proveedores \> Configuración \> Flujos de trabajo de proveedores**.
5. Vaya **Proveedores \> Configuración \> Parámetros de proveedores** y seleccione la pestaña **Automatización de factura de proveedor**. Para obtener más información, consulte [Opciones de configuración para la automatización de factura de proveedor](vnd-invoice-set-up-options.md).
6. Establezca la opción **Enviar automáticamente facturas importadas al flujo de trabajo** en **Sí**.
7. Si los recibos de productos deben coincidir automáticamente, establezca la opción **Asociar automáticamente las recepciones de productos con las líneas de facturas** en **Sí**.
8. Revise las demás configuraciones opcionales y configúrelas de acuerdo con los requisitos de su organización.
9. Vaya a **Administración del sistema \> Configuración \> Parámetros del sistema** para establecer **Divisa del sistema** y **Tipo de cambio del sistema**.
10. Vaya a **Contabilidad general \> Configuración \> Libro mayor** y establezca **Divisa de contabilidad** y **Tipo de cambio**.
11. Vaya a **Contabilidad general \> Divisas \> Tipos de cambio de divisa** e introduzca los tipos de cambio entre la divisa de la transacción y la divisa de contabilidad, y entre la divisa de contabilidad y la divisa del sistema.
12. Vaya a **Administración del sistema \> Configuración \> Almacén de entidades** y busque **Medida de automatización de factura de proveedor**. Seleccione **Actualizar**.

Para poder ver la información que se muestra en el espacio de trabajo debe tener el rol de seguridad Administrador de proveedores o Funcionario de proveedores.

## <a name="my-work-view"></a>Vista Mi trabajo

### <a name="company-selection"></a>Selección de empresa

Cuando la característica **Automatización de facturas de proveedor** está activada, aparece un campo **Empresa** en la parte superior del espacio de trabajo. La selección del campo **Empresa** afecta a toda la información que se muestra en el espacio de trabajo. De forma predeterminada, la vista muestra información de la empresa en la que inició sesión. Al seleccionar una empresa diferente en el campo **Empresa**, puede mostrar información de esa empresa en el espacio de trabajo. Puede seleccionar un icono del espacio de trabajo para ir a la página relacionada en la empresa seleccionada.

### <a name="summary-tiles"></a>Iconos de resumen

Los iconos de la sección **Resumen de facturas pendientes** de la vista **Mi trabajo** ofrecen una visión general del estado de sus facturas de proveedor. Puede ver los diarios que aún no se han registrado y las facturas retenidas. Además, hay cuatro iconos asociados con la característica Automatización de facturas de proveedores:

- **Es necesaria una coincidencia de recepción manual**
- **Validación de coincidencia no correcta**
- **Facturas no enviadas al flujo de trabajo**
- **Facturas no importadas**

(Estos cuatro mosaicos requieren que la característica Automatización de facturas de proveedores esté activada en **Administración de características**).

Para usar el icono **Recuperar facturas de proveedores**, la característica debe estar activada en **Parámetros de proveedores**. Vaya a **Proveedores \> Parámetros de proveedores** y, a continuación, en la pestaña **Factura**, establezca la opción **Permitir recuperación de factura de proveedor** en **Sí**.

Cuando la característica está activada, también verá en el espacio de trabajo tres iconos agrupados en una sección llamada **Diarios**. Los iconos se titulan **Diarios**, **Diarios asignados a mí** y **Grupo de facturas**. 

La información de la sección **Resumen de facturas pendientes** es para la empresa establecida como empresa predeterminada para su inicio de sesión.

### <a name="creating-new-records"></a>Creando registros nuevos

Para crear un nuevo registro de factura, seleccione **Nuevo** y, a continuación, seleccione uno de los siguientes tipos de registro de la lista:

- Factura del proveedor
- Diario de facturas
- Diario de facturas global
- Registro de facturas
- Aprobación de factura

Tenga en cuenta que el registro que crea se basa en el filtro de la empresa, no en la empresa en la que inició sesión. Por ejemplo, ha iniciado sesión en la empresa **UMSF**, pero el filtro de empresa está configurado para **GBSI**. En este caso, si seleccione **Nuevo** y después seleccione un tipo de registro en la lista, el registro se crea en la empresa GBSI.

### <a name="documents-not-invoiced-grids"></a>Cuadrículas de documentos no facturados

La sección **Documentos no facturados** contiene cuadrículas que muestran documentos que esperan facturas de proveedores.

La cuadrícula **Abrir pedidos de compra** muestra todos los pedidos de compra que aún no se han facturado por completo. Puede usar el botón **Factura ahora** para crear una factura de proveedor para un pedido de compra. Puede usar el botón **Factura de anticipo ahora** para crear una factura de anticipo para un pedido de compra.

La cuadrícula **Recepciones de productos** muestra todas las transacciones de recepción de compra que aún no se han facturado por completo. Puede usar el botón **Factura ahora** para crear una factura de proveedor para un pedido de compra.

La cuadrícula **Facturas de proveedor pendientes** muestra todas las facturas de proveedor que no se han enviado al sistema de flujo de trabajo. Puede usar el campo **Buscar** y/o el filtro de la empresa para buscar una factura de proveedor específica. Puedes usar el botón **Editar** para editar una transacción que aparece en la cuadrícula.

En la cuadrícula **Buscar pedido de compra** puede utilizar el campo **Buscar** para buscar un pedido de compra específico.

### <a name="related-information"></a>Información relacionada

Puede ver información sobre las facturas registradas mediante los vínculos a la derecha del espacio de trabajo. Estos vínculos incluyen **Facturas de proveedor abiertas**, **Diario de facturas** e **Historial de facturas y detalles coincidentes**. En la sección **Proveedores** puede acceder a una lista filtrada que muestra todos los proveedores que están en espera, o puede utilizar el vínculo **Todos los proveedores**. Los enlaces **Todas las órdenes de compra** y **Pagos anticipados abiertos** también están disponibles.

### <a name="analytics--all-companies-page"></a>Página Análisis de todas las empresas

Cuando la opción **Enviar automáticamente facturas importadas al flujo de trabajo** está establecida en **Sí** en la página **Parámetros de proveedores**, puede ver análisis de automatización. La página **Análisis de todas las empresas** proporciona métricas importantes, como las facturas de proveedores que están aprobadas por el aprobador y por la empresa. Esta página contiene cinco páginas de informe. Una página ofrece una visión general, y las otras ocho proporcionan información detallada acerca de las métricas de automatización de proveedores.

En la tabla siguiente se muestran las visualizaciones que se encuentran disponibles en cada página de informe.

| Página de informes                    | Visualizaciones |
|--------------------------------|----------------|
| Visión general de factura de proveedor        | <ul><li>Facturas de proveedor pendientes en automatización en divisa del sistema</li><li>Facturas que no se pudieron importar</li><li>Facturas en flujo de trabajo</li><li>Las facturas sin contacto duran 30 días</li><li>Total de facturas automatizadas en los últimos 30 días</li><li>Saldo de facturas abiertas en la divisa del sistema</li><li>Razones de los errores en los últimos 30 días</li><li>Porcentaje de facturas registradas que se procesaron automáticamente</li><li>Días para procesar una factura</ul></li> |
| Estado de automatización              | <ul><li>Las facturas sin contacto duran 30 días</li><li>Las facturas sin contacto duran 30 días por empresa</li><li>Las facturas sin contacto duran 30 días por grupo de proveedores</li><li>Porcentaje de facturas registradas que se procesaron automáticamente</li><li>Días para procesar una factura</li></ul> |
| Facturas que no se pudieron importar | <ul><li>Facturas que no se pudieron importar</li><li>Facturas que no se pudieron importar por empresa</li></ul> |
| Razones del error de automatización | <ul><li>Facturas con error</li><li>Facturas con error por empresa</li><li>Facturas con error por grupo de proveedores</li></ul> |
| Estado de flujo de trabajo                | <ul><li>Facturas en flujo de trabajo</li><li>Instancias de flujo de trabajo de factura de proveedor</li><li>Asignación por aprobador</li><li>Flujo de trabajo de factura de proveedor por empresa</li><li>Promedio días en el flujo de trabajo por responsable</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
