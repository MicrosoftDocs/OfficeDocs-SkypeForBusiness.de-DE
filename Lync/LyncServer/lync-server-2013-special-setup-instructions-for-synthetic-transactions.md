---
title: 'Lync Server 2013: spezielle Einrichtungsanweisungen für synthetische Transaktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92786b50bc0b29fe5bc7f6b5b8ac978a17085aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="82e42-102">Spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82e42-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82e42-103">_**Letztes Änderungsstand des Themas:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="82e42-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="82e42-p101">Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ohne größere Umstände ausgeführt werden. Das bedeutet, sobald eine synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wurde, kann sie vom Watcher-Knoten bei seinen Testdurchläufen eingesetzt werden. Allerdings gilt dies nicht für alle synthetischen Transaktionen. Für welche synthetischen Transaktionen spezielle Einrichtungsschritte erforderlich sind, wird in den nächsten Abschnitten erklärt.</span><span class="sxs-lookup"><span data-stu-id="82e42-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="82e42-107">Umgang mit Server Timeout Fehlern</span><span class="sxs-lookup"><span data-stu-id="82e42-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="82e42-108">In einigen Fällen können Sie feststellen, dass Ihre synthetischen Transaktionen mit Servertimeout Fehlern fehlschlagen (Fehlercode 504).</span><span class="sxs-lookup"><span data-stu-id="82e42-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="82e42-109">Diese Fehler sind in der Regel auf Firewall-Probleme zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="82e42-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="82e42-110">Wenn eine synthetische Transaktion ausgeführt wird, wird diese Transaktion unter dem Prozess Monitoringhost. exe ausgeführt; im Gegenzug startet MonitoringHost. exe eine Instanz des PowerShell. exe-Prozesses.</span><span class="sxs-lookup"><span data-stu-id="82e42-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="82e42-111">Wenn entweder MonitoringHost. exe oder PowerShell. exe von Ihrer Firewall blockiert wird, schlägt die synthetische Transaktion fehl, und es wird ein 504-Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="82e42-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="82e42-112">Um dieses Problem zu beheben, sollten Sie manuell eingehende Firewallregeln für MonitoringHost. exe und PowerShell. exe auf dem lokalen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="82e42-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="82e42-113">Dies kann in Abhängigkeit von der bereits vorhandenen Konfiguration des Servers über die Windows-Firewall oder eine lokale Firewallsoftware eines Drittanbieters erfolgen.</span><span class="sxs-lookup"><span data-stu-id="82e42-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="82e42-114">Wenn Sie ein Netzwerkfirewall-Gerät zwischen dem Hostcomputer der synthetischen Transaktion und den lync-Servern verwenden, die Sie überwachen möchten, sollten Sie den Host als Clientcomputer behandeln und alle Firewall-Portanforderungen von [Ports und Protokollen für interne Server in lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md)beobachten.</span><span class="sxs-lookup"><span data-stu-id="82e42-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="82e42-115">Synthetische Transaktion für Datenkonferenzen</span><span class="sxs-lookup"><span data-stu-id="82e42-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="82e42-116">Wenn sich der Monitor Knoten Computer außerhalb des Umkreisnetzwerks befindet, können Sie die synthetische Datenkonferenz-Transaktion möglicherweise nur ausführen, wenn Sie zuerst die Internet Explorer Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="82e42-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="82e42-117">Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="82e42-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="82e42-118">Klicken Sie auf dem Computer mit den Watcher-Knoten auf **Start**, **Alle Programme**, **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="82e42-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="82e42-119">Geben Sie in dem Konsolenfenster den folgenden Befehl ein, und drücken Sie anschließend die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="82e42-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="82e42-120">Die folgende Meldung wird im Befehlsfenster angezeigt:</span><span class="sxs-lookup"><span data-stu-id="82e42-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="82e42-121">Diese Meldung bedeutet, dass Sie die Internet Explorer Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="82e42-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="82e42-122">Synthetische Transaktionen für Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="82e42-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="82e42-123">Die Exchange Unified Messaging (um) synthetische Transaktion überprüft, ob Testbenutzer eine Verbindung mit Voicemail-Konten herstellen können, die in Exchange verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="82e42-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="82e42-124">Diese Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert werden, bevor sie die Exchange-UM-Tests verwenden können.</span><span class="sxs-lookup"><span data-stu-id="82e42-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="82e42-125">Synthetische Transaktionen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="82e42-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="82e42-126">Um die synthetische persistent Chat-Transaktion zu verwenden, müssen Administratoren zunächst einen Kanal erstellen und den Testbenutzern Berechtigungen zur Verwendung geben.</span><span class="sxs-lookup"><span data-stu-id="82e42-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="82e42-127">Das Cmdlet [Test-cspersistentchatmessage "](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) kann verwendet werden, um diese Testbenutzer ordnungsgemäß zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="82e42-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="82e42-128">Diese Einrichtungsaufgabe muss auf einem Computer innerhalb des Unternehmens durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="82e42-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="82e42-129">Wenn das Cmdlet auf einem Computer ausgeführt wird, der kein Server ist, muss der entsprechende Benutzer bei rollenbasierter Zugriffssteuerung (RBAC) Mitglied der Rolle "PersistentChatAdministrators" sein.</span><span class="sxs-lookup"><span data-stu-id="82e42-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="82e42-130">Wenn das Cmdlet auf dem Server selbst ausgeführt wird, sollte der entsprechende Benutzer Mitglied der Gruppe "RTCUniversalServerAdmins" sein.</span><span class="sxs-lookup"><span data-stu-id="82e42-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="82e42-131">In dem oben gezeigten Befehl wurde der Parameter "Setup" eingefügt und auf "True" ($True) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="82e42-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="82e42-132">Wenn Sie den Parameter Setup einschließen, erstellt Test-cspersistentchatmessage "einen speziellen beständigen Chatroom und füllt diesen Raum mit den Testbenutzern auf.</span><span class="sxs-lookup"><span data-stu-id="82e42-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="82e42-133">Dadurch soll sichergestellt werden, dass tatsächlich ein Chatroom für Testzwecke verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="82e42-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="82e42-134">Beachten Sie, dass der Setup-Parameter nur von einem Front-End-Server ausgeführt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="82e42-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="82e42-135">Der per Test-CsPersistentChatMessage erstellte Chatroom kann nur von einem Administrator gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="82e42-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="82e42-136">Synthetische Transaktionen für Peer-zu-Peer-Festnetzanrufe</span><span class="sxs-lookup"><span data-stu-id="82e42-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="82e42-137">Die synthetische [Test-CsPstnPeerToPeerCall-](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Transaktion überprüft die Möglichkeit, Anrufe über das Telefon Festnetz (Public Switched Telephone Network, PSTN) zu tätigen und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="82e42-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="82e42-138">Zum Ausführen dieser synthetischen Transaktion müssen Administratoren Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="82e42-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="82e42-139">Zwei Testbenutzer (ein Anrufer und ein Empfänger), die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="82e42-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="82e42-140">DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="82e42-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="82e42-141">VoIP-Richtlinien und -Routen, über die Anrufer mit der Nummer des Empfängers das PSTN-Gateway erreichen</span><span class="sxs-lookup"><span data-stu-id="82e42-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="82e42-142">Ein PSTN-Gateway, das Anrufe entgegennimmt, und Medien, die Anrufe anhand der gewählten Nummer zurück zum Homepool des Empfängers leiten</span><span class="sxs-lookup"><span data-stu-id="82e42-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="82e42-143">Synthetische Transaktionen für den einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="82e42-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="82e42-144">Die synthetische Transaktion des einheitlichen Kontaktspeichers überprüft, ob lync Server 2013 Kontakte im Namen eines Benutzers aus Microsoft Exchange Server 2013 abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="82e42-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="82e42-145">Für die Verwendung dieser synthetischen Transaktionen müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="82e42-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="82e42-146">Die [Verwaltung der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) muss zwischen lync Server 2013 und Exchange 2013 konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="82e42-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="82e42-147">Test Benutzer müssen über ein gültiges Exchange 2013 Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="82e42-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="82e42-148">Wenn diese Bedingungen erfüllt sind, können Administratoren mit dem folgenden Befehl überprüfen, ob der Benutzer mit der SIP-Adresse "kenmyer@litwareinc.com" seine Kontakte aus dem einheitlichen Kontaktspeicher abrufen kann:</span><span class="sxs-lookup"><span data-stu-id="82e42-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="82e42-149">Beachten Sie die Verwendung des Setup-Parameters im oben gezeigten Befehl.</span><span class="sxs-lookup"><span data-stu-id="82e42-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="82e42-150">Bei Ausführung des Test-CsUnifiedContactStore mit diesem Parameter werden die Kontakte des angegebenen Benutzers (in diesem Fall: sip:kenmyer@litwareinc.com) in den einheitlichen Kontaktspeicher verschoben (falls sie sich nicht bereits dort befinden).</span><span class="sxs-lookup"><span data-stu-id="82e42-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="82e42-151">(Selbstverständlich, wenn sich die Kontakte des Benutzers bereits im einheitlichen Kontaktspeicher befinden, müssen Sie nicht verschoben werden.) Der Setup-Parameter wird in der Regel nur einmal verwendet (das erste Mal, dass Test-CsUnifiedContactStore ausgeführt wird), und sollte nur mit Testbenutzern verwendet werden; Das heißt, mit Benutzerkonten, die nie tatsächlich bei lync Server angemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="82e42-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="82e42-152">Nachdem Ihre Testbenutzer zum einheitlichen Kontaktspeicher migriert wurden, können Sie durch Aufruf von Test-CsUnifiedContactStore ohne Setup-Parameter überprüfen, ob die Kontakte des Benutzers abgerufen werden können:</span><span class="sxs-lookup"><span data-stu-id="82e42-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="82e42-153">Synthetische XMPP-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="82e42-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="82e42-154">Für die synthetischen XMPP-IM-Transaktionen (Extensible Messaging and Presence Protocol) ist es erforderlich, dass die XMPP-Funktion mit einer oder mehreren Verbunddomänen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="82e42-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="82e42-155">Zum Aktivieren der synthetischen XMPP-Transaktion muss der Parameter "XmppTestReceiverMailAddress" mit einem Benutzerkonto bei einer routingfähigen XMPP-Domäne angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="82e42-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="82e42-156">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="82e42-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="82e42-157">In diesem Beispiel muss eine lync Server 2013-Regel vorhanden sein, um Nachrichten für litwareinc.com an ein XMPP-Gateway weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="82e42-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

