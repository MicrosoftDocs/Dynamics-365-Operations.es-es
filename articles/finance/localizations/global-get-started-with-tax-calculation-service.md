---
title: Introducción al cálculo de impuestos
description: Este tema explica cómo configurar el cálculo de impuestos.
author: wangchen
ms.date: 05/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3f8aa791cee1926afe6be347331d47902a3b7304
ms.sourcegitcommit: f4dc09601bceb5cdc88ee184ce7c8f369e3e6e86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "6060572"
---
# <a name="get-started-with-the-tax-calculation-preview"></a>Comenzar con el cálculo de impuestos (versión preliminar)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tema proporciona información sobre cómo comenzar con el cálculo de impuestos. Primero le guía por los pasos de configuración en Microsoft Dynamics Lifecycle Services (LCS), Servicio de Configuración Regulatoria (RCS), Dynamics 365 Finance y Dynamics 365 Supply Chain Management. A continuación, revisa el proceso común para utilizar las funcionalidades de cálculo de impuestos en las transacciones de Finance y Supply Chain Management.

La configuración consta de cuatro pasos principales:

1. En LCS, instale el cálculo de impuestos.
2. En RCS, configure la función de cálculo de impuestos. Esta configuración no es específica de una entidad jurídica. Se puede compartir entre entidades legales en Finance y Supply Chain Management.
3. En Finance y Supply Chain Management, configure los parámetros del cálculo de impuestos por entidad jurídica.
4. En Finance y Supply Chain Management, cree transacciones, como pedidos de venta, y utilice el cálculo de impuestos para determinar y calcular los impuestos.

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos:

- Tiene acceso a su cuenta LCS y ha implementado un proyecto LCS con un ambiente de Nivel 2 (o superior) que ejecuta Dynamics 365, versión 10.0.18 o posterior con [KB4616360](https://fix.lcs.dynamics.com/Issue/Details?kb=4616360&bugId=568738&dbType=3&qc=1f1c04ff39adad74ef871f539e8d73e14c1893ef7cc4b6e3f7d5c5864ec2781a) o posterior.
- Dispone de acceso a su cuenta de RCS.
- Se ha puesto en contacto con Microsoft para habilitar la distribución en su ambiente implementado de Finance o Supply Chain Management.

## <a name="set-up-tax-calculation-in-lcs"></a>Configurar el cálculo de impuestos en LCS

1. Iniciar sesión en [LCS](https://lcs.dynamics.com)
2. Complete la configuración para la integración de Microsoft Power Platform. Para obtener más información, consulte [Información general de complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Seleccione uno de sus entornos de no producción implementados y luego seleccione **Instalar un nuevo complemento**.
4. Seleccione **Cálculo de impuestos (versión preliminar)**.
5. Lea y acepte los términos y condiciones, y luego seleccione **Instalar**.

## <a name="set-up-tax-calculation-in-rcs"></a>Configurar el cálculo de impuestos en RCS

Los pasos de esta sección no están relacionados con una entidad jurídica específica. Debe completar este procedimiento solo una vez, y puede completarlo en cualquier entidad jurídica en RCS.

1. Inicie sesión en [RCS](https://marketing.configure.global.dynamics.com/).
2. En Finance, en el espacio de trabajo **Informes electrónicos**, agregue un nuevo proveedor de configuración. Utilice el nombre de su empresa como el nombre del proveedor. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Seleccione el proveedor de configuración que acaba de crear y luego seleccione **Establecer como activo**.
4. Seleccione el proveedor de configuración **Microsoft** y luego **Repositorios**.
5. En el campo **Tipo**, seleccione **Global**.
6. Seleccione **Abrir**.
7. Vaya a **Modelo de datos fiscales**, expanda el árbol de archivos y luego seleccione **Configuración fiscal**.
8. Seleccione la última versión y luego seleccione **Importar**.
9. Vuelva al espacio de trabajo **Características de globalización (versión preliminar)**, seleccione **Características**, elija el mosaico **Cálculo de impuestos** y finalmente **Agregar**.
10. Seleccione uno de los siguientes tipos de característica:

    - **Nueva caracteristica**: cree una configuración de característica con el contenido en blanco.
    - **Basada en una característica existente**: cree una función a partir de una función existente y copie el contenido de la configuración de la función existente.

11. Introduzca un nombre y una descripción de la característica, y luego seleccione **Crear característica**.

    Una vez creada la característica, se crea automáticamente una versión de borrador.

12. Seleccione la versión preliminar de la característica y luego elija **Editar**. Se rellena la página **Configuración de cálculo de impuestos**.
13. Seleccione **Crear configuración**. Debería ver la versión de configuración que importó en el paso 8.

    Microsoft proporciona una configuración de impuestos predeterminada para el complemento de cálculo de impuestos. Esta configuración cubre la mayoría de los requisitos de los comportamientos de cálculo de impuestos. Se actualizará en función de los comentarios del mercado. Si debe ampliar la configuración para cumplir requisitos específicos, consulte [Cómo construir extensiones en el servicio tributario](./tax-service-add-data-fields-tax-integration-by-extension.md) para obtener información sobre cómo generar y seleccionar su propia configuración de impuestos.

    Después de seleccionar **Versión de configuración**, aparecen varias pestañas adicionales:

    - **Códigos de impuestos** - Esta pestaña es obligatoria. Se utiliza para mantener datos maestros para códigos de impuestos. Todos los códigos de impuestos que se crean en esta pestaña se sincronizan automáticamente con Finance al habilitar la versión actual de la configuración de la característica de impuestos en la entidad jurídica.
    - **Aplicabilidad de impuestos** - Esta pestaña es obligatoria. Se utiliza para definir una matriz que determina el código de impuestos, el grupo de impuestos y el grupo de impuestos del artículo. El código de impuestos que se determina se utiliza para calcular el importe del impuesto. Los valores de los campos **Código de impuestos**, **Grupo fiscal** y **Grupo de impuestos de artículo** se devuelven a Finance.
    - **Aplicabilidad del número de registro de impuestos del cliente**: esta pestaña es opcional. Si tiene varios números de registro de impuestos para un cliente, el cálculo de impuestos puede determinar automáticamente el número de registro de impuestos correcto. En la matriz de esta pestaña, usted define las reglas para tomar la decisión. De lo contrario, Finance y Supply Chain Management continuarán usando el número de registro de impuestos predeterminado en los documentos imponibles para las transacciones de ventas.
    - **Aplicabilidad del número de registro de impuestos del proveedor**: esta pestaña es opcional. Si tiene varios números de registro de impuestos para un proveedor, el cálculo de impuestos puede determinar automáticamente el número de registro de impuestos correcto. En la matriz de esta pestaña, usted define las reglas para tomar la decisión. De lo contrario, Finance y Supply Chain Management continuarán usando el número de registro de impuestos predeterminado en los documentos imponibles para las transacciones de compras.
    - **Aplicabilidad del código de lista** - Esta pestaña es opcional. Puede ayudar a determinar automáticamente el valor del campo **Código de lista** mediante reglas más flexibles y configurables. En la matriz de esta pestaña, usted puede definir las reglas para tomar la decisión. De lo contrario, Finance y Supply Chain Management continuarán usando el código predeterminado en los documentos imponibles para las transacciones de ventas.

14. En la pestaña **Códigos de impuestos**, seleccione **Agregar** e introduzca el código de impuestos y una descripción.
15. Seleccione **Componente de impuestos**. El componente de impuestos es un grupo de métodos de cálculo de impuestos que se definieron en la versión anterior de la configuración de impuestos seleccionada. Están disponibles los siguientes componentes de impuestos:

    - Por importe neto
    - Por importe bruto
    - Por cantidad
    - Por margen
    - Impuesto sobre impuesto

16. Seleccione **Guardar**. Hay más campos disponibles, según el componente de impuestos que haya seleccionado.
17. Utilice las siguientes opciones para identificar la naturaleza del código fiscal:

    - Está exento
    - Es IVA de importación
    - Es cargo invertido
    - Excluir del cálculo de la cantidad base

    Para un escenario de IVA de importación, configure un código impositivo único que tenga un tipo impositivo positiva y márquelo como **Es IVA de importación**.

    Para un escenario de cargo invertido, configure dos códigos de impuestos, uno de los cuales tiene un tipo impositivo positivo y el otro tiene un tipo impositivo negativo pero el mismo valor absoluto del tipo. Marque el código impositivo negativo como **Es cargo invertido**. Para obtener más información sobre la solución de cargo invertido en Finance, consulte [Mecanismo de cargo invertido para esquema de IVA/GST](emea-reverse-charge.md).
    
    Para algunos tipos de impuestos que deben excluirse en el cálculo del importe de la base imponible para transacciones con precio incluido, como los derechos de aduana en algunos países, seleccione la casilla **Excluir del cálculo de la cantidad base**.

    Mantenga los tipos impositivos y los límites de importe impositivo para este código impositivo.

18. Repita los pasos del 14 al 17 para agregar el resto de códigos de impuesto necesarios.
19. En la pestaña **Aplicabilidad de códigos de impuestos**, seleccione las columnas necesarias para determinar el código de impuestos correcto y, a continuación, seleccione **Agregar**.
20. Introduzca o seleccione valores para cada columna. Los campos **Código de impuestos**, **Grupo fiscal** y **Grupo de impuestos de artículo** se entregarán a esta matriz.
21. Repita los pasos del 19 al 20 para configurar la aplicabilidad de los números de registro de impuestos de clientes, los números de registro de impuestos de proveedores y los códigos de lista.
22. Haga clic en **Guardar** y, a continuación, cierre la página.
23. Seleccione **Cambiar estado** \> **Completada**. Una vez que el estado cambia a **Completo**, la versión ya no se puede editar.
24. Seleccione **Cambiar estado** \> **Publicar**. Esta versión de la configuración de la característica de impuestos se enviará al repositorio global y será visible para cada entidad legal en Finance.

## <a name="dynamics-365-setup"></a>Configuración de Dynamics 365

Después de completar la configuración en RCS, como se describe en la sección anterior, tendrá una versión publicada de la característica de impuestos. Siga estos pasos para configurar el cálculo de impuestos en Finance.

La configuración en esta sección se realiza por entidad jurídica. Debe configurarlo para cada entidad jurídica para la que desee habilitar el cálculo de impuestos en Finance.

1. En Finance, vaya a **Impuesto** \> **Configuración** \> **Configuración de impuestos** \> **Configuración del cálculo de impuestos (versión preliminar)**.
2. En la pestaña **General**, establezca los campos siguientes:

    - **Habilitar el cálculo de impuestos**: seleccione esta casilla para habilitar el cálculo de impuestos para la entidad jurídica. Si el complemento de cálculo de impuestos no está habilitado para la entidad jurídica actual, la entidad jurídica seguirá utilizando el motor de impuestos existente para determinar y calcular los impuestos.
    - **Configuración de características**: seleccione una configuración y versión de característica de impuestos publicada para la entidad jurídica. Para obtener más información sobre cómo configurar y completar una característica de impuestos publicada, consulte la sección anterior de este tema.
    - **Procesos de negocio** - Seleccione los procesos comerciales para habilitar.
    - **Habilitar ajuste del código de impuestos**: establezca esta opción en **Sí** para habilitar los ajustes del código de impuestos en la página de impuestos.

3. En la pestaña **Cálculo**, defina la regla de redondeo esperada para la entidad jurídica.
4. En la pestaña **Manejo de errores**, defina el método de manejo de errores esperado para la entidad jurídica. Hay tres opciones disponibles para cada código de resultado:

    - N.º
    - Advertencia
    - Error

5. Guarde la configuración.
6. Repita los pasos 1 a 5 para cada entidad jurídica adicional.

## <a name="transaction-processing"></a>Procesamiento de transacciones

Una vez que haya completado todos los procedimientos de configuración, puede usar el cálculo de impuestos para determinar y calcular los impuestos en Finance. Los pasos para procesar transacciones siguen siendo los mismos. Las siguientes transacciones son compatibles con Finance, versión 10.0.18:

- Proceso de ventas

    - Presupuesto de ventas
    - Pedido de ventas
    - Confirmación
    - Lista de selección
    - Traslado
    - Factura de ventas
    - Factura rectificativa
    - Pedido de devolución
    - Cargo de encabezado
    - Cargo de línea

- Proceso de compra

    - Pedido de compra
    - Confirmación
    - Lista de recepciones
    - Recepción de producto
    - Factura de compra
    - Cargo de encabezado
    - Cargo de línea
    - Factura rectificativa
    - Pedido de devolución
    - Solicitud de compra
    - Cargo de línea de solicitud de compra
    - Solicitud de presupuesto
    - Cargo de encabezado de solicitud de presupuesto
    - Cargo de línea de solicitud de presupuesto

- Proceso de inventario

    - Pedido de transferencia: envío
    - Pedido de transferencia: recepción
