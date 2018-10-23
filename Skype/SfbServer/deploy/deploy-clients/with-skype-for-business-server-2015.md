---
title: Bereitstellen von Skype Raum Systemen v2 mit Skype für Business Server
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
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lesen Sie dieses Thema bietet Informationen zum Skype Raum Systemen v2 mit Skype für Business Server bereitstellen.
ms.openlocfilehash: 891f716be3a2b7d8479af83b57dfccd70500e50d
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699380"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a><span data-ttu-id="f31fd-103">Bereitstellen von Skype Raum Systemen v2 mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="f31fd-103">Deploy Skype Room Systems v2 with Skype for Business Server</span></span>
  
<span data-ttu-id="f31fd-104">In diesem Thema wird erläutert, wie Sie ein Gerät Konto für Skype Raum Systemen v2 hinzufügen, wenn Sie eine einzelnen Gesamtstruktur, lokale Bereitstellung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f31fd-104">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="f31fd-105">Wenn Sie einer einzelnen Gesamtstruktur, lokalen Bereitstellung von Exchange 2013 SP1 oder höher und Skype für Business Server 2015 oder höher verfügen, können Sie bereitgestellte Windows PowerShell-Skripts verwenden, um Gerät Konten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f31fd-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="f31fd-106">Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, können Sie die entsprechenden-Cmdlets verwenden, die die gleichen Ergebnisse erzeugt.</span><span class="sxs-lookup"><span data-stu-id="f31fd-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="f31fd-107">Diese Cmdlets werden in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f31fd-107">Those cmdlets are described in this section.</span></span>

<span data-ttu-id="f31fd-108">Die einfachste Möglichkeit zum Einrichten von Benutzerkonten ist von remote Windows PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f31fd-108">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="f31fd-109">Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten, mit denen Sie damit können Sie diese in kompatibel Skype Raum Systemen v2-Benutzerkonten aktivieren überprüfen helfen.</span><span class="sxs-lookup"><span data-stu-id="f31fd-109">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="f31fd-110">Auf Wunsch können Sie die Schritte unten, um Geräts v2 Skype Raum Systemen verwendeten Konten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f31fd-110">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a><span data-ttu-id="f31fd-111">Bereitstellen von Skype Raum Systemen v2 mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="f31fd-111">Deploy Skype Room Systems v2 with Skype for Business Server</span></span>

<span data-ttu-id="f31fd-112">Bevor Sie Skype Raum Systemen v2 mit Skype für Business Server bereitstellen, achten Sie darauf, dass Sie die Anforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="f31fd-112">Before you deploy Skype Room Systems v2 with Skype for Business Server, be sure you have met the requirements.</span></span> <span data-ttu-id="f31fd-113">Weitere Informationen finden Sie unter [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f31fd-113">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="f31fd-114">Bevor Sie Skype Raum Systemen v2 bereitstellen beginnen, müssen Sie unbedingt, mit denen Sie die entsprechenden Berechtigungen für die zugehörigen Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="f31fd-114">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="f31fd-115">Eine Windows PowerShell-Remotesitzung von einem PC starten und eine Verbindung mit Exchange herstellen.</span><span class="sxs-lookup"><span data-stu-id="f31fd-115">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span> 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   <span data-ttu-id="f31fd-116">Beachten Sie, dass $strExchangeServer den vollqualifizierten Domänennamen (FQDN) des Exchange-Servers, und $strLyncFQDN der FQDN des Ihrer Skype für Business Server-Bereitstellung ist.</span><span class="sxs-lookup"><span data-stu-id="f31fd-116">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>
    
2. <span data-ttu-id="f31fd-117">Nach dem Einrichten einer Sitzung, werden Sie entweder ein neues Postfach erstellen und als eine RoomMailboxAccount zu aktivieren oder Ändern der Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="f31fd-117">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="f31fd-118">Dadurch wird das Konto zum Skype Raum Systemen v2 authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="f31fd-118">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
    <span data-ttu-id="f31fd-119">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="f31fd-119">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="f31fd-120">Wenn Sie eine neue Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="f31fd-120">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="f31fd-121">Sie können die verschiedenen Exchange-Eigenschaften auf das Gerät Konto zur Verbesserung der besprechungsumgebung für Personen festlegen.</span><span class="sxs-lookup"><span data-stu-id="f31fd-121">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="f31fd-122">Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="f31fd-122">You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="f31fd-123">Wenn Sie sich entscheiden, damit das Kennwort nicht abläuft, können Sie, die mit Windows PowerShell-Cmdlets zu festlegen.</span><span class="sxs-lookup"><span data-stu-id="f31fd-123">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="f31fd-124">Weitere Informationen finden Sie unter „Kennwortverwaltung“.</span><span class="sxs-lookup"><span data-stu-id="f31fd-124">See Password management for more information.</span></span>
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="f31fd-125">Aktivieren Sie das Konto in Active Directory, damit es Skype Raum Systemen V2 authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="f31fd-125">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="f31fd-126">Aktivieren Sie das Gerät Konto mit Skype für Business Server, indem Ihre Skype Raum Systemen v2 Active Directory-Kontos auf einen Skype für Business Server-Pool aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f31fd-126">Enable the device account with Skype for Business Server by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="f31fd-127">Sie müssen die SIP-Adresse (Session Initiation-Protokoll) und den Domänencontroller für das Projekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="f31fd-127">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span> 
    
7. <span data-ttu-id="f31fd-128">**Optional.**</span><span class="sxs-lookup"><span data-stu-id="f31fd-128">**Optional.**</span></span> <span data-ttu-id="f31fd-129">Sie können auch Skype Raum Systemen v2 tätigen und annehmen von public switched Telephone Network, (PSTN) Telefonanrufe durch Aktivieren von Enterprise-VoIP für Ihr Konto.</span><span class="sxs-lookup"><span data-stu-id="f31fd-129">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="f31fd-130">Enterprise-VoIP ist eine Voraussetzung für Skype Raum Systemen v2 nicht, wenn Sie PSTN-Einwahl-Funktionalität für den Skype Raum Systemen v2 Client möchten, es gibt aber noch zum Aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f31fd-130">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="f31fd-p108">Auch hier müssen Sie die bereitgestellten Beispiele für den Domänencontroller und die Telefonnummer durch Ihre eigenen Informationen ersetzen. Der Parameterwert „$true“ bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="f31fd-p108">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="f31fd-133">Beispiel: Raum kontoeinrichtung in Exchange und Skype für Business Server lokal</span><span class="sxs-lookup"><span data-stu-id="f31fd-133">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="f31fd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f31fd-134">See also</span></span>

[<span data-ttu-id="f31fd-135">Konfigurieren von Konten für Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="f31fd-135">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="f31fd-136">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="f31fd-136">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="f31fd-137">Bereitstellen von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="f31fd-137">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="f31fd-138">Konfigurieren einer Konsole für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="f31fd-138">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="f31fd-139">Verwalten von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="f31fd-139">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)