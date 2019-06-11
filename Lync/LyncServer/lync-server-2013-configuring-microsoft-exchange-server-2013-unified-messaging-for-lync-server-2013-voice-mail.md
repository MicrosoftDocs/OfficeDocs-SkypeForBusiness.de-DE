---
title: 'Lync Server 2013: Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für lync Server 2013-Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1d2bac84183e6cc274d6bb297c17401b3ff7f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für Microsoft lync Server 2013-Voicemail

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-04_

Mit Microsoft lync Server 2013 können Sie Voicemail-Nachrichten in Microsoft Exchange Server 2013 speichern. Diese Sprachnachrichten werden dann als e-Mail-Nachrichten in den Posteingängen Ihrer Benutzer angezeigt. Diese Funktion wurde auch in den 2010-Editionen von lync Server und Exchange gefunden. der Vorgang zum Konfigurieren dieses "Unified Messaging" wurde in den 2013-Editionen jedoch dank der Einführung der um-Anruf-Router-Komponente vereinfacht. Diese Komponente ist auf dem Exchange 2013-Client Zugriffsserver installiert, und alle Anrufe an Exchange Unified Messaging (wie eine Sprachnachricht) werden zuerst über den Anruf Router weitergeleitet und dann an den entsprechenden Postfachserver umgeleitet.

Wenn Sie die Server-zu-Server-Authentifizierung bereits zwischen lync Server 2013 und Exchange 2013 konfiguriert haben, können Sie Unified Messaging einrichten. Dazu müssen Sie zuerst einen neuen Unified Messaging-Wählplan auf dem Exchange-Server erstellen und zuweisen. So konfigurieren diese beiden Befehle (die in der Exchange-Verwaltungsshell ausgeführt werden) einen neuen dreistelligen Wählplan für Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

Im ersten Befehl im Beispiel geben der Parameter „VoIPSecurity“ und der Parameterwert „Secured“ an, dass der Signalkanal mithilfe von TLS (Transport Layer Security) verschlüsselt wird. Der URI-Typ „SipName“ gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert „1“ für „CountryOrRegionCode“ gibt an, dass der Wählplan für die USA gilt.

Im zweiten Befehl gibt der an den Parameter „ConfiguredInCountryOrRegionGroups“ übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können. Der Parameterwert "Anywhere;\*\*,\*" legt Folgendes fest:

  - Gruppenname („Anywhere“)

  - AllowedNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige Zahlen Zeichenfolge zulässig ist)

  - DialNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine gewählte Nummer zulässig ist)

  - Textcomment (\*ein Platzhalterzeichen, das angibt, dass ein beliebiger Textbefehl zulässig ist)

<div>


> [!NOTE]  
> Die Erstellung eines neuen Wählplans sorgt zusätzlich für die Erstellung einer standardmäßigen Postfachrichtlinie.



</div>

Nachdem Sie den neuen Wählplan erstellt und konfiguriert haben, müssen Sie den neuen Wählplan dem Unified Messaging-Server hinzufügen und dann den Startmodus dieses Servers ändern. insbesondere müssen Sie den Startmodus auf "Dual" einstellen. Sie können diese beiden Aufgaben in der Exchange-Verwaltungsshell ausführen:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Nachdem der Unified Messaging-Server konfiguriert wurde, müssen Sie als nächstes das Cmdlet Enable-ExchangeCertificate ausführen, um sicherzustellen, dass Ihr Exchange-Zertifikat auf den Unified Messaging-Dienst angewendet wird:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Nachdem das Zertifikat ordnungsgemäß zugewiesen wurde, müssen Sie den MsExchangeUM-Dienst auf dem Unified Messaging-Server beenden und neu starten. Dieser Dienst muss jedes Mal beendet und neu gestartet werden, wenn der Startmodus geändert wurde.

Wenn die Konfiguration des UM-Servers abgeschlossen ist, können Sie den UM-Anrufrouter konfigurieren:

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Da der Startmodus geändert wurde, müssen Sie den MsExchangeUMCR-Dienst auf dem Computer mit dem UM-Anrufrouter beenden und neu starten.

Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

Sie können Unified Messaging für einen Benutzer mit einem Befehl wie dem folgenden aktivieren:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

Im vorherigen Befehl steht der Parameter „Extensions“ für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.

Nach dem Aktivieren des Postfachs sollte der Benutzer „kenmyer@litwareinc.com“ Exchange Unified Messaging verwenden können. Sie können überprüfen, ob der Benutzer eine Verbindung mit Exchange um herstellen kann, indem Sie das Cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) in der lync Server-Verwaltungsshell ausführen:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Wenn ein zweiter Benutzer vorhanden ist, für den Unified Messaging aktiviert wurde, können Sie mit dem Cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) sicherstellen, dass dieser zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

