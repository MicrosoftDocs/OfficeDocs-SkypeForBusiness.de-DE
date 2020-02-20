---
title: Installieren der lync Server 2013-Hauptdateien und der RTCLocal-Datenbank
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17b3b1925607a80f143c57e6185c7a709b19ee0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Installieren der lync Server 2013-Hauptdateien und der RTCLocal-Datenbank

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

Um die lync Server 2013 Kerndateien auf einem Computer zu installieren, führen Sie das folgende Verfahren aus. Die RTCLocal-Datenbank wird automatisch bei der Installation der Hauptdateien installiert. Beachten Sie, dass Sie SQL Server nicht auf den Watcher-Knoten installieren müssen. Stattdessen wird SQL Server Express automatisch für Sie installiert.

So installieren Sie die lync Server 2013 Kerndateien und die RTCLocal-Datenbank:

1.  Klicken Sie auf dem Computer mit den Watcher-Knoten auf **Start**, **Alle Programme**, **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE, und verwenden Sie den entsprechenden Pfad zu ihren lync Server-Setupdateien:
    
        D:\Setup.exe /BootstrapLocalMgmt

Um sicherzustellen, dass die Kern lync Server Komponenten erfolgreich installiert wurden, klicken Sie auf **Start**, auf **Alle Programme**, auf **lync Server 2013**und dann auf **lync Server-Verwaltungsshell**. Geben Sie in der lync Server 2013 Verwaltungsshell den folgenden Windows PowerShell Befehl ein, und drücken Sie dann die EINGABETASTE:

    Get-CsWatcherNodeConfiguration

Bei der ersten Ausführung dieses Befehls werden keine Daten zurückgegeben, da noch keine Computer mit Watcher-Knoten konfiguriert wurden. Solange der Befehl ausgeführt wird, ohne dass ein Fehler zurückgegeben wird, können Sie davon ausgehen, dass das lync Server-Setup erfolgreich abgeschlossen wurde.

Wenn sich der Monitor Knoten Computer in Ihrem Umkreisnetzwerk befindet, können Sie den folgenden Befehl ausführen, um die Installation von lync Server 2013 zu überprüfen:

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

</div>

<span> </span>

</div>

</div>

</div>

