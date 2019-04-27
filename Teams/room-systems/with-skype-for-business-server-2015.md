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
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Bereitstellen von Microsoft-Teams, Räume mit Skype für Business Server
  
In diesem Thema wird erläutert, wie Sie ein Gerät-Konto für Microsoft-Teams Chatrooms hinzufügen, Sie mit eine einzelnen Gesamtstruktur, lokale Bereitstellung haben.
  
Wenn Sie einer einzelnen Gesamtstruktur, lokalen Bereitstellung von Exchange 2013 SP1 oder höher und Skype für Business Server 2015 oder höher verfügen, können Sie bereitgestellte Windows PowerShell-Skripts verwenden, um Gerät Konten zu erstellen. Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, können Sie die entsprechenden-Cmdlets verwenden, die die gleichen Ergebnisse erzeugt. Diese Cmdlets werden in diesem Abschnitt beschrieben.

  
Bevor Sie Microsoft Teams Chatrooms bereitstellen beginnen, müssen Sie unbedingt, mit denen Sie die entsprechenden Berechtigungen für die zugehörigen Cmdlets ausführen.
  

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

   Beachten Sie, dass $strExchangeServer den vollqualifizierten Domänennamen (FQDN) des Exchange-Servers, und $strLyncFQDN der FQDN des Ihrer Skype für Business Server-Bereitstellung ist.

2. Nach dem Einrichten einer Sitzung, werden Sie entweder ein neues Postfach erstellen und als eine RoomMailboxAccount zu aktivieren oder Ändern der Einstellungen für ein vorhandenes Raumpostfach. Dadurch wird das Konto zum Microsoft-Teams Chatrooms authentifizieren.

    Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Wenn Sie eine neue Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Sie können die verschiedenen Exchange-Eigenschaften auf das Gerät Konto zur Verbesserung der besprechungsumgebung für Personen festlegen. Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Wenn Sie sich entscheiden, damit das Kennwort nicht abläuft, können Sie, die mit Windows PowerShell-Cmdlets zu festlegen. Weitere Informationen finden Sie unter „Kennwortverwaltung“.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Aktivieren Sie das Konto in Active Directory, damit es zu Microsoft-Teams Räumen authentifiziert wird.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Aktivieren Sie das Gerät Konto mit Skype für Business Server, indem Ihre Microsoft Teams Chatrooms Active Directory-Kontos auf einen Skype für Business Server-Pool aktivieren:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Sie müssen die SIP-Adresse (Session Initiation-Protokoll) und den Domänencontroller für das Projekt verwenden.

7. **Optional.** Sie können auch Microsoft Teams Chatrooms tätigen und annehmen von public switched Telephone Network, (PSTN) Telefonanrufe durch Aktivieren von Enterprise-VoIP für Ihr Konto. Enterprise-VoIP ist eine Voraussetzung für Microsoft-Teams Chatrooms nicht, wenn Sie PSTN-Einwahl-Funktionalität für den Client für Microsoft-Teams Chatrooms möchten, es gibt aber noch zum Aktivieren:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Auch hier müssen Sie die bereitgestellten Beispiele für den Domänencontroller und die Telefonnummer durch Ihre eigenen Informationen ersetzen. Der Parameterwert „$true“ bleibt unverändert.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Beispiel: Raum kontoeinrichtung in Exchange und Skype für Business Server lokal

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

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Microsoft-Teams Räume](room-systems-v2-configure-accounts.md)

[Planen der Microsoft-Teams, Räume](skype-room-systems-v2-0.md)
  
[Bereitstellen von Microsoft-Teams, Räume](room-systems-v2.md)
  
[Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)