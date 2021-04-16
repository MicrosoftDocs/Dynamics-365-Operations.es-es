---
title: Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce
description: Este tema explica cómo configurar la compra en línea, la recogida en la tienda (BOPIS) en un ambiente de evaluación de Microsoft Dynamics 365 Commerce después de que se haya aprovisionado.
author: rubendel
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 219504da62fd4637ed01f9acbab32f873cef81b0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795964"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a>Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tema explica cómo configurar la compra en línea, la recogida en la tienda (BOPIS) en un ambiente de evaluación de Microsoft Dynamics 365 Commerce después de que el entorno se haya aprovisionado.

## <a name="prerequisite"></a>Requisito previo

Complete los procedimientos de este tema solo después de que se haya aprovisionado y configurado su entorno de evaluación de Commerce. Para obtener información sobre cómo aprovisionar y configurar su entorno, consulte [Aprovisionar un entorno de evaluación de Dynamics 365 Commerce](provisioning-guide.md) y [Configurar un entorno de evaluación de Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).

Después de que su entorno de Commerce se haya aprovisionado y configurado de principio a fin, puede usar este tema para habilitar escenarios BOPIS.

## <a name="configure-the-pos"></a>Configurar el PDV

### <a name="configure-modern-pos"></a>Configurar Modern POS

Los escenarios BOPIS que implican un pago con tarjeta de crédito requieren una estación de hardware. La estación de hardware se ha incluido en el programa Modern POS para clientes Windows y Android. Si está utilizando Cloud POS o Modern POS para iOS, el cliente del punto de venta (PDV) debe estar emparejado con una estación de hardware compartida. Este tema explica cómo configurar BOPIS para clientes Windows y Android. Para obtener más información sobre cómo configurar una estación de hardware compartida, consulte [Configurar e instalar la estación de hardware de Retail](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).

1. Vaya a **Venta minorista y comercio \> Configuración de canal \> Configuración de PDV \> Registros**.
2. Seleccione el registro **SANFRAN-5** y luego seleccione **Editar**.
3. Cambie el valor del campo **Perfil de hardware** de **HW002** a **HW001** y luego seleccione **Guardar**.
4. Para sincronizar los cambios, vaya **Venta minorista y comercio \> TI de venta minorista y comercio \> Programación distribución**.
5. Seleccione la programación de distribución **1090** y en el panel de acciones, seleccione **Ejecutar ahora**.
6. Seleccione **Sí** y luego **Aceptar** para iniciar la sincronización de datos. 

### <a name="install-modern-pos"></a>Instalar Modern POS

1. Vaya a **Venta minorista y comercio \> Configuración de canal \> Configuración de PDV \> Dispositivos**.
2. Seleccione el dispositivo **SANFRANCIS-5**.
3. En el panel de acciones, seleccione **Descargar** y **Archivo de configuración**.
4. Seleccione **Descargar** y luego **Retail Modern POS**. 
5. Cuando descargue el archivo **ModernPOSSetup.exe**, seleccione **Abrir archivo**.

    ![Abrir archivo](./dev-itpro/media/PAYMENTS/openfile.png)

6. Seleccione **Siguiente** para ejecutar el proceso de instalación. Cuando se complete la instalación, seleccione **Cerrar**.

### <a name="activate-modern-pos"></a>Activar Modern POS

1. En el escritorio de Windows, seleccione el botón **Inicio** e introduzca **Retail Modern POS**.
2. Seleccione la aplicación **Retail Modern POS** para iniciar la activación.
3. Seleccione **Siguiente**. Los campos **URL del servidor**, **ID del dispositivo** y **Número de registro** deben preestablecerse utilizando la información del archivo de configuración que descargó en el procedimiento anterior.
4. Seleccione **Activar**.
5. Aparece un cuadro de diálogo de autenticación. Seleccione la cuenta que usa la dirección de correo electrónico que anteriormente estaba asociada con el trabajador **000713 - Andrew Collette**.

    > [!NOTE]
    > Si aún no ha asociado a un trabajador con su identidad, la activación no tendrá éxito. En este caso, siga los pasos de la sección "Asociar un trabajador con su identidad" en el tema [Configurar un entorno de evaluación de Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).
    
6. Cuando se le solicite que permita que su organización administre el dispositivo, seleccione **Esta aplicación solo**.
7. Cuando se complete la activación, seleccione **Empezar**.

### <a name="enable-bopis-in-modern-pos"></a>Habilitar BOPIS en Modern POS

1. Inicie sesión en Modern POS utilizando **000713** como id. de operador y **123** como contraseña.
2. Mientras se reproduce el vídeo introductorio, seleccione las dos casillas de verificación en la esquina inferior izquierda del cuadro de diálogo y luego cierre el cuadro de diálogo.
3. Si no se le solicita que cierre el turno, desplácese hacia la derecha en la página **Bienvenidos**, seleccione **Cerrar turno** y luego vuelva a iniciar sesión en el PDV.
4. Después de iniciar sesión, cuando se le solicite, seleccione **Realizar operaciones no relacionadas con la caja registradora**.
5. En la página **Bienvenidos**, desplácese hacia la derecha y seleccione la operación **Seleccionar estación de hardware**.
6. Seleccione **Gestionar**, establezca la opción **Usar estación de hardware** en **Activar** y luego seleccione **Aceptar**.
7. Cierre sesión del PDV y, a continuación, vuelva a iniciar sesión.
8. Después de iniciar sesión, seleccione **Abrir un nuevo turno** y luego seleccione **Cajón**.

## <a name="complete-a-bopis-scenario"></a>Completar un escenario BOPIS

### <a name="create-a-storefront-order-for-in-store-pickup"></a>Crear un pedido de escaparate para recoger en la tienda

1. Vaya a la URL que especificó en el paso [Inicializar comercio electrónico](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) durante la configuración del entorno.
2. Seleccione un artículo y seleccione **Añadir al carrito**.
3. En la página de la bolsa de compras, seleccione **Recoger esto** para la línea de pedido que acaba de agregar.
4. En el cuadro de diálogo **Seleccionar una tienda**, ingrese **San Francisco** y luego seleccione el botón **Buscar**.
5. En la lista de resultados, busque la tienda de San Francisco y seleccione **Recoger aquí**.
6. En la página de la bolsa de compras, seleccione **Pagar como invitado**. 

    > [!NOTE]
    > Para continuar con el pago, debe aceptar el aviso de cookies. Este aviso aparece como un banner en la parte superior de la página de pago.

7. Para el método de pago con tarjeta de crédito, ingrese los siguientes detalles:

    - **Nombre del titular de la tarjeta**: ingrese cualquier nombre.
    - **Número de tarjeta**: introduzca **4111-1111-1111-1111**.
    - **Fecha de vencimiento**: introduzca **10/20**.
    - **Código de seguridad de la tarjeta (CVV)**: introduzca **737**.

    > [!IMPORTANT]
    > Bajo ninguna circunstancia intente usar la información de un tarjeta de crédito real en el sitio de prueba.

8. Continúe con el pago ingresando los detalles de la dirección de facturación y luego seleccione **Guardar y continuar**.
9. Cuando el pedido esté listo para ser realizado, seleccione **Finalizar compra**.

### <a name="synchronize-online-orders-to-the-back-office"></a>Sincronizar pedidos en línea con la oficina administrativa

Para obtener información sobre cómo sincronizar pedidos en línea, vea [Publicación de ventas y pagos en línea](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).

### <a name="pick-up-an-order-in-the-store"></a>Recoger un pedido en tienda

1. Inicie sesión en el PDV.
2. En la página **Bienvenidos**, seleccione **Cumplimiento de la orden**.
3. En la lista de artículos para recoger, seleccione la línea del pedido que se realizó en línea.
4. Con la línea de pedido seleccionada, seleccione **Recoger**.

    La línea de pedido se agrega a la pantalla de transacción y aparece **$ 0.00** como saldo adeudado.

5. Seleccione el saldo adeudado de **$ 0.00** o seleccione cualquier método de pago para concluir la transacción.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a>Los pedidos en línea que se recuperan en el PDV tienen un saldo adeudado distinto de cero.

Cuando se recupera un pedido para la recogida en la tienda, si el saldo adeudado no es 0 (cero), asegúrese de que se esté utilizando Modern POS y que la estación de hardware esté activa. Si se utiliza Cloud POS o Modern POS para iOS, asegúrese de que haya activado una estación de hardware compartida. Se requiere alguna forma de estación de hardware activa para recuperar los pagos que se realizaron en línea.

### <a name="general-issues-with-payment-capture"></a>Problemas generales con la captura de pagos

Para todos los problemas generales, siempre debe consultar los registros de eventos de la estación de hardware de Modern POS o Internet Information Services (IIS) como primer paso. Puede encontrar estos registros en los siguientes nodos en el registro de eventos de Windows:

- Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> Commerce-ModernPOS
- Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> estación de hardware de Commerce

## <a name="additional-resources"></a>Recursos adicionales

[Información general del entorno de evaluación de Dynamics 365 Commerce](cpe-overview.md)

[Aprovisionar un entorno de evaluación de Dynamics 365 Commerce](provisioning-guide.md)

[Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce](cpe-optional-features.md)

[Preguntas frecuentes sobre el entorno de evaluación de Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal de Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Conector de pago Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[Guardar los instrumentos de pago en línea con el conector de Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[Visión general de pagos omnicanal](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)


[!INCLUDE[footer-include](../includes/footer-banner.md)]