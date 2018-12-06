---
title: Installieren der Lync Server 2013-Hauptdateien und der Datenbank "RTCLocal"
TOCTitle: Installieren der Lync Server 2013-Hauptdateien und der Datenbank "RTCLocal"
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204734(v=OCS.15)
ms:contentKeyID: 49293397
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren der Lync Server 2013-Hauptdateien und der Datenbank \"RTCLocal\"

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Führen Sie zum Installieren der Lync Server 2013-Hauptdateien auf einem Computer die folgenden Schritte aus. Die RTCLocal-Datenbank wird automatisch bei der Installation der Hauptdateien installiert. SQL Server muss auf den Watcher-Knoten nicht installiert werden. Stattdessen wird SQL Server Express automatisch installiert.

So installieren Sie die Lync Server 2013-Hauptdateien und die RTCLocal-Datenbank:

1.  Klicken Sie auf dem Computer mit den Watcher-Knoten auf **Start**, **Alle Programme**, **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie die EINGABETASTE. Verwenden Sie den entsprechenden Pfad zu den Lync Server-Setupdateien:
    
        D:\Setup.exe /BootstrapLocalMgmt

Um zu überprüfen, ob die Lync Server-Hauptkomponenten erfolgreich installiert wurden, klicken Sie auf **Start**, **Alle Programme**, **Lync Server 2013** und anschließend auf **Lync Server-Verwaltungsshell**. Geben Sie in der Verwaltungsshell für Lync Server 2013 den folgenden Windows PowerShell-Befehl ein, und drücken Sie die EINGABETASTE:

    Get-CsWatcherNodeConfiguration

Bei der ersten Ausführung dieses Befehls werden keine Daten zurückgegeben, da noch keine Computer mit Watcher-Knoten konfiguriert wurden. Solange der Befehl ohne Fehler ausgeführt wird, können Sie davon ausgehen, dass das Lync Server-Setup erfolgreich abgeschlossen wurde.

Befindet sich der Computer mit den Watcher-Knoten in Ihrem Umkreisnetzwerk, können Sie den folgenden Befehl zum Überprüfen der Lync Server 2013-Installation ausführen:

    Get-CsPinPolicy

Sie erhalten in etwa folgende Informationen, abhängig von der Anzahl der zur Verwendung in Ihrer Organisation konfigurierten PIN-Richtlinien:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Werden Informationen zu Ihren PIN-Richtlinien angezeigt, weist das darauf hin, dass die Hauptkomponenten erfolgreich installiert wurden.

