---
title: 'Lync Server 2013: (Optional) Ändern der Tastenzuordnung für DTMF-Befehle'
TOCTitle: (Optional) Ändern der Tastenzuordnung für DTMF-Befehle
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398943(v=OCS.15)
ms:contentKeyID: 49295559
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Optional) Ändern der Tastenzuordnung für DTMF-Befehle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Einwahlkonferenzbenutzer können DTMF-Befehle (Dual-Tone Multi-Frequency) mithilfe der Tasten ihres Telefons ausführen. Mit DTMF-Befehlen können Benutzer, die sich bei einer Konferenz einwählen, Konferenzeinstellungen mit der Telefontastatur steuern (z. B. eigene Person stummschalten bzw. Stummschaltung der eigenen Person aufheben oder Konferenz sperren bzw. entsperren). Sie können Cmdlets verwenden, um die Tastaturzuordnung für die DTMF-Befehle zu ändern. Dieser Schritt ist optional.


> [!NOTE]
> Ausführliche Informationen zur Verwendung dieser Cmdlets und den möglichen DTMF-Optionen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation oder in der Lync Server-Verwaltungsshell-Befehlszeilenhilfe.



## So ändern Sie die Tastaturzuordnung für DTMF-Befehle

1.  Melden Sie sich beim Computer als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Dieses Cmdlet gibt die in Einwahlkonferenzen verwendeten DTMF-Einstellungen zurück.

4.  Führen Sie das folgende Cmdlet aus, und geben Sie für jede Option, die Sie ändern möchten, die gewünschte Taste an:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Dieses Cmdlet ändert die in Einwahlkonferenzen verwendeten DTMF-Einstellungen.
    
    Beispiel:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    In diesem Beispiel wird die Taste zur Aktivierung und Deaktivierung von Ankündigungen mit der Taste zur Stummschaltung und Aufhebung der Stummschaltung aller Teilnehmer getauscht. Da für "Identity" kein Wert angegeben ist, werden diese Änderungen auf die globalen DTMF-Einstellungen angewendet.

5.  (Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts. Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. Ausführliche Informationen hierzu finden Sie in der Lync Server-Verwaltungsshell-Dokumentation oder in der Lync Server-Verwaltungsshell-Befehlszeilenhilfe.

