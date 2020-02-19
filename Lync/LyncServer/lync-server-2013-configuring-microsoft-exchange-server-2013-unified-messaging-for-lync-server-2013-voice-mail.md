---
title: 'Lync Server 2013: Konfigurieren Microsoft Exchange Server 2013 Unified Messaging für lync Server 2013-Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33c506e8b9f1201ad9382e361afc376590c6feca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Konfigurieren Microsoft Exchange Server 2013 Unified Messaging für Microsoft lync Server 2013-Voicemail

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-04_

Microsoft lync Server 2013 können Voicemail-Nachrichten in Microsoft Exchange Server 2013 gespeichert werden; Diese Voicemail-Nachrichten werden dann als e-Mail-Nachrichten in den Posteingängen Ihrer Benutzer angezeigt. Diese Funktion wurde auch in den 2010-Editionen von lync Server und Exchange gefunden; das Konfigurieren dieses "Unified Messaging" wurde in den 2013-Editionen jedoch dank der Einführung der um-Anruf-Router-Komponente vereinfacht. Diese Komponente wird auf dem Exchange 2013-Client Zugriffsserver installiert, und alle Anrufe an Exchange Unified Messaging (beispielsweise eine Voicemail) werden zuerst über den Anruf Router geleitet und dann an den entsprechenden Postfachserver umgeleitet.

Wenn Sie die Server-zu-Server-Authentifizierung bereits zwischen lync Server 2013 und Exchange 2013 konfiguriert haben, sind Sie zum Einrichten von Unified Messaging fähig. Hierzu müssen Sie zuerst einen neuen Unified Messaging-Wählplan auf Ihrem Exchange-Server erstellen und zuweisen. Beispielsweise werden mit diesen beiden Befehlen (die in der Exchange-Verwaltungsshell ausgeführt werden) ein neuer dreistelliger Wählplan für Exchange konfiguriert:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

Im ersten Befehl im Beispiel geben der Parameter "VoIPSecurity" und der Parameterwert "Secured" an, dass der Signalkanal mithilfe von TLS (Transport Layer Security) verschlüsselt wird. Der URI-Typ "SipName" gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert "1" für "CountryOrRegionCode" gibt an, dass der Wählplan für die USA gilt.

Im zweiten Befehl gibt der an den Parameter "ConfiguredInCountryOrRegionGroups" übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können. Der Parameterwert "Anywhere,\*,\*,\*" legt Folgendes fest:

  - Gruppenname ("Anywhere")

  - AllowedNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige Nummernzeichenfolge zulässig ist)

  - DialNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige gewählte Nummer zulässig ist)

  - Textcomment (\*, ein Platzhalterzeichen, das angibt, dass ein beliebiger Textbefehl zulässig ist)

<div>


> [!NOTE]  
> Durch das Erstellen eines neuen Wählplans wird auch eine standardmäßige Postfachrichtlinie erstellt.



</div>

Nachdem Sie die neuen Wähleinstellungen erstellt und konfiguriert haben, müssen Sie den neuen Wählplan dem Unified Messaging-Server hinzufügen und dann den Startmodus dieses Servers ändern. insbesondere müssen Sie den Startmodus auf "Dual" festlegen. Sie können diese beiden Aufgaben in der Exchange-Verwaltungsshell ausführen:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Nach dem Konfigurieren des Unified Messaging-Servers sollten Sie als nächstes das Cmdlet Enable-ExchangeCertificate ausführen, um sicherzustellen, dass Ihr Exchange-Zertifikat auf den Unified Messaging-Dienst angewendet wird:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Nachdem das Zertifikat ordnungsgemäß zugewiesen wurde, müssen Sie den MsExchangeUM-Dienst auf dem Unified Messaging-Server beenden und neu starten. Dieser Dienst muss jedes Mal beendet und neu gestartet werden, wenn der Startmodus geändert wurde.

Wenn die Konfiguration des UM-Servers abgeschlossen ist, können Sie den UM-Anrufrouter konfigurieren:

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Da der Startmodus geändert wurde, müssen Sie den MsExchangeUMCR-Dienst auf dem Computer mit dem UM-Anrufrouter beenden und neu starten.

Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie, und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

Sie können für einen Benutzer Unified Messaging mit einem Befehl wie diesem aktivieren:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

Im vorhergehenden Befehl steht der Parameter "Extensions" für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.

Nach dem Aktivieren des Postfachs sollte der Benutzer "kenmyer@litwareinc.com" Exchange Unified Messaging verwenden können. Sie können überprüfen, ob der Benutzer eine Verbindung mit Exchange um herstellen kann, indem Sie das [Test-csexumconnectivity "-](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) Cmdlet in der lync Server-Verwaltungsshell ausführen:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Wenn ein zweiter Benutzer ist, für den Unified Messaging aktiviert wurde, können Sie mit dem Cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) sicherstellen, dass dieser zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

