---
title: 'Lync Server 2013: Aktivieren der Funktion zum Parken von Anrufen für Benutzer'
TOCTitle: Aktivieren der Funktion zum Parken von Anrufen für Benutzer
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398753(v=OCS.15)
ms:contentKeyID: 49294784
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Funktion zum Parken von Anrufen für Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Benutzer können Anrufe erst parken oder geparkte Anrufe wiederaufnehmen, wenn sie in einer VoIP-Richtlinie für die Parken von Anrufen aktiviert wurden.


> [!NOTE]
> In der Standardeinstellung ist die Parken von Anrufen für alle Benutzer deaktiviert.



Sie können die Parken von Anrufen global oder auf Standort- bzw. Benutzerebene aktivieren. Auf Benutzerebene festgelegte Einstellungen haben Vorrang vor Einstellungen auf Standortebene, und Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen. Wenn Sie über mehrere VoIP-Richtlinien verfügen, überprüfen Sie nicht nur die globale Richtlinie, sondern sämtliche Richtlinien, um die Parken von Anrufen zu aktivieren.

## So verwenden Sie die Lync Server-Systemsteuerung, um Parken von Anrufen für Benutzer zu aktivieren

1.  Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator** , **CsServerAdministrator** oder **CsAdministrator** beim Computer an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** .

4.  Klicken Sie auf die Registerkarte **VoIP-Richtlinie** .

5.  Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.

6.  Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.

7.  Klicken Sie auf **OK** , um die VoIP-Richtlinie zu speichern.

## So verwenden Sie Cmdlets, um Parken von Anrufen für Benutzer zu aktivieren

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der administrativen Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    So aktivieren Sie die Parken von Anrufen z. B. für die globale VoIP-Standardrichtlinie:
    
        Set-CsVoicePolicy -EnableCallPark $true

## Siehe auch

#### Aufgaben

[Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

