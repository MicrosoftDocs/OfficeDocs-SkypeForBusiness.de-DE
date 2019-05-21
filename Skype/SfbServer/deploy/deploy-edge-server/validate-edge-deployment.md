---
title: Überprüfen Ihrer Edge-Bereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie überprüfen können, ob Ihre Bereitstellung des Edge-Servers oder des Edge-Server-Pools in Skype for Business Server funktioniert.'
ms.openlocfilehash: 0c432cba78e97add71bb7c4e21e155f92c9fe66a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306888"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="38817-103">Überprüfen Ihrer Edge-Bereitstellung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38817-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="38817-104">**Zusammenfassung:** Erfahren Sie, wie Sie überprüfen können, ob Ihre Bereitstellung des Edge-Servers oder des Edge-Server-Pools in Skype for Business Server funktioniert.</span><span class="sxs-lookup"><span data-stu-id="38817-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="38817-105">Nachdem Sie Ihren Edge-Server oder Edge-Server-Pool bereitgestellt haben, müssen Sie wissen, ob er ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="38817-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="38817-106">Hier sind ein paar Dinge, die Ihnen helfen können, zu bestätigen, dass Ihre Edge-Umgebung mit ihren internen Servern verbunden ist, und dass Ihre externen Benutzer auch über Ihren Edge eine Verbindung mit Ihrer Skype for Business Server-Umgebung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="38817-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="38817-107">Überprüfen der Konnektivität zwischen Ihren internen Servern und Ihren Edgeservern</span><span class="sxs-lookup"><span data-stu-id="38817-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="38817-108">Während die Überprüfung der Konnektivität automatisch im Edge-Server oder im Edge-Server-Pool erfolgt, wenn die Edgeserver installiert sind, können Sie dies mit Windows PowerShell dennoch selbst bestätigen.</span><span class="sxs-lookup"><span data-stu-id="38817-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="38817-109">Führen Sie das Cmdlet "Get-CsManagementStoreReplicationStatus" auf dem internen Server mit dem zentralen Verwaltungsspeicher oder einem beliebigen Domänen verbundenen Computer aus, auf dem die Skype for Business Server Core-Komponenten (OcsCore. msi) installiert sind.</span><span class="sxs-lookup"><span data-stu-id="38817-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="38817-p103">Das erste Ergebnis beim Ausführen dieses Befehls kann für Replikation der Status „False“ statt „True“ sein. Führen Sie das cmdlet Invoke-CsManagementStoreReplication aus, wenn das der Fall ist. Lassen Sie ausreichend Zeit für den Abschluss der Replikation und führen Sie dann das cmdlet Get-CsManagementStoreReplicationStatus erneut aus.</span><span class="sxs-lookup"><span data-stu-id="38817-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="38817-113">Überprüfen der Konnektivität für Ihre externen Benutzer</span><span class="sxs-lookup"><span data-stu-id="38817-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="38817-114">Wir verfügen über ein großartiges Tool zur Bestätigung Ihrer Edge-Server-Konfiguration und die Möglichkeit, die richtigen Nachrichten für Edge-Server-Szenarien zu verbinden, zu senden und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="38817-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="38817-115">Es handelt sich um die [Anaylzer-Website für Remote Konnektivität](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="38817-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="38817-116">Dieser Standort wird vom Microsoft-Support verwaltet.</span><span class="sxs-lookup"><span data-stu-id="38817-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="38817-117">Um dieses Instrument zu verwenden, öffnen Sie die Website in einem Browser und folgen Sie den Anweisungen zum Auswählen des richtigen Szenarios.</span><span class="sxs-lookup"><span data-stu-id="38817-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="38817-118">Zu beachtende Punkte beim Testen der Konnektivität für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="38817-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="38817-119">Jegliche Tests für den Zugriff durch externe Benutzer müssen sämtliche Typen interner Benutzer umfassen, die von Ihrer Organisation unterstützt werden. Dazu können einer oder alle der folgenden Typen zählen:</span><span class="sxs-lookup"><span data-stu-id="38817-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="38817-120">Benutzer aus mindestens einer Partnerdomäne (wir empfehlen, dass Sie alle testen)</span><span class="sxs-lookup"><span data-stu-id="38817-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="38817-121">Anonyme Benutzer.</span><span class="sxs-lookup"><span data-stu-id="38817-121">Anonymous users.</span></span>
    
- <span data-ttu-id="38817-122">Benutzer in Ihrer Organisation, die in Skype for Business Remote angemeldet sind, aber keine VPN-Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="38817-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="38817-123">Mit diesen Tests wird ermittelt, ob der Edgeserver wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="38817-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="38817-124">Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="38817-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="38817-125">Zum Beispiel: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="38817-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="38817-126">Je nach Bereitstellung sollten Sie den vorhergehenden Test für die Ports ausführen, die Sie auf Ihrem Edge-Server oder Edge-Server-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="38817-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="38817-127">Ausführen einer präzisen externen DNS-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="38817-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="38817-128">Pingen Sie von außerhalb Ihres Netzwerks alle externen FQDNs Ihres Edge-Servers oder Edge-Server-Pools.</span><span class="sxs-lookup"><span data-stu-id="38817-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="38817-129">Auch wenn der Ping-Fehler fehlschlägt, werden die IP-Adressen angezeigt, die Sie mit den zuvor zugewiesenen IP-Adressen vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="38817-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

