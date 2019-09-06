---
title: Bereitstellen von Microsoft Teams-Chatrooms mit Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Skype for Business Server.
ms.openlocfilehash: 0661a19b3569cbfde5edfb5ceb631fab7282d302
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774946"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Bereitstellen von Microsoft Teams-Chatrooms mit Skype for Business Server
  
In diesem Thema wird erläutert, wie Sie ein Geräte Konto für Microsoft Teams-Chatrooms hinzufügen, wenn Sie über eine einzelne Gesamtstruktur verfügen, die lokal bereitgestellt wird.
  
Wenn Sie über eine einzelne Gesamtstruktur, eine lokale Bereitstellung mit Exchange 2013 SP1 oder höher und Skype for Business Server 2015 oder höher verfügen, können Sie die bereitgestellten Windows PowerShell-Skripts verwenden, um Geräte Konten zu erstellen. Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, können Sie entsprechende Cmdlets verwenden, die die gleichen Ergebnisse erzielen. Diese Cmdlets werden in diesem Abschnitt beschrieben.

  
Bevor Sie mit der Bereitstellung von Microsoft Teams-Räumen beginnen, müssen Sie sicherstellen, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen.
  

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

   Beachten Sie, dass $strExchangeServer der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) Ihres Exchange-Servers und $strLyncFQDN der FQDN Ihrer Skype for Business Server-Bereitstellung ist.

2. Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie können die Einstellungen für ein vorhandenes Raumpostfach ändern. Dadurch kann sich das Konto bei Microsoft Teams-Räumen authentifizieren.

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

3. Sie können verschiedene Exchange-Eigenschaften für das Geräte Konto einrichten, um die Besprechungs Erfahrung für Personen zu verbessern. Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Wenn Sie sich entscheiden, dass das Kennwort nicht abläuft, können Sie dies auch mit Windows PowerShell-Cmdlets festlegen. Weitere Informationen finden Sie unter „Kennwortverwaltung“.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Aktivieren Sie das Konto in Active Directory, damit es sich bei Microsoft Teams-Räumen authentifiziert.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Aktivieren Sie das Geräte Konto in Skype for Business Server, indem Sie Ihr Microsoft Teams rooms Active Directory-Konto in einem Skype for Business Server-Pool aktivieren:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Sie müssen die SIP-Adresse (Session Initiation-Protokoll) und den Domänencontroller für das Projekt verwenden.

7. **Optional.** Sie können auch Microsoft Teams-Chatrooms das tätigen und empfangen von PSTN-Telefon anrufen (Public Switched Telephone Network) ermöglichen, indem Sie Enterprise-VoIP für Ihr Konto aktivieren. Enterprise-VoIP ist keine Voraussetzung für Microsoft Teams-Chatrooms, aber wenn Sie die PSTN-Wählfunktion für den Microsoft Teams rooms-Client nutzen möchten, können Sie ihn so aktivieren:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Auch hier müssen Sie die bereitgestellten Beispiele für den Domänencontroller und die Telefonnummer durch Ihre eigenen Informationen ersetzen. Der Parameterwert „$true“ bleibt unverändert.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Beispiel: Einrichtung des Room-Kontos in Exchange und Skype for Business Server lokal

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

[Konfigurieren von Konten für Microsoft Teams-Chatrooms](room-systems-v2-configure-accounts.md)

[Planen von Microsoft Teams-Räumen](skype-room-systems-v2-0.md)
  
[Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)
  
[Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
