---
title: Ausführen eines Updates von der Evaluierungsversion von Lync Server 2013
TOCTitle: Ausführen eines Updates von der Evaluierungsversion von Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521005(v=OCS.15)
ms:contentKeyID: 49294197
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Updates von der Evaluierungsversion von Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-20_

Wenn Sie die Evaluierungsversion von Microsoft Lync Server 2013 installiert haben, müssen Sie diese Version spätestens 180 Tage nach der Installation mit einer lizenzierten Kopie der Software aktualisieren. Es ist jedoch nicht notwendig, die Evaluierungsversion vollständig zu deinstallieren und anschließend die lizenzierte Version zu installieren. Stattdessen können Sie nach dem Erhalt eines gültigen Lizenzschlüssels die Evaluierungsversion von Lync Server 2013 aktualisieren, indem Sie die folgenden Schritte auf jedem Computer ausführen, der als Lync Server Front-End-Server, Director oder Edgeserver genutzt wird. Beachten Sie, dass Computer, die für andere Serverrollen (z. B. Monitoring-Server oder Archivierungsserver) verwendet werden, nicht aktualisiert werden müssen.

## Aktualisieren der Evaluierungsversion von Microsoft Lync Server 2013

So aktualisieren Sie einen Computer von der Evaluierungsversion auf die lizenzierte Version von Lync Server 2013

**Aktualisieren der Evaluierungsversion von Microsoft Lync Server 2013**

1.  Melden Sie sich beim Computer als lokaler Administrator an.

2.  Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server 2013**, und klicken Sie dann auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Möglicherweise müssen Sie den vollständigen Pfad zur Datei SERVER.MSI angeben. Diese Datei befindet sich im Ordner SETUP der Lync Server-Medieninstallationsdateien.

4.  Nach der Ausführung von Setup geben Sie an einer Eingabeaufforderung den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
        Enable-CsComputer

5.  Wiederholen Sie diese Vorgehensweise auf allen anderen Front-End-Server, Directors oder Edgeserver, auf denen eine Evaluierungskopie von Lync Server ausgeführt wird. Dieses Verfahren sollten Sie auch auf Zweigstellenservern ausführen, die mithilfe der Lync Server-Medieninstallationsdateien bereitgestellt wurden.

Wenn Sie bei einem bestimmten Computer nicht sicher sind, ob auf ihm die Evaluierungsversion von Lync Server ausgeführt wird, können Sie dies durch Eingabe des folgenden Befehls in der Lync Server-Verwaltungsshell überprüfen:

    Get-CsServerVersion

Das Cmdlet [Get-CsServerVersion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsServerVersion) analysiert den lokalen Computer und gibt eine der folgenden Informationen zurück:

  - Auf dem Computer ist der Lync Server-Volumenlizenzschlüssel installiert, sodass keine Aktualisierung erforderlich ist.

  - Auf dem Computer ist der Lync Server-Volumenlizenzschlüssel nicht installiert, daher ist eine Aktualisierung erforderlich.

  - Auf dem Computer ist kein Volumenlizenzschlüssel erforderlich. Die Aktualisierung der Evaluierungsversion auf die lizenzierte Version ist nur auf Front-End-Servern, Directors und Edgeservern notwendig.

