---
title: Konfigurieren der SCOM-Überwachung
TOCTitle: Konfigurieren der SCOM-Überwachung
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49890718
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der SCOM-Überwachung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Nach der Migration zu Microsoft Lync Server 2013 müssen Sie einige Aufgaben zur Konfiguration von Lync Server 2013 für die Zusammenarbeit mit System Center Operations Manager ausführen.

  - Wenden Sie die Updates von Lync Server 2010 auf einen Server an, der zur Verwaltung der zentralen Erkennungslogik ausgewählt wurde.

  - Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.

  - Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten des Kandidaten für die zentrale Erkennung überschrieben wird.

Anweisungen für diese Aufgaben finden Sie unten.

**Wenden Sie die Updates von Lync Server 2010 auf einen Server an, der zur Verwaltung der zentralen Erkennungslogik ausgewählt wurde.**

1.  Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und der als Kandidatenermittlungsknoten konfiguriert ist.

2.  Wenden Sie Lync Server 2010-Aktualisierungen auf diesen Server an. Lesen Sie die Informationen im Thema [Anwenden von Lync Server 2010-Updates](apply-lync-server-2010-updates.md).

**Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.**

1.  Öffnen Sie auf dem Server, der zur Verwaltung der zentralen Erkennungslogik ausgewählt wurde, ein Windows PowerShell-Befehlsfenster.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"

       &nbsp;
    
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
    

    > [!NOTE]
    > Bei jeder Bearbeitung der Registrierung kann eine Fehlermeldung angezeigt werden, dass der Befehl nicht ausgeführt wurde, wenn der Registrierungsschlüssel bereits vorhanden ist. Falls dies der Fall ist, können Sie die Fehlermeldung getrost ignorieren.



**Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Watcher-Knoten des Kandidaten für die zentrale Erkennung überschrieben wird.**

1.  Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte**, und wählen Sie **Objektermittlungen** aus.

2.  Klicken Sie auf **Bereich ändern**.

3.  Wählen Sie auf der Seite **Management Pack-Objekte in Bereiche einteilen** den Eintrag **LS-Ermittlungskandidat** aus.

4.  Überschreiben Sie den **Effektivwert für den LS-Ermittlungskandidaten** mit dem Namen des zuvor ausgewählten Kandidatenservers.

Starten Sie zuletzt den Integritätsdienst auf dem System Center Operations Manager-Stammverwaltungsserver neu, um Ihre Änderungen abzuschließen.

