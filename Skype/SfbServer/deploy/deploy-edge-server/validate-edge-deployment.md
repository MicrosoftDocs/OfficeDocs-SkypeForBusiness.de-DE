---
title: Überprüfen der Edgebereitstellung in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Zusammenfassung: Informationen Sie zum Überprüfen, ob Ihre Bereitstellung der Edgeserver oder edgeserverpool Business Server 2015 in Skype funktioniert.'
ms.openlocfilehash: b8adc5e8d652607156d0136671b1f149fbfe27b4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="9fe20-103">Überprüfen der Edgebereitstellung in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fe20-103">Validate your Edge deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9fe20-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie sicherstellen, dass Ihre Bereitstellung der Edgeserver oder edgeserverpool Business Server 2015 in Skype funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9fe20-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9fe20-105">Nachdem Sie den Edge-Server oder Pool von Edge-Server bereitgestellt haben, müssen Sie wissen, ob sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9fe20-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="9fe20-106">Hier sind einige Dinge, die mit bestätigt wird, ist der Edge-Umgebung verbunden helfen kann für den internen Servern und auch, die für externe Benutzer zu Ihrer Skype für Business Server 2015 Umgebung durch Ihre Kante verbinden können.</span><span class="sxs-lookup"><span data-stu-id="9fe20-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server 2015 environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="9fe20-107">Überprüfen der Konnektivität zwischen Ihren internen Servern und Ihren Edgeservern</span><span class="sxs-lookup"><span data-stu-id="9fe20-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="9fe20-108">Während der Überprüfung der Konnektivität automatisch erfolgt in Edgeserver oder edgeserverpool Wenn die Edge-Server installiert sind, können Sie weiterhin dies für sich selbst mit Windows PowerShell überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9fe20-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="9fe20-109">Führen Sie das Get-CsManagementStoreReplicationStatus-Cmdlet auf dem internen Server, der die zentrale Verwaltung gespeichert hat, oder einem beliebigen Computer der Domäne beigetreten sind auf welche Skype für Business Server 2015-Hauptkomponenten (OcsCore.msi) installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9fe20-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server 2015 Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="9fe20-p103">Das erste Ergebnis beim Ausführen dieses Befehls kann für Replikation der Status „False“ statt „True“ sein. Führen Sie das cmdlet Invoke-CsManagementStoreReplication aus, wenn das der Fall ist. Lassen Sie ausreichend Zeit für den Abschluss der Replikation und führen Sie dann das cmdlet Get-CsManagementStoreReplicationStatus erneut aus.</span><span class="sxs-lookup"><span data-stu-id="9fe20-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="9fe20-113">Überprüfen der Konnektivität für Ihre externen Benutzer</span><span class="sxs-lookup"><span data-stu-id="9fe20-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="9fe20-114">Wir haben ein hervorragendes Tool für die Bestätigung der Edge-Server-Konfiguration und die Möglichkeit, eine Verbindung herstellen, Nachrichten senden und empfangen die richtigen für Edge-Server-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="9fe20-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="9fe20-115">Es ist die [Remote Connectivity Anaylzer-Website](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9fe20-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="9fe20-116">Dieser Standort wird vom Microsoft-Support verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9fe20-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="9fe20-117">Um dieses Instrument zu verwenden, öffnen Sie die Website in einem Browser und folgen Sie den Anweisungen zum Auswählen des richtigen Szenarios.</span><span class="sxs-lookup"><span data-stu-id="9fe20-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="9fe20-118">Zu beachtende Punkte beim Testen der Konnektivität für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="9fe20-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="9fe20-119">Jegliche Tests für den Zugriff durch externe Benutzer müssen sämtliche Typen interner Benutzer umfassen, die von Ihrer Organisation unterstützt werden. Dazu können einer oder alle der folgenden Typen zählen:</span><span class="sxs-lookup"><span data-stu-id="9fe20-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="9fe20-120">Benutzer aus mindestens einer Partnerdomäne (wir empfehlen, dass Sie alle testen)</span><span class="sxs-lookup"><span data-stu-id="9fe20-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="9fe20-121">Anonyme Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9fe20-121">Anonymous users.</span></span>
    
- <span data-ttu-id="9fe20-122">Benutzer in Ihrer Organisation, Remote bei Skype für Unternehmen angemeldet sind, aber nicht VPN verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fe20-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="9fe20-123">Diese Tests bestimmt, ob der Edge-Server ist:</span><span class="sxs-lookup"><span data-stu-id="9fe20-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="9fe20-124">Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="9fe20-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="9fe20-125">Zum Beispiel: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="9fe20-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="9fe20-126">Sie sollten des vorstehenden Tests für die Ports ausführen, die Sie auf dem Edge-Server oder Pool für Edge-Server, abhängig von Ihrer Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fe20-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="9fe20-127">Ausführen einer präzisen externen DNS-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="9fe20-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="9fe20-128">Pingen auf außerhalb Ihres Netzwerks aller externen FQDNs der Edge-Server oder Pool für Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="9fe20-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="9fe20-129">Selbst wenn der Ping-Befehl ein Fehler auftritt, sehen Sie die IP-Adressen, denen Sie die IP-Adressen vergleichen können, die Sie zuvor zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="9fe20-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

