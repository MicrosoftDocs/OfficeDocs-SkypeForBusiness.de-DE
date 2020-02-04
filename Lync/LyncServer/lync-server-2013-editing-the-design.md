---
title: 'Lync Server 2013: Bearbeiten des Entwurfs'
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
ms.openlocfilehash: dfce3bc4242140364005a9a981282ecb90a42d3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="a081a-102">Bearbeiten des Entwurfs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a081a-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a081a-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a081a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a081a-p101">Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Machen Sie hierzu auf der Seite **Globale Topologie** einen Doppelklick auf den Standort, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a081a-p101">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="a081a-106">Das Planungs Tool zeigt die Standorttopologie für die ausgewählte Website an.</span><span class="sxs-lookup"><span data-stu-id="a081a-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="a081a-107">Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a081a-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="a081a-108">![Standorttopologie des Planungstools](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Standorttopologie des Planungstools")</span><span class="sxs-lookup"><span data-stu-id="a081a-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="a081a-109">Standorttopologie - Die aktuell angezeigte Seite mit einer optischen Übersicht der empfohlenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="a081a-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="a081a-110">Edge-Netzwerkdiagramm – auf der Seite "Edge-Netzwerkdiagramm" werden die meisten Aufgaben im Planungs Tool vom Designer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a081a-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="a081a-111">Das Diagramm zeigt die Netzwerkkonfiguration für eine empfohlene lync Server 2013-Topologie mit bearbeitbaren Einträgen für IP-Adressen und FQDNs für Server, Pool sowie Hardware-und DNS-Lastenausgleichssysteme (Domain Name System) an.</span><span class="sxs-lookup"><span data-stu-id="a081a-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="a081a-112">Edgeverwaltungsbericht - Der Edgeverwaltungsbericht umfasst insgesamt vier Berichte:</span><span class="sxs-lookup"><span data-stu-id="a081a-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="a081a-113">![Seite "Edge-Administrator Bericht"](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Seite "Edge-Administrator Bericht"")</span><span class="sxs-lookup"><span data-stu-id="a081a-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="a081a-p104">Zusammenfassungsbericht – Ein allgemeiner Bericht zu den Einstellungen der Edgenetzwerkkonfiguration. Wenn Sie auf der Seite **Edge-Netzwerkdiagramm** die TCP-IP- und FQDN-Werte der Topologie in die der tatsächlichen Bereitstellung ändern, werden diese Adressen und Namen hier dargestellt. Andernfalls wird hier der Standardtext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a081a-p104">Summary Report – A general report of settings for the Edge network configuration. If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here. Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="a081a-117">Zertifikatbericht - Der Zertifikatbericht führt den Antragstellernamen und alternative Antragstellernamen für die Zertifikate auf, die für die Topologie benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a081a-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="a081a-p105">Firewallbericht - Im Firewallbericht werden Informationen aufgeführt, die zum Konfigurieren von Umkreisfirewalls in der Infrastruktur benötigt werden. Diese umfassen die IP-Adressen (entweder die Standardwerte oder die bearbeiteten Werte), Serverrolle, Quell-IP und Port, Ziel-IP und Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.</span><span class="sxs-lookup"><span data-stu-id="a081a-p105">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure. This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="a081a-p106">DNS-Bericht - Im DNS-Bericht werden Informationen zu den DNS-Einträgen aufgeführt, die Sie erstellen müssen. Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.</span><span class="sxs-lookup"><span data-stu-id="a081a-p106">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create. The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="a081a-p107">Standortzusammenfassung – Die Standortzusammenfassung liefert einen Überblick über die Auswahl, die entweder bei den anfänglichen Fragen oder durch Angeben der Werte in **Websites entwerfen** getroffen wurde. Es werden auch Kapazitätsinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a081a-p107">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**. Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a081a-124">Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.</span><span class="sxs-lookup"><span data-stu-id="a081a-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="a081a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a081a-125">See Also</span></span>


[<span data-ttu-id="a081a-126">Bearbeiten des Netzwerk Konfigurations Diagramms in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a081a-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

