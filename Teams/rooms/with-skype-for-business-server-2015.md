---
title: Bereitstellen von Microsoft Teams-Chatrooms mit Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Skype for Business Server.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f1f0788e9c2342f2bac8484ceb1cc83bf30fd8d3
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140998"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="d9b28-103">Bereitstellen von Microsoft Teams-Chatrooms mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d9b28-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="d9b28-104">In diesem Thema wird erläutert, wie Sie ein Geräte Konto für Microsoft Teams-Chatrooms hinzufügen, wenn Sie über eine einzelne Gesamtstruktur verfügen, die lokal bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d9b28-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="d9b28-105">Wenn Sie über eine einzelne Gesamtstruktur, eine lokale Bereitstellung mit Exchange 2013 SP1 oder höher und Skype for Business Server 2015 oder höher verfügen, können Sie die bereitgestellten Windows PowerShell-Skripts verwenden, um Geräte Konten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9b28-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="d9b28-106">Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, können Sie entsprechende Cmdlets verwenden, die die gleichen Ergebnisse erzielen.</span><span class="sxs-lookup"><span data-stu-id="d9b28-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="d9b28-107">Diese Cmdlets werden in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9b28-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="d9b28-108">Bevor Sie mit der Bereitstellung von Microsoft Teams-Räumen beginnen, müssen Sie sicherstellen, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen.</span><span class="sxs-lookup"><span data-stu-id="d9b28-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="d9b28-109">Beachten Sie, dass $strExchangeServer der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) Ihres Exchange-Servers und $strLyncFQDN der FQDN Ihrer Skype for Business Server-Bereitstellung ist.</span><span class="sxs-lookup"><span data-stu-id="d9b28-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="d9b28-110">Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie können die Einstellungen für ein vorhandenes Raumpostfach ändern.</span><span class="sxs-lookup"><span data-stu-id="d9b28-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="d9b28-111">Dadurch kann sich das Konto bei Microsoft Teams-Räumen authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="d9b28-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="d9b28-112">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="d9b28-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="d9b28-113">Wenn Sie ein neues Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="d9b28-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="d9b28-114">Sie können verschiedene Exchange-Eigenschaften für das Geräte Konto einrichten, um die Besprechungs Erfahrung für Personen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d9b28-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="d9b28-115">Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="d9b28-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="d9b28-116">Wenn Sie sich entscheiden, dass das Kennwort nicht abläuft, können Sie dies auch mit Windows PowerShell-Cmdlets festlegen.</span><span class="sxs-lookup"><span data-stu-id="d9b28-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="d9b28-117">Weitere Informationen finden Sie unter „Kennwortverwaltung“.</span><span class="sxs-lookup"><span data-stu-id="d9b28-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="d9b28-118">Aktivieren Sie das Konto in Active Directory, damit es sich bei Microsoft Teams-Räumen authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="d9b28-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="d9b28-119">Aktivieren Sie das Geräte Konto in Skype for Business Server, indem Sie Ihr Microsoft Teams rooms Active Directory-Konto in einem Skype for Business Server-Pool aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d9b28-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="d9b28-120">Sie müssen die SIP-Adresse (Session Initiation-Protokoll) und den Domänencontroller für das Projekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9b28-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="d9b28-121">**Optional.**</span><span class="sxs-lookup"><span data-stu-id="d9b28-121">**Optional.**</span></span> <span data-ttu-id="d9b28-122">Sie können auch Microsoft Teams-Chatrooms das tätigen und empfangen von PSTN-Telefon anrufen (Public Switched Telephone Network) ermöglichen, indem Sie Enterprise-VoIP für Ihr Konto aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d9b28-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="d9b28-123">Enterprise-VoIP ist keine Voraussetzung für Microsoft Teams-Chatrooms, aber wenn Sie die PSTN-Wählfunktion für den Microsoft Teams rooms-Client nutzen möchten, können Sie ihn so aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d9b28-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="d9b28-p106">Auch hier müssen Sie die bereitgestellten Beispiele für den Domänencontroller und die Telefonnummer durch Ihre eigenen Informationen ersetzen. Der Parameterwert „$true“ bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="d9b28-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="d9b28-126">Beispiel: Einrichtung des Room-Kontos in Exchange und Skype for Business Server lokal</span><span class="sxs-lookup"><span data-stu-id="d9b28-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d9b28-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9b28-127">See also</span></span>

[<span data-ttu-id="d9b28-128">Konfigurieren von Konten für Microsoft Teams-Chatrooms</span><span class="sxs-lookup"><span data-stu-id="d9b28-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="d9b28-129">Planen von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="d9b28-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="d9b28-130">Bereitstellen von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="d9b28-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="d9b28-131">Konfigurieren einer Microsoft Teams rooms-Konsole</span><span class="sxs-lookup"><span data-stu-id="d9b28-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="d9b28-132">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="d9b28-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
