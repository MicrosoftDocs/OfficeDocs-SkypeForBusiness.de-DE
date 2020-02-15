---
title: 'Lync Server 2013: Aktualisieren von der Evaluierungsversion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 703362f34c367d301e7d47e1bdc65f16a497ce88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Aktualisieren von der Evaluierungsversion von lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-20_

Wenn Sie die Evaluierungsversion von Microsoft lync Server 2013 installiert haben, müssen Sie diese Installation schließlich mit einer lizenzierten Kopie der Software aktualisieren. Das liegt daran, dass die Evaluierungsversion 180 Tage nach der Installation abläuft. Es ist jedoch nicht notwendig, die Evaluierungsversion vollständig zu deinstallieren und anschließend die lizenzierte Version zu installieren. Nachdem Sie einen gültigen Lizenzierungsschlüssel erhalten haben, können Sie stattdessen die Evaluierungsversion von lync Server 2013 aktualisieren, indem Sie auf jedem Computer, der als lync Server Front-End-Server, Director oder Edgeserver fungiert, das folgende Verfahren ausführen. Beachten Sie, dass Computer, die für andere Serverrollen (z. B. Monitoring-Server oder Archivierungsserver) verwendet werden, nicht aktualisiert werden müssen.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Aktualisieren von der Evaluierungs Version von Microsoft lync Server 2013

So aktualisieren Sie einen Computer von der Evaluierungsversion von lync Server 2013 auf die lizenzierte Version der Software:

**Aktualisieren von der Evaluierungs Version von Microsoft lync Server 2013**

1.  Melden Sie sich beim Computer als lokaler Administrator an.

2.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie im lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Möglicherweise müssen Sie den vollständigen Pfad zur Datei SERVER.MSI angeben. Diese Datei befindet sich im Installationsordner der lync Server Volume Media-Installationsdateien.

4.  Nach der Ausführung von Setup geben Sie an einer Eingabeaufforderung den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
        Enable-CsComputer

5.  Wiederholen Sie dieses Verfahren für alle anderen Front-End-Server, Director oder Edgeserver, die eine Evaluierungskopie von lync Server ausführen. Dieses Verfahren sollte auch auf allen Zweigstellenservern ausgeführt werden, die mithilfe der lync Server Medien Installationsdateien bereitgestellt wurden.

Wenn Sie nicht sicher sind, ob die Evaluierungsversion von lync Server auf einem bestimmten Computer läuft, können Sie dies überprüfen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:

    Get-CsServerVersion

Das Cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analysiert den lokalen Computer und gibt eine der folgenden Informationen zurück:

  - , Dass der lync Server Volumenlizenzschlüssel auf dem Computer installiert wurde, was bedeutet, dass keine Aktualisierung erforderlich ist.

  - , Dass der lync Server Evaluierungslizenz Schlüssel installiert wurde, was bedeutet, dass der Computer aktualisiert werden muss.

  - Auf dem Computer ist kein Volumenlizenzschlüssel erforderlich. Die Aktualisierung der Evaluierungsversion auf die lizenzierte Version ist nur auf Front-End-Servern, Directors und Edgeservern notwendig.

</div>

</div>

<span> </span>

</div>

</div>

</div>

