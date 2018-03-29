---
title: Konfigurieren von IP-Adresstypen in Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Zusammenfassung: Überprüfen der Faktoren für den IP-Adresse unter vor der Implementierung von Skype für Business Server 2015.'
ms.openlocfilehash: facfff432cfcde74af737b5a7c5db87d36f3eb41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="70b76-103">Konfigurieren von IP-Adresstypen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="70b76-103">Configure IP address types in Skype for Business</span></span>
 
<span data-ttu-id="70b76-104">**Zusammenfassung:** Überprüfen Sie vor der Implementierung von Skype für Business Server 2015 Faktoren für die IP-Adresse unten.</span><span class="sxs-lookup"><span data-stu-id="70b76-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="70b76-105">Sie stellen IP-Adresstypen mithilfe des Topologie-Einstellungen, die Sie im Topologie-Generator konfigurieren bereit.</span><span class="sxs-lookup"><span data-stu-id="70b76-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="70b76-106">In diesem Abschnitt wird beschrieben, wie IP-Adresstypen auf Front-End-Servern und Vermittlungsservern Edge-Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="70b76-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="70b76-107">Bereitstellen von IP-Adresstypen auf einem Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="70b76-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="70b76-108">Führen Sie Topologie-Generator verwenden, die Schritte in das folgende Verfahren zum Bereitstellen von IP-Adresstypen auf einem Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="70b76-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="70b76-109">So stellen Sie IP-Adressentypen auf einem Front-End-Server bereit</span><span class="sxs-lookup"><span data-stu-id="70b76-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="70b76-p102">Klicken Sie unter **Enterprise Edition-Front-End-Pools** mit der rechten Maustaste auf den Server in einem Pool und wählen Sie anschließend **Eigenschaften bearbeiten**. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)</span><span class="sxs-lookup"><span data-stu-id="70b76-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="70b76-p103">Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="70b76-p103">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="70b76-114">**Bearbeiten Sie im Dialogfeld Eigenschaften für den Front-End-Server-pool**</span><span class="sxs-lookup"><span data-stu-id="70b76-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

  - <span data-ttu-id="70b76-p104">**Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70b76-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="70b76-117">Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="70b76-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="70b76-p105">**Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für **Primäre IP-Adresse** angeben.</span><span class="sxs-lookup"><span data-stu-id="70b76-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
  - <span data-ttu-id="70b76-p106">**Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="70b76-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="70b76-p107">**PSTN-IP-Adresse**. Geben Sie eine PSTN-IP-Adresse an, wenn auf dem Front-End-Server ein Vermittlungsserver angeordnet wird. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="70b76-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70b76-127">Die Installation von zusätzlichen Netzwerkschnittstellenkarten (NICs) zur Unterstützung von PSTN-IP-Adresskonfiguration auf Front-End-Servern wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="70b76-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration on Front End Servers is not supported.</span></span> <span data-ttu-id="70b76-128">Weitere Informationen zu unterstützten NIC-Konfigurationen für Skype für Business Server finden Sie unter [Server Hardware Platforms für Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="70b76-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="70b76-129">Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="70b76-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="70b76-130">Führen Sie Topologie-Generator verwenden, die Schritte in das folgende Verfahren zum Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="70b76-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="70b76-131">So stellen Sie IP-Adresstypen auf einem Vermittlungsserver bereit</span><span class="sxs-lookup"><span data-stu-id="70b76-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="70b76-132">Klicken Sie im Topologie-Generator unter **vermittlungspools**mit der rechten Maustaste des Servers in einem Pool, und wählen Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="70b76-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="70b76-133">(Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)</span><span class="sxs-lookup"><span data-stu-id="70b76-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
- <span data-ttu-id="70b76-p110">Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="70b76-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="70b76-136">**Bearbeiten Sie im Dialogfeld Eigenschaften für den vermittlungsserverpool**</span><span class="sxs-lookup"><span data-stu-id="70b76-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="70b76-p111">**Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70b76-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="70b76-139">Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="70b76-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="70b76-p112">**Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für „Primäre IP-Adresse“ angeben.</span><span class="sxs-lookup"><span data-stu-id="70b76-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
  - <span data-ttu-id="70b76-p113">**Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="70b76-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="70b76-p114">**PSTN-IP-Adresse**. Geben Sie eine PSTN-IP-Adresse an, wenn auf dem Front-End-Server ein Vermittlungsserver angeordnet wird. Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="70b76-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70b76-149">Die Installation von zusätzlichen Netzwerkschnittstellenkarten (NICs) zur Unterstützung der Konfiguration der PSTN-IP-Adresse in den eigenständigen Vermittlungsserver wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="70b76-149">The installation of additional NICs to support the PSTN IP address configuration on stand-alone Mediation Servers is not supported.</span></span> <span data-ttu-id="70b76-150">Weitere Informationen zu unterstützten NIC-Konfigurationen für Skype für Business Server finden Sie unter [Server Hardware Platforms für Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="70b76-150">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-edge-server"></a><span data-ttu-id="70b76-151">Bereitstellen von IP-Adresstypen auf einem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="70b76-151">Deploy IP address types on a Edge Server</span></span>

<span data-ttu-id="70b76-152">Führen Sie Topologie-Generator verwenden, die Schritte in das folgende Verfahren zum Bereitstellen von IP-Adresstypen auf einem Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="70b76-152">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="70b76-153">So stellen Sie IP-Adresstypen auf dem Edgeserver bereit</span><span class="sxs-lookup"><span data-stu-id="70b76-153">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="70b76-154">Im Topologie-Generator unter **edgepools**mit der rechten Maustaste des Servers in einem Pool, und wählen Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="70b76-154">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="70b76-155">(Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)</span><span class="sxs-lookup"><span data-stu-id="70b76-155">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="70b76-p117">Wählen Sie im Fenster **Eigenschaften bearbeiten** die IP-Adresskonfiguration, die Sie unterstützen möchten. In den folgenden Abbildungen wird eine Dualstapelkonfiguration für die interne und die externe Schnittstelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="70b76-p117">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
   <span data-ttu-id="70b76-158">**Duale gestapelte internen Edge-Server-Schnittstelle**</span><span class="sxs-lookup"><span data-stu-id="70b76-158">**Dual stacked Edge Server internal interface**</span></span>

   <span data-ttu-id="70b76-159">**Duale gestapelte externen Edge-Server-Schnittstelle**</span><span class="sxs-lookup"><span data-stu-id="70b76-159">**Dual stacked Edge Server external interface**</span></span>

3. <span data-ttu-id="70b76-160">Für jeden Adresstyp, den Sie auswählen, müssen Sie die geeigneten internen und externen Adressen auswählen.</span><span class="sxs-lookup"><span data-stu-id="70b76-160">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
    

