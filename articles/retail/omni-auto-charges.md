<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="omni-auto-charges.md" target-language="es-ES">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>omni-auto-charges.2f6e37.47829a6fcae37e03510929dc46b942455016df0b.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>47829a6fcae37e03510929dc46b942455016df0b</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\omni-auto-charges.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cargos automáticos avanzados omnicanal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes capabilities for managing additional order charges for Retail channel orders using advanced auto charges features.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este tema describe las capacidades para gestionar los cargos adicionales de pedidos de los pedidos del canal de minoristas mediante las el uso de varias funciones avanzadas de cargos automáticos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cargos automáticos avanzados omnicanal</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides information on configuration and deployment of the advanced auto-charges feature which are available in Dynamics 365 for Retail version 10.0.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este tema proporciona información acerca de la configuración y la implementación de características avanzadas de cargos automáticos disponibles en Dynamics 365 for Retail versión 10.0.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>When the advanced auto-charges features are enabled, orders created in any supported Retail channel (point of sale (POS), call center, and online), can take advantage of the <bpt id="p1">[</bpt>auto-charges<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations defined in the ERP application for both header and line-level related charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si se habilitan las funciones avanzadas de cargos automáticos, los pedidos creados en cualquier canal minorista admitido (punto de venta (PDV), centro de asistencia telefónica y en línea), pueden aprovechar las configuraciones de <bpt id="p1">[</bpt>cargos automáticos<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> definidas en la aplicación de ERP para el encabezado y los cargos relacionados a nivel de línea.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>In releases prior to Dynamics 365 for Retail version 10.0, <bpt id="p1">[</bpt>auto-charge<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations are only accessible by orders created in e-Commerce and call center channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En las versiones anteriores a Dynamics 365 for Retail versión 10.0 , las configuraciones de <bpt id="p1">[</bpt>cargo automático<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> solo están accesibles para los pedidos creados en e-commerce y canales de centro de llamadas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>In versions 10.0 and later, POS-created orders can leverage the auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En las versiones 10.0 y posteriores, los perdidos creados en PDV pueden aprovechar las configuraciones de cargos automáticos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>That way, additional miscellaneous charges can systematically be added to sales transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">De esta manera, los cargos adicionales se puede agregar sistemáticamente a las transacciones de ventas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>When using releases prior to version 10.0, a POS user is prompted to manually enter a shipping fee during the creation of a "ship all" or "ship selected" POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Al usar versiones previas a la versión 10.0, se debe pedir a un usuario PDV que especifique manualmente una cuota de envío durante la creación de una transacción PDV con “Enviar todo” o “Enviar selección".</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>While the miscellaneous charges capabilities of the application are utilized in respect to how the charges are written to the order, no systematic calculation is provided – the calculation relies on the user's input to determine the value of the charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Aunque las capacidades para cargos varios de la aplicación se usan en relación a cómo se escriben los cargos en el pedido, no se proporciona cálculo sistemático alguno; el cálculo depende de los datos del usuario para determinar el valor de los cargos.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The charges can only be added as a single "shipping" related charges code and cannot easily be edited or changed in the POS after they are created.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los cargos solo se pueden agregar como único código de cargos tipo “envío” y no pueden editarse o cambiarse fácilmente en el PDV después de que los creen.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The use of manual prompts to add shipping charges is still available in versions 10.0 and later.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El uso de indicadores manuales de agregar cargos de envío aún está disponible en versiones 10.0 y posteriormente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>If an organization does not enable the <bpt id="p1">**</bpt>Advanced Auto-charges<ept id="p1">**</ept> parameter, the POS prompts for manual entry of charges will remain the same.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si una organización no habilita el parámetro <bpt id="p1">**</bpt>cargos automáticos avanzados<ept id="p1">**</ept> , los indicadores del sistema PDV para la entrada manual de cargos seguirán igual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>With the advanced auto-charges feature, POS users can have systematic calculations for any defined miscellaneous charges based on auto-charges setup tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Con la función avanzado de cargos automáticos, los usuarios de PDV pueden tener cálculos sistemáticos para los cargos varios definido basados en las tablas de configuración de los cargos automáticos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In addition, users will have the ability to add or edit an unlimited amount of additional charges and fees to any POS sales transaction at the header or line-level (for a cash and carry or customer order).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Además, los usuarios tendrán de la capacidad de agregar o editar un importe ilimitado de cargos adicionales y cuotas a cualquier transacción de las ventas PDV en la cabecera o el nivel de línea (para pedidos en efectivo o de clientes).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Enabling advanced auto-charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Activar cargos automáticos avanzados</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>On the <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Headquarters setup <ph id="ph2">\&gt;</ph> Parameters <ph id="ph3">\&gt;</ph> Retail parameters<ept id="p1">**</ept> page, go to the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab. On the <bpt id="p3">**</bpt>Charges<ept id="p3">**</ept> FastTab, set <bpt id="p4">**</bpt>Use advanced auto-charges<ept id="p4">**</ept> to <bpt id="p5">**</bpt>Yes<ept id="p5">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">En la página <bpt id="p1">**</bpt>Ventas al por menor <ph id="ph1">\&gt;</ph> Configuración de sede <ph id="ph2">\&gt;</ph> Parámetros <ph id="ph3">\&gt;</ph> Parámetros minoristas<ept id="p1">**</ept>, vaya a la pestaña <bpt id="p2">**</bpt>Pedidos de cliente<ept id="p2">**</ept>. En la ficha desplegable <bpt id="p3">**</bpt>Cargos<ept id="p3">**</ept>, establezca <bpt id="p4">**</bpt>Usar cargos automáticos avanzados<ept id="p4">**</ept> en <bpt id="p5">**</bpt>Sí<ept id="p5">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Advanced Auto-Charges Parameter</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parámetros de cargos automáticos avanzados</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>When advanced auto-charges are enabled, users are no longer prompted to manually enter a shipping charge at the POS terminal when creating a ship-all or ship-selected customer order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cuando se habilitan los cargos automáticos, ya no se pide a los usuarios que especifiquen manualmente un cargo de envío en el terminal del PDV al crear un pedido de cliente con enviar todo o enviar selección.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>POS order charges are systematically calculated and added to the POS transaction (if a corresponding auto-charges table that matches the criterion of the order being created are found).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los cargos de pedidos PDV se calculan sistemáticamente y se añaden a la transacción del PDV (si se encuentra la tabla correspondiente de cargos automáticos que coincide con el criterio del pedido que se está creando).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Users can also add or maintain header or line-level charges manually through newly added POS operations that can be added to the POS screen layouts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los usuarios también pueden agregar o mantener los cargos de encabezado o de nivel de línea manualmente con las operaciones recién agregadas de PDV que se pueden agregar a los diseños de pantalla de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>When advanced auto-charges are enabled, the existing <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> for <bpt id="p2">**</bpt>Shipping charges code<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> are no longer utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cuando habilitan los cargos automáticos, los <bpt id="p1">**</bpt>Parámetros de ventas<ept id="p1">**</ept> existentes para <bpt id="p2">**</bpt>Código de los cargos de envío<ept id="p2">**</ept> y <bpt id="p3">**</bpt>cargos de envío de la devolución<ept id="p3">**</ept> ya no se usan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>These parameters are only applicable if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>No<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Estos parámetros solo son aplicables si el parámetro <bpt id="p1">**</bpt>Usar cargos automáticos avanzados<ept id="p1">**</ept> se establece en <bpt id="p2">**</bpt>No<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Before you enable this feature, ensure that you have tested and trained your employees, as this will change the business process flow of how shipping or other charges are calculated and added to POS sales orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Antes de habilitar esta función, asegúrese de que se haya probado y haya formado a sus empleados, ya que esto cambiará el flujo de proceso empresarial de cómo calculan y se agrega a los cargos de envío u otros a pedidos de ventas PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Make sure that you understand the impact of the process flow to the creation of transactions from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Asegúrese de que entiende el impacto del flujo de proceso en la creación de transacciones de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For call center and e-Commerce orders, the impact of enabling advanced auto-charges is minimal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para el centro de asistencia telefónica y pedidos de e-commerce, el impacto de habilitar los cargos automáticos avanzados es mínimo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Call center and e-Commerce applications will continue to have the same behavior they have had historically related to the auto-charges tables to calculate additional order fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El centro de asistencia telefónica y las aplicaciones de comercio electrónico seguirán teniendo el mismo comportamiento que han tenido históricamente relacionado con las tablas de cargos automáticos para calcular las cuotas adicionales del pedido.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Call center channel users will continue to have the ability to manually edit any system calculated auto-charges at the header or line level, or manually add additional miscellaneous charges at the header or line level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los usuarios del canal de centro de asistencia telefónica seguirán teniendo la capacidad de editar manualmente a cualquier cargo automático calculado por sistema en la cabecera o el nivel de línea, o agregar manualmente cargos varios extra en la cabecera o el nivel de línea.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Additional POS operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Operaciones adicionales de PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>For advanced auto-charges to work properly in your POS application environment, new POS operations have been added.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para que los cargos automáticos avanzados funcionen correctamente en el entorno de aplicación de PDV se han agregado nuevas operaciones de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>These operations must be added to your <bpt id="p1">[</bpt>POS screen layouts<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> and deployed to the POS devices as you deploy advanced auto-charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Estas operaciones deben agregarse a su <bpt id="p1">[</bpt>Diseño de pantalla del PDV<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> e implementar en los dispositivos de PDV mientras implementa los cargos automáticos avanzados.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>If these operations are not added, users will not be able to manage or maintain miscellaneous charges on the POS transactions and will have no way of adjusting or changing the charges values that are systematically calculated based on auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si estas operaciones no se agregan, los usuarios no podrán administrar o mantener cargos varios en las transacciones PDV y no tendrán ningún modo de ajustar o de cambiar los valores de cargos varios que se calculan sistemáticamente en función de la configuración de los cargos automáticos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>At minimum, it is suggested that you deploy the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation to your POS layout.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Como mínimo, se sugiere que implementa la operación <bpt id="p1">**</bpt>Gestionar los cargos<ept id="p1">**</ept> en su diseño de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The new operations are as follows.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Las nuevas operaciones son las siguientes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source><bpt id="p1">**</bpt>142 - Manage charges<ept id="p1">**</ept> – Use this operation to allow POS users to view and edit miscellaneous charges for the POS transaction that were either added manually or systematically through auto-charges calculations.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>142 - Gestionar cargos<ept id="p1">**</ept> - Esta operación permite a los usuarios de PDV editar los cargos varios para la transacción PDV que se han agregado manualmente o sistemáticamente con los cálculos cargos automáticos.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>141 - Add header charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a header-level miscellaneous charge to any POS sales transaction (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>141 - Agregar cargos de encabezado<ept id="p1">**</ept> - Use esta operación para dar al usuario la capacidad de agregar manualmente cargos varios a nivel de encabezado en cualquier transacción de las ventas PDV (y seleccione el código de cargos que se utilizará).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>140 - Add line charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a line level miscellaneous charge to any POS sales transaction line (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>140 - Agregar cargos de línea<ept id="p1">**</ept> - Use esta operación para dar al usuario la capacidad de agregar manualmente cargos varios de línea en cualquier transacción de las ventas PDV de línea (y seleccione el código de cargos que se utilizará).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>143 - Recalculate charges<ept id="p1">**</ept> – Use this operation to perform a full re-calculation of the charges for the sales transaction.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>143 - Actualizar los cargos<ept id="p1">**</ept> - Esta operación permite realizar un cálculo completo de los cargos para la transacción de ventas.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Any previously user-overwritten auto-charges will be recalculated based on the current cart configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Actualizará cualquier cargo automático sobrescrito por el usuario basándose en la configuración de carrito actual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>As with all POS operations, security configurations can be made to require manager approval in order to execute the operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Como con todas las operaciones de PDV, las configuraciones de seguridad se pueden crear para requerir la aprobación del director para ejecutar la operación.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>It is important to note that the above listed POS operations can also be added to the POS layout even if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Es importante tener en cuenta que las operaciones arriba enumeradas de PDV también se pueden agregar al diseño de PDV incluso si se deshabilita el parámetro <bpt id="p1">**</bpt>Usar cargos automáticos avanzados<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>In this scenario, organizations will still get added benefits of being able to view manually added charges and edit them using the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En esta situación, las organizaciones seguirán con los beneficios agregados de poder ver los gastos manualmente agregados y editarlos mediante la operación <bpt id="p1">**</bpt>Gestionar cargos<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Users may also use the <bpt id="p1">**</bpt>Add header charges<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Add line charges<ept id="p2">**</ept> operations for POS transactions even when <bpt id="p3">**</bpt>Use advanced auto-charges<ept id="p3">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los usuarios también pueden usar las operaciones <bpt id="p1">**</bpt>Agregar cargos de encabezado<ept id="p1">**</ept> y <bpt id="p2">**</bpt>Agregar cargos de línea<ept id="p2">**</ept> para las transacciones de PDV incluso cuando se deshabilita el parámetro <bpt id="p3">**</bpt>Usar cargos automáticos avanzados<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>The <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation has less functionality if used when <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La operación <bpt id="p1">**</bpt>Actualizar los cargos<ept id="p1">**</ept> tiene menos funcionalidad si se usa cuando se deshabilita <bpt id="p2">**</bpt>Usar cargos automáticos avanzados<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In this sceanrio, nothing would be recalculated and any charges manually added to the transaction would just reset to $0.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En este caso, no se actualizaría nada y cualquier cargo agregado manualmente a la transacción se restablecería en $0,00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Use case examples</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ejemplos de caso de uso</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In this section, sample use cases are presented to help you understand the configuration and usage of auto-charges and miscellaneous charges within the context of Retail channel orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En esta sección, los casos de uso del ejemplo se muestran para ayudarle a comprender la configuración y uso de cargos automáticos y cargos varios en el contexto de pedidos del canal minoristas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>These examples illustrate the behavior of the application when the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter has been enabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En los ejemplos se muestra el comportamiento de la aplicación cuando se ha habilitado el parámetro <bpt id="p1">**</bpt>Usar cargos automáticos avanzados<ept id="p1">**</ept> .</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Auto-charges header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ejemplo de cargos automáticos en cargos de encabezado</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Escenario del caso de uso</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>A retailer wants to automatically add charges for freight when transactions are created in any Retail channel that require a shipment of products to the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un minoristas desea agregar automáticamente los cargos de flete cuando se realizan transacciones en cualquier canal minorista que requieren un envío de productos al cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The retailer offers 2 methods of delivery: Ground and Air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El minorista 2 proporciona métodos de entrega: tierra y aire.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>If a customer chooses Ground delivery and the order value is less than $100, the retailer wants to charge the customer a freight charge of $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si un cliente elige la entrega por tierra y el valor del pedido menos de 100 $, el minoristas desea cobrar al cliente un flete de 10 $.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>If the order is over $100 in value and the customer chooses ground shipping, the customer will not be charged any additional freight fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si el pedido es de más de 100 $ y el cliente tienen el envío por tierra, no cobrará al cliente ningún cargo de flete adicional.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>If the customer chooses the Air method of delivery for all orders, regardless of their total value, will be charged a freight fee of $20.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si el cliente elige aire como método de entrega para todos los pedidos, independientemente de su valor total, se cargarán una cuota de flete de 20 $.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Establecimiento y configuración</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>This scenario requires the configuration of two auto-charges tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este escenario requiere la configuración de dos tablas de cargos automáticos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Go to <bpt id="p1">**</bpt>Accounts receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vaya a <bpt id="p1">**</bpt>Clientes <ph id="ph1">\&gt;</ph> Configuración de cargos <ph id="ph2">\&gt;</ph> cargos automáticos<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Configure two different header-level auto charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configure dos cargos automáticos a nivel de encabezado.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Configure one for the "Ground mode" of delivery and one for the "Air mode" of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurar uno para el "Modo tierra" de entrega y otro para el “Modo aire” de entrega.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>For this scenario, configure them to be used for "All customers".</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para esta situación, configúrelos para usar para “Todos los clientes”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>For the ground delivery charges, in the lines section of the <bpt id="p1">**</bpt>Auto-charges<ept id="p1">**</ept> page, define a charge that will be applied for orders between $.01 and $100 as $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para los cargos de entrega por tierra, en la sección líneas de la página <bpt id="p1">**</bpt>cargos automáticos<ept id="p1">**</ept> , defina un cargo que se aplique para los pedidos entre 0,01 $ y 100 $ como 10 $.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Create another charges line to indicate orders over $100.01 will have no charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cree otra línea de cargos para indicar que los pedidos de más de 100,01 $ no tendrán cargos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ejemplo de cargos automáticos</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>For the air delivery charges, in the lines section of the auto-charges form, define a charge of $20.00 that will be applied to all orders (between a value of $.01 to $9,999,999).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para los cargos de entrega por aire, en la sección líneas del formulario cargos automáticos, defina un cargo de 20 $ que se aplicará a todos los pedidos (entre un valor de 0,01 $ a 9 999 999 $).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Send the changes to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Envíe los cambios al servidor minorista/DB de canal para que los PDV puedan usarlos ejecutando el trabajo <bpt id="p1">**</bpt>Programación de distribución 1040<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Procesado de ventas para este escenario</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>After the configuration steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have the ground or air delivery methods set at the header level will utilize these charges and automatically apply them to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una vez que los pasos de configuración anteriores se completen y los cambios se han aplicado a la base de datos de canal, cualquier pedido de cliente o la transacción de ventas creada en PDV, el centro de asistencia, telefónica o los canales de e-commerce que tienen los métodos de entrega por tierra o aire establecidos en el nivel de encabezado usarán estos castos y los aplicarán automáticamente a la venta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>At this time the charges will apply to all sales transactions created within the legal entity that utilize these delivery modes, as there is no functionality to designate that an auto-charge configuration will only apply to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En este tiempo los cargos se aplicarán a todas las transacciones de ventas creadas dentro de la entidad jurídica que usen estos modos de entrega, ya que no hay funcionalidad para indicar que una configuración de cargo automático se aplique sólo a un canal vendedor específico.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For POS and e-Commerce scenarios, because there is no clearly defined "header" on these orders, header-level charges will only apply if all sales lines on the transaction are set to ship with the exact same mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para los escenarios de PDV e informes de e-commerce, como no hay “cabecera" definida en estos pedidos, los cargos a nivel de encabezado solo se aplicarán si todas las líneas de ventas en la transacción se fijan para entregarse con el mismo modo de envío.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If there are "mixed-modes" of fulfillment on the transactions created by POS or e-Commerce, only line-level auto-charges will be considered and applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si hay “modos mixtos” de cumplimiento en las transacciones realizadas por el sistema PDV o e-commerce, sólo tendrán en cuenta y se aplicarán cargos automáticos a nivel de línea.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>In call center scenarios, the user has control over the setting of the delivery mode at the order header, therefore header-level charges will apply for these orders even if some of the sales lines have been configured to use a different mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En escenarios de centro de asistencia telefónica, el usuario tiene control sobre el valor del modo de entrega en el encabezado del pedido, por tanto los cargos nivel de encabezado se aplicarán estos pedidos incluso si alguna de las líneas de ventas que se han configurado usan otro modo de entrega.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Header-level charges for call center orders will always be based on the mode of delivery that is defined at the order header level of the sales order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los cargos a nivel de encabezado para los pedidos de centro de asistencia telefónica siempre se basarán en el modo de entrega definido en el nivel de encabezado del pedido del pedido de ventas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Auto-charges line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ejemplo de cargos automáticos de cargos de línea</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Escenario del caso de uso</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>A retailer wants to add an additional charge to the customer for setup fees when the customer purchases a particular model of computer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un minorista desea agregar un cargo adicional al cliente para las cuotas de configuración cuando el cliente compra un modelo determinado de equipo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>This computer requires additional non-optional setup actions that the retailer will perform for the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este equipo requiere las acciones de instalación no opcionales adicionales que el minorista realizará para el cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The retailer has informed customers that there will be an additional fee for this setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El minorista ha informado a los clientes que habrá una cuota adicional para esta configuración.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>The retailer prefers to manage the charges related to this fee separately from the product sales price for financial reporting purposes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El minorista prefiere administrar los cargos relacionados con esta cuota de manera independiente del precio de venta del producto para los informes financieros.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>A setup fee of $19.99 will be charged to the customer when this specific computer is purchased in any retail channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se facturará al cliente una cuota de instalación de 19,99 $ cuando este equipo específico se compre en cualquier canal minorista.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Establecimiento y configuración</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>This scenario requires the configuration of one line-level auto charges table.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este escenario requiere la configuración de una tabla de cargos automáticos a nivel de línea.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Go to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vaya a <bpt id="p1">**</bpt>Clientes <ph id="ph1">\&gt;</ph> Configuración de cargos <ph id="ph2">\&gt;</ph> Cargos automáticos<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Set the <bpt id="p1">**</bpt>Level<ept id="p1">**</ept> drop-down menu to <bpt id="p2">**</bpt>Line<ept id="p2">**</ept>, and create a new auto-charges record for all customers and for the specific product or product group where the setup fees will be charged.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Establezca el menú desplegable <bpt id="p1">**</bpt>Nivel<ept id="p1">**</ept> en <bpt id="p2">**</bpt>Línea<ept id="p2">**</ept>, y cree un nuevo registro de cargos automáticos para todos los clientes y para el producto o el grupo de productos específico donde se cargarán las cuotas de configuración.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ejemplo de cargos automáticos</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Envíe los cargos al servidor minorista/DB de canal para que los PDV puedan usarlos ejecutando el trabajo <bpt id="p1">**</bpt>Programación de distribución 1040<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Procesado de ventas para este escenario</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>After the configurations steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have this item on the order will trigger a line-level charge to be systematically added to the order total.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una vez que los pasos de configuración anteriores se completen y los cambios se han aplicado a la base de datos de canal, cualquier pedido de cliente o la transacción de ventas creada en PDV, el centro de asistencia, telefónica o los canales de e-commerce que tienen este elemento activarán un cargo a nivel de línea que se añadirá sistemáticamente al total del pedido.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>At this time the charges will apply to any sales line that matches the configuration of the line-level auto charges within the legal entity, as there is no functionality to configure a line-level auto-charge to apply only to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En este tiempo los cargos se aplicarán a cualquier línea de ventas que coincida con la configuración de los cargos automáticos a nivel de línea dentro de la entidad jurídica, ya que no hay funcionalidad para configurar un cargo automático a nivel de línea para que se aplique solo a un canal de venta específico.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Manual header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ejemplo de cargos manuales de encabezado</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Use case scenario description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Descripción del escenario caso de uso</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>A retailer is making an exception to typical processes by offering to provide a special home delivery of products to a customers who order products in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un minorista está creando una excepción a los procesos típicos ofertando un servicio a domicilio especial para productos a los clientes que piden productos en la tienda.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The retailer and the customer have agreed that the customer will pay an additional $25 handling fee for this service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El minorista y el cliente han acordado que el cliente pagará una cuota de manipulación adicional de 25 $ por este servicio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The order-taker needs to add this additional fee to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El que realiza el pedido necesita agregar esta cuota adicional a la transacción.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Because the fee is a blanket fee and not related to any single product on the order, a header charge will be utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dado que la cuota es una cuota plana y no relacionada con un producto único del pedido, se va a utilizar un cargo de cabecera.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Establecimiento y configuración</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Asegúrese de que el código de cargo que se usará en este escenario se ha configurado correctamente al encabezado <bpt id="p1">**</bpt>Clientes <ph id="ph1">\&gt;</ph> Configuración de cargos <ph id="ph2">\&gt;</ph> Cargos<ept id="p1">**</ept> para definir un código de cargo adecuado para la situación.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ejemplo de cargos</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Si se considerará que el cargo un cargo relacionado con el “envío” con el fin de descuentos de promociones o relacionados de envío, establezca el <bpt id="p1">**</bpt>Cargo de envío<ept id="p1">**</ept> en el código de cargos en <bpt id="p2">**</bpt>Sí<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>If this charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si se permite que este cargo también pueda reembolsarse sistemáticamente durante el procesamiento de una transacción de devolución en la aplicación del PDV, establezca <bpt id="p1">**</bpt>Reembolsable<ept id="p1">**</ept> en <bpt id="p2">**</bpt>Sí<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El indicador <bpt id="p1">**</bpt>Reembolsable<ept id="p1">**</ept> solo se aplica cuando el parámetro <bpt id="p2">**</bpt>Usar cargos automáticos avanzados<ept id="p2">**</ept> se establece en <bpt id="p3">**</bpt>Sí<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Envíe los cargos al servidor minorista/DB de canal para que los PDV puedan usarlos ejecutando el trabajo <bpt id="p1">**</bpt>Programación de distribución 1040<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>The <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 141).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La operación <bpt id="p1">**</bpt>Agregar cargo de encabezado<ept id="p1">**</ept> se debe configurar en su <bpt id="p2">[</bpt>Diseño de pantalla de PDV<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> de modo que un botón que es accesible al usuario del PDV pueda llamar a esta operación (operación 141).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los cambios del diseño de pantalla se deben dirigir también al canal minoristas con la función de programación de la distribución.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Sales processing of manual header charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Procesamiento de ventas de cargos del encabezado manuales</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para ejecutar el escenario en la aplicación de PDV, el usuario PDV creará la transacción de ventas como de costumbre, agregando los productos y cualquier otra configuración para la venta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Prior to collecting payment, the user should execute the <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation, which will prompt the user to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Antes de cobrar el pago, el usuario debe ejecutar la operación <bpt id="p1">**</bpt>Agregar cargo de encabezado<ept id="p1">**</ept> , que solicitará al usuario seleccione un código de cargos y especifica el valor de los cargos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Once the user completes the process, the charge will be added to the sales order as a header-level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una vez que el usuario complete el proceso, agregar el cargo al pedido de ventas como un cargo nivel de encabezado.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>This process can be applied in the call center by using the existing <bpt id="p1">**</bpt>Charges<ept id="p1">**</ept> feature found on the <bpt id="p2">**</bpt>Sell<ept id="p2">**</ept> tab on the toolbar.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este proceso se puede aplicar al centro de asistencia telefónica mediante la función <bpt id="p1">**</bpt>Cargos<ept id="p1">**</ept> existente que aparece en la pestaña <bpt id="p2">**</bpt>Venta<ept id="p2">**</ept> en la barra de herramientas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>On the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page, the user can add a new charges line to the order header.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En la página <bpt id="p1">**</bpt>Mantener cargos<ept id="p1">**</ept> , el usuario puede agregar nuevos cargos de líneas a la cabecera del pedido.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Manual line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ejemplo de cargos manuales de línea</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Escenario del caso de uso</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>A customer has requested that 2 of the 5 items on their sales order be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un cliente ha solicitado que los 2 de 5 artículos en el pedido de ventas se envuelvan para regalo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>The retailer offers this optional service for a fee of $2.00 per item.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El minorista ofrece este servicio opcional con una cuota de 2 $ por artículo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>The order-taker will need to add these fees to the specific items that need to be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El que realice el pedido deberá agregar estas cuotas a los artículos específicos que deben llevarse a envuelto para regalos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Establecimiento y configuración</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Asegúrese de que el código de cargo que se usará en este escenario se ha configurado correctamente al encabezado <bpt id="p1">**</bpt>Clientes <ph id="ph1">\&gt;</ph> Configuración de cargos <ph id="ph2">\&gt;</ph> Cargos<ept id="p1">**</ept> para definir un código de cargo adecuado para la situación.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set the <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si se considerará que el cargo debe considerarse un cargo relacionado con el “envío” con el fin de descuentos de promociones, establezca <bpt id="p1">**</bpt>cargos de envío<ept id="p1">**</ept> en el código de cargos en <bpt id="p2">**</bpt>Sí<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>If the charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si se permite que el cargo también pueda reembolsarse sistemáticamente durante el procesamiento de una transacción de devolución en la aplicación del PDV, establezca <bpt id="p1">**</bpt>Reembolsable<ept id="p1">**</ept> en <bpt id="p2">**</bpt>Sí<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El indicador <bpt id="p1">**</bpt>Reembolsable<ept id="p1">**</ept> solo se aplica cuando el parámetro <bpt id="p2">**</bpt>Usar cargos automáticos avanzados<ept id="p2">**</ept> se establece en <bpt id="p3">**</bpt>Sí<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Envíe los cargos al servidor minorista/DB de canal para que los PDV puedan usarlos ejecutando el trabajo <bpt id="p1">**</bpt>Programación de distribución 1040<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>The <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 140).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La operación <bpt id="p1">**</bpt>Agregar cargo de línea<ept id="p1">**</ept> se debe configurar en su <bpt id="p2">[</bpt>Diseño de pantalla de PDV<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> de modo que un botón que es accesible al usuario del PDV pueda llamar a esta operación (operación 140).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los cambios del diseño de pantalla se deben dirigir también al canal minoristas con la función de programación de la distribución.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>Sales processing of the manual line charge</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Procesamiento de ventas de cargos de línea manuales</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para ejecutar el escenario en la aplicación de PDV, el usuario PDV creará la transacción de ventas como de costumbre, agregando los productos y cualquier otra configuración para la venta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Prior to collecting payment, the user should select the specific line where the charge will apply from the POS item list display and execute the <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Antes de cobrar el pago, el usuario debe seleccionar la línea específica en el cargo que se aplicará en la visualización de la lista de artículos del PDV y ejecutar la operación <bpt id="p1">**</bpt>Agregar cargo de línea<ept id="p1">**</ept> .</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>The user will be prompted to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se le solicitará al usuario seleccionar un código de cargos y especifica el valor de los cargos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Once the user completes the process, the charge will be linked to the line and added to the order total as a line level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una vez que el usuario complete el proceso, el cargo se vinculará a la línea y añadirá al total del pedido como un cargo a nivel de línea.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The user can repeat the process to add additional line charges to other items lines on the transaction if needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El usuario puede repetir el proceso para agregar cargos de línea adicionales a otras líneas de los artículos de la transacción, si es necesario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The same process can be applied in the call center by using the "maintain charges" feature found under the <bpt id="p1">**</bpt>Financials<ept id="p1">**</ept> drop-down menu in the <bpt id="p2">**</bpt>Sales order lines<ept id="p2">**</ept> section on the <bpt id="p3">**</bpt>Sales order<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El mismo proceso se puede aplicar al centro de asistencia telefónica mediante la función “mantener cargos” encontrada bajo el menú <bpt id="p1">**</bpt>Operaciones financieras<ept id="p1">**</ept> en la sección <bpt id="p2">**</bpt>Líneas de pedido de ventas<ept id="p2">**</ept> en la página <bpt id="p3">**</bpt>Pedidos de ventas<ept id="p3">**</ept> .</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>This will open the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page where the user can add a new line specific charge to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se abrirá la página <bpt id="p1">**</bpt>Mantener cargos<ept id="p1">**</ept> donde el usuario puede agregar un cargo específico de la nueva línea a la transacción.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Additional features</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funciones adicionales</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>Editing charges on a POS sales transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Editar cargos en una transacción de las ventas PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>The <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation (142) should be added to the <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a user can view and edit or override any system-calculated or manually-created header or line-level charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La operación <bpt id="p1">**</bpt>Gestionar cargos<ept id="p1">**</ept> (142) se debe agregar a <bpt id="p2">[</bpt>Diseño de pantalla de PDV<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> de modo que un usuario pueda ver y editar o reemplazar los cargos de encabezado o línea calculados por el sistema o creados manualmente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>If the operation is not added, users will not be able to adjust the value of the charges on the POS transaction, nor will they be able to view the details of the charges such as the type of charges code tied to the charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si la operación no se agrega, los usuarios no podrán ajustar el valor de los cargos en la transacción PDV, ni podrán ver los detalles de los cargos como el tipo de código de cargos atado el cargo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>On the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> page in POS, the user can view both header and line-level charges details.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En la página <bpt id="p1">**</bpt>Gestionar cargos<ept id="p1">**</ept> en el PDV, el usuario puede ver los detalles de los cargos de encabezado y de nivel de línea.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The user can use the <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> function available on this page to make changes to the amount charged to a specific charges line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El usuario puede utilizar la función <bpt id="p1">**</bpt>Editar<ept id="p1">**</ept> disponible en esta página para realizar cambios en el importe cargado en los cargos específicos particular.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>Once a charges line is overwritten manually, it will not be systematically recalculated unless the user initiates the <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una vez un cargo de línea se actualice manualmente no se volverá a calcular sistemáticamente a menos que el usuario inicie la operación <bpt id="p1">**</bpt>Actualizar cargos<ept id="p1">**</ept> .</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>If the <bpt id="p1">**</bpt>Charge override reason code<ept id="p1">**</ept> has been configured on the <bpt id="p2">**</bpt>Retail parameters<ept id="p2">**</ept> setup page, the user will be prompted to provide a reason code when charges have been modified in the POS application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si <bpt id="p1">**</bpt>Código de motivo de la anulación del cargo<ept id="p1">**</ept> se ha configurado en la página <bpt id="p2">**</bpt>Parámetros minoristas<ept id="p2">**</ept>, se le solicitará al usuario especificar un código de motivo cuando hayan modificado los cargos en la aplicación PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>If reason codes have been captured for overwritten charges, a new report is also available to review and audit these overrides.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si los códigos de motivo se capturan para cargos sobrescritos, un nuevo informe también estará disponible para revisar y auditar los cambios.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The report can be found in <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge override history<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El informe se puede encontrar en <bpt id="p1">**</bpt>Ventas al por menor <ph id="ph1">\&gt;</ph> Consultas e informes <ph id="ph2">\&gt;</ph> Historial de la anulación de cargos<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Refunding charges on a POS return transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Recuperación de cargos de una transacción de devolución de PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>If the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>, the existing retail parameter for <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> is no longer applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si el parámetro <bpt id="p1">**</bpt>Usar cargos automáticos avanzados<ept id="p1">**</ept> se establece en <bpt id="p2">**</bpt>Sí<ept id="p2">**</ept>, el parámetro de ventas existente para <bpt id="p3">**</bpt>Devolver cargos de envío<ept id="p3">**</ept> ya no es aplicable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>To indicate which charges should be systematically refunded to a customer when using advanced auto-charges, ensure the related charges code has been configured as <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para indicar qué cargos se deben devolver sistemáticamente a un cliente al usar cargos automáticos avanzados, asegúrese de que el código de cargos relacionado se ha configurado como <bpt id="p1">**</bpt>Reembolsable<ept id="p1">**</ept> en la página de configuración <bpt id="p2">**</bpt>Código de cargos<ept id="p2">**</ept> .</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>Make sure that the settings have been synchronized to your Retail channel databases through distribution schedule processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Asegúrese de que los valores se hayan sincronizado a las bases de datos del canal minoristas con el proceso de programación de la distribución.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Refunding charges on a return order transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Devolución de cargos de una transacción de devolución de pedido</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>Charges are not systematically refunded to <bpt id="p1">**</bpt>Return orders<ept id="p1">**</ept> created in Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los cargos no se devuelven sistemáticamente a los <bpt id="p1">**</bpt>Devolver pedidos<ept id="p1">**</ept> creados en ventas al por menor.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>Users are required to select the <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> option when creating the <bpt id="p2">**</bpt>Return order<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los usuarios deben seleccionar la opción <bpt id="p1">**</bpt>Copiar cargos<ept id="p1">**</ept> al crear el <bpt id="p2">**</bpt>Pedido de devolución<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is not selected, charges from the original sales transaction will not be automatically refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si <bpt id="p1">**</bpt>Copiar cargos<ept id="p1">**</ept> no está seleccionada, no se devolverán automáticamente los cargos de la transacción de ventas original.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is selected, all charges will be copied to the return order and the user can manually edit or remove any charges they do not want to have refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si se selecciona <bpt id="p1">**</bpt>Copiar cargos<ept id="p1">**</ept>, se copiarán todos los cargos al pedido de devolución y el usuario puede editar o eliminar manualmente los cargos que éste no desee tener devueltos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>The call center return order process currently does not acknowledge the <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El proceso de pedido de devolución de centro de asistencia telefónica no confirma actualmente el indicador <bpt id="p1">**</bpt>Reembolsable<ept id="p1">**</ept> en la configuración <bpt id="p2">**</bpt>Código de cargos<ept id="p2">**</ept> .</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>Configuring POS receipts to show charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurar recibod PDV para mostrar cargos</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>The following receipt elements have been added to the receipt line and footer to support the advanced auto-charges functionality.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Los siguientes elementos de recibo se han agregado a la línea y el pie de página del recibo para admitir la funcionalidad avanzada de cargos automáticos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source><bpt id="p1">**</bpt>Line Shipping Charges<ept id="p1">**</ept> – This line-level element can be used to recap specific charges codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>cargos de envío de la línea<ept id="p1">**</ept> - Este artículo de nivel de línea se puede usar para recapitular los códigos de cargos específicos que se aplicaron a la línea de ventas.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>Only charges codes that have been flagged as <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> charges on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page will be displayed here.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Sólo los códigos de cargos se han designado marcados como <bpt id="p1">**</bpt>Envío<ept id="p1">**</ept> en la página <bpt id="p2">**</bpt>Código de cargos<ept id="p2">**</ept> aparecerán aquí.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source><bpt id="p1">**</bpt>Line Other Charges<ept id="p1">**</ept> – This line-level element can be used to recap any non-shipping specific charge codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Otros cargos de línea<ept id="p1">**</ept> - Este artículo de nivel de línea se puede usar para recapitular los códigos de cargos específicos que no son de envío que se aplicaron a la línea de ventas.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>These are charges codes where the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page has not been enabled.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Estos son los códigos de cargos en que el indicador <bpt id="p1">**</bpt>Envío<ept id="p1">**</ept> en la página <bpt id="p2">**</bpt>Código de cargos<ept id="p2">**</ept> no se ha habilitado.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source><bpt id="p1">**</bpt>Order Shipping Charges Details<ept id="p1">**</ept> – This footer-level element displays the descriptions of the charge codes applied to the order that have been flagged as <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept> charges on the <bpt id="p3">**</bpt>Charges code<ept id="p3">**</ept> setup page.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Detalles de los cargos de envío del pedido<ept id="p1">**</ept> - Este artículo de pie de página nivel muestra las descripciones de los códigos de cargo que se aplicaron al pedido que se han designado como cargos de <bpt id="p2">**</bpt>Envío<ept id="p2">**</ept> en la página de configuración <bpt id="p3">**</bpt>Código de cargos<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source><bpt id="p1">**</bpt>Order Shipping Charges<ept id="p1">**</ept> – This footer-level element shows the dollar value of the shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Cargos de envío del pedido<ept id="p1">**</ept> - Este artículo de pie de página muestra el valor de los cargos relacionados con el envío.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source><bpt id="p1">**</bpt>Order Other Charges Details<ept id="p1">**</ept> – This footer-level element displays the description of the charges codes applied to the order that have not been flagged as shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Detalles otros cargos del pedido<ept id="p1">**</ept> - Este artículo de pie de página nivel muestra las descripciones de los códigos de cargos que se aplicaron al pedido que no se han designado como cargos relacionados con el envío.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source><bpt id="p1">**</bpt>Order Other Charges<ept id="p1">**</ept> – This footer-level element displays the dollar value of the other charges that are not shipping-related.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Otros cargos de pedido<ept id="p1">**</ept> - Este artículo de pie de página muestra el valor en dólares de los otros cargos que no están relacionados con el envío.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>It is recommended that the organization also add free text fields to the receipt footer, in order to define the areas where charges will be recapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se recomienda que la organización también añada campos de texto libre al pie del recibo, para definir las áreas en las que se recapitularán los cargos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Preventing charges from being calculated until the POS order is completed</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Evitar que se calculen los cargos hasta que el pedido de PDV se complete</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Some organizations may prefer to wait until the user has finished adding all of the sales lines to the POS transaction before calculating charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Algunas organizaciones pueden preferir espera hasta que el usuario haya terminado de agregar todas las líneas de ventas a la transacción PDV antes de calcular los cargos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>To prevent calculation of charges as items are added to the POS transaction, turn on the <bpt id="p1">**</bpt>Manual charge calculation<ept id="p1">**</ept> parameter in the <bpt id="p2">**</bpt>Functionality profile<ept id="p2">**</ept> used by the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para evitar el cálculo de cargos en artículos a medida que se agregan a la transacción PDV, active el parámetro <bpt id="p1">**</bpt>Cálculo del cargo manual<ept id="p1">**</ept> en el <bpt id="p2">**</bpt>Perfil de funcionalidad<ept id="p2">**</ept> que usa la tienda.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Enabling this parameter will require the POS user to use the <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation when they have completed adding the products to the POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Habilitar este parámetro requerirán al usuario PDV usar la operación <bpt id="p1">**</bpt>Calcular totales<ept id="p1">**</ept> cuando han terminado de añadir los productos a la transacción PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>The <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation will then trigger the calculation of any auto charges for the order header or lines as applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La operación <bpt id="p1">**</bpt>Calcular totales<ept id="p1">**</ept> se activará y calculará cualquier cargo automático para el encabezado o líneas del pedido, según sea aplicable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>Charges override reports</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Informes de anulación de cargos</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>If users manually override the calculated charges or add a manual charge to the transaction, this data will available for auditing in the <bpt id="p1">**</bpt>Charge Override History<ept id="p1">**</ept> report.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si los usuarios manualmente anulan los gastos calculados o agregan gastos manualmente a la transacción, estos datos estarán disponibles para fines de auditoría en el informe <bpt id="p1">**</bpt>Historial de la anulación de cargos<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>The report can be accessed from <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge Override History<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El informe se puede encontrar en <bpt id="p1">**</bpt>Ventas al por menor <ph id="ph1">\&gt;</ph> Consultas e informes <ph id="ph2">\&gt;</ph> Historial de la anulación de cargos<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>It is important to note that the data needed for this report is imported from the channel database into HQ through the "P" distribution schedule jobs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Es importante tener en cuenta que los datos necesarios para este informe se importan de la base de datos del canal en la Sede a través de los trabajos de la programación de distribución “P”.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>Therefore, information about overrides just performed in the POS may not be immediately available on this report until this job has uploaded the store transaction data into HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Por lo tanto, la información sobre anulaciones recién efectuadas en el PDV puede no estar disponible inmediatamente en este informe hasta que el trabajo haya cargado los datos de transacciones de la tienda en la Sede.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>