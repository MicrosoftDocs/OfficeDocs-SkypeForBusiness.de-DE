---
title: Konfigurieren von Testbenutzern und Einstellungen für Monitorknoten
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Zusammenfassung: Konfigurieren von Testbenutzerkonten und Watcher-Knoten-Einstellungen für Skype für synthetische Transaktionen Business Server.'
ms.openlocfilehash: ee5330f10dd97e8ecc8a3e3e30962e6e8a69555b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569875"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="22bf6-103">Konfigurieren von Testbenutzern und Einstellungen für Monitorknoten</span><span class="sxs-lookup"><span data-stu-id="22bf6-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="22bf6-104">**Zusammenfassung:** Konfigurieren von Testbenutzerkonten und Watcher-Knoten-Einstellungen für Skype für synthetische Transaktionen Business Server.</span><span class="sxs-lookup"><span data-stu-id="22bf6-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="22bf6-105">Nachdem Sie den Computer konfiguriert haben, der als Watcher-Knoten agieren wird, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="22bf6-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="22bf6-106">[Konfigurieren von Testbenutzerkonten](test-users-and-settings.md#testuser) von diese Watcher-Knoten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22bf6-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="22bf6-107">Wenn Sie die Aushandlungsauthentifizierungsmethode verwenden, müssen Sie auch das Cmdlet **Set-CsTestUserCredential** verwenden, um die Verwendung dieser Testkonten auf dem Watcher-Knoten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="22bf6-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="22bf6-108">Aktualisieren Sie die Konfigurationseinstellungen für den Watcher-Knoten.</span><span class="sxs-lookup"><span data-stu-id="22bf6-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="22bf6-109">Konfigurieren von Testbenutzerkonten</span><span class="sxs-lookup"><span data-stu-id="22bf6-109">Configure Test User Accounts</span></span>
<span data-ttu-id="22bf6-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="22bf6-110"></span></span>

<span data-ttu-id="22bf6-111">Testkonten müssen keine tatsächliche Personen darstellen, jedoch muss es sich um gültige Active Directory-Konten.</span><span class="sxs-lookup"><span data-stu-id="22bf6-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="22bf6-112">Darüber hinaus dieser Konten müssen für Skype für Business Server 2015 aktiviert werden, über eine gültige SIP-Adressen verfügen, und sie für Enterprise-VoIP (zur Verwendung von der synthetischen Transaktionsprotokolls Test-CsPstnPeerToPeerCall) aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="22bf6-112">In addition, these accounts must be enabled for Skype for Business Server 2015, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="22bf6-113">Wenn Sie die TrustedServer-Authentifizierungsmethode verwenden, müssen Sie lediglich sicherstellen, dass diese Konten vorhanden sind und wie bereits erwähnt konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="22bf6-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="22bf6-114">Sie sollten für jeden zu testenden Pool mindestens drei Testbenutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="22bf6-115">Wenn Sie die Authentifizierungsmethode verhandeln verwenden, müssen Sie auch die Cmdlets "Set-cstestusercredential" verwenden, und die Skype für Business Server-Verwaltungsshell, um diese zu aktivieren Testkonten synthetischen Transaktionen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="22bf6-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="22bf6-116">Dazu führen einen Befehl ähnlich dem folgenden (diese Befehle wird davon ausgegangen, dass die folgenden drei Active Directory-Benutzerkonten erstellt wurden und dass diese Konten für Skype für Business Server 2015 aktiviert sind):</span><span class="sxs-lookup"><span data-stu-id="22bf6-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server 2015):</span></span>
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="22bf6-p104">Sie müssen zusätzlich zur SIP-Adresse auch den Benutzernamen und das Kennwort einfügen. Wenn Sie das Kennwort nicht einfügen, werden Sie vom Set-CsTestUserCredential-Cmdlet zur Eingabe dieser Informationen aufgefordert. Der Benutzername kann im Format „Domänenname\Benutzername“, das im vorangehenden Codeblock gezeigt wurde, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22bf6-p104">You must include not only the SIP address, but also the user name and password. If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information. The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="22bf6-120">Um sicherzustellen, dass die testbenutzeranmeldeinformationen erstellt wurden, führen Sie diese Befehle an der Skype für Business Server-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="22bf6-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="22bf6-121">Daraufhin werden für jeden Benutzer Informationen zurückgegeben werden, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="22bf6-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="22bf6-122">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="22bf6-122">**UserName**</span></span>|<span data-ttu-id="22bf6-123">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="22bf6-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22bf6-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="22bf6-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="22bf6-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="22bf6-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="22bf6-126">Konfigurieren eines einfachen Watcher-Knotens mit den synthetischen Standardtransaktionen</span><span class="sxs-lookup"><span data-stu-id="22bf6-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="22bf6-127">Nachdem die Testbenutzer erstellt wurden, können Sie mithilfe eines Befehls, der dem Folgenden ähnelt, einen Watcher-Knoten erstellen:</span><span class="sxs-lookup"><span data-stu-id="22bf6-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="22bf6-p105">Mithilfe dieses Befehls wird ein neuer Watcher-Knoten erstellt, für den die Standardeinstellungen verwendet werden und der die Standardgruppe synthetischer Transaktionen ausführt. Für den neuen Watcher-Knoten werden zudem die Testbenutzer watcher1@litwareinc.com, watcher2@litwareinc.com und watcher3@litwareinc.com verwendet. Wenn der Watcher-Knoten die TrustedServer-Authentifizierung verwendet, kann es sich bei den drei Testkonten um beliebige gültige Benutzerkonten handeln, die für Active Directory und Skype for Business Server aktiviert sind. Wenn der Watcher-Knoten die Negotiate-Authentifizierungsmethode verwendet, müssen Sie diese Benutzerkonten auch für den Watcher-Knoten aktivieren, indem Sie das Cmdlet Set-CsTestUserCredential verwenden.</span><span class="sxs-lookup"><span data-stu-id="22bf6-p105">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions. The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com. If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server. If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="22bf6-132">Um zu überprüfen, ob die automatische Ermittlung des Zielpools zur Anmeldung ordnungsgemäß konfiguriert ist, führen Sie diese Schritte aus, statt einen Pool direkt vorzugeben:</span><span class="sxs-lookup"><span data-stu-id="22bf6-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="22bf6-133">Konfigurieren erweiterter Tests</span><span class="sxs-lookup"><span data-stu-id="22bf6-133">Configuring Extended Tests</span></span>

<span data-ttu-id="22bf6-p106">Wenn Sie den PSTN-Test aktivieren möchten, mit dessen Hilfe die Verbindung mit dem Telefonfestnetz überprüft wird, müssen Sie beim Einrichten des Watcher-Knotens einige zusätzliche Konfigurationsschritte ausführen. Zuerst müssen Sie die Testbenutzer dem PSTN-Testtyp zuweisen. Führen Sie dazu in der Skype for Business Server-Verwaltungsshell einen Befehl aus, der dem Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p106">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node. First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="22bf6-p107">Die Ergebnisse dieses Befehls müssen in einer Variablen gespeichert werden. In diesem Beispiel handelt es sich dabei um die Variable $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="22bf6-p107">The results of this command must be stored in a variable. In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="22bf6-p108">Anschließend können Sie das Cmdlet **New-CsWatcherNodeConfiguration** verwenden, um den Testtyp (in der Variablen $pstnTest gespeichert) einem Skype for Business Server 2015-Pool zuzuweisen. Mithilfe des folgenden Befehls wird beispielsweise eine neue Watcher-Knotenkonfiguration für den Pool atl-cs-001.litwareinc.com erstellt, wobei die drei zuvor erstellten Testbenutzer und der PSTN-Testtyp hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p108">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server 2015 pool. For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="22bf6-140">Der zuvor angeführte Befehl gibt einen Fehler zurück, wenn Sie die Skype for Business Server-Hauptdateien und die RTCLocal-Datenbank nicht auf dem Computer des Watcher-Knotens installiert haben.</span><span class="sxs-lookup"><span data-stu-id="22bf6-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="22bf6-p109">Wenn Sie mehrere VoIP-Richtlinien testen möchten, können Sie für alle Richtlinien mithilfe des Cmdlets **New-CsExtendedTest** einen erweiterten Test erstellen. Die diesem Test zugewiesenen Benutzer müssen mit den gewünschten VoIP-Richtlinien konfiguriert werden. Die erweiterten Tests werden mit Komma-Trennzeichen an das Cmdlet **New-CsWatcherNodeConfiguration** übergeben, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p109">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet. The users provided should be configured with the desired voice policies. The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="22bf6-144">-ExtendedTests @{Add = pstnTest1$, pstnTest2$, $pstnTest3}</span><span class="sxs-lookup"><span data-stu-id="22bf6-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="22bf6-p110">Da das **New-CsWatcherNodeConfiguration**-Cmdlet ohne den Parameter „Tests“ aufgerufen wird, bedeutet dies, dass für den neuen Watcher-Knoten nur die synthetischen Standardtransaktionen (und die angegebene erweiterte synthetische Transaktion) aktiviert werden. Daher testet der Watcher-Knoten die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p110">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="22bf6-147">Registrierung</span><span class="sxs-lookup"><span data-stu-id="22bf6-147">Registration</span></span>
    
- <span data-ttu-id="22bf6-148">IM</span><span class="sxs-lookup"><span data-stu-id="22bf6-148">IM</span></span>
    
- <span data-ttu-id="22bf6-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="22bf6-149">GroupIM</span></span>
    
- <span data-ttu-id="22bf6-150">P2PAV (Peer-zu-Peer-Audio/Videositzungen)</span><span class="sxs-lookup"><span data-stu-id="22bf6-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="22bf6-151">AvConference (Audio/Konferenzen)</span><span class="sxs-lookup"><span data-stu-id="22bf6-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="22bf6-152">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="22bf6-152">Presence</span></span>
    
- <span data-ttu-id="22bf6-153">ABS (Adressbuchdienst)</span><span class="sxs-lookup"><span data-stu-id="22bf6-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="22bf6-154">ABWQ (Adressbuchwebdienst)</span><span class="sxs-lookup"><span data-stu-id="22bf6-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="22bf6-155">Die folgenden Komponenten werden standardmäßig nicht getestet:</span><span class="sxs-lookup"><span data-stu-id="22bf6-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="22bf6-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="22bf6-156">ASConference</span></span>
    
- <span data-ttu-id="22bf6-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="22bf6-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="22bf6-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="22bf6-158">DataConference</span></span>
    
- <span data-ttu-id="22bf6-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="22bf6-159">DialinConferencing</span></span>
    
- <span data-ttu-id="22bf6-160">ExumConnectivity (Exchange Unified Messaging)</span><span class="sxs-lookup"><span data-stu-id="22bf6-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="22bf6-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="22bf6-161">JoinLauncher</span></span>
    
- <span data-ttu-id="22bf6-162">MCXP2PIM (Instant Messaging für mobile Geräte)</span><span class="sxs-lookup"><span data-stu-id="22bf6-162">MCXP2PIM (mobile device instant messaging)</span></span>
    
- <span data-ttu-id="22bf6-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="22bf6-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="22bf6-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="22bf6-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="22bf6-165">PSTN (PSTN-Gatewayanrufe, angegeben als erweiterter Test)</span><span class="sxs-lookup"><span data-stu-id="22bf6-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="22bf6-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="22bf6-166">UcwaConference</span></span>
    
- <span data-ttu-id="22bf6-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="22bf6-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="22bf6-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="22bf6-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="22bf6-169">Hinzufügen und Entfernen synthetischer Transaktionen</span><span class="sxs-lookup"><span data-stu-id="22bf6-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="22bf6-p111">Nachdem ein Watcher-Knoten konfiguriert wurde, können Sie dem Knoten mithilfe des Cmdlets Set-CsWatcherNodeConfiguration synthetische Transaktionen hinzufügen oder Knoten daraus entfernen. Wenn Sie beispielsweise dem Watcher-Knoten den Test PersistentChatMessage hinzufügen möchten, verwenden Sie die Add-Methode und einen Befehl, der dem Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p111">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node. For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="22bf6-p112">Sie können mehrere Tests hinzufügen, indem Sie die Testnamen durch Kommas voneinander trennen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p112">Multiple tests can be added by separating the test names by using commas. For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="22bf6-p113">Ein Fehler tritt auf, wenn einer oder mehrere dieser Tests (z. B. DataConference) bereits für den Watcher-Knoten aktiviert wurden. In diesem Fall erhalten Sie eine Fehlermeldung, die der Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p113">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="22bf6-176">Set-CsWatcherNodeConfiguration: There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span><span class="sxs-lookup"><span data-stu-id="22bf6-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="22bf6-177">Wenn dieser Fehler auftritt, werden keine Änderungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="22bf6-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="22bf6-178">Führen Sie den Befehl erneut aus, nachdem Sie den doppelten Test entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="22bf6-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="22bf6-p115">Wenn Sie eine synthetische Transaktion aus einem Watcher-Knoten entfernen möchten, verwenden Sie die Remove-Methode. Mithilfe des folgenden Befehls wird beispielsweise der ABWQ-Test aus einem Watcher-Knoten entfernt:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p115">To remove a synthetic transaction from a watcher node, use the Remove method. For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="22bf6-p116">Sie können die Replace-Methode verwenden, um alle momentan aktivierten Tests durch einen oder mehrere neue Tests zu ersetzen. Wenn Sie beispielsweise möchten, dass ein Watcher-Knoten nur den IM-Test ausführt, können Sie dieses Verhalten mithilfe des folgenden Befehls konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p116">You can use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="22bf6-183">Wenn Sie diesen Befehl ausführen, werden mit Ausnahme von IM alle synthetischen Transaktionen für den angegebenen Watcher-Knoten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="22bf6-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="22bf6-184">Anzeigen und Testen der Konfiguration des Watcher-Knotens</span><span class="sxs-lookup"><span data-stu-id="22bf6-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="22bf6-185">Wenn Sie die Tests anzeigen möchten, die einem Watcher-Knoten zugewiesen wurden, verwenden Sie einen Befehl, der dem Folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="22bf6-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="22bf6-186">Mithilfe dieses Befehls werden je nach den synthetischen Transaktionen, die dem Knoten zugewiesen wurden, Informationen zurückgegeben, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="22bf6-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="22bf6-187">Registrierung Sofortnachrichten GroupIM P2PAV AvConference Anwesenheit PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="22bf6-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="22bf6-188">Wenn Sie die synthetischen Transaktionen in alphabetischer Reihenfolge anzeigen möchten, verwenden Sie stattdessen den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="22bf6-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="22bf6-189">Wenn Sie überprüfen möchten, ob ein Watcher-Knoten erstellt wurde, geben Sie den folgenden Befehl über die Skype for Business Server-Verwaltungsshell ein:</span><span class="sxs-lookup"><span data-stu-id="22bf6-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="22bf6-190">Sie erhalten Informationen, die den Folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="22bf6-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="22bf6-191">Identität: "Atl-Cs-001.litwareinc.com" TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="22bf6-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="22bf6-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="22bf6-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="22bf6-193">"Targetfqdn": "Atl-Cs-001.litwareinc.com" Portnummer: 5061To stellen Sie sicher, dass der Watcher-Knoten konfiguriert wurde ordnungsgemäß funktioniert, geben Sie den folgenden Befehl aus der Skype für Business Server-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="22bf6-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="22bf6-194">Mit diesem Befehl werden alle Watcher-Knoten in Ihrer Bereitstellung getestet und überprüft, ob die folgenden Aktionen durchgeführt wurden:</span><span class="sxs-lookup"><span data-stu-id="22bf6-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="22bf6-195">Ob die erforderliche Registrar-Rolle installiert wurde</span><span class="sxs-lookup"><span data-stu-id="22bf6-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="22bf6-196">Ob der erforderliche Registrierungsschlüssel erstellt wurde (abgeschlossen, als Sie das Cmdlet Set-CsWatcherNodeConfiguration ausgeführt haben)</span><span class="sxs-lookup"><span data-stu-id="22bf6-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="22bf6-197">Ob auf Ihren Servern die richtige Version von Skype for Business Server ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="22bf6-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="22bf6-198">Ob Ihre Ports ordnungsgemäß konfiguriert wurden</span><span class="sxs-lookup"><span data-stu-id="22bf6-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="22bf6-199">Ob die zugewiesenen Testbenutzer über die erforderlichen Anmeldeinformationen verfügen</span><span class="sxs-lookup"><span data-stu-id="22bf6-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="22bf6-200">Verwalten von Watcher-Knoten</span><span class="sxs-lookup"><span data-stu-id="22bf6-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="22bf6-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="22bf6-201"></span></span>

<span data-ttu-id="22bf6-202">Mit dem **Set-CsWatcherNodeConfiguration**-Cmdlet können Sie nicht nur die auf einem Watcher-Knoten ausgeführten synthetischen Transaktionen ändern, sondern auch noch zwei andere wichtige Aufgaben durchführen: das Aktivieren und Deaktivieren des Watcher-Knotens sowie das Konfigurieren des Watcher-Knotens zur Verwendung interner oder externer Web-URLs beim Durchführen seiner Tests.</span><span class="sxs-lookup"><span data-stu-id="22bf6-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="22bf6-p118">In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Manchmal müssen solche Transaktionen jedoch angehalten werden. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Verbindung mit dem Netzwerk würden solche Transaktionen fehlschlagen. Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren, führen Sie in der Skype for Business Server-Verwaltungsshell einen Befehl aus, der in etwa so aussieht:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p118">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions. At times, however, you may want to suspend those transactions. For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions. Without network connectivity, those transactions will fail. To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="22bf6-p119">Dieser Befehl deaktiviert die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten „atl-watcher- 001.litwareinc.com“. Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft „Enabled“ wieder zurück auf „True“ ($True):</span><span class="sxs-lookup"><span data-stu-id="22bf6-p119">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="22bf6-p120">Mithilfe der Eigenschaft „Enabled“ können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das **Remove-CsWatcherNodeConfiguration**-Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p120">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="22bf6-p121">Dieser Befehl entfernt auf dem angegebenen Computer alle Konfigurationseinstellungen für Watcher-Knoten, sodass auf diesem Computer keine synthetischen Transaktionen mehr automatisch ausgeführt werden. Allerdings werden dabei weder die System Center-Agentdateien noch die Skype for Business Server 2015-Systemdateien deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="22bf6-p121">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions. However, the command does not uninstall the System Center agent files or the Skype for Business Server 2015 system files.</span></span>
  
<span data-ttu-id="22bf6-p122">In der Standardeinstellung verwenden Watcher-Knoten bei der Durchführung ihrer Tests externe Web-URLs des Unternehmens. Es ist jedoch auch möglich, die Verwendung interner Web-URLs zu konfigurieren. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Wenn Sie einen Watcher-Knoten so konfigurieren möchten, dass er interne anstatt externe URLs verwendet, legen Sie die Eigenschaft UseInternalWebURls auf „True“ ($True) fest:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p122">By default, watcher nodes use an organization's external Web URLs when conducting tests. However, watcher nodes can also be configured to use the organization's internal Web URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="22bf6-218">Zurücksetzen dieser Eigenschaft auf den Standardwert „False“ ($False) führt dazu, dass der Watcher-Knoten wieder externe URLs verwendet:</span><span class="sxs-lookup"><span data-stu-id="22bf6-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="22bf6-219">Besondere Anweisungen zum Einrichten von synthetischen Transaktionen</span><span class="sxs-lookup"><span data-stu-id="22bf6-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="22bf6-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="22bf6-220"></span></span>

<span data-ttu-id="22bf6-p123">Die meisten synthetischen Transaktionen können auf einem Watcher-Knoten ohne größere Umstände ausgeführt werden. Sobald eine synthetische Transaktion den Konfigurationseinstellungen des Watcher-Knotens hinzugefügt wurde, kann sie in den meisten Fällen vom Watcher-Knoten bei seinen Testdurchläufen eingesetzt werden. Allerdings gibt es einige synthetische Transaktionen, für die spezielle Einrichtungsschritte erforderlich sind, wie in den nächsten Abschnitten erklärt.</span><span class="sxs-lookup"><span data-stu-id="22bf6-p123">Most synthetic transactions can run on a watcher node as-is. In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes. However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="22bf6-224">Synthetische Transaktion für Datenkonferenzen</span><span class="sxs-lookup"><span data-stu-id="22bf6-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="22bf6-225">Wenn sich Ihr Watcher-Knoten-Computer außerhalb Ihres Umkreisnetzwerks befindet, werden Sie die synthetische Transaktion für Datenkonferenzen wahrscheinlich erst dann ausführen können, nachdem Sie zuerst die Proxyeinstellungen für den Windows Internet Explorer®-Internetbrowser für das Konto „Netzwerkdienst“ mithilfe der folgenden Schritte deaktiviert haben:</span><span class="sxs-lookup"><span data-stu-id="22bf6-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="22bf6-226">Klicken Sie auf dem Watcher-Knoten-Computer auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="22bf6-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="22bf6-227">Geben Sie im Konsolenfenster den folgenden Befehl ein und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="22bf6-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="22bf6-228">Die folgende Meldung wird im Befehlsfenster angezeigt:</span><span class="sxs-lookup"><span data-stu-id="22bf6-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="22bf6-p124">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="22bf6-p124">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="22bf6-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="22bf6-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="22bf6-232">(connection = default)</span><span class="sxs-lookup"><span data-stu-id="22bf6-232">(connection = default)</span></span>
  
<span data-ttu-id="22bf6-233">Diese Meldung weist darauf hin, dass Sie die Internet Explorer-Proxyeinstellungen für das Konto „Netzwerkdienst“ deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="22bf6-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="22bf6-234">Synthetische Transaktionen „Exchange Unified Messaging“</span><span class="sxs-lookup"><span data-stu-id="22bf6-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="22bf6-235">Die synthetischen Transaktion „Exchange Unified Messaging“ (UM) überprüft, ob Testbenutzer eine Verbindung zu in Exchange geführten Voicemail-Konten herstellen können.</span><span class="sxs-lookup"><span data-stu-id="22bf6-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="22bf6-236">Die Testbenutzer müssen mit Voicemail-Konten vorkonfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="22bf6-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="22bf6-237">Synthetische Transaktion „Beständiger Chat“</span><span class="sxs-lookup"><span data-stu-id="22bf6-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="22bf6-238">Für die Verwendung der synthetischen Transaktion „Beständiger Chat“ müssen Sie zuerst einen Kanal erstellen und den Testbenutzern die Berechtigung für dessen Verwendung erteilen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="22bf6-239">Sie können die synthetische Transaktion „Beständiger Chat“ zum Konfigurieren dieses Kanals verwenden:</span><span class="sxs-lookup"><span data-stu-id="22bf6-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="22bf6-240">Sie müssen diese Einrichtungsaufgabe auf einem Computer innerhalb des Unternehmens durchführen:</span><span class="sxs-lookup"><span data-stu-id="22bf6-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="22bf6-241">Wenn das Cmdlet auf einem Computer ausgeführt wird, der kein Server ist, muss der entsprechende Benutzer bei rollenbasierter Zugriffssteuerung (RBAC) Mitglied der Rolle CsPersistentChatAdministrators sein.</span><span class="sxs-lookup"><span data-stu-id="22bf6-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="22bf6-242">Wenn das Cmdlet auf dem Server selbst ausgeführt wird, muss der entsprechende Benutzer Mitglied der Gruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="22bf6-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="22bf6-243">Synthetische Transaktionen für Peer-zu-Peer-Festnetzanrufe</span><span class="sxs-lookup"><span data-stu-id="22bf6-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="22bf6-244">Die synthetische Test-CsPstnPeerToPeerCall-Transaktion überprüft, ob es möglich ist, Anrufe über das Festnetz zu tätigen und entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="22bf6-245">Zum Ausführen dieser synthetischen Transaktion müssen Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="22bf6-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="22bf6-246">Zwei UC-fähige Testbenutzer (einen Anrufer und einen Empfänger)</span><span class="sxs-lookup"><span data-stu-id="22bf6-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="22bf6-247">DID-Nummern (Direct Inward Dialing) für jedes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="22bf6-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="22bf6-248">VoIP-Richtlinien und VoIP-Routen, mit denen Sie Anrufe an die der Nummer des Empfängers das PSTN-Gateway erreichen können.</span><span class="sxs-lookup"><span data-stu-id="22bf6-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="22bf6-249">Ein PSTN-Gateway, das akzeptiert Anruf und Medien, die Routen der Anrufe zurück zum Homepool des Empfängers, basierend auf der Anzahl gewählt.</span><span class="sxs-lookup"><span data-stu-id="22bf6-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="22bf6-250">Synthetische Transaktion für den einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="22bf6-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="22bf6-251">Die synthetische Transaktion für den einheitlichen Kontaktspeicher überprüft, ob Skype for Business Server 2015 in der Lage ist, Kontakte im Namen eines Benutzers aus Exchange abzurufen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server 2015 to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="22bf6-252">Für die Verwendung dieser synthetischen Transaktion müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="22bf6-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="22bf6-253">Lyss-Exchange-Server-Server-Authentifizierung muss konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="22bf6-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="22bf6-254">Testbenutzer müssen ein gültiges Exchange-Postfach besitzen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="22bf6-255">Wenn diese Bedingungen erfüllt sind, können Sie das folgenden Windows PowerShell-Cmdlet zum Migrieren der Testbenutzer Kontaktlisten in Exchange ausführen:</span><span class="sxs-lookup"><span data-stu-id="22bf6-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="22bf6-256">Es kann einige Zeit dauern, bis die Migration der Testbenutzer-Kontaktlisten Migration nach Exchange abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="22bf6-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="22bf6-257">Um den Migrationsstatus zu überwachen, kann die gleiche Command-Line ohne das - Setup-Flag ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="22bf6-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="22bf6-258">Diese Befehlszeile hat nach Abschluss der Migration Erfolg.</span><span class="sxs-lookup"><span data-stu-id="22bf6-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="22bf6-259">Synthetische XMPP-Transaktion</span><span class="sxs-lookup"><span data-stu-id="22bf6-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="22bf6-260">Für die synthetische XMPP-IM-Transaktion (Extensible Messaging and Presence Protocol) ist es erforderlich, dass Sie die XMPP-Funktion mit einer oder mehreren Verbunddomänen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="22bf6-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="22bf6-261">Zum Aktivieren der synthetischen XMPP-Transaktion müssen Sie den Parameter XmppTestReceiverMailAddress mit einem Benutzerkonto bei einer routingfähigen XMPP-Domäne angeben.</span><span class="sxs-lookup"><span data-stu-id="22bf6-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="22bf6-262">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="22bf6-262">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="22bf6-263">In diesem Beispiel muss Skype for Business Server 2015-Regel vorhanden sein, die Nachrichten für litwareinc.com zu einem XMPP-Gateway routet.</span><span class="sxs-lookup"><span data-stu-id="22bf6-263">In this example, a Skype for Business Server 2015 rule will need to exist to route messages for litwareinc.com to an XMPP gateway</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="22bf6-264">Synthetische VIS-Transaktion (Video Interop Server)</span><span class="sxs-lookup"><span data-stu-id="22bf6-264">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="22bf6-265">Die synthetische Transaktion Video Interop Server (gegenüber) erfordert, dass Sie herunterladen und installieren die synthetische Transaktion Unterstützungsdateien ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="22bf6-265">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="22bf6-266">Für die Installation der Datei VISSTSupportPackage.msi stellen Sie sicher, dass die Abhängigkeiten (unter Systemanforderungen) für die MSI-Datei bereits installiert sind.</span><span class="sxs-lookup"><span data-stu-id="22bf6-266">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="22bf6-267">Führen Sie VISSTSupportPackage.msi aus, um eine einfache Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-267">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="22bf6-268">MSI-Datei installiert alle Dateien in den folgenden Pfad: "%ProgramFiles%\VIS synthetische Transaktion Support-Paket".</span><span class="sxs-lookup"><span data-stu-id="22bf6-268">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="22bf6-269">Weitere Informationen zum Ausführen von die synthetische Transaktion gegenüber finden Sie in der Dokumentation für das Cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="22bf6-269">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="22bf6-270">Ändern der Häufigkeit für die Ausführung synthetischer Transaktionen</span><span class="sxs-lookup"><span data-stu-id="22bf6-270">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="22bf6-271"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="22bf6-271"></span></span>

<span data-ttu-id="22bf6-272">Standardmäßig werden synthetische Transaktionen mit den konfigurierten Benutzern alle 15 Minuten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="22bf6-272">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="22bf6-273">Synthetische Transaktionen werden nacheinander innerhalb einer Gruppe von Benutzern ausgeführt, um zu vermeiden, dass zwei synthetische Transaktionen miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-273">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="22bf6-274">Ein längeres Intervall ist erforderlich, damit genügend Zeit für den Abschluss aller synthetischen Transaktionen zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="22bf6-274">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="22bf6-275">Wenn es wünschenswert ist, synthetische Transaktionen häufiger auszuführen, sollte die Anzahl synthetischer Transaktionen, die mit einer vorgegebenen Gruppe von Benutzern ausgeführt wird, verringert werden, damit die Tests im gewünschten Zeitraum mit einem Puffer für gelegentliche Netzwerkverzögerungen abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="22bf6-275">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="22bf6-276">Wenn es wünschenswert ist, mehr synthetische Transaktionen auszuführen, erstellen Sie weitere Benutzergruppen, um zusätzliche synthetische Transaktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-276">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="22bf6-277">So ändern Sie die Häufigkeit, mit der synthetischen Transaktionen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="22bf6-277">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="22bf6-278">Öffnen Sie System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="22bf6-278">Open System Center Operations Manager.</span></span> <span data-ttu-id="22bf6-279">Klicken Sie auf den Abschnitt „Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="22bf6-279">Click Authoring section.</span></span> <span data-ttu-id="22bf6-280">Klicken Sie auf den Abschnitt „Regeln“ (unter „Konfiguration“).</span><span class="sxs-lookup"><span data-stu-id="22bf6-280">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="22bf6-281">Suchen Sie im Abschnitt Regeln die Regel mit dem Namen "Main synthetische Transaktion Testprogramm Leistung Collection Rule"</span><span class="sxs-lookup"><span data-stu-id="22bf6-281">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="22bf6-282">Klicken Sie mit der rechten Maustaste auf die Regel, und wählen Sie Außerkraftsetzungen, wählen Sie die Regel Außerkraftsetzung und wählen Sie dann "für alle Objekte der Klasse: Pool Watcher"</span><span class="sxs-lookup"><span data-stu-id="22bf6-282">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="22bf6-283">Wählen Sie im Fenster Eigenschaften außer Kraft setzen Name des Parameters "Häufigkeit" aus, und legen Sie den Wert außer Kraft setzen, zu dem gewünschten.</span><span class="sxs-lookup"><span data-stu-id="22bf6-283">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="22bf6-284">Im selben Fenster wählen Sie das Management Pack aus, auf das die Überschreibung angewendet werden muss</span><span class="sxs-lookup"><span data-stu-id="22bf6-284">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="22bf6-285">Verwenden von erweiterter Protokollierung für synthetische Transaktionen</span><span class="sxs-lookup"><span data-stu-id="22bf6-285">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="22bf6-286"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="22bf6-286"></span></span>

<span data-ttu-id="22bf6-287">Synthetische Transaktionen sind äußerst nützlich, um Probleme mit dem System zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="22bf6-287">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="22bf6-288">Beispiel: Das Cmdlet Test-CsRegistration kann Administratoren darauf aufmerksam machen, dass Benutzer Schwierigkeiten haben, sich bei Skype for Business Server zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="22bf6-288">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="22bf6-289">Es können jedoch zusätzliche Details erforderlich sein, um die tatsächliche Fehlerursache festzustellen.</span><span class="sxs-lookup"><span data-stu-id="22bf6-289">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="22bf6-p132">Aus diesem Grund stellen synthetische Transaktionen umfassende Protokollierung bereit. Dabei werden für jede Aktivität, die eine synthetische Transaktion unternimmt, die folgenden Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="22bf6-p132">For this reason, synthetic transactions provide rich logging. With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="22bf6-292">Die Uhrzeit, zu der die Aktivität begann.</span><span class="sxs-lookup"><span data-stu-id="22bf6-292">The time that the activity started.</span></span>
    
- <span data-ttu-id="22bf6-293">Die Uhrzeit, zu der die Aktivität endete.</span><span class="sxs-lookup"><span data-stu-id="22bf6-293">The time that the activity finished.</span></span>
    
- <span data-ttu-id="22bf6-294">Die Aktion, die durchgeführt wurde (z. B. Erstellen, Beitreten zu oder Verlassen einer Konferenz, Anmelden bei Skype for Business Server, Senden einer Chatnachricht).</span><span class="sxs-lookup"><span data-stu-id="22bf6-294">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="22bf6-295">Informative oder ausführliche Meldungen bzw. Warn- oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden</span><span class="sxs-lookup"><span data-stu-id="22bf6-295">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="22bf6-296">Meldungen zur SIP-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="22bf6-296">SIP registration messages.</span></span>
    
- <span data-ttu-id="22bf6-297">Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="22bf6-297">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="22bf6-298">Das Resultat der Aktivitätsausführung.</span><span class="sxs-lookup"><span data-stu-id="22bf6-298">The net result of running the activity.</span></span>
    
<span data-ttu-id="22bf6-p133">Diese Informationen werden bei jeder Ausführung einer synthetischen Transaktion automatisch generiert. Sie werden jedoch nicht automatisch angezeigt oder in einer Protokolldatei gespeichert. Wenn Sie eine synthetische Transaktion manuell durchführen, können Sie den Parameter OutLoggerVariable verwenden, um eine Windows PowerShell-Variable anzugeben, in der diese Informationen gespeichert werden. Sie können dann das umfassende Protokoll mithilfe von Methoden entweder im XML- oder HTML-Format anzeigen und/oder speichern.</span><span class="sxs-lookup"><span data-stu-id="22bf6-p133">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file. If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored. From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="22bf6-302">Zum Abrufen der Informationen zur Problembehandlung geben Sie den Parameter OutLoggerVariable an, gefolgt von einem Variablennamen, den Sie auswählen:</span><span class="sxs-lookup"><span data-stu-id="22bf6-302">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="22bf6-303">: Der Name der Variablen mit dem Zeichen $ führen Sie nicht vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="22bf6-303">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="22bf6-304">Verwenden Sie einen Variablennamen wie RegistrationTest (nicht $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="22bf6-304">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="22bf6-305">Wenn Sie diesen Befehl ausführen, sehen Sie eine Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="22bf6-305">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="22bf6-306">Ziel-Fqdn: "Atl-Cs-001.litwareinc.com" Ergebnis: Fehler bei Wartezeit: 00:00:00 Fehlermeldung: diesen Computer verfügt nicht über alle zugewiesenen Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="22bf6-306">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="22bf6-307">Diagnose: Sie ausführlichere Informationen für diesen Fehler als nur die hier angezeigten Fehlermeldung zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="22bf6-307">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="22bf6-308">Sie können einen ähnlichen Befehl wie den folgenden verwenden, um auf diese Informationen im HTML-Format zuzugreifen und die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="22bf6-308">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="22bf6-309">Alternativ können Sie die ToXML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="22bf6-309">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="22bf6-310">Sie können diese Dateien mithilfe von Windows Internet Explorer, Microsoft Visual Studio oder einer beliebigen anderen Anwendung anzeigen, die HTML-/XML-Dateien öffnen kann.</span><span class="sxs-lookup"><span data-stu-id="22bf6-310">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="22bf6-311">Führen Sie in System Center Operations Manager von synthetische Transaktionen werden diese Protokolldateien für Fehler automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="22bf6-311">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="22bf6-312">Diese Protokolle werden jedoch nicht generiert, wenn die Ausführung scheitert, bevor die synthetische Transaktion in Skype for Business Server PowerShell geladen und ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="22bf6-312">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="22bf6-313">In Skype for Business Server 2015 werden die Protokolldateien standardmäßig in einem Ordner gespeichert, der nicht freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="22bf6-313">By default, Skype for Business Server 2015 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="22bf6-314">Um den Zugriff auf diese Protokolle zu ermöglichen, sollten Sie diesen Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="22bf6-314">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="22bf6-315">Beispiel: \\atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="22bf6-315">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 