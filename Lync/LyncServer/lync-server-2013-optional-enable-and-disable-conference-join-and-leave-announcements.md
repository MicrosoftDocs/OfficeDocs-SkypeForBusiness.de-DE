---
title: 'Lync Server 2013: (Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen'
TOCTitle: (Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398834(v=OCS.15)
ms:contentKeyID: 49295390
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Wenn Einwahlbenutzer einer Konferenz beitreten oder diese verlassen, kann die Konferenzankündigungsanwendung dies durch Abspielen eines Tons oder durch eine Ansage des Benutzernamens ankündigen. Durch verschiedene Cmdlets können Sie die Funktionsweise von Ankündigungen ändern. Dieser Schritt ist optional.

## So ändern Sie das Verhalten von Ankündigungen beim Beitreten oder Verlassen einer Konferenz

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingConfiguration
    
    Dieses Cmdlet ruft Informationen dazu ab, ob Teilnehmer beim Beitreten einer Konferenz ihren Namen aufzeichnen müssen und wie Lync Server reagiert, wenn Teilnehmer einer Einwahlkonferenz beitreten oder diese verlassen.

4.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   Legt fest, ob anonyme Teilnehmer vor dem Beitreten einer Konferenz dazu aufgefordert werden, ihren Namen aufzuzeichnen. Der Standardwert lautet "$true". Dies bedeutet, dass anonyme Teilnehmer aufgefordert werden, ihren Namen zu sagen, wenn sie einer Konferenz beitreten möchten. (Authentifizierte Teilnehmer müssen ihren Namen nicht aufzeichnen, da stattdessen ihr Anzeigename verwendet wird.)
    
    **EntryExitAnnouncementsEnabledByDefault**   Gibt ab, ob Ankündigungen standardmäßig aktiviert oder deaktiviert sind. Der Standardwert lautet "$false". Dies bedeutet, dass standardmäßig keine Ankündigung erfolgt, wenn Teilnehmer einer Konferenz beitreten oder diese verlassen. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.
    
    **EntryExitAnnouncementsType**   Gibt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer einer Konferenz, für welche die Ankündigungsfunktion aktiviert ist, beitritt oder diese verlässt. Der Standardwert lautet "UseNames". Dies bedeutet, dass eine Ankündigung ähnlich dieser erfolgt: "Ken Myer ist der Konferenz beigetreten."
    
    Sie können diese Einstellungen auf globaler oder Standortebene konfigurieren. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen.
    
    Beispiel:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    In diesem Beispiel sind die Einstellungen auf Standortebene für Redmond konfiguriert. Die Ankündigungsfunktion ist aktiviert, Teilnehmer müssen jedoch nicht ihren Namen sagen, wenn sie einer Konferenz beitreten. Wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, wird ein Ton abgespielt.

