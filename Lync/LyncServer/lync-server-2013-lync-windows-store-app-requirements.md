---
title: 'Lync Server 2013: lync Windows Store-App-Anforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5e85bf0d6e4281094be562bd94c8e5b76e02453
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="e6976-102">Lync Windows Store-App-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6976-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6976-103">_**Letztes Änderungsstand des Themas:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="e6976-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="e6976-104">Organisationen mit einer lokalen Bereitstellung von lync Server müssen die folgenden Anforderungen erfüllen, um die lync Windows Store-App zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e6976-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6976-105">Führen Sie für lync Server 2010 das kumulative Update für lync Server 2010: Februar 2012 (verfügbar unter <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) oder höher auf allen Servern aus.</span><span class="sxs-lookup"><span data-stu-id="e6976-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="e6976-106">Um Benutzern die Teilnahme an Besprechungen zu ermöglichen, führen Sie das kumulative Update für lync Server 2010: Oktober 2012 (verfügbar unter <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2737915</A>) auf den Servern aus.</span><span class="sxs-lookup"><span data-stu-id="e6976-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="e6976-107">Aktivieren Sie die Auto Ermittlungs-, lync Web App-und webticketdienst-Dienste auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="e6976-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="e6976-108">Aktivieren Sie die Zertifikatauthentifizierung auf dem Front-End-Server oder Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="e6976-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="e6976-109">(Der Benutzerregistrierungsprozess im Front-End-Server oder Front-End-Pool wird häufig als Registrierungsstelle bezeichnet.) Ausführliche Informationen finden Sie unter [Create Registrar Configuration Settings in lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e6976-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="e6976-110">Veröffentlichen Sie die DNS-Aliasressourceneinträge (CNAME) für den AutoErmittlungsdienst.</span><span class="sxs-lookup"><span data-stu-id="e6976-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="e6976-111">Es ist nicht mehr erforderlich, sicherzustellen, dass der Zertifikatsperrlisten-Verteilungspunkt (CRL) für die an lync Server ausgestellten Zertifikate auf eine HTTP-Ressource statt auf eine LDAP-Ressource verweist.</span><span class="sxs-lookup"><span data-stu-id="e6976-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="e6976-112">Stellen Sie jedoch sicher, dass auf den Clientcomputern die neuesten Windows-Updates installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e6976-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="e6976-113">Konfigurieren Sie HTTP-Proxys im Unternehmen, um den lync Server-bezogenen HTTP-Datenverkehr zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="e6976-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="e6976-114">Fügen Sie bei Bedarf Ausnahmen für die Auto Ermittlungs-, lync Web App-und WebTICKET-Dienste hinzu.</span><span class="sxs-lookup"><span data-stu-id="e6976-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="e6976-115">Installieren Sie auf Clients Windows 8.1 und die neueste Version der lync Windows Store-App, um ein Anmeldeproblem zu beheben, das in der Regel bei der Verwendung mehrerer Domänen auftritt (beispielsweise, wenn der SIP-URI **UserA@domainZ.com** ist, die Edgeserver jedoch **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="e6976-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="e6976-116">Wenn Ihre Organisation lync Online oder Microsoft 365 abonniert und Sie Ihren eigenen Domänennamen verwenden, müssen Sie einige zusätzliche Schritte Unternehmen, um Ihr Netzwerk für die AutoErmittlung der lync-Server einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e6976-116">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="e6976-117">Die Anforderungen an die Netzwerkkonfiguration sind für lync Windows Store-Apps und lync auf mobilen Geräten identisch.</span><span class="sxs-lookup"><span data-stu-id="e6976-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e6976-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6976-118">See Also</span></span>


[<span data-ttu-id="e6976-119">Bereitstellen der lync Windows Store-App in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6976-119">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
