---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7705da8beee8f6ee45d74fbdbb6eb03180234a47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="b7da6-102">Bereitstellen von IP-Adresstypen auf einem Vermittlungsserver für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7da6-102">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7da6-103">_**Letztes Änderungsstand des Themas:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="b7da6-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="b7da6-104">Führen Sie mithilfe des Topologie-Generators die Schritte im folgenden Verfahren aus, um IP-Adresstypen auf einem Vermittlungsserver bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b7da6-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="b7da6-105">So stellen Sie IP-Adresstypen auf einem Vermittlungsserver bereit</span><span class="sxs-lookup"><span data-stu-id="b7da6-105">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="b7da6-106">Klicken Sie im Topologie-Generator unter **Vermittlungs Pools**mit der rechten Maustaste auf den Server in einem Pool, und wählen Sie dann **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="b7da6-106">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="b7da6-107">(Wählen Sie alternativ den Server und klicken Sie auf **Eigenschaften bearbeiten** im Menü **Aktion**.)</span><span class="sxs-lookup"><span data-stu-id="b7da6-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="b7da6-p102">Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** den IP-Adressentyp, den Sie konfigurieren möchten. Wählen Sie für Dualstapel-Konfiguration wie in der folgenden Abbildung zu sehen **IPv4 aktivieren** und **IPv6 aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="b7da6-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="b7da6-110">**Das Dialogfeld "Eigenschaften bearbeiten" für den Vermittlungsserverpool**</span><span class="sxs-lookup"><span data-stu-id="b7da6-110">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="b7da6-111">![Lync Server allgemeine Eigenschaftenseite mit FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server allgemeine Eigenschaftenseite mit FQDN")</span><span class="sxs-lookup"><span data-stu-id="b7da6-111">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="b7da6-p103">**Alle konfigurierten IP-Adressen verwenden**. Wählen Sie diese Option, wenn Sie zulassen möchten, dass eine beliebige auf dem Computer festgelegte IP-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b7da6-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b7da6-114">Für IPv6-Konfigurationen wird diese Option empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b7da6-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="b7da6-p104">**Dienstnutzung auf ausgewählte IP-Adressen beschränken**. Aktivieren Sie diese Option, um eine bestimmte IP-Adresse anzugeben, die auf dem neuen Server verwendet werden soll. Bei Auswahl dieser Option müssen Sie einen Wert für die "Primäre IP-Adresse" angeben.</span><span class="sxs-lookup"><span data-stu-id="b7da6-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="b7da6-p105">**Primäre IP-Adresse**. Geben Sie eine IP-Adresse ein, die der Server bei allen Kommunikationsvorgängen außer beim Telefonfestnetz (PSTN) verwenden soll. Die hier eingegebene IP-Adresse muss in dem Format des ausgewählten Adresstyps stehen.</span><span class="sxs-lookup"><span data-stu-id="b7da6-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="b7da6-121">**PSTN-IP-Adresse**.</span><span class="sxs-lookup"><span data-stu-id="b7da6-121">**PSTN IP address**.</span></span> <span data-ttu-id="b7da6-122">Definieren Sie eine PSTN-IP-Adresse, wenn ein Vermittlungsserver eigenständig ist.</span><span class="sxs-lookup"><span data-stu-id="b7da6-122">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="b7da6-123">Diese Adresse muss mit dem Format des ausgewählten Adressentyps übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b7da6-123">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b7da6-124">Die Installation zusätzlicher Netzwerkschnittstellenkarten (NIC) s zur Unterstützung der Konfiguration von PSTN-IP-Adressen für lync Server 2013 wird für zusammengefasste Vermittlungsserver Rollen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b7da6-124">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="b7da6-125">Weitere Informationen zu unterstützten NIC-Konfigurationen für lync Server 2013 finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b7da6-125">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

