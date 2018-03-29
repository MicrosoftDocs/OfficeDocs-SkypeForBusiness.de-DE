---
title: Konfigurieren von Exchange Server Unified Messaging für Voicemail on Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Zusammenfassung: Konfigurieren Sie Exchange Server Unified Messaging für Skype für Voicemail Business Server.'
ms.openlocfilehash: 9f4cb3dcd43d8f6300a5fbe38bd37c40d48e8273
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a>Konfigurieren von Exchange Server Unified Messaging für Voicemail on Skype for Business Server 2015
 
**Zusammenfassung:** Konfigurieren von Exchange Server Unified Messaging für Skype für Voicemail Business Server.
  
Skype für Business Server 2015 können Sie Voicemail-Nachrichten in Exchange Server 2016 oder Exchange Server 2013 gespeichert haben. Diese Voicemailnachrichten werden dann als e-Mail-Nachrichten in die Posteingänge der Benutzer angezeigt. 
  
Wenn Sie die Server-zu-Server-Authentifizierung zwischen Skype für Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 bereits konfiguriert haben, sind Sie bereit, So richten Sie unified messaging. Hierzu müssen Sie zuerst erstellen und zuweisen ein neuen Wählplans für unified messaging auf Ihrem Exchange Server. Diese beiden Befehle (von in der Exchange-Verwaltungsshell ausgeführt) konfigurieren beispielsweise einen neuen 3 Ziffer Wählplan für Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Im ersten Befehl im Beispiel geben der Parameter „VoIPSecurity“ und der Parameterwert „Secured“ an, dass der Signalkanal mithilfe von TLS (Transport Layer Security) verschlüsselt wird. Der URI-Typ „SipName“ gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert „1“ für „CountryOrRegionCode“ gibt an, dass der Wählplan für die USA gilt.
  
Im zweiten Befehl gibt der an den Parameter „ConfiguredInCountryOrRegionGroups“ übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können. Der Wert des Parameters "Anywhere,\*,\*,\*" legt Folgendes fest:
  
- Gruppenname („Anywhere“)
    
- AllowedNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige Nummernzeichenfolge zulässig ist)
    
- DialNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige gewählte Nummer zulässig ist)
    
- TextComment (\*, ein Platzhalterzeichen, das angibt, dass alle Textbefehl zulässig ist)
    
> [!NOTE]
> Die Erstellung eines neuen Wählplans sorgt zusätzlich für die Erstellung einer standardmäßigen Postfachrichtlinie. 
  
Nach dem Erstellen und Konfigurieren des neuen Wählplans müssen Sie das neue Wählplan an Ihre unified messaging-Server aus, und ändern Sie den Startmodus des betreffenden Servers hinzufügen. Insbesondere müssen Sie den Startmodus zu "Dual" festlegen. Sie können diese beiden Aufgaben aus in der Exchange-Verwaltungsshell ausführen:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Nach dem Konfigurieren der unified messaging-Servers sollten Sie als Nächstes ausführen das Cmdlet Enable-ExchangeCertificate, um sicherzustellen, dass Ihre Exchange-Zertifikat auf den unified messaging-Dienst angewendet wird:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Nachdem das Zertifikat ordnungsgemäß zugewiesen wurde, müssen Sie den MsExchangeUM-Dienst auf dem Unified Messaging-Server beenden und neu starten. Dieser Dienst muss jedes Mal beendet und neu gestartet werden, wenn der Startmodus geändert wurde.
  
Wenn die Konfiguration des UM-Servers abgeschlossen ist, können Sie den UM-Anrufrouter konfigurieren:
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Da der Startmodus geändert wurde, müssen Sie den MsExchangeUMCR-Dienst auf dem Computer mit dem UM-Anrufrouter beenden und neu starten.
  
Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Sie können Unified Messaging für einen Benutzer mit einem Befehl wie dem folgenden aktivieren:
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

Im vorherigen Befehl steht der Parameter „Extensions“ für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.
  
Nach dem Aktivieren des Postfachs sollte der Benutzer „kenmyer@litwareinc.com“ Exchange Unified Messaging verwenden können. Sie können überprüfen, ob der Benutzer mit Exchange UM verbinden kann, indem das Cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) von innerhalb der Skype für Business Server-Verwaltungsshell ausgeführt:
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Wenn Sie einen zweiten Benutzer verfügen, die für unified messaging aktiviert wurde können Sie das Cmdlet " [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) " verwenden, um sicherzustellen, dass der zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


