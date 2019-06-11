---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrieren von Zugriffsnummern für die Einwahl

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Zum Migrieren der Kontaktobjekte muss das Cmdlet **Move-CsApplicationEndpoint** ausgeführt werden, um die Einwahl Zugriffsnummern von lync Server 2010 auf lync Server 2013 zu migrieren. Während des koexistenzbereichs lync Server 2010 und lync Server 2013 Verhalten sich die in lync Server 2013 erstellten Einwahl Zugriffsnummern ähnlich wie die Einwahl Zugriffsnummern, die Sie in lync Server 2010 erstellen, wie in diesem Abschnitt beschrieben.

Einwahl Zugriffsnummern, die Sie in lync Server 2010 erstellt, aber nach lync Server 2013 verschoben haben oder die Sie in lync Server 2013 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:

  - Sie werden nicht auf Office Communications Server 2007 R2-Besprechungseinladungen und auf der Seite Einwahl Zugriffsnummer angezeigt.

  - In lync Server 2010-Besprechungseinladungen und auf der Seite "Einwahl Zugriffsnummer" angezeigt.

  - In lync Server 2013-Besprechungseinladungen und auf der Seite "Einwahl Zugriffsnummer" angezeigt.

  - Kann im Office Communications Server 2007 R2-Verwaltungstool nicht angezeigt oder geändert werden.

  - Kann in der lync Server 2010-Systemsteuerung und in der lync Server 2010-Verwaltungsshell angezeigt und geändert werden.

  - Kann in der lync Server 2013-Systemsteuerung und in der lync Server 2013-Verwaltungsshell angezeigt und geändert werden.

  - Kann innerhalb des Bereichs mithilfe des Cmdlets "CsDialinConferencingAccessNumber" mit dem Priority-Parameter neu sequenziert werden.

Sie müssen die Migration von Einwahl Zugriffsnummern beenden, die auf einen lync Server 2010-Pool verweisen, bevor Sie den lync Server 2010-Pool außer Betrieb bringen. Wenn Sie die Migration von Einwahlnummern wie im folgenden Verfahren beschrieben nicht abschließen, treten bei eingehenden Anrufen an die Zugriffsnummern keine Fehler auf.

<div>


> [!IMPORTANT]  
> Sie müssen dieses Verfahren vor der Außerbetriebnahme des lync Server 2010-Pools ausführen.



</div>

<div>


> [!NOTE]  
> Es wird empfohlen, Einwahlnummern zu verschieben, wenn die Netzwerkauslastung gering ist, falls es einen kurzen Zeitraum für einen Ausfall des Diensts gibt.



</div>

**So identifizieren und verschieben Sie Einwahl Zugriffsnummern**

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Wenn Sie jede Einwahl Zugriffsnummer in einen Pool verschieben möchten, der auf lync Server 2013 gehostet wird, führen Sie die folgenden Schritte aus:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Öffnen Sie die Lync Server-Systemsteuerung.

4.  Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

5.  Klicken Sie auf die Registerkarte **Einwahlnummer** .

6.  Stellen Sie sicher, dass keine Einwahl Zugriffsnummern für den lync Server 2010-Pool verbleiben, von dem aus Sie migrieren.
    
    <div>
    

    > [!NOTE]  
    > Wenn alle Einwahl Zugriffsnummern auf den lync Server 2013-Pool verweisen, können Sie den lync Server 2010-Pool außer Betrieb stellen.

    
    </div>

**Überprüfen der Migration von Einwahl Zugriffsnummern mithilfe der lync Server-Systemsteuerung**

1.  Melden Sie sich bei einem Benutzerkonto, das der **CsUserAdministrator** -Rolle oder der **CsAdministrator** -Rolle zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

4.  Klicken Sie auf die Registerkarte **Einwahlnummer** .

5.  Überprüfen Sie, ob alle Einwahl Zugriffsnummern in den Pool migriert werden, der auf lync Server 2013 gehostet wird.

**Überprüfen der Migration von Einwahl Zugriffsnummern mithilfe der lync Server-Verwaltungsshell**

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Um alle migrierten Zugriffsnummern für Einwahlkonferenzen zurückzugeben, führen Sie über die Befehlszeile Folgendes aus:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Überprüfen Sie, ob alle Einwahl Zugriffsnummern in den Pool migriert werden, der auf lync Server 2013 gehostet wird.

</div>

<span> </span>

</div>

</div>

</div>

