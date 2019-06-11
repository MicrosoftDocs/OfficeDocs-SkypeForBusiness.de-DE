---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Front-End-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33ab774cc5b0f15ed04d3803741b6355230130fb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="3f96f-102">Bereitstellen von IP-Adresstypen auf einem Front-End-Server für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f96f-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f96f-103">_**Letztes Änderungsdatum des Themas:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="3f96f-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="3f96f-104">Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Front-End-Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3f96f-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="3f96f-105">So stellen Sie IP-Adressentypen auf einem Front-End-Server bereit</span><span class="sxs-lookup"><span data-stu-id="3f96f-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="3f96f-p101">Klicken Sie unter **Enterprise Edition-Front-End-Pools** mit der rechten Maustaste auf den Server in einem Pool und wählen Sie anschließend **Eigenschaften bearbeiten**. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)</span><span class="sxs-lookup"><span data-stu-id="3f96f-p101">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="3f96f-p102">Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für eine Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="3f96f-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3f96f-110">**Dialogfeld „Eigenschaften bearbeiten“ für den Front-End-Server-Pool**</span><span class="sxs-lookup"><span data-stu-id="3f96f-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="3f96f-111">![Front-End-Server-Dialogfeld ' Eigenschaften bearbeiten] ' (images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front-End-Server-Dialogfeld ' Eigenschaften bearbeiten") '</span><span class="sxs-lookup"><span data-stu-id="3f96f-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="3f96f-p103">**Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f96f-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3f96f-114">Diese Option wird für IP Version 6-Konfigurationen (IPv6) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3f96f-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="3f96f-p104">**Dienstverwendung auf ausgewählte IP-Adressen begrenzen**. Wählen Sie diese Option, um eine spezifische Adresse zur Verwendung auf dem neuen Server anzugeben. Wenn Sie diese Option auswählen, müssen Sie einen Wert für **Primäre IP-Adresse** angeben.</span><span class="sxs-lookup"><span data-stu-id="3f96f-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="3f96f-p105">**Primäre IP-Adresse**. Geben Sie eine IP-Adresse an, die der Server für sämtliche Kommunikationsvorgänge mit Ausnahme der PSTN (Public Switched Telephone Network, Telefonfestnetz)-Kommunikation verwendet. Die eingegebene IP-Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3f96f-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="3f96f-121">**PSTN-IP-Adresse**.</span><span class="sxs-lookup"><span data-stu-id="3f96f-121">**PSTN IP address**.</span></span> <span data-ttu-id="3f96f-122">Die Installation zusätzlicher Netzwerkschnittstellenkarten (NIC) s zur Unterstützung der Konfiguration der PSTN-IP-Adresse für lync Server 2013 wird in den Serverrollen für festgestellten Vermittlungsserver nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3f96f-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="3f96f-123">Weitere Informationen zu unterstützten NIC-Konfigurationen für lync Server 2013 finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="3f96f-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

