---
title: Bereitstellen von Skype Room Systems v2 mit Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Skype Raum Systemen v2 mit Skype für Business Server 2015.
ms.openlocfilehash: 904835e766283791f52c0dc1d1221a0d7253e3e1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a>Bereitstellen von Skype Room Systems v2 mit Skype for Business Server 2015
 
Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Skype Raum Systemen v2 mit Skype für Business Server 2015.
  
In diesem Thema wird erläutert, wie Sie ein Gerät Konto für Skype Raum Systemen v2 hinzufügen, wenn Sie eine einzelnen Gesamtstruktur, lokale Bereitstellung vorhanden sind.
  
Wenn Sie einer einzelnen Gesamtstruktur, lokalen Bereitstellung von Exchange 2013 SP1 oder höher und Skype für Business Server 2015 oder höher verfügen, können Sie bereitgestellte Windows PowerShell-Skripts verwenden, um Gerät Konten zu erstellen. Wenn Sie eine Bereitstellung mit mehreren Gesamtstrukturen verwenden, können Sie die entsprechenden-Cmdlets verwenden, die die gleichen Ergebnisse erzeugt. Diese Cmdlets werden in diesem Abschnitt beschrieben.
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a>Bereitstellen von Skype Room Systems v2 mit Skype for Business Server 2015

Vor der Bereitstellung von Skype Raum Systemen v2 mit Skype für Business Server 2015, achten Sie darauf, dass Sie die Anforderungen erfüllt sind. Weitere Informationen finden Sie unter [Skype Raum Systemen v2 Requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Bevor Sie Skype Raum Systemen v2 bereitstellen beginnen, müssen Sie unbedingt, mit denen Sie die entsprechenden Berechtigungen für die zugehörigen Cmdlets ausführen.
  
1. Eine Windows PowerShell-Remotesitzung von einem PC starten und eine Verbindung mit Exchange herstellen. 
    
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

   Beachten Sie, dass $strExchangeServer den vollqualifizierten Domänennamen (FQDN) des Exchange-Servers ist, und $strLyncFQDN der FQDN des Ihrer Skype für Business Server 2015 Bereitstellung ist.
    
2. Nach dem Einrichten einer Sitzung, werden Sie entweder ein neues Postfach erstellen und als eine RoomMailboxAccount zu aktivieren oder Ändern der Einstellungen für ein vorhandenes Raumpostfach. Dadurch wird das Konto zum Skype Raum Systemen v2 authentifizieren.
    
    Wenn Sie ein vorhandenes Ressourcenpostfach ändern:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Wenn Sie eine neue Ressourcenpostfach erstellen:
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Sie können die verschiedenen Exchange-Eigenschaften auf das Gerät Konto zur Verbesserung der besprechungsumgebung für Personen festlegen. Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Wenn Sie sich entscheiden, damit das Kennwort nicht abläuft, können Sie, die mit Windows PowerShell-Cmdlets zu festlegen. Weitere Informationen finden Sie unter „Kennwortverwaltung“.
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Aktivieren Sie das Konto in Active Directory, damit es Skype Raum Systemen V2 authentifiziert wird.
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Aktivieren Sie das Gerät Konto mit Skype für Business Server 2015, indem Ihre Skype Raum Systemen v2 Active Directory-Kontos auf einen Skype für Business Server 2015 Pool aktivieren:
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Sie müssen die SIP-Adresse (Session Initiation-Protokoll) und den Domänencontroller für das Projekt verwenden. 
    
7. **Optional.** Sie können auch Skype Raum Systemen v2 tätigen und annehmen von public switched Telephone Network, (PSTN) Telefonanrufe durch Aktivieren von Enterprise-VoIP für Ihr Konto. Enterprise-VoIP ist eine Voraussetzung für Skype Raum Systemen v2 nicht, wenn Sie PSTN-Einwahl-Funktionalität für den Skype Raum Systemen v2 Client möchten, es gibt aber noch zum Aktivieren:
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01

   ```

   Auch hier müssen Sie die bereitgestellten Beispiele für den Domänencontroller und die Telefonnummer durch Ihre eigenen Informationen ersetzen. Der Parameterwert „$true“ bleibt unverändert.
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a>Beispiel: Raum kontoeinrichtung in Exchange und Skype für Business Server 2015 lokal

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

## <a name="see-also"></a>Siehe auch

#### 

[Planen von Skype Raum Systemen v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)
  
[Konfigurieren einer Skype Raum Systemen v2-Konsole](console.md)
  
[Verwalten von Skype Raum Systemen v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

