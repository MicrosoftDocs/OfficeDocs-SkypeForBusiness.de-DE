---
title: Ausführen der Abwärtskompatibilität für den Server für beständigen Chat
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c96b2ad99ce403df32cc224d854c34160bd6c613
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518092"
---
# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="cc99b-102">Ausführen der Abwärtskompatibilität für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="cc99b-102">Run backward compatibility for Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc99b-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cc99b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cc99b-104">Der Serverendpunkt für beständigen Chat mit lync Server 2013 bietet eine Möglichkeit zum Erstellen einer einfachen URL, die auf einen Serverpool für beständigen Chat zeigt.</span><span class="sxs-lookup"><span data-stu-id="cc99b-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="cc99b-105">Dies ist nützlich für Legacy-Clients (Microsoft Office Communications Server 2007 R2 Gruppenchat Server oder lync Server 2010 Gruppenchat), da Benutzer eine einfache URL in die manuelle Konfiguration eingeben können, wenn Sie versuchen, den Legacy-Client auf einen Computer mit lync 2013, beständigen Chat, zu deuten.</span><span class="sxs-lookup"><span data-stu-id="cc99b-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="cc99b-106">Dieser Endpunkt wird nicht vom beständigen Chat verwendet und ist nur für ältere Clients erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cc99b-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="cc99b-107">Dies ist für die Zwischenzeit nützlich, in der Räume möglicherweise migriert werden, aber die lync 2013 Clients nicht in der gesamten Organisation bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc99b-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="cc99b-108">Benutzer, die lync 2010 Gruppen Chat (Client) durchführen, können dann weiterhin eine Verbindung mit dem Back-End-Server des Servers für beständigen Chat herstellen.</span><span class="sxs-lookup"><span data-stu-id="cc99b-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="cc99b-109">Sie müssen nicht mehrere persistent Chat-Server Endpunkte erstellen; Sie benötigen nur einen für jeden Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="cc99b-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="cc99b-110">Administratoren können mehrere Endpunkte (eine pro Pool) erstellen, ältere Clients können jedoch so konfiguriert werden, dass jeweils nur eine Verbindung mit einem Pool hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cc99b-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="cc99b-111">Im üblichen oder Mainstream-Szenario ist die Legacy-Bereitstellung nur ein Pool.</span><span class="sxs-lookup"><span data-stu-id="cc99b-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="cc99b-112">Eine neue Bereitstellung migriert diesen Pool im Allgemeinen zu einem neuen lync Server 2013 und fügt möglicherweise einige neue Server Pools für beständigen Chat hinzu.</span><span class="sxs-lookup"><span data-stu-id="cc99b-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="cc99b-113">Übliche Szenarien weisen i. d. R. folgendes Muster auf:</span><span class="sxs-lookup"><span data-stu-id="cc99b-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="cc99b-114">Sie verwalten Benutzer mit einem lync Server 2010, einem Gruppenchat Pool und ihren lync 2010 Gruppenchatclients, die eine Verbindung mit diesem Pool herstellen, indem Sie einen bekannten Benutzer verwenden (entweder standardmäßig SIP: OCSChat@ \<domainName\> . com oder ein ähnliches).</span><span class="sxs-lookup"><span data-stu-id="cc99b-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="cc99b-115">Die Benutzer sind SIP-fähige Active Directory-Domänendienste, und der Nachschlage Dienst registriert sich mit diesen, um eingehende Anforderungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="cc99b-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="cc99b-116">Anschließend installieren Sie einen Serverpool für beständiger Chat von lync Server 2013 Server und einen beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="cc99b-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="cc99b-117">Für den Zeitraum, in dem die Benutzer für gewöhnlich offline sind (z. B. am Wochenende) werden folgende Maßnahmen empfohlen:</span><span class="sxs-lookup"><span data-stu-id="cc99b-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="cc99b-118">Deaktivieren Sie lync Server 2010, Gruppen Chat.</span><span class="sxs-lookup"><span data-stu-id="cc99b-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="cc99b-119">Migrieren von Daten aus dem lync Server 2010, Gruppen Chat Pool in den beständiger Chat von lync Server 2013 Server Pool.</span><span class="sxs-lookup"><span data-stu-id="cc99b-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="cc99b-120">Löschen Sie den bekannten Benutzer aus dem Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="cc99b-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="cc99b-121">Erstellen Sie einen neuen *Endpunkt für Vorversionen* mit dem gleichen SIP-URI wie für den zuvor gelöschten bekannten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cc99b-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="cc99b-122">Starten Sie den Server für beständigen Chat lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc99b-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="cc99b-123">Benutzer melden sich mit Ihrem lync 2010 Gruppen Chat (Client) wieder an und stellen eine Verbindung zu Ihren Daten her, ohne dass eine Konfiguration geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="cc99b-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="cc99b-124">Zu einem späteren Zeitpunkt können Sie den lync Server 2010 und Gruppen Chat außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="cc99b-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="cc99b-125">Anschließend können Sie lync Server 2013, beständigen Chat Server bereitstellen und neue beständiger Chat von lync Server 2013 Server Pools installieren.</span><span class="sxs-lookup"><span data-stu-id="cc99b-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="cc99b-126">Ausführliche Informationen zum Migrieren von lync Server 2010, Gruppenchat zu lync Server 2013, beständiger Chat Server, finden Sie unter [Migration from lync Server 2010, Group Chat oder Office Communications Server 2007 R2 Group Chat to lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="cc99b-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="cc99b-127">So führen Sie Abwärtskompatibilität aus (um einen Serverendpunkt für beständigen Chat zu erstellen, der auf einen Serverpool für beständigen Chat verweist, der von Legacy Gruppen-Chat Pool Clients verwendet werden kann):</span><span class="sxs-lookup"><span data-stu-id="cc99b-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="cc99b-128">Konfigurieren Sie als nächstes Clients für beständigen Chat so, dass diese SIP-Adresse als Kontaktobjekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cc99b-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="cc99b-129">Die SIP-Adresse wird mit dem **New-cspersistentchatendpoint "-** Cmdlet für einen bestimmten Server Pool für beständigen Chat erstellt.</span><span class="sxs-lookup"><span data-stu-id="cc99b-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="cc99b-130">Wenn Sie den Server Endpunkt für beständigen Chat mithilfe Windows PowerShell Befehlszeilenschnittstelle hinzufügen möchten, sollten Sie das folgende Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc99b-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="cc99b-131">In diesem Fall konfigurieren Sie das Kontaktobjekt und weisen ihm den Namen "persistentchat" für die Topologie "contoso.com" zu, deren vollqualifizierter Pooldomänenname "pcpool.contoso.com" lautet:</span><span class="sxs-lookup"><span data-stu-id="cc99b-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="cc99b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc99b-132">See Also</span></span>


[<span data-ttu-id="cc99b-133">Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="cc99b-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

