---
title: Konfigurieren von Benutzern und Einstellungen für den Watcher-Knotentest
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Zusammenfassung: Konfigurieren von Testbenutzerkonten und Watcher-Knoten Einstellungen für Skype for Business Server synthetischen Transaktionen.'
ms.openlocfilehash: 8b586cf4c1d003bb54afa050469a10eee8d113e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005950"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="8585e-103">Konfigurieren von Benutzern und Einstellungen für den Watcher-Knotentest</span><span class="sxs-lookup"><span data-stu-id="8585e-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="8585e-104">**Zusammenfassung:** Konfigurieren Sie Testbenutzerkonten und Watcher-Knoten Einstellungen für Skype for Business Server synthetischen Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="8585e-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="8585e-105">Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8585e-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="8585e-106">[Konfigurieren Sie Test Benutzerkonten](test-users-and-settings.md#testuser) , die von diesen Watcher-Knoten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8585e-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="8585e-107">Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8585e-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="8585e-108">Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.</span><span class="sxs-lookup"><span data-stu-id="8585e-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="8585e-109">Konfigurieren von Test Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="8585e-109">Configure Test User Accounts</span></span>
<span data-ttu-id="8585e-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="8585e-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="8585e-111">Test Konten müssen keine tatsächlichen Personen darstellen, Sie müssen jedoch Active Directory Konten gültig sein.</span><span class="sxs-lookup"><span data-stu-id="8585e-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="8585e-112">Darüber hinaus müssen diese Konten für Skype for Business Server aktiviert sein, Sie müssen über gültige SIP-Adressen verfügen und für Enterprise-VoIP aktiviert sein (für die Verwendung der synthetischen Test-CsPstnPeerToPeerCall-Transaktion).</span><span class="sxs-lookup"><span data-stu-id="8585e-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="8585e-113">Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind, und Sie wie angegeben konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8585e-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="8585e-114">Sie sollten mindestens zwei Testbenutzer für jeden Pool zuweisen, den Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="8585e-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="8585e-115">Wenn Sie die Negotiate-Authentifizierungsmethode verwenden, müssen Sie auch das Cmdlet "CsTestUserCredential" und die Skype for Business Server-Verwaltungsshell verwenden, damit diese Testkonten mit den synthetischen Transaktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8585e-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="8585e-116">Führen Sie dazu einen Befehl wie den folgenden aus (bei diesen Befehlen wird davon ausgegangen, dass die beiden Active Directory Benutzerkonten erstellt wurden und diese Konten für Skype for Business Server aktiviert sind):</span><span class="sxs-lookup"><span data-stu-id="8585e-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="8585e-117">Sie müssen nicht nur die SIP-Adresse, sondern auch den Benutzernamen und das Kennwort einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="8585e-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="8585e-118">Wenn Sie das Kennwort nicht einschließen, werden Sie vom Cmdlet "CsTestUserCredential" aufgefordert, diese Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="8585e-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="8585e-119">Der Benutzername kann mithilfe des im vorherigen Codeblock angezeigten Namensformats für Domänenname \ Benutzer angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="8585e-120">Um sicherzustellen, dass die Testbenutzer Anmeldeinformationen erstellt wurden, führen Sie diese Befehle in der Skype for Business Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="8585e-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="8585e-121">Informationen wie diese werden für jeden Benutzer zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="8585e-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="8585e-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="8585e-122">**UserName**</span></span>|<span data-ttu-id="8585e-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="8585e-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8585e-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="8585e-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="8585e-125">System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="8585e-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="8585e-126">Konfigurieren eines Basis Monitor Knotens mit den synthetischen Standardtransaktionen</span><span class="sxs-lookup"><span data-stu-id="8585e-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="8585e-127">Nachdem die Testbenutzer erstellt wurden, können Sie einen Watcher-Knoten erstellen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="8585e-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="8585e-128">Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt.</span><span class="sxs-lookup"><span data-stu-id="8585e-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="8585e-129">Der neue Watcher-Knoten verwendet auch die Testbenutzer watcher1@litwareinc.com und watcher2@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8585e-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="8585e-130">Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, können die beiden Testkonten alle gültigen Benutzerkonten sein, die für Active Directory und Skype for Business Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8585e-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="8585e-131">Wenn der Watcher-Knoten die Negotiate-Authentifizierungsmethode verwendet, müssen diese Benutzerkonten auch für den Watcher-Knoten mithilfe des Cmdlets "CsTestUserCredential" aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="8585e-132">Um zu überprüfen, ob die automatische Ermittlung des Ziel Pools zur Anmeldung ordnungsgemäß konfiguriert ist, statt einen Pool direkt zu verwenden, führen Sie stattdessen die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8585e-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="8585e-133">Konfigurieren erweiterter Tests</span><span class="sxs-lookup"><span data-stu-id="8585e-133">Configuring Extended Tests</span></span>

<span data-ttu-id="8585e-134">Wenn Sie den PSTN-Test aktivieren möchten, der die Verbindung mit dem öffentlichen Telefonnetz überprüft, müssen Sie beim Einrichten des Watcher-Knotens eine zusätzliche Konfiguration durchführen.</span><span class="sxs-lookup"><span data-stu-id="8585e-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="8585e-135">Zunächst müssen Sie die Testbenutzer dem PSTN-Testtyp zuordnen, indem Sie einen Befehl wie den folgenden in der Skype for Business Server Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="8585e-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="8585e-136">Die Ergebnisse dieses Befehls müssen in einer Variablen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="8585e-137">In diesem Beispiel wird die Variable $pstnTest benannt.</span><span class="sxs-lookup"><span data-stu-id="8585e-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="8585e-138">Im nächsten Schritt können Sie das Cmdlet **New-CsWatcherNodeConfiguration** verwenden, um den in der Variablen $pstnTest gespeicherten Testtyp einem Skype for Business Server-Pool zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="8585e-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="8585e-139">Mit dem folgenden Befehl wird beispielsweise eine neue Watcher-Knoten Konfiguration für den Pool ATL-CS-001.litwareinc.com erstellt, wobei die beiden zuvor erstellten Testbenutzer hinzugefügt und der PSTN-Testtyp hinzugefügt wurde:</span><span class="sxs-lookup"><span data-stu-id="8585e-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="8585e-140">Der obige Befehl schlägt fehl, wenn Sie die Skype for Business Server Kerndateien und die RTCLocal-Datenbank nicht auf dem Watcher-Knoten Computer installiert haben.</span><span class="sxs-lookup"><span data-stu-id="8585e-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="8585e-141">Um mehrere VoIP-Richtlinien zu testen, können Sie mithilfe des Cmdlets **New-csextendedtest "** einen erweiterten Test für jede Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="8585e-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="8585e-142">Die bereitgestellten Benutzer sollten mit den gewünschten VoIP-Richtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="8585e-143">Die erweiterten Tests werden mithilfe von Kommatrennzeichen an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="8585e-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="8585e-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="8585e-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="8585e-145">Da das **New-CsWatcherNodeConfiguration-** Cmdlet ohne Verwendung des Parameters Tests aufgerufen wurde, werden nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) für den neuen Watcher-Knoten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8585e-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="8585e-146">Daher testet der Watcher-Knoten die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="8585e-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="8585e-147">Registrierung</span><span class="sxs-lookup"><span data-stu-id="8585e-147">Registration</span></span>
    
- <span data-ttu-id="8585e-148">Chat</span><span class="sxs-lookup"><span data-stu-id="8585e-148">IM</span></span>
    
- <span data-ttu-id="8585e-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="8585e-149">GroupIM</span></span>
    
- <span data-ttu-id="8585e-150">P2PAV (Peer-zu-Peer-Audio/Videositzungen)</span><span class="sxs-lookup"><span data-stu-id="8585e-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="8585e-151">AvConference (Audio/Konferenzen)</span><span class="sxs-lookup"><span data-stu-id="8585e-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="8585e-152">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="8585e-152">Presence</span></span>
    
- <span data-ttu-id="8585e-153">ABS (Adressbuchdienst)</span><span class="sxs-lookup"><span data-stu-id="8585e-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="8585e-154">ABWQ (Adressbuchwebdienst)</span><span class="sxs-lookup"><span data-stu-id="8585e-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="8585e-155">Die folgenden Komponenten werden standardmäßig nicht getestet:</span><span class="sxs-lookup"><span data-stu-id="8585e-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="8585e-156">Konferenz</span><span class="sxs-lookup"><span data-stu-id="8585e-156">ASConference</span></span>
    
- <span data-ttu-id="8585e-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="8585e-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="8585e-158">Dataconference</span><span class="sxs-lookup"><span data-stu-id="8585e-158">DataConference</span></span>
    
- <span data-ttu-id="8585e-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="8585e-159">DialinConferencing</span></span>
    
- <span data-ttu-id="8585e-160">ExumConnectivity (Exchange Unified Messaging)</span><span class="sxs-lookup"><span data-stu-id="8585e-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="8585e-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="8585e-161">JoinLauncher</span></span>
    
- <span data-ttu-id="8585e-162">MCXP2PIM (Instant Messaging für ältere Mobile Geräte)</span><span class="sxs-lookup"><span data-stu-id="8585e-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="8585e-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="8585e-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="8585e-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="8585e-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="8585e-165">PSTN (PSTN-Gateway-Anrufe, angegeben als erweiterter Test)</span><span class="sxs-lookup"><span data-stu-id="8585e-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="8585e-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="8585e-166">UcwaConference</span></span>
    
- <span data-ttu-id="8585e-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="8585e-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="8585e-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="8585e-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="8585e-169">Hinzufügen und Entfernen synthetischer Transaktionen</span><span class="sxs-lookup"><span data-stu-id="8585e-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="8585e-170">Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie dem Knoten mithilfe des Cmdlets Set-CsWatcherNodeConfiguration synthetische Transaktionen hinzufügen oder Knoten daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="8585e-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="8585e-171">Wenn Sie beispielsweise dem Watcher-Knoten den Test "PersistentChatMessage" hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="8585e-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="8585e-172">Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen.</span><span class="sxs-lookup"><span data-stu-id="8585e-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="8585e-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8585e-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="8585e-174">Wenn mindestens ein solcher Test (beispielsweise dataconference) auf dem Watcher-Knoten bereits aktiviert wurde, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="8585e-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="8585e-175">In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="8585e-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="8585e-176">CsWatcherNodeConfiguration: Es gibt eine doppelte Schlüsselsequenz "dataconference" für die Key-oder Unique Identity-Einschränkung "urn: Schema: Microsoft. RTC. Management. Settings. WatcherNode. 2010: Testname".</span><span class="sxs-lookup"><span data-stu-id="8585e-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="8585e-177">Wenn dieser Fehler auftritt, werden keine Änderungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="8585e-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="8585e-178">Der Befehl sollte erneut ausgeführt werden, wenn der doppelte Test entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="8585e-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="8585e-179">Verwenden Sie die Remove-Methode, um eine synthetische Transaktion aus einem Watcher-Knoten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8585e-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="8585e-180">Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:</span><span class="sxs-lookup"><span data-stu-id="8585e-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="8585e-181">Sie können die Replace-Methode verwenden, um alle derzeit aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8585e-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="8585e-182">Wenn Sie beispielsweise einen Watcher-Knoten nur zum Ausführen des Sofortnachrichten Tests verwenden möchten, können Sie diesen mithilfe dieses Befehls konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8585e-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="8585e-183">Wenn Sie diesen Befehl ausführen, werden alle synthetischen Transaktionen auf dem angegebenen Watcher-Knoten mit Ausnahme von Chatnachrichten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8585e-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="8585e-184">Anzeigen und Testen der Konfiguration des Watcher-Knotens</span><span class="sxs-lookup"><span data-stu-id="8585e-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="8585e-185">Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="8585e-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="8585e-186">Dieser Befehl gibt abhängig von den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, ähnliche Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="8585e-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="8585e-187">Registrierung im GroupIM P2PAV AvConference Presence PersistentChatMessage dataconference</span><span class="sxs-lookup"><span data-stu-id="8585e-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="8585e-188">Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="8585e-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="8585e-189">Um zu überprüfen, ob ein Watcher-Knoten erstellt wurde, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="8585e-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="8585e-190">Sie erhalten wieder Informationen wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="8585e-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="8585e-191">Identity: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8585e-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="8585e-192">TestUsers: {SIP:watcher1@litwareinc.com, SIP:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="8585e-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="8585e-193">ExtendedTests: {TestUsers = IList<System. String>; Name = PSTN-Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="8585e-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="8585e-194">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8585e-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="8585e-195">PortNumber: 5061</span><span class="sxs-lookup"><span data-stu-id="8585e-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="8585e-196">Um zu überprüfen, ob der Watcher-Knoten ordnungsgemäß konfiguriert wurde, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="8585e-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="8585e-197">Mit diesem Befehl wird jeder Watcher-Knoten in Ihrer Bereitstellung getestet, und es wird überprüft, ob die folgenden Aktionen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="8585e-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="8585e-198">Die erforderliche Registrierungsstellen Rolle ist installiert.</span><span class="sxs-lookup"><span data-stu-id="8585e-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="8585e-199">Der erforderliche Registrierungsschlüssel wird erstellt (abgeschlossen, als Sie das Cmdlet "CsWatcherNodeConfiguration" ausgeführt haben).</span><span class="sxs-lookup"><span data-stu-id="8585e-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="8585e-200">Auf Ihren Servern wird die richtige Version von Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8585e-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="8585e-201">Ihre Ports sind ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8585e-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="8585e-202">Ob die zugewiesenen Testbenutzer über die erforderlichen Anmeldeinformationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="8585e-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="8585e-203">Verwalten von Watcher-Knoten</span><span class="sxs-lookup"><span data-stu-id="8585e-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="8585e-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="8585e-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="8585e-205">Zusätzlich zum Ändern der synthetischen Transaktionen, die auf einem Watcher-Knoten ausgeführt werden, können Sie auch das Cmdlet " **CsWatcherNodeConfiguration** " verwenden, um zwei andere wichtige Aufgaben auszuführen: Aktivieren und Deaktivieren des Watcher-Knotens und Konfigurieren des Watcher-Knotens zur Verwendung interner oder externer weburls beim Ausführen der Tests.</span><span class="sxs-lookup"><span data-stu-id="8585e-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="8585e-206">In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus.</span><span class="sxs-lookup"><span data-stu-id="8585e-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="8585e-207">Gelegentlich möchten Sie jedoch diese Transaktionen anhalten.</span><span class="sxs-lookup"><span data-stu-id="8585e-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="8585e-208">Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="8585e-209">Ohne Netzwerkkonnektivität treten bei diesen Transaktionen Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="8585e-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="8585e-210">Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren möchten, führen Sie einen Befehl wie den folgenden aus der Skype for Business Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="8585e-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="8585e-211">Mit diesem Befehl wird die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten ATL Watcher 001.litwareinc.com deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8585e-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="8585e-212">Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft "Enabled" wieder zurück auf "True" ($True):</span><span class="sxs-lookup"><span data-stu-id="8585e-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="8585e-213">Mithilfe der Eigenschaft "Enabled" können Watcher-Knoten ein- und ausgeschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="8585e-214">Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das **Remove-CsWatcherNodeConfiguration**-Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8585e-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="8585e-215">Mit diesem Befehl werden alle Konfigurationseinstellungen des Watcher-Knotens aus dem angegebenen Computer entfernt, wodurch verhindert wird, dass der Computer synthetische Transaktionen automatisch ausführt.</span><span class="sxs-lookup"><span data-stu-id="8585e-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="8585e-216">Mit dem Befehl werden die System Center-Agent-Dateien oder die Skype for Business Server Systemdateien jedoch nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="8585e-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="8585e-217">Standardmäßig verwenden Watcher-Knoten beim Durchführen von Tests die externen weburls einer Organisation.</span><span class="sxs-lookup"><span data-stu-id="8585e-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="8585e-218">Watcher-Knoten können jedoch auch für die Verwendung der internen weburls der Organisation konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="8585e-219">Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8585e-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="8585e-220">Wenn Sie einen Watcher-Knoten so konfigurieren möchten, dass er interne URLs anstelle externer URLs verwendet, legen Sie die UseInternalWebURls-Eigenschaft auf true ($true) fest:</span><span class="sxs-lookup"><span data-stu-id="8585e-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="8585e-221">Wenn Sie diese Eigenschaft auf den Standardwert false ($false) zurücksetzen, wird die externe URL vom Watcher erneut verwendet:</span><span class="sxs-lookup"><span data-stu-id="8585e-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="8585e-222">Besondere Anweisungen zum Einrichten von synthetischen Transaktionen</span><span class="sxs-lookup"><span data-stu-id="8585e-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="8585e-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="8585e-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="8585e-224">Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="8585e-225">In den meisten Fällen kann der Watcher-Knoten, sobald die synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wird, diese synthetische Transaktion während der Testdurchläufe verwenden.</span><span class="sxs-lookup"><span data-stu-id="8585e-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="8585e-226">Es gibt jedoch einige synthetische Transaktionen, die spezielle Setupanweisungen erfordern, wie in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="8585e-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="8585e-227">Synthetische Datenkonferenz Transaktion</span><span class="sxs-lookup"><span data-stu-id="8585e-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="8585e-228">Wenn sich der Monitor Knoten Computer außerhalb des Umkreisnetzwerks befindet, können Sie die synthetische Datenkonferenz-Transaktion möglicherweise nicht ausführen, es sei denn, Sie deaktivieren zunächst die Windows Internet Explorer® Internet Browser-Proxyeinstellungen für das Netzwerk Dienstkonto, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8585e-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="8585e-229">Klicken Sie auf dem Monitor Knoten Computer auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8585e-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="8585e-230">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8585e-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="8585e-231">Im Befehlsfenster wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8585e-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="8585e-232">Diese Meldung weist darauf hin, dass Sie die Internet Explorer Proxyeinstellungen für das Netzwerkdienstkonto deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="8585e-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="8585e-233">Synthetische Exchange Unified Messaging-Transaktion</span><span class="sxs-lookup"><span data-stu-id="8585e-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="8585e-234">Die Exchange Unified Messaging (um) synthetische Transaktion überprüft, ob Testbenutzer eine Verbindung mit Voicemail-Konten herstellen können, die in Exchange verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="8585e-235">Die Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="8585e-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="8585e-236">Synthetische Transaktion für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="8585e-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="8585e-237">Um die synthetische persistent Chat-Transaktion zu verwenden, müssen Sie zunächst einen Kanal erstellen und den Testbenutzern Berechtigungen zur Verwendung geben.</span><span class="sxs-lookup"><span data-stu-id="8585e-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="8585e-238">Sie können die synthetische persistent Chat-Transaktion zum Konfigurieren dieses Kanals verwenden:</span><span class="sxs-lookup"><span data-stu-id="8585e-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="8585e-239">Sie müssen diesen Setup-Task ausführen innerhalb des Unternehmens ausführen:</span><span class="sxs-lookup"><span data-stu-id="8585e-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="8585e-240">Wenn von einem Computer ohne Server ausgeführt wird, muss der Benutzer, der das Cmdlet ausführt, ein Mitglied der CsPersistentChatAdministrators-Rolle für die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) sein.</span><span class="sxs-lookup"><span data-stu-id="8585e-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="8585e-241">Wenn Sie vom Server selbst ausgeführt wird, muss der Benutzer, der das Cmdlet ausführt, Mitglied der RTCUniversalServerAdmins-Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="8585e-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="8585e-242">PSTN-Peer-to-Peer-Anruf synthetische Transaktion</span><span class="sxs-lookup"><span data-stu-id="8585e-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="8585e-243">Die synthetische Test-CsPstnPeerToPeerCall-Transaktion überprüft, ob Anrufe über ein öffentliches Telefonnetz (PSTN) getätigt und empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="8585e-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="8585e-244">Um diese synthetische Transaktion auszuführen, müssen Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8585e-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="8585e-245">Zwei UC-fähige Testbenutzer (Anrufer und Empfänger).</span><span class="sxs-lookup"><span data-stu-id="8585e-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="8585e-246">DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="8585e-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="8585e-247">VoIP-Richtlinien und VoIP-Routen, bei denen Anrufe an die Nummer des Empfängers das PSTN-Gateway erreichen können.</span><span class="sxs-lookup"><span data-stu-id="8585e-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="8585e-248">Ein PSTN-Gateway, das Anrufe und Medien annimmt, die Anrufe basierend auf der gewählten Nummer zurück an den Home-Pool eines Empfängers weiterleiten werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="8585e-249">Synthetische Transaktion des einheitlichen Kontaktspeichers</span><span class="sxs-lookup"><span data-stu-id="8585e-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="8585e-250">Die synthetische Transaktion des einheitlichen Kontaktspeichers überprüft, ob Skype for Business Server Kontakte im Auftrag eines Benutzers aus Exchange abrufen können.</span><span class="sxs-lookup"><span data-stu-id="8585e-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="8585e-251">Für die Verwendung dieser synthetischen Transaktionen müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="8585e-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="8585e-252">Lyss-Exchange Server-zu-Server-Authentifizierung muss konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="8585e-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="8585e-253">Test Benutzer benötigen ein gültiges Exchange-Postfach.</span><span class="sxs-lookup"><span data-stu-id="8585e-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="8585e-254">Nachdem diese Bedingungen erfüllt sind, können Sie das folgende Windows PowerShell-Cmdlet ausführen, um die Kontaktlisten der Testbenutzer zu Exchange zu migrieren:</span><span class="sxs-lookup"><span data-stu-id="8585e-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="8585e-255">Es kann einige Zeit dauern, bis die Testbenutzer Kontaktlisten zu Exchange migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="8585e-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="8585e-256">Um den Migrations Fortschritt zu überwachen, kann dieselbe Befehlszeile ohne das Flag-Setup ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="8585e-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="8585e-257">Diese Befehlszeile ist nach Abschluss der Migration erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8585e-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="8585e-258">Synthetische XMPP-Transaktion</span><span class="sxs-lookup"><span data-stu-id="8585e-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="8585e-259">Für die synthetische XMPP-Sofortnachrichten Transaktion (Extensible Messaging and Presence Protocol) ist es erforderlich, dass Sie das XMPP-Feature mit einer oder mehreren Verbunddomänen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8585e-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="8585e-260">Um die synthetische XMPP-Transaktion zu aktivieren, müssen Sie einen XmppTestReceiverMailAddress-Parameter mit einem Benutzerkonto in einer routingfähigen XMPP-Domäne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8585e-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="8585e-261">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8585e-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="8585e-262">In diesem Beispiel muss eine Skype for Business Server-Regel vorhanden sein, um Nachrichten für litwareinc.com an ein XMPP-Gateway weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="8585e-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="8585e-263">XMPP-Gateways und-Proxys stehen in Skype for Business Server 2015 zur Verfügung, werden in Skype for Business Server 2019 jedoch nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8585e-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8585e-264">Weitere Informationen finden Sie unter [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="8585e-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="8585e-265">Synthetische Transaktion für Video-Interop-Server (VIS)</span><span class="sxs-lookup"><span data-stu-id="8585e-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="8585e-266">Für die synthetische Video Interop Server-Transaktion ist es erforderlich, dass Sie die synthetischen Transaktions Unterstützungsdateien ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)) herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="8585e-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="8585e-267">Zum Installieren von VISSTSupportPackage. msi stellen Sie sicher, dass die Abhängigkeiten (unter System Anforderungen) für die MSI-Datei bereits installiert sind.</span><span class="sxs-lookup"><span data-stu-id="8585e-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="8585e-268">Führen Sie VISSTSupportPackage. msi aus, um eine einfache Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="8585e-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="8585e-269">Die MSI-Datei installiert alle Dateien im folgenden Pfad: "%ProgramFiles%\VIS synthetische Transaktions Unterstützungspaket".</span><span class="sxs-lookup"><span data-stu-id="8585e-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="8585e-270">Weitere Informationen zum Ausführen der VIS-synthetischen Transaktion finden Sie in der Dokumentation zum Cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8585e-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="8585e-271">Ändern der Lauf Häufigkeit für synthetische Transaktionen</span><span class="sxs-lookup"><span data-stu-id="8585e-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="8585e-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="8585e-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="8585e-273">Standardmäßig werden synthetische Transaktionen alle 15 Minuten mit den konfigurierten Benutzern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8585e-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="8585e-274">Synthetische Transaktionen werden nacheinander in einer Gruppe von Benutzern ausgeführt, um zu vermeiden, dass zwei synthetische Transaktionen miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="8585e-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="8585e-275">Es ist ein längeres Intervall erforderlich, um Zeit für die Ausführung aller synthetischen Transaktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8585e-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="8585e-276">Wenn es wünschenswert ist, synthetische Transaktionen häufiger auszuführen, sollte die Anzahl der synthetischen Transaktionen, die mit einer bestimmten Gruppe von Benutzern ausgeführt werden, verringert werden, damit die Tests im gewünschten Zeitbereich mit einem Puffer für gelegentliche Netzwerkverzögerungen abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="8585e-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="8585e-277">Wenn das Ausführen von mehr synthetischen Transaktionen wünschenswert ist, erstellen Sie weitere Benutzergruppen, um zusätzliche synthetische Transaktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8585e-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="8585e-278">Führen Sie die folgenden Schritte aus, um die Häufigkeit zu ändern, mit der synthetische Transaktionen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="8585e-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="8585e-279">Öffnen Sie System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8585e-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="8585e-280">Klicken Sie auf Erstellungs Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="8585e-280">Click Authoring section.</span></span> <span data-ttu-id="8585e-281">Klicken Sie auf Rules section (unter Authoring).</span><span class="sxs-lookup"><span data-stu-id="8585e-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="8585e-282">Suchen Sie im Abschnitt Regeln nach der Regel mit dem Namen "primäre synthetische Transaktions Runner-Leistungssammlungsregel".</span><span class="sxs-lookup"><span data-stu-id="8585e-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="8585e-283">Klicken Sie mit der rechten Maustaste auf die Regel, und wählen Sie Außerkraftsetzungen, die Regel außer Kraft setzen aus, und wählen Sie dann "für alle Objekte der Klasse: Pool Watcher" aus.</span><span class="sxs-lookup"><span data-stu-id="8585e-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="8585e-284">Wählen Sie im Fenster Außerkraftsetzungseigenschaften die Option Parameter Name "Frequency" aus, und legen Sie den Außerkraftsetzungswert auf den gewünschten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="8585e-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="8585e-285">Wählen Sie im gleichen Fenster das Management Pack aus, auf das diese Außerkraftsetzung angewendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="8585e-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="8585e-286">Verwenden von erweiterter Protokollierung für synthetische Transaktionen</span><span class="sxs-lookup"><span data-stu-id="8585e-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="8585e-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="8585e-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="8585e-288">Synthetische Transaktionen sind äußerst hilfreich, um Probleme mit dem System zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="8585e-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="8585e-289">Beispielsweise könnte das Test-CsRegistration-Cmdlet Administratoren darauf hinweisen, dass die Benutzer bei der Registrierung bei Skype for Business Server Schwierigkeiten hatten.</span><span class="sxs-lookup"><span data-stu-id="8585e-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="8585e-290">Es sind jedoch möglicherweise zusätzliche Details erforderlich, um die tatsächliche Ursache eines Fehlers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8585e-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="8585e-291">Aus diesem Grund bieten synthetische Transaktionen umfangreiche Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="8585e-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="8585e-292">Bei der umfangreichen Protokollierung werden für jede Aktivität, die eine synthetische Transaktion unternimmt, die folgenden Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="8585e-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="8585e-293">Die Zeit, zu der die Aktivität gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="8585e-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="8585e-294">Die Zeit, zu der die Aktivität abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="8585e-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="8585e-295">Die Aktion, die ausgeführt wurde (beispielsweise zum Erstellen, hinzufügen oder verlassen einer Konferenz; Anmelden bei Skype for Business Server; senden einer Sofortnachricht).</span><span class="sxs-lookup"><span data-stu-id="8585e-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="8585e-296">Informations-, ausführliche, Warn-oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8585e-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="8585e-297">SIP-Registrierungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="8585e-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="8585e-298">Ausnahmedaten Sätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8585e-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="8585e-299">Das Ergebnis der Ausführung der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8585e-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="8585e-300">Diese Informationen werden automatisch jedes Mal generiert, wenn eine synthetische Transaktion ausgeführt wird, aber nicht automatisch angezeigt oder in einer Protokolldatei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8585e-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="8585e-301">Wenn Sie eine synthetische Transaktion manuell durchführen, können Sie den OutLoggerVariable-Parameter verwenden, um eine Windows PowerShell Variable anzugeben, in der die Informationen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8585e-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="8585e-302">Von dort haben Sie die Möglichkeit, eine der beiden folgenden Methoden zum Speichern und/oder Anzeigen von Fehlermeldungen im Rich-Protokoll im XML-oder HTML-Format zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8585e-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="8585e-303">Um die Informationen zur Problembehandlung abzurufen, geben Sie den OutLoggerVariable-Parameter an, gefolgt von einem Variablennamen, den Sie auswählen:</span><span class="sxs-lookup"><span data-stu-id="8585e-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="8585e-304">Stellen Sie dem Variablennamen kein $-Zeichen voran.</span><span class="sxs-lookup"><span data-stu-id="8585e-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="8585e-305">Verwenden Sie einen Variablennamen wie RegistrationTest (nicht $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="8585e-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="8585e-306">Wenn Sie diesen Befehl ausführen, wird die Ausgabe ähnlich der folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8585e-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="8585e-307">Ziel-FQDN: ATL-CS-001.litwareinc.com Ergebnis: Fehlerwartezeit: 00:00:00 Fehlermeldung: dieser Computer verfügt über keine zugewiesenen Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="8585e-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="8585e-308">Diagnose: Sie können auf ausführlichere Informationen für diesen Fehler zugreifen, als nur die hier gezeigte Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="8585e-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="8585e-309">Um auf diese Informationen im HTML-Format zuzugreifen, verwenden Sie einen Befehl wie den folgenden, um die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="8585e-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="8585e-310">Alternativ können Sie die XML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="8585e-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="8585e-311">Sie können diese Dateien mithilfe von Windows Internet Explorer, Microsoft Visual Studio oder einer anderen Anwendung anzeigen, die HTML/XML-Dateien öffnen kann.</span><span class="sxs-lookup"><span data-stu-id="8585e-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="8585e-312">Synthetische Transaktionen, die von innerhalb von System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien automatisch für Fehler.</span><span class="sxs-lookup"><span data-stu-id="8585e-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="8585e-313">Diese Protokolle werden nicht generiert, wenn die Ausführung fehlschlägt, bevor Skype for Business Server PowerShell die synthetische Transaktion laden und ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="8585e-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8585e-314">Standardmäßig speichert Skype for Business Server Protokolldateien in einem Ordner, der nicht freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8585e-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="8585e-315">Damit diese Protokolle leicht zugänglich sind, sollten Sie diesen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="8585e-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="8585e-316">Beispiel: \\ATL-Watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="8585e-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
