---
title: Verbinden einer Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Verbinden einer Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Jede Survivable Branch Appliance (SBA) ist mit einem Front-End-Pool verbunden, der als Backup-Registrar für die SBA fungiert. Wenn der Front-End-Pool zu lync Server 2013 migriert wird, muss die SBA vom lync Server 2010-Front-End-Pool nicht zugeordnet werden, während der Pool aktualisiert wird, nachdem der Pool zu lync Server 2013 migriert wurde, kann die SBA erneut mit dem aktualisierten Front-End-Pool verknüpft werden. Dies umfasst das Löschen des SBA aus der Legacy lync Server 2010-Topologie im Topologie-Generator und das anschließende Hinzufügen der SBA zur lync Server 2013-Topologie. Benutzer, die auf dem Legacy-lync Server 2010 SBA verwaltet werden, müssen zuerst in einen anderen Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Sobald die SBA zur lync Server 2013-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBA verschoben werden. Nachfolgend werden die folgenden Schritte zusammengefasst:

1.  Verschieben Sie Branch-Benutzer, die sich auf der Legacy-SBA lync Server 2010 befinden, in einen anderen Front-End-Pool.

2.  Entfernen Sie SBA aus der Legacy lync Server 2010-Topologie, um den vorhandenen Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.

3.  Fügen Sie SBA zur lync Server 2013-Topologie hinzu, und konfigurieren Sie diesen neuen Front-End-Pool als Sicherungs Registrierungsstelle.

4.  Verschieben Sie die Benutzer der Verzweigung in den neuen lync Server 2013 SBA.

**Hinzufügen der lync Server 2010 SBA-Verzweigungs Website zu Ihrer Topologie**

1.  Öffnen Sie den **Topologie-Generator**.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Verzweigungs Websites**, und klicken Sie dann auf **neue Verzweigungs Website**.

3.  Klicken Sie im Dialogfeld **neue Verzweigungs Website definieren** auf **Name**, und geben Sie dann den Namen der Verzweigungs Website ein.

4.  Optional Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Verzweigungs Website ein.

5.  Klicken Sie auf **Weiter**.

6.  Optional Führen Sie im nächsten Dialogfeld **neue Verzweigungs Website definieren** eine der folgenden Aktionen aus:
    
    1.  Klicken Sie auf **Stadt**, und geben Sie dann den Namen des Orts ein, in dem sich die Zweigstelle befindet.
    
    2.  Klicken Sie auf **Bundesland/Region**, und geben Sie dann den Namen des Bundeslands oder der Region ein, in dem sich die Verzweigungs Website befindet.
    
    3.  Klicken Sie auf **Landesvorwahl**, und geben Sie dann den zweistelligen anrufcode für das Land/die Region ein, in dem sich die Zweigstelle befindet.

7.  Klicken Sie auf **weiter**, und führen Sie dann eine der folgenden Aktionen aus:
    
    1.  Wenn Sie eine überlebensfähige lync 2010-Branch-Appliance oder einen Server auf dieser Website verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird. Klicken Sie auf **Fertig stellen**.

8.  So ordnen Sie den Legacy-lync Server 2010 SBA dem lync Server 2013-Front-End-Pool zu:
    
    1.  Erweitern Sie die erstellte Verzweigungs Website.
    
    2.  Klicken Sie mit der rechten Maustaste auf **lync Server 2010** , und klicken Sie dann auf **neu**.
    
    3.  Klicken Sie auf **Survivable Branch Appliance...**

9.  Folgen Sie den Anweisungen im Assistenten, der geöffnet wird. Informationen zu Assistenten Elementen finden Sie unter Definieren einer überlebensfähigen [Verzweigungs Einheit oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Eine Survivable Branch-Appliance von lync Server 2010 kann nur einem lync Server 2010-Überwachungsspeicher zugeordnet werden.

    
    </div>

10. Wenn Sie keine Survivable Branch-Appliance oder einen Server an dieser Website verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.

11. Wiederholen Sie die vorherigen Schritte für jede Verzweigungs Website, die Sie der Topologie hinzufügen möchten.

</div>

<span> </span>

</div>

</div>

</div>

