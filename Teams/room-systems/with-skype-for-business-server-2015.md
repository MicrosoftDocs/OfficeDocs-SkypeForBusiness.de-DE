---
title: Bereitstellen von Microsoft-Teams, Räume mit Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lesen Sie dieses Thema bietet Informationen zum Microsoft-Teams Chatrooms mit Skype für Business Server bereitstellen.
ms.openlocfilehash: f047eceedba698d186490aa80646aa21b44c1e2d
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362839"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="784c0-103">Bereitstellen von Microsoft-Teams, Räume mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="784c0-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="784c0-104">In diesem Thema wird erläutert, wie Sie ein Gerät-Konto für Microsoft-Teams Chatrooms hinzufügen, Sie mit eine einzelnen Gesamtstruktur, lokale Bereitstellung haben.</span><span class="sxs-lookup"><span data-stu-id="784c0-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="784c0-105">Wenn Sie einer einzelnen Gesamtstruktur, lokalen Bereitstellung von Exchange 2013 SP1 oder höher und Skype für Business Server 2015 oder höher verfügen, können Sie bereitgestellte Windows PowerShell-Skripts verwenden, um Gerät Konten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="784c0-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="784c0-106">Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, können Sie die entsprechenden-Cmdlets verwenden, die die gleichen Ergebnisse erzeugt.</span><span class="sxs-lookup"><span data-stu-id="784c0-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="784c0-107">Diese Cmdlets werden in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="784c0-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="784c0-108">Bevor Sie Microsoft Teams Chatrooms bereitstellen beginnen, müssen Sie unbedingt, mit denen Sie die entsprechenden Berechtigungen für die zugehörigen Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="784c0-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   <span data-ttu-id="784c0-109">Beachten Sie, dass $strExchangeServer den vollqualifizierten Domänennamen (FQDN) des Exchange-Servers, und $strLyncFQDN der FQDN des Ihrer Skype für Business Server-Bereitstellung ist.</span><span class="sxs-lookup"><span data-stu-id="784c0-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="784c0-110">Nach dem Einrichten einer Sitzung, werden Sie entweder ein neues Postfach erstellen und als eine RoomMailboxAccount zu aktivieren oder Ändern der Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="784c0-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="784c0-111">Dadurch wird das Konto zum Microsoft-Teams Chatrooms authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="784c0-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="784c0-112">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="784c0-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="784c0-113">Wenn Sie eine neue Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="784c0-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="784c0-114">Sie können die verschiedenen Exchange-Eigenschaften auf das Gerät Konto zur Verbesserung der besprechungsumgebung für Personen festlegen.</span><span class="sxs-lookup"><span data-stu-id="784c0-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="784c0-115">Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="784c0-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="784c0-116">Wenn Sie sich entscheiden, damit das Kennwort nicht abläuft, können Sie, die mit Windows PowerShell-Cmdlets zu festlegen.</span><span class="sxs-lookup"><span data-stu-id="784c0-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="784c0-117">Weitere Informationen finden Sie unter „Kennwortverwaltung“.</span><span class="sxs-lookup"><span data-stu-id="784c0-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="784c0-118">Aktivieren Sie das Konto in Active Directory, damit es zu Microsoft-Teams Räumen authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="784c0-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="784c0-119">Aktivieren Sie das Gerät Konto mit Skype für Business Server, indem Ihre Microsoft Teams Chatrooms Active Directory-Kontos auf einen Skype für Business Server-Pool aktivieren:</span><span class="sxs-lookup"><span data-stu-id="784c0-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="784c0-120">Sie müssen die SIP-Adresse (Session Initiation-Protokoll) und den Domänencontroller für das Projekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="784c0-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="784c0-121">**Optional.**</span><span class="sxs-lookup"><span data-stu-id="784c0-121">**Optional.**</span></span> <span data-ttu-id="784c0-122">Sie können auch Microsoft Teams Chatrooms tätigen und annehmen von public switched Telephone Network, (PSTN) Telefonanrufe durch Aktivieren von Enterprise-VoIP für Ihr Konto.</span><span class="sxs-lookup"><span data-stu-id="784c0-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="784c0-123">Enterprise-VoIP ist eine Voraussetzung für Microsoft-Teams Chatrooms nicht, wenn Sie PSTN-Einwahl-Funktionalität für den Client für Microsoft-Teams Chatrooms möchten, es gibt aber noch zum Aktivieren:</span><span class="sxs-lookup"><span data-stu-id="784c0-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="784c0-p106">Auch hier müssen Sie die bereitgestellten Beispiele für den Domänencontroller und die Telefonnummer durch Ihre eigenen Informationen ersetzen. Der Parameterwert „$true“ bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="784c0-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="784c0-126">Beispiel: Raum kontoeinrichtung in Exchange und Skype für Business Server lokal</span><span class="sxs-lookup"><span data-stu-id="784c0-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a><span data-ttu-id="784c0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="784c0-127">See also</span></span>

[<span data-ttu-id="784c0-128">Konfigurieren von Konten für Microsoft-Teams Räume</span><span class="sxs-lookup"><span data-stu-id="784c0-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="784c0-129">Planen der Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="784c0-129">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="784c0-130">Bereitstellen von Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="784c0-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="784c0-131">Konfigurieren einer Microsoft-Teams Räume-Konsole</span><span class="sxs-lookup"><span data-stu-id="784c0-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="784c0-132">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="784c0-132">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)