---
title: Bereitstellen Microsoft Teams-Räume mit Skype for Business Server
ms.author: dstrome
author: dstrome
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
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Skype for Business Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 14d942e041d11cfd95b38f4cdcc18ad614c135df9d88b3a3e55261236144bffd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296642"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Bereitstellen Microsoft Teams-Räume mit Skype for Business Server
  
In diesem Thema wird erläutert, wie Sie ein Gerätekonto für Microsoft Teams-Räume, wenn Sie über eine lokale Bereitstellung mit einer Gesamtstruktur verfügen.
  
Wenn Sie über eine lokale Bereitstellung mit einer Gesamtstruktur mit Exchange 2013 SP1 oder höher und Skype for Business Server 2015 oder höher verfügen, können Sie die bereitgestellten Windows PowerShell-Skripts verwenden, um Gerätekonten zu erstellen. Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, können Sie entsprechende Cmdlets verwenden, die dieselben Ergebnisse erzeugen. Diese Cmdlets werden in diesem Abschnitt beschrieben.

  
Bevor Sie mit der Bereitstellung Microsoft Teams-Räume, stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen.
  

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

   Beachten Sie$strExchangeServer dass $strExchangeServer der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) Ihres Exchange-Servers und $strLyncFQDN der FQDN Ihrer Skype for Business Server ist.

2. Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch kann sich das Konto bei anderen Microsoft Teams-Räume.

    Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Wenn Sie ein neues Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Sie können verschiedene Exchange Eigenschaften für das Gerätekonto festlegen, um die Besprechungserfahrung für die Benutzer zu verbessern. Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Wenn das Kennwort nicht ablaufen soll, können Sie dies auch mit Windows PowerShell festlegen. Weitere Informationen finden Sie unter „Kennwortverwaltung“.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Aktivieren Sie das Konto in Active Directory, damit es sich für die Microsoft Teams-Räume.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Aktivieren Sie das Gerätekonto mit Skype for Business Server, indem Sie Ihr Microsoft Teams-Räume Active Directory-Konto in einem Skype for Business Server aktivieren:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Sie müssen die SIP-Adresse (Session Initiation-Protokoll) und den Domänencontroller für das Projekt verwenden.

7. **Optional.** Sie können Benutzern auch Microsoft Teams-Räume, Telefonanrufe im öffentlichen Telefonnetz (PSTN) zu erstellen und zu empfangen, indem Sie Enterprise-VoIP Für Ihr Konto aktivieren. Enterprise-VoIP ist für Microsoft Teams-Räume keine Voraussetzung. Wenn Sie aber PSTN-Wählfunktionen für den Microsoft Teams-Räume-Client verwenden möchten, können Sie ihn wie hier gezeigt aktivieren:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Auch hier müssen Sie die bereitgestellten Beispiele für den Domänencontroller und die Telefonnummer durch Ihre eigenen Informationen ersetzen. Der Parameterwert „$true“ bleibt unverändert.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Beispiel: Einrichten eines Raumkontos in Exchange und Skype for Business Server lokal

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

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
