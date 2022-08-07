---
title: Bereitstellen von Microsoft Teams-Räume mit Skype for Business Server
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Skype for Business Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 53903052efe28a85400ba8b418bd8869ef2dec4e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271680"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Bereitstellen von Microsoft Teams-Räume mit Skype for Business Server
  
In diesem Thema wird erläutert, wie Sie ein Ressourcenkonto für Microsoft Teams-Räume hinzufügen, wenn Sie über eine lokale Bereitstellung mit einer einzigen Gesamtstruktur verfügen.
  
Wenn Sie über eine lokale Bereitstellung mit einer einzelnen Gesamtstruktur mit Exchange 2013 SP1 oder höher und Skype for Business Server 2015 oder höher verfügen, können Sie die bereitgestellten Windows PowerShell Skripts verwenden, um Gerätekonten zu erstellen. Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, können Sie äquivalente Cmdlets verwenden, die dieselben Ergebnisse liefern. Diese Cmdlets werden in diesem Abschnitt beschrieben.
  
Bevor Sie mit der Bereitstellung von Microsoft Teams-Räume beginnen, stellen Sie sicher, dass Sie über die richtigen Berechtigungen zum Ausführen der zugeordneten Cmdlets verfügen.
  

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

   Beachten Sie, dass $strExchangeServer der vollqualifizierte Domänenname (FQDN) Ihres Exchange-Servers ist und $strLyncFQDN der FQDN Ihrer Skype for Business Server-Bereitstellung ist.

2. Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount oder ändern die Einstellungen für ein vorhandenes Raumpostfach. Dadurch kann sich das Konto bei Microsoft Teams-Räume authentifizieren.

    Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Wenn Sie ein neues Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Sie können verschiedene Exchange-Eigenschaften für das Teams-Räume Ressourcenkonto festlegen, um die Besprechungserfahrung für Personen zu verbessern. Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. Deaktivieren Sie den Kennwortablauf für das Ressourcenkonto.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Aktivieren Sie das Ressourcenkonto in Active Directory, damit es sich bei Microsoft Teams-Räume authentifiziert.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. Aktivieren Sie das Ressourcenkonto mit Skype for Business Server, indem Sie Ihr Microsoft Teams-Räume Active Directory-Konto in einem Skype for Business Server-Pool aktivieren:

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    Ändern Sie die `-DomainController` `-RegistrarPool` Und-Attribute in Werte, die für Ihre Umgebung geeignet sind.

7. **Optional.** Sie können auch zulassen, dass Microsoft Teams-Räume PSTN-Telefonanrufe tätigen und empfangen, indem Sie Enterprise-VoIP für Ihr Konto aktivieren. Enterprise-VoIP ist keine Anforderung für Microsoft Teams-Räume, aber wenn Sie PSTN-Wählfunktionen für Microsoft Teams-Räume möchten, gehen Sie wie folgt vor, um sie zu aktivieren:

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   Auch hier müssen Sie die bereitgestellten Beispiele für den Domänencontroller und die Telefonnummer durch Ihre eigenen Informationen ersetzen. Der Parameterwert „$true“ bleibt unverändert. Außerdem müssen Sie die Namen der VoIP-Richtlinie und der Wählplanrichtlinien ersetzen.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Beispiel: Einrichten von Raumkonten in Exchange und Skype for Business Server lokal

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
