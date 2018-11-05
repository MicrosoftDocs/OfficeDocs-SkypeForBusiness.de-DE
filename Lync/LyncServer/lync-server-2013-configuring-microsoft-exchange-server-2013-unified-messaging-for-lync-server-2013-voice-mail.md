---
title: Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für Microsoft Lync Server 2013-Voicemail
TOCTitle: Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für Microsoft Lync Server 2013-Voicemail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49890646
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für Microsoft Lync Server 2013-Voicemail

 

_**Letztes Änderungsdatum des Themas:** 2013-02-04_

Mit Microsoft Lync Server 2013 können Sie Voicemailnachrichten Microsoft Exchange Server 2013 speichern. Diese Voicemailnachrichten werden dann als E-Mail-Nachrichten in den Postfächern Ihrer Benutzer angezeigt. Diese Funktion stand auch in den 2010-Editionen von Lync Server und Exchange zur Verfügung. Die Vorgehensweise zum Konfigurieren des sogenannten "Unified Messaging" wurde jedoch in den 2013-Editionen dank der Einführung der Komponente für die UM-Anrufrouting vereinfacht. Diese Komponente wird auf dem Exchange 2013-Clientzugriffsserver installiert. Alle Anrufe zu Exchange Unified Messaging (z. B. Voicemail) werden zunächst über den Anrufrouter geleitet und anschließend an den entsprechenden Postfachserver umgeleitet.

Wenn Sie bereits die Authentifizierung zwischen Servern für Lync Server 2013 und Exchange 2013 konfiguriert haben, können Sie nun Unified Messaging einrichten. Erstellen Sie dazu zuerst auf Ihrem Exchange-Server einen neuen UM-Wählplan, und weisen Sie ihn zu. Mit den folgenden beiden Befehlen (ausgeführt in der Exchange-Verwaltungsshell) wird beispielsweise ein neuer dreistelliger Wählplan für Exchange konfiguriert:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

Im ersten Befehl im Beispiel geben der Parameter "VoIPSecurity" und der Parameterwert "Secured" an, dass der Signalkanal mithilfe von TLS (Transport Layer Security) verschlüsselt wird. Der URI-Typ "SipName" gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert "1" für "CountryOrRegionCode" gibt an, dass der Wählplan für die USA gilt.

Im zweiten Befehl gibt der an den Parameter "ConfiguredInCountryOrRegionGroups" übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können. Der Parameterwert "Anywhere,\*,\*,\*" legt Folgendes fest:

  - Gruppenname ("Anywhere")

  - AllowedNumberString (\*, ein Platzhalter, der angibt, dass eine beliebige Nummernzeichenfolge zulässig ist)

  - DialNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige gewählte Nummer zulässig ist)

  - TextComment (\*, ein Platzhalterzeichen, das angibt, dass ein beliebiger Textbefehl zulässig ist)

Nach dem Erstellen und Konfigurieren des neuen Wählplans müssen Sie ihn zum Unified Messaging-Server hinzufügen und anschließend den Startmodus dieses Servers ändern, d. h. Sie müssen für den Startmodus "Dual" festlegen. Sie können beide Aufgaben in der Exchange-Verwaltungsshell ausführen:

    Set-UmServer -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Nach dem Konfigurieren des Unified Messaging-Servers sollten Sie als nächstes das Cmdlet "Enable-ExchangeCertificate" ausführen, um sicherzustellen, dass das Exchange-Zertifikat auf den Unified Messaging-Dienst angewendet wird:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Nachdem das Zertifikat ordnungsgemäß zugewiesen wurde, müssen Sie den MsExchangeUM-Dienst auf dem Unified Messaging-Server beenden und neu starten. Dieser Dienst muss jedes Mal beendet und neu gestartet werden, wenn der Startmodus geändert wurde.

Wenn die Konfiguration des UM-Servers abgeschlossen ist, können Sie den UM-Anrufrouter konfigurieren:

    Set-CsUMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Da der Startmodus geändert wurde, müssen Sie den MsExchangeUMCR-Dienst auf dem Computer mit dem UM-Anrufrouter beenden und neu starten.

Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie, und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:

    New-UMMailboxPolicy -ID "RedmondMailboxPolicy" -AllowedCountryOrRegionGroups "Anywhere"

Sie können für einen Benutzer Unified Messaging mit einem Befehl wie diesem aktivieren:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

Im vorhergehenden Befehl steht der Parameter "Extensions" für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.

Nach dem Aktivieren des Postfachs sollte der Benutzer "kenmyer@litwareinc.com" Exchange Unified Messaging verwenden können. Sie können überprüfen, ob der Benutzer eine Verbindung mit Exchange UM herstellen kann, indem Sie das Cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMConnectivity) über die Lync Server-Verwaltungsshell ausführen:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Wenn ein zweiter Benutzer ist, für den Unified Messaging aktiviert wurde, können Sie mit dem Cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMVoiceMail) sicherstellen, dass dieser zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

