---
title: Compatibilidad de la característica de impuestos para pedidos de transferencia
description: Este tema explica la compatibilidad con la nueva función de impuestos para los pedidos de transferencia mediante el servicio de cálculo de impuestos.
author: Kai-Cloud
ms.date: 10/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f68a3d7ed4384fe5a97f1e59903e3191df6b741
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647722"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Compatibilidad de la característica de impuestos para pedidos de transferencia

[!include [banner](../../includes/banner.md)]

Este tema proporciona información sobre el cálculo de impuestos y la integración de la contabilización en los pedidos de transferencia. Esta funcionalidad le permite configurar el cálculo de impuestos y la contabilización en pedidos de transferencia para transferencias de existencias. Según las regulaciones del impuesto sobre el valor añadido (IVA) de la Unión Europea (UE), las transferencias de existencias se consideran suministro intracomunitario y adquisiciones intracomunitarias.

Para configurar y utilizar esta funcionalidad, debe completar tres pasos principales:

1. **Configuración de RCS:** En el Servicio de configuración regulatoria, configure la función de impuestos, los códigos de impuestos y la aplicabilidad de los códigos de impuestos para la determinación del código de impuestos en los pedidos de transferencia.
2. **Configuración Dynamics 365 Finance**: en Finance , habilite la característica **Impuesto en pedido de transferencia**, configure los parámetros del servicio de cálculo de impuestos para el inventario y configure los parámetros de impuestos básicos.
3. **Configuración de inventario:** estableca la configuración de inventario para transacciones de pedidos de transferencia.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Configurar RCS para transacciones de pedidos de transferencia e impuestos

Siga estos pasos para configurar el impuesto involucrado en un pedido de transferencia. En el ejemplo que se muestra aquí, el pedido de transferencia es de Países Bajos a Bélgica.

1. En la página **Características fiscales**, en la pestaña **Versiones**, seleccione la versión preliminar de la función y luego seleccione **Editar**.

2. En la página **Configuración de características fiscales**, en la pestaña **Códigos de impuestos**, seleccione **Agregar** para crear nuevos códigos de impuestos. Para este ejemplo, se crean tres códigos de impuestos: **NL-Exento**, **BE-RC-21** y **BE-RC+21**.

    - Cuando un pedido de transferencia se envía desde un almacén en Países Bajos, se aplica el código impositivo exento de IVA de Países Bajos (**NL-Exento**).
      
        Cree el código de impuestos **NL-Exento**.
        1. Seleccione **Agregar** e introduzca **NL-Exento** en el campo **Código de impuesto**.
        2. Seleccione **Por importe neto** en el campo **Componente fiscal**.
        3. Seleccione **Guardar**.
        4. Seleccione **Agregar** en la tabla **Tipo**.
        5. Estableza **Está exento** a **Sí** en la sección **General**.
        6. En el campo **Código de exención**, introduzca **EC**.

    - Cuando se recibe un pedido de transferencia en un almacén de Bélgica, el mecanismo de inversión del cargo se aplica mediante los códigos de impuestos **BE-RC-21** y **BE-RC+21**.
        
        Cree el código de impuestos **BE-RC-21**.      
        1. Seleccione **Agregar** e introduzca **BE-RC-21** en el campo **Código de impuesto**.
        2. Seleccione **Por importe neto** en el campo **Componente fiscal**.
        3. Seleccione **Guardar**.
        4. Seleccione **Agregar** en la tabla **Tipo**.
        5. Introduzca **-21** en el campo **Tipo impositivo**.
        6. Establezca **Es cargo invertido** a **Sí** en la sección **General**.
        7. Seleccione **Guardar**.
        
        Cree el código de impuestos **BE-RC+21**.
        1. Seleccione **Agregar** e introduzca **BE-RC-21** en el campo **Código de impuesto**.
        2. Seleccione **Por importe neto** en el campo **Componente fiscal**.
        3. Seleccione **Guardar**.
        4. Seleccione **Agregar** en la tabla **Tipo**.
        5. Introduzca **21** en el campo **Tipo impositivo**.
        6. Seleccione **Guardar**.

3. Defina el grupo de impuestos.
    1. Seleccione **Administrar columnas** y luego seleccione el campo de línea **Grupo de impuestos**.
    2. Seleccione **->** y, a continuación, seleccione **Aceptar**.
    3. Seleccione **Agregar** para agregar un grupo de impuestos.
    4. En la columna **Grupo de impuestos**, introduzca **AR-UE** y luego seleccione el código de exención **NL-Exento**.
    5. Seleccione **Agregar** para agregar un grupo de impuestos.
    6. En la columna **Grupo de impuestos**, introduzca **RC-VAT** y luego seleccione los códigos de impuestos **BE-RC-21** y **BE-RC+21**.
4. Defina el grupo de impuestos de artículos.
    1. Seleccione **Administrar columnas** y luego seleccione el campo de línea **Grupo de impuestos de artículos**.
    2. Seleccione **->** y, a continuación, seleccione **Aceptar**.
    3. Seleccione **Agregar** para agregar un grupo de impuestos de artículos.
    4. Introduzca **FULL** en la columna **Grupo de impuestos de artículos**. Seleccione los códigos de impuestos **BE-RC-21**, **BE-RC+21** y **NL-Exento**.
5. Defina la aplicabilidad de los grupos de impuestos.

    1. Seleccione **Administrar columnas** y, a continuación, seleccione las columnas que se deben utilizar para crear la tabla de aplicabilidad.

        > [!NOTE]
        > Asegúrese de agregar las columnas **Procesos de negocio** y **Direcciones de impuestos** a la tabla. Ambas columnas son esenciales para la funcionalidad de los impuestos en pedidos de transferencia.

    2. Agregue reglas de aplicabilidad. No deje en blanco el campo **Grupo de impuestos**.
        
        Agregue una nueva regla para el envío de pedidos de transferencia.
        1. Seleccione **Agregar** en la tabla **Reglas de aplicabilidad**.
        2. En el campo **Procesos de negocio**, seleccione **Inventario** para que la regla sea aplicable a un pedido de transferencia.
        3. En el campo **Enviar desde país o región**, introduzca **NLD**.
        4. En el campo **Enviar a país o región**, introduzca **BEL**.
        5. En el campo **Dirección fiscal**, seleccione **Salida** para que la regla sea aplicable al envío del pedido de transferencia.
        6. En el campo **Grupo de impuestos**, seleccione **AR-EU**.
        
        Agregue otra regla para la recepción de pedidos de transferencia.
        
        1. Seleccione **Agregar** en la tabla **Reglas de aplicabilidad**.
        2. En el campo **Procesos de negocio**, seleccione **Inventario** para que la regla sea aplicable a un pedido de transferencia.
        3. En el campo **Enviar desde país o región**, introduzca **NLD**.
        4. En el campo **Enviar a país o región**, introduzca **BEL**.
        5. En el campo **Dirección fiscal**, seleccione **Entrada** para que la regla sea aplicable a la recepción de pedidos de transferencia.
        6. En el campo **Grupo de impuestos**, seleccione **RC-VAT**.

6. Defina la aplicabilidad de los grupos de impuestos de artículos.

    1. Seleccione **Administrar columnas** y, a continuación, seleccione las columnas que se deben utilizar para crear la tabla de aplicabilidad.
    2. Agregue reglas de aplicabilidad. No deje en blanco el campo **Grupo de impuestos de artículos**.
        
        Agregue una nueva regla para el envío y la recepción de pedidos de transferencia.
        1. En la página **Reglas de aplicabilidad**, seleccione **Agregar**.
        2. En el campo **Procesos de negocio**, seleccione **Inventario** para que la regla sea aplicable para el pedido de transferencia.
        3. En el campo **Grupo de impuestos de artículos**, seleccione **FULL**.
7. Complete y publique la nueva versión de la característica fiscal.


## <a name="set-up-finance-for-transfer-order-transactions"></a>Configurar Finance para transacciones de pedidos de transferencia

Siga estos pasos para habilitar y configurar impuestos para pedidos de transferencia.

1. En Finance, vaya a **Espacios de trabajo** > **Administración de características**.
2. En la lista, busque y seleccione la característica **Impuesto en pedido de transferencia** y, a continuación, seleccione **Habilitar ahora** para activarla.

    > [!IMPORTANT]
    > La característica **Impuesto en pedido de transferencia** depende completamente del servicio de cálculo de impuestos. Por lo tanto, solo se puede activar después de haber instalado el servicio de cálculo de impuestos.

    ![Impuesto en la característica de pedido de transferencia.](../media/image7.png)

3. Habilite el servicio de cálculo de impuestos y seleccione el proceso de negocio **Inventario**.

    > [!IMPORTANT]
    > Debe completar este paso para cada entidad jurídica de Finance donde desee que el servicio de cálculo de impuestos y la funcionalidad para impuestos en pedidos de transferencia estén disponibles.

    1. Vaya a **Impuesto** > **Configuración** > **Configuración de impuestos** > **Parámetros de cálculo de impuestos**.
    2. En el campo **Procesos de negocio**, seleccione **Inventario**.

4. Verifique que el mecanismo de cargo inverso esté configurado. Vaya a **Contabilidad general** \> **Configuración** \> **Parámetros** y luego, en la pestaña **Invertir cargo**, verifique que la opción **Habilitar cargo inverso** esté configurada en **Sí**.

    ![Habilitar la opción de cargo inverso.](../media/image9.png)

5. Verifique que los códigos de impuestos relacionados, los grupos de impuestos, los grupos de impuestos de artículos y los números de registro de IVA se hayan configurado en Finance de acuerdo con la guía del servicio cálculo de impuestos.
6. Configure una cuenta de tránsito provisional. Este paso es necesario solo cuando el impuesto que se aplica a un pedido de transferencia no es aplicable a un mecanismo de exención de impuestos o de cargo invertido.

    1. Vaya a **Impuestos** > **Configuración** > **Impuestos** > **Grupos de registro**.
    2. En el campo **Tránsito provisional**, seleccione una cuenta contable.

       ![Selección de una cuenta de tránsito provisional.](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Configurar el inventario básico para transacciones de pedidos de transferencia

Siga estos pasos para configurar el inventario básico para habilitar las transacciones de pedidos de transferencia.

1. Cree sitios de salida de envío y de llegada de envío para sus almacenes en diferentes países o regiones, y agregue la dirección principal para cada sitio.

    1. Vaya a **Gestión de almacenes** > **Configurar** > **Almacén** > **Sitios**.
    2. Seleccione **Nuevo** para crear el sitio que luego asignará a un almacén.
    3. Repita el paso 2 para el resto de sitios que deba crear.

    > [!NOTE]
    > Uno de los sitios que cree debe tener por nombre **Tránsito**. En los pasos posteriores de este procedimiento, asignará este sitio al almacén de tránsito, de modo que los asiento de inventario relacionados con los impuestos se puedan registrar en las transacciones de "enviar" y "recibir" para los pedidos de transferencia. La dirección del sitio de tránsito es irrelevante para el cálculo de impuestos. Por tanto, no se puede dejar en blanco.

    ![Configuración de sitios.](../media/image11.png)

2. Cree almacenes de envío, tránsito y destino. Cualquier información de dirección que se mantenga en un almacén anulará la dirección del sitio durante el cálculo de impuestos.

    1. Vaya a **Gestión de almacenes** > **Configurar** > **Almacén** > **Almacenes**.
    2. Seleccione **Nuevo** para crear un almacén y asignarlo al sitio correspondiente.
    3. Repita el paso 2 para crear un almacén para cada sitio, según sea necesario.

       ![Configuración de almacenes.](../media/image12.png)

    > [!NOTE]
    > Para un almacén de envío, se debe seleccionar un almacén de tránsito en el campo **Almacén de tránsito** para transacciones de pedidos de transferencia.
    >
    > ![Selección de un almacén de tránsito.](../media/image13.png)

3. Verifique que la configuración de contabilización de inventario esté configurada para transacciones de pedidos de transferencia.

    1. Vaya a **Gestión de inventarios** > **Configurar** > **Registro** > **Registro**.
    2. En la pestaña **Inventario**, verifique que una cuenta contable esté configurada para la contabilización de **Problema de inventario** y **Recibo de inventario**.

        ![Configuración de incidencias de inventario y contabilización de recibos de inventario.](../media/image14.png)

    3. Verifique que una cuenta contable esté configurada para la contabilidad **Pagadera entre unidades**.

        ![Configuración de contabilización pagadera entre unidades.](../media/image15.png)

    4. Verifique que una cuenta contable esté configurada para contabilización **Recibible entre unidades**.

        ![Configuración de contabilización recibible entre unidades.](../media/image16.png)
        
        
  [!INCLUDE[footer-include](../../../includes/footer-banner.md)]
