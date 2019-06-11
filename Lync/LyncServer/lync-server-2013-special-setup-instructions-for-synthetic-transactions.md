---
title: 'Lync Server 2013: spezielle Setupanweisungen für synthetische Transaktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c2f0f45aa2187f1b47f8dfa81b3ba121388f6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="db91e-102">Spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db91e-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db91e-103">_**Letztes Änderungsdatum des Themas:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="db91e-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="db91e-104">Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ausgeführt werden. Das heißt, sobald die synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wurde, kann der Watcher-Knoten die synthetische Transaktion während der Testdurchläufe verwenden.</span><span class="sxs-lookup"><span data-stu-id="db91e-104">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes.</span></span> <span data-ttu-id="db91e-105">Dies gilt allerdings nicht für alle synthetischen Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="db91e-105">However, this is not true for all synthetic transactions.</span></span> <span data-ttu-id="db91e-106">Die Ausnahmen – synthetische Transaktionen, die spezielle Einrichtungsanweisungen erfordern – werden in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="db91e-106">The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="db91e-107">Umgang mit Server Timeout Fehlern</span><span class="sxs-lookup"><span data-stu-id="db91e-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="db91e-108">In einigen Fällen stellen Sie möglicherweise fest, dass Ihre synthetischen Transaktionen mit Servertimeout Fehlern fehlschlagen (Fehlercode 504).</span><span class="sxs-lookup"><span data-stu-id="db91e-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="db91e-109">Diese Fehler sind in der Regel auf Firewall-Probleme zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="db91e-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="db91e-110">Wenn eine synthetische Transaktion ausgeführt wird, wird diese Transaktion unter dem Prozess "MonitoringHost. exe" ausgeführt. im Gegenzug startet MonitoringHost. exe eine Instanz des Prozesses "PowerShell. exe".</span><span class="sxs-lookup"><span data-stu-id="db91e-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="db91e-111">Wenn entweder "MonitoringHost. exe" oder "PowerShell. exe" von Ihrer Firewall blockiert wird, schlägt die synthetische Transaktion fehl, und es wird ein 504-Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="db91e-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="db91e-112">Um dieses Problem zu beheben, sollten Sie die eingehenden Firewallregeln sowohl für MonitoringHost. exe als auch für PowerShell. exe auf dem lokalen Computer manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="db91e-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="db91e-113">Dies kann abhängig von der bereits vorhandenen Konfiguration des Servers über die Windows-Firewall oder eine lokale Firewall-Software eines Drittanbieters erfolgen.</span><span class="sxs-lookup"><span data-stu-id="db91e-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="db91e-114">Wenn Sie ein Netzwerkfirewall-Gerät zwischen dem synthetischen Transaktions Hostcomputer und den lync-Servern verwenden, die Sie überwachen möchten, sollten Sie den Host als Clientcomputer behandeln und alle Firewall-Portanforderungen aus [Ports und Protokollen beachten. für interne Server in lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="db91e-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="db91e-115">Synthetische Datenkonferenz Transaktionen</span><span class="sxs-lookup"><span data-stu-id="db91e-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="db91e-116">Wenn sich Ihr Watcher-Knoten Computer außerhalb des Umkreisnetzwerks befindet, können Sie die synthetische Datenkonferenz-Transaktion wahrscheinlich nur ausführen, wenn Sie zuerst die Internet Explorer-Proxyeinstellungen für das Netzwerkdienstkonto deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="db91e-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="db91e-117">Führen Sie die folgenden Schritte aus, um die Proxyeinstellungen für diesen Dienst zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="db91e-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="db91e-118">Klicken Sie auf dem Watcher-Knoten Computer auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="db91e-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="db91e-119">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="db91e-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="db91e-120">Im Befehlsfenster wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="db91e-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="db91e-121">Diese Meldung bedeutet, dass Sie die Internet Explorer-Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="db91e-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="db91e-122">Synthetische Exchange Unified Messaging-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="db91e-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="db91e-123">Die synthetischen Transaktion „Exchange Unified Messaging“ (UM) überprüft, ob Testbenutzer eine Verbindung zu in Exchange geführten Voicemail-Konten herstellen können.</span><span class="sxs-lookup"><span data-stu-id="db91e-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="db91e-124">Diese Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert sein, bevor Sie die Exchange um-Tests verwenden können.</span><span class="sxs-lookup"><span data-stu-id="db91e-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="db91e-125">Synthetische Transaktionen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="db91e-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="db91e-126">Um die synthetische persistent-Chat-Transaktion zu verwenden, müssen Administratoren zunächst einen Kanal erstellen und den Testbenutzern die Berechtigung erteilen, diese zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="db91e-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="db91e-127">Das Cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) kann verwendet werden, um diese Testbenutzer ordnungsgemäß zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="db91e-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="db91e-128">Dieser Einrichtungs Task muss innerhalb des Unternehmens ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="db91e-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="db91e-129">Wenn der Benutzer, der das Cmdlet ausführt, von einem nicht Server basierten Computer ausgeführt wird, muss er Mitglied der Rolle PersistentChatAdministrators für rollenbasierte Zugriffssteuerung sein.</span><span class="sxs-lookup"><span data-stu-id="db91e-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="db91e-130">Wenn vom Server selbst ausgeführt wird, sollte der Benutzer, der das Cmdlet ausführt, ein Mitglied der RTCUniversalServerAdmins-Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="db91e-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="db91e-131">Im vorhergehenden Befehl wurde der Setup-Parameter aufgenommen und auf true ($true) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="db91e-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="db91e-132">Wenn Sie den Setup-Parameter einbeziehen, erstellt Test-CsPersistentChatMessage einen speziellen beständigen Chatroom und füllt diesen Raum mit den Testbenutzern auf.</span><span class="sxs-lookup"><span data-stu-id="db91e-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="db91e-133">Dadurch wird sichergestellt, dass tatsächlich ein Chatroom für Testzwecke zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="db91e-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="db91e-134">Beachten Sie, dass der Setup-Parameter nur von einem Front-End-Server ausgeführt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="db91e-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="db91e-135">Der von Test-CsPersistentChatMessage erstellte Chatroom kann nur von einem Administrator gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="db91e-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="db91e-136">PSTN-Peer-to-Peer-Anruf synthetische Transaktionen</span><span class="sxs-lookup"><span data-stu-id="db91e-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="db91e-137">Die synthetische [Test-CsPstnPeerToPeerCall-](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Transaktion überprüft die Möglichkeit, Anrufe über das öffentlich geschaltete Telefonnetz (PSTN) zu tätigen und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="db91e-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="db91e-138">Zum Ausführen dieser synthetischen Transaktion müssen Administratoren Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="db91e-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="db91e-139">Zwei Testbenutzer (ein Anrufer und ein Empfänger) sind für Enterprise-VoIP aktiviert.</span><span class="sxs-lookup"><span data-stu-id="db91e-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="db91e-140">DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="db91e-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="db91e-141">VoIP-Richtlinien und VoIP-Routen, die Anrufe an die Rufnummer des Empfängers ermöglichen, um das PSTN-Gateway zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="db91e-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="db91e-142">Ein PSTN-Gateway, das Anrufe annimmt, und Medien, die auf der Grundlage der gewählten Nummer Anrufe zurück an den Home-Pool eines Empfängers weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="db91e-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="db91e-143">Synthetische Transaktionen im Unified Contact Store</span><span class="sxs-lookup"><span data-stu-id="db91e-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="db91e-144">Durch die synthetische Unified Contact Store-Transaktion wird überprüft, ob lync Server 2013 Kontakte für einen Benutzer aus Microsoft Exchange Server 2013 abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="db91e-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="db91e-145">Für die Verwendung dieser synthetischen Transaktion müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="db91e-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="db91e-146">[Das Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) muss zwischen lync Server 2013 und Exchange 2013 konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="db91e-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="db91e-147">Test Benutzer müssen über ein gültiges Exchange 2013-Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="db91e-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="db91e-148">Nachdem diese Bedingungen erfüllt sind, können Administratoren den folgenden Befehl ausführen, um zu überprüfen, ob der Benutzer mit der SIP-Adresse kenmyer@litwareinc.com seine Kontakte aus dem Unified Contact Store abrufen kann:</span><span class="sxs-lookup"><span data-stu-id="db91e-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="db91e-149">Beachten Sie die Verwendung des im vorhergehenden Befehl verwendeten Setup-Parameters.</span><span class="sxs-lookup"><span data-stu-id="db91e-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="db91e-150">Wenn der Setup-Parameter beim Ausführen von Test-CsUnifiedContactStore enthalten ist, werden die Kontakte des angegebenen Benutzers (in diesem Fall SIP:kenmyer@litwareinc.com) in den einheitlichen Kontaktspeicher verschoben.</span><span class="sxs-lookup"><span data-stu-id="db91e-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="db91e-151">(Wenn sich die Kontakte des Benutzers bereits im Unified Contact Store befinden, müssen Sie natürlich nicht verschoben werden.) Der Setup-Parameter wird in der Regel nur einmal verwendet (das erste Mal, wenn Test-CsUnifiedContactStore ausgeführt wird), und sollte nur für Testbenutzer verwendet werden. Das heißt, mit Benutzerkonten, die nie tatsächlich bei lync Server angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="db91e-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="db91e-152">Nachdem der Testbenutzer in den einheitlichen Kontaktspeicher migriert wurde, können Sie überprüfen, ob die Kontakte des Benutzers durch Aufrufen von Test-CsUnifiedContactStore ohne den Setup-Parameter abgerufen werden können:</span><span class="sxs-lookup"><span data-stu-id="db91e-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="db91e-153">Synthetische XMPP-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="db91e-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="db91e-154">Die synthetische Transaktion xmpp (Extensible Messaging and Presence Protocol) erfordert, dass das XMPP-Feature mit mindestens einer Föderationsdomäne konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="db91e-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="db91e-155">Zum Aktivieren der synthetischen XMPP-Transaktion muss ein XmppTestReceiverMailAddress-Parameter mit einem Benutzerkonto in einer routingfähigen XMPP-Domäne bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="db91e-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="db91e-156">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="db91e-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="db91e-157">In diesem Beispiel muss eine lync Server 2013-Regel vorhanden sein, damit Nachrichten für litwareinc.com an ein XMPP-Gateway weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="db91e-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

