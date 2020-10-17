---
title: Konfigurieren von Testbenutzern und Konfigurationseinstellungen für Watcher-Knoten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ecb6946bcbb7244ef3e5ef8504312063ab1bd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507522"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="610fd-102">Konfigurieren von Testbenutzern und Konfigurationseinstellungen für Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="610fd-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="610fd-103">_**Letztes Änderungsstand des Themas:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="610fd-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="610fd-104">Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="610fd-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="610fd-105">Erstellen Sie die von diesen Watcher-Knoten zu verwendenden Testkonten.</span><span class="sxs-lookup"><span data-stu-id="610fd-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="610fd-106">Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="610fd-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="610fd-107">Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.</span><span class="sxs-lookup"><span data-stu-id="610fd-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="610fd-108">In diesem Abschnitt werden folgende Themen behandelt:</span><span class="sxs-lookup"><span data-stu-id="610fd-108">This section covers:</span></span>

  - <span data-ttu-id="610fd-109">Konfigurieren von Testbenutzerkonten</span><span class="sxs-lookup"><span data-stu-id="610fd-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="610fd-110">Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen</span><span class="sxs-lookup"><span data-stu-id="610fd-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="610fd-111">Konfigurieren erweiterter Tests</span><span class="sxs-lookup"><span data-stu-id="610fd-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="610fd-112">Hinzufügen und Entfernen synthetischer Transaktionen</span><span class="sxs-lookup"><span data-stu-id="610fd-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="610fd-113">Anzeigen und Testen der Konfiguration des Watcher-Knotens</span><span class="sxs-lookup"><span data-stu-id="610fd-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="610fd-114">Konfigurieren von Testbenutzerkonten</span><span class="sxs-lookup"><span data-stu-id="610fd-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="610fd-115">Test Benutzer müssen keine tatsächlichen Personen darstellen, Sie müssen jedoch Active Directory-Domänendienste Konten gültig sein; Darüber hinaus müssen diese Konten für lync Server 2013 aktiviert sein, Sie müssen über gültige SIP-Adressen verfügen und für Enterprise-VoIP aktiviert sein (für die Verwendung der Test-CsPstnPeerToPeerCall synthetischen Transaktion).</span><span class="sxs-lookup"><span data-stu-id="610fd-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="610fd-116">Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind und gemäß den Angaben in diesem  Dokument konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="610fd-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="610fd-117">Sie sollten für jeden zu testenden Pool mindestens drei Testbenutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="610fd-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="610fd-118">Wenn Sie die Negotiate-Authentifizierungsmethode verwenden, müssen Sie auch das Cmdlet " **CsTestUserCredential** " und die lync Server-Verwaltungsshell verwenden, damit diese Testkonten mit den synthetischen Transaktionen arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="610fd-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="610fd-119">Dazu können Sie einen Befehl ausführen, der dem Folgenden ähnelt.</span><span class="sxs-lookup"><span data-stu-id="610fd-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="610fd-120">(Bei diesen Befehlen wird davon ausgegangen, dass die drei Active Directory Benutzerkonten bereits erstellt wurden und diese Konten für lync Server 2013 aktiviert wurden.):</span><span class="sxs-lookup"><span data-stu-id="610fd-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="610fd-121">Beachten Sie, dass Sie nicht nur die SIP-Adresse, sondern auch den Benutzernamen und das Kennwort einbeziehen müssen.</span><span class="sxs-lookup"><span data-stu-id="610fd-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="610fd-122">Wenn Sie das Kennwort nicht einschließen Set-CsTestUserCredential werden Sie zur Eingabe dieser Informationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="610fd-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="610fd-123">Der Benutzername kann mit dem oben aufgeführten Domänennamen \\ -Benutzernamenformat oder mit dem Format User Name@Domain Name angegeben werden; Beispiel:</span><span class="sxs-lookup"><span data-stu-id="610fd-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="610fd-124">Um sicherzustellen, dass die Testbenutzer Anmeldeinformationen erstellt wurden, führen Sie diese Befehle in der lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="610fd-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="610fd-125">Daraufhin sollten für jeden Benutzer Informationen zurückgegeben werden, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="610fd-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="610fd-126">Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen</span><span class="sxs-lookup"><span data-stu-id="610fd-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="610fd-127">Nachdem die Testbenutzer erstellt wurden, können Sie mithilfe eines Befehls, der dem Folgenden ähnelt, einen Watcher-Knoten erstellen:</span><span class="sxs-lookup"><span data-stu-id="610fd-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="610fd-128">Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt.</span><span class="sxs-lookup"><span data-stu-id="610fd-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="610fd-129">Für den neuen Watcher-Knoten werden zudem die Testbenutzer "watcher1@litwareinc.com", "watcher2@litwareinc.com" und "watcher3@litwareinc.com" verwendet.</span><span class="sxs-lookup"><span data-stu-id="610fd-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="610fd-130">Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, können die drei Testkonten alle gültigen Benutzerkonten sein, die für Active Directory und lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="610fd-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="610fd-131">Wenn der Watcher-Knoten die Aushandlungsauthentifizierungsmethode verwendet, müssen Sie diese Benutzerkonten auch für den Watcher-Knoten aktivieren, indem Sie das Cmdlet **Set-CsTestUserCredential** verwenden.</span><span class="sxs-lookup"><span data-stu-id="610fd-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="610fd-132">Konfigurieren erweiterter Tests</span><span class="sxs-lookup"><span data-stu-id="610fd-132">Configuring Extended Tests</span></span>

<span data-ttu-id="610fd-133">Wen Sie den PSTN-Test (Public Switched Telephone Network, Telefonfestnetz) aktivieren möchten, mit dessen Hilfe die Verbindung mit dem Telefonfestnetz überprüft wird, müssen Sie beim Einrichten des Watcher-Knotens einige zusätzliche Konfigurationsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="610fd-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="610fd-134">Zuerst müssen Sie die Testbenutzer dem PSTN-Testtyp zuweisen.</span><span class="sxs-lookup"><span data-stu-id="610fd-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="610fd-135">Führen Sie dazu einen Befehl wie den folgenden aus dem lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="610fd-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="610fd-136">Beachten Sie, dass die Ergebnisse dieses Befehls in einer Variable gespeichert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="610fd-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="610fd-137">In diesem Beispiel handelt es sich dabei um die Variable "$pstnTest".</span><span class="sxs-lookup"><span data-stu-id="610fd-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="610fd-138">Zu diesem Zeitpunkt können Sie das Cmdlet **New-CsWatcherNodeConfiguration** verwenden, um den in der Variablen $pstnTest gespeicherten Testtyp einem lync Server 2013-Pool zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="610fd-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="610fd-139">Mithilfe des folgenden Befehls wird beispielsweise eine neue Watcher-Knotenkonfiguration für den Pool "atl-cs-001.litwareinc.com" erstellt, wobei die drei zuvor erstellten Testbenutzer und der PSTN-Testtyp hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="610fd-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="610fd-140">Beachten Sie, dass der obige Befehl fehlschlägt, wenn Sie die lync Server Kerndateien und die RTCLocal-Datenbank nicht auf dem Watcher-Knoten Computer installiert haben.</span><span class="sxs-lookup"><span data-stu-id="610fd-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="610fd-141">Wenn Sie mehrere VoIP-Richtlinien testen möchten, müssen Sie für alle Richtlinien mithilfe des Cmdlets **New-CsExtendedTest** einen erweiterten Test erstellen.</span><span class="sxs-lookup"><span data-stu-id="610fd-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="610fd-142">Die diesem Test zugewiesenen Benutzer müssen mit den gewünschten VoIP-Richtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="610fd-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="610fd-143">Anschließend werden die erweiterten Tests mithilfe eines Befehls, der dem Folgenden ähnelt, an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben:</span><span class="sxs-lookup"><span data-stu-id="610fd-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="610fd-p110">Wenn "New-CsWatcherNodeConfiguration" ohne den Parameter "Tests" aufgerufen wird, bedeutet dies, dass für den neuen Watcher-Knoten nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) aktiviert werden. Demnach testet der Watcher-Knoten die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="610fd-p110">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="610fd-146">Registrierung</span><span class="sxs-lookup"><span data-stu-id="610fd-146">Registration</span></span>

  - <span data-ttu-id="610fd-147">Chat</span><span class="sxs-lookup"><span data-stu-id="610fd-147">IM</span></span>

  - <span data-ttu-id="610fd-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="610fd-148">GroupIM</span></span>

  - <span data-ttu-id="610fd-149">P2PAV (Peer-zu-Peer-Audio/Videositzungen)</span><span class="sxs-lookup"><span data-stu-id="610fd-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="610fd-150">AvConference (Audio/Konferenzen)</span><span class="sxs-lookup"><span data-stu-id="610fd-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="610fd-151">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="610fd-151">Presence</span></span>

  - <span data-ttu-id="610fd-152">ABS (Adressbuchdienst)</span><span class="sxs-lookup"><span data-stu-id="610fd-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="610fd-153">ABWQ (Adressbuchwebdienst)</span><span class="sxs-lookup"><span data-stu-id="610fd-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="610fd-p111">PSTN (PSTN-Gatewayanrufe, angegeben als erweiterter Test. PSTN ist standardmäßig deaktiviert. Der Test wird in diesem Fall nur aktiviert, weil der Befehl PSTN mithilfe des Parameters "ExtendedTests" aktiviert hat.)</span><span class="sxs-lookup"><span data-stu-id="610fd-p111">PSTN (PSTN gateway calls, specified as an extended test. By default, PSTN is disabled. The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="610fd-157">Dies bedeutet auch, dass die folgenden Komponenten standardmäßig nicht getestet werden:</span><span class="sxs-lookup"><span data-stu-id="610fd-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="610fd-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="610fd-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="610fd-159">MCXP2PIM (Instant Messaging für mobile Geräte)</span><span class="sxs-lookup"><span data-stu-id="610fd-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="610fd-160">ExumConnectivity (Exchange Unified Messaging)</span><span class="sxs-lookup"><span data-stu-id="610fd-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="610fd-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="610fd-161">JoinLauncher</span></span>

  - <span data-ttu-id="610fd-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="610fd-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="610fd-163">Dataconference</span><span class="sxs-lookup"><span data-stu-id="610fd-163">DataConference</span></span>

  - <span data-ttu-id="610fd-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="610fd-164">XmppIM</span></span>

  - <span data-ttu-id="610fd-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="610fd-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="610fd-166">Hinzufügen und Entfernen synthetischer Transaktionen</span><span class="sxs-lookup"><span data-stu-id="610fd-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="610fd-167">Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie dem Knoten mithilfe des Cmdlets **Set-CsWatcherNodeConfiguration** synthetische Transaktionen hinzufügen oder Knoten daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="610fd-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="610fd-168">Wenn Sie beispielsweise dem Watcher-Knoten den Test "PersistentChatMessage" hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="610fd-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="610fd-p113">Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="610fd-p113">Multiple tests can be added by separating the test names by using commas. For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="610fd-p114">Beachten Sie, dass ein Fehler auftritt, wenn einer oder mehrere dieser Tests (z. B. "DataConference") bereits für den Watcher-Knoten aktiviert wurden. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="610fd-p114">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="610fd-173">Wenn dieser Fehler auftritt, werden keine Änderungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="610fd-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="610fd-174">Führen Sie den Befehl erneut aus, nachdem Sie den doppelten Test entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="610fd-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="610fd-p116">Wenn Sie eine synthetische Transaktion aus einem Watcher-Knoten entfernen möchten, verwenden Sie anstelle der Add-Methode die Remove-Methode. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:</span><span class="sxs-lookup"><span data-stu-id="610fd-p116">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method. For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="610fd-p117">Sie können auch die Replace-Methode verwenden, um alle momentan aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise möchten, dass ein Watcher-Knoten nur den IM-Test ausführt, können Sie dieses Verhalten mithilfe des folgenden Befehls konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="610fd-p117">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="610fd-179">Wenn Sie den zuvor aufgeführten Befehl ausführen, werden mit Ausnahme von IM alle synthetischen Transaktionen für den angegebenen Watcher-Knoten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="610fd-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="610fd-180">Anzeigen und Testen der Konfiguration des Watcher-Knotens</span><span class="sxs-lookup"><span data-stu-id="610fd-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="610fd-181">Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="610fd-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="610fd-182">Mithilfe des zuvor genannten Befehls werden je nach den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, Informationen zurückgegeben, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="610fd-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> <span data-ttu-id="610fd-183">Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="610fd-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="610fd-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span><span class="sxs-lookup"><span data-stu-id="610fd-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="610fd-185">Um zu überprüfen, ob ein Watcher-Knoten erstellt wurde, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="610fd-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="610fd-186">Daraufhin werden Informationen zurückgegeben, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="610fd-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="610fd-187">Um zu überprüfen, ob der Watcher-Knoten ordnungsgemäß konfiguriert wurde, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="610fd-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="610fd-188">Mithilfe des vorherigen Befehls werden alle Watcher-Knoten in Ihrer Bereitstellung getestet, und Sie erhalten Informationen zu Folgendem:</span><span class="sxs-lookup"><span data-stu-id="610fd-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="610fd-189">Ob die erforderliche Registrar-Rolle installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="610fd-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="610fd-190">Ob der erforderliche Registrierungsschlüssel für Sie erstellt wurde, als Sie "Set-CsWatcherNodeConfiguration" ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="610fd-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="610fd-191">Auf Ihren Servern wird die richtige Version von lync Server.</span><span class="sxs-lookup"><span data-stu-id="610fd-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="610fd-192">Ob Ihre Ports ordnungsgemäß konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="610fd-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="610fd-193">Ob die zugewiesenen Testbenutzer über die erforderlichen Anmeldeinformationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="610fd-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

