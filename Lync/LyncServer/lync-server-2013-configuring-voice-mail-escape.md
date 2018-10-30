---
title: Konfigurieren des Wechsels der Voicemail in Lync Server 2013
TOCTitle: Konfigurieren des Wechsels der Voicemail in Lync Server 2013
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49890867
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Wechsels der Voicemail in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Wenn ein Benutzer das gleichzeitige Klingeln für ein Mobiltelefon konfiguriert, werden Anrufer normalerweise an den persönlichen Voicemail-Dienst des Benutzers weitergeleitet, wenn das Mobiltelefon ausgeschaltet wird, wenn der Akku leer ist oder wenn sich das Mobiltelefon außerhalb des Empfangsbereichs befindet. Mit Microsoft Lync Server 2013 können Benutzer festlegen, dass geschäftliche Anrufe an das Voicemail-System ihres Unternehmens weitergeleitet werden. Insbesondere kann ein Timer konfiguriert werden, und wenn der Anruf innerhalb des definierten Zeitraums vom Voicemail-System des Betreibers angenommen wird, trennt Lync Server 2013 die Verbindung mit dem Voicemail-System des Betreibers (und mit dem persönlichen Voicemail-Dienst des Benutzers), während es an den verbleibenden Endpunkten des Benutzers im System des Unternehmens weiterhin klingelt. Somit wird der Anrufer automatisch an das Voicemail-System des Unternehmens des Benutzers weitergeleitet.

Diese Konfiguration erfolgt mithilfe des Lync Server-Verwaltungsshell-Cmdlets, mit "Set-CsVoicePolicy" und auf Ebene der VoIP-Richtlinie mithilfe der folgenden Parameter.

## Konfigurieren von Voicemail Escape

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:
    
      - **EnableVoicemailEscapeTimer** – Aktiviert oder deaktiviert den Escape-Timer.
    
      - **PSTNVoicemailEscapeTimer** – Gibt den Zeitüberschreitungswert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden, und der Wert kan zwischen 0 und 8000 Millisekunden liegen.

## Beispiel

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

## Siehe auch

#### Weitere Ressourcen

[Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

