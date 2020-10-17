---
title: 'Lync Server 2013: Bearbeiten des Entwurfs'
description: 'Lync Server 2013: Bearbeiten des Designs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20462c1c1813551159e8eeb3b255bd9069e3cce1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570621"
---
# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="0098d-103">Bearbeiten des Entwurfs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0098d-103">Editing the design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0098d-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0098d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0098d-105">Nach Abschluss der ersten Interview Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen für die Website bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0098d-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="0098d-106">Doppelklicken Sie hierzu auf der Seite **Globale Topologie** auf den Standort, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="0098d-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="0098d-107">Das Planungs Tool zeigt die Standorttopologie für den ausgewählten Standort an.</span><span class="sxs-lookup"><span data-stu-id="0098d-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="0098d-108">Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0098d-108">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="0098d-109">![Planungs Tool-Standorttopologie](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planungs Tool-Standorttopologie")</span><span class="sxs-lookup"><span data-stu-id="0098d-109">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="0098d-110">Standorttopologie – Die aktuell angezeigte Seite mit einer optischen Übersicht der empfohlenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="0098d-110">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="0098d-111">Edge-Netzwerkdiagramm – die Seite "Netzplandiagramm für Edge" ist der Ort, an dem der Designer den Großteil der Arbeit im Planungs Tool ausführt.</span><span class="sxs-lookup"><span data-stu-id="0098d-111">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="0098d-112">Das Diagramm zeigt die Netzwerkkonfiguration für eine empfohlene lync Server 2013 Topologie mit editierbaren Einträgen für IP-Adressen und FQDNs für Server, Pools und sowohl Hardware-als auch Domain Name System (DNS) Lastenausgleich an.</span><span class="sxs-lookup"><span data-stu-id="0098d-112">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="0098d-113">Edgeverwaltungsbericht – Der Edgeverwaltungsbericht umfasst insgesamt vier Berichte:</span><span class="sxs-lookup"><span data-stu-id="0098d-113">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="0098d-114">![Seite "Edge-Administrator Bericht"](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Seite "Edge-Administrator Bericht"")</span><span class="sxs-lookup"><span data-stu-id="0098d-114">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="0098d-115">Zusammenfassungsbericht – Ein allgemeiner Bericht zu den Einstellungen der Edgenetzwerkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="0098d-115">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="0098d-116">Wenn Sie die Werte auf der Seite **Netzwerkdiagramm für Edge** mit der Topologie TCP/IP und FQDN von, die in der eigentlichen Bereitstellung verwendet werden, bearbeiten, werden diese Adressen und Namen hier dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0098d-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="0098d-117">Andernfalls wird der Standardtext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0098d-117">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="0098d-118">Zertifikatbericht – Der Zertifikatbericht führt den Antragstellernamen und alternative Antragstellernamen für die Zertifikate auf, die für die Topologie benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="0098d-118">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="0098d-119">Firewallbericht – Im Firewallbericht werden Informationen aufgeführt, die zum Konfigurieren von Umkreisfirewalls in der Infrastruktur benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="0098d-119">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="0098d-120">Dies umfasst die IP-Adressen (entweder die Standardwerte oder bearbeiteten Werte), Serverrolle, Quell-IP und Port, Ziel-IP und Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.</span><span class="sxs-lookup"><span data-stu-id="0098d-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="0098d-121">DNS-Bericht – der DNS-Bericht enthält relevante Informationen zu den DNS-Einträgen, die Sie erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="0098d-121">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="0098d-122">Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.</span><span class="sxs-lookup"><span data-stu-id="0098d-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="0098d-123">Website Zusammenfassung – die Website Zusammenfassung enthält eine Übersicht über die Auswahl, die Sie entweder bei der Beantwortung der anfänglichen Interview Fragen oder beim Ausfüllen der Werte in **Design Websites**getroffen haben.</span><span class="sxs-lookup"><span data-stu-id="0098d-123">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="0098d-124">Kapazitätsinformationen werden ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0098d-124">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0098d-125">Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.</span><span class="sxs-lookup"><span data-stu-id="0098d-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="0098d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0098d-126">See Also</span></span>


[<span data-ttu-id="0098d-127">Bearbeiten des Netzwerk Konfigurations Diagramms in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0098d-127">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

