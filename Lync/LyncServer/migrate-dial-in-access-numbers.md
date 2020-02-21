---
title: Migrieren von Zugriffsnummern für die Einwahl
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e808e587c9bd65668e35eba46692591bf72b9c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrieren von Zugriffsnummern für die Einwahl

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Das Migrieren der Kontaktobjekte erfordert das Ausführen des Cmdlets " **CsApplicationEndpoint** ", um die Zugriffsnummern für die Einwahl von lync Server 2010 auf lync Server 2013 zu migrieren. Während des Zeitraums für lync Server 2010 und lync Server 2013 Koexistenz Verhalten sich Einwahlnummern, die Sie in lync Server 2013 erstellt haben, entsprechend den in diesem Abschnitt beschriebenen Zugriffsnummern für Einwahlen, die Sie in lync Server 2010 erstellt haben.

Einwahlnummern, die Sie in lync Server 2010 erstellt, aber in lync Server 2013 verschoben haben oder die Sie in lync Server 2013 vor, während oder nach der Migration erstellt haben, weisen die folgenden Merkmale auf:

  - Sie werden nicht in Office Communications Server 2007 R2-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.

  - Sie werden in Lync Server 2010-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.

  - Sie werden in Lync Server 2013-Besprechungseinladungen und auf der Einwahlnummernseite angezeigt.

  - Sie können nicht im Verwaltungstool von Office Communications Server 2007 R2 angezeigt oder geändert werden.

  - Sie können in der Lync Server 2010-Systemsteuerung und in der Lync Server 2010-Verwaltungsshell angezeigt und geändert werden.

  - Sie können in der Lync Server 2013-Systemsteuerung und in der Lync Server 2013-Verwaltungsshell angezeigt und geändert werden.

  - Sie können innerhalb des Bereichs durch Verwendung des Set-CsDialinConferencingAccessNumber-Cmdlets mit dem Priority-Parameter neu sequenziert werden.

Sie müssen die Migration von Einwahlnummern abschließen, die auf einen Lync Server 2010-Pool verweisen, bevor Sie den Lync Server 2010-Pool außer Betrieb nehmen. Wenn Sie die Migration von Einwahlnummern nicht wie im folgenden Verfahren beschrieben abschließen, schlagen eingehende Anrufe an die Einwahlnummern fehl.

<div>


> [!IMPORTANT]  
> Sie müssen dieses Verfahren vor der Außerbetriebnahme des lync Server 2010 Pools ausführen.



</div>

<div>


> [!NOTE]  
> Wir empfehlen, das Verschieben von Einwahlen zu einem Zeitpunkt vorzunehmen, zu dem die Netzwerkauslastung möglichst gering ist, für den Fall, dass es zu einem kurzen Dienstausfall kommt.



</div>

**So identifizieren und verschieben Sie Einwahlnummern**

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Um jede Zugriffsnummer für die Einwahl in einen Pool zu migrieren, der auf lync Server 2013 gehostet wird, führen Sie über die Befehlszeile Folgendes aus:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Öffnen Sie die Lync Server-Systemsteuerung.

4.  Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

5.  Klicken Sie auf die Registerkarte **Einwahlnummer**.

6.  Stellen Sie sicher, dass keine Einwahlnummern für den lync Server 2010 Pool verbleiben, von dem Sie migrieren.
    
    <div>
    

    > [!NOTE]  
    > Wenn alle Zugriffsnummern für Einwahlen auf den lync Server 2013 Pool deuten, können Sie den lync Server 2010-Pool außer Betrieb nehmen.

    
    </div>

**Überprüfen der Migration der Einwahlnummern mithilfe der Lync Server-Systemsteuerung**

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle **CsUserAdministrator** oder **CsAdministrator** zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz**.

4.  Klicken Sie auf die Registerkarte **Einwahlnummer**.

5.  Vergewissern Sie sich, dass alle Einwahlnummern zu dem auf lync Server 2013 gehosteten Pool migriert wurden.

**Überprüfen der Migration der Einwahlnummern mithilfe der Lync Server-Verwaltungsshell**

1.  Öffnen Sie lync Server-Verwaltungsshell.

2.  Um alle migrierten Einwahlnummern für Konferenzen zurückzugeben, führen Sie an der Befehlszeile folgenden Befehl aus:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Überprüfen Sie, ob alle Einwahlnummern zu dem auf lync Server 2013 gehosteten Pool migriert wurden.

</div>

<span> </span>

</div>

</div>

</div>

