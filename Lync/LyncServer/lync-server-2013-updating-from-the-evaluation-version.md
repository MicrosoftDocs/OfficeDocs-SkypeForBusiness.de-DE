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
ms.openlocfilehash: 2b4cc704a77f824cbf7b2ec8ab4920c25454f3c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Aktualisieren von der Evaluierungsversion von lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-20_

Wenn Sie die Evaluierungsversion von Microsoft lync Server 2013 installiert haben, müssen Sie diese Installation eventuell mit einer lizenzierten Kopie der Software aktualisieren. Das liegt daran, dass die Evaluierungsversion 180 Tage nach der Installation abläuft. Sie müssen die Evaluierungsversion jedoch nicht vollständig deinstallieren und dann die lizenzierte Version installieren. Nachdem Sie einen gültigen Lizenzierungsschlüssel erhalten haben, können Sie stattdessen die Evaluierungsversion von lync Server 2013 aktualisieren, indem Sie auf jedem Computer, der als lync Server-Front-End-Server,-Director oder-Edgeserver fungiert, die folgenden Schritte ausführen. Beachten Sie, dass Sie keine Computer aktualisieren müssen, die andere Serverrollen ausführen, beispielsweise einen Überwachungsserver oder einen Archivierungsserver.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Aktualisieren von der Evaluierungs Version von Microsoft lync Server 2013

So aktualisieren Sie einen Computer aus der Evaluierungsversion von lync Server 2013 auf die lizenzierte Version der Software:

**Aktualisieren von der Evaluierungs Version von Microsoft lync Server 2013**

1.  Melden Sie sich als lokaler Administrator am Computer an.

2.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie in der lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Beachten Sie, dass Sie möglicherweise den vollständigen Pfad zur Dateiserver. msi angeben müssen. Diese Datei befindet sich im Setup-Ordner der lync Server Volume Media-Installationsdateien.

4.  Nachdem die Ausführung von Setup beendet wurde, geben Sie Folgendes an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
    
        Enable-CsComputer

5.  Wiederholen Sie diesen Vorgang auf jedem anderen Front-End-Server, Director oder Edgeserver, auf dem eine Evaluierungskopie von lync Server ausgeführt wird. Dieses Verfahren sollte auch für alle Branch Office-Server ausgeführt werden, die mithilfe der lync Server Media-Installationsdateien bereitgestellt wurden.

Wenn Sie nicht sicher sind, ob die Evaluierungsversion von lync Server auf einem bestimmten Computer ausgeführt wird, können Sie dies überprüfen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:

    Get-CsServerVersion

Mit dem Cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) wird der lokale Computer analysiert und eine der folgenden Berichte zurückgemeldet:

  - , Dass der lync Server-Volumenlizenzschlüssel auf dem Computer installiert wurde, was bedeutet, dass keine Aktualisierung erforderlich ist.

  - , Dass der lync Server-Evaluierungslizenz Schlüssel installiert wurde, was bedeutet, dass der Computer aktualisiert werden muss.

  - , Dass auf dem Computer kein Volumenlizenzschlüssel erforderlich ist. Das Aktualisieren von der Evaluierungsversion auf die lizenzierte Version ist nur auf Front-End-Servern, Directors und Edge-Servern erforderlich.

</div>

</div>

<span> </span>

</div>

</div>

</div>

