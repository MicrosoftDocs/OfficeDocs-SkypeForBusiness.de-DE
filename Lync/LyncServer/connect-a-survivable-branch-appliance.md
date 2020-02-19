---
title: Verbinden eines Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8840bb7c9beec8170b26783a180d9f8bf1347e22
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Verbinden eines Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Jede Survivable Branch Appliance (SBA) ist einer Front-End-Pool zugeordnet, die als Sicherungs Registrierungsstelle für die SBVg dient. Wenn die Front-End-Pool zu lync Server 2013 migriert wird, muss die SBVg von der lync Server 2010 entfernt werden Front-End-Pool während der Pool aktualisiert wird, nachdem der Pool zu lync Server 2013 migriert wurde, kann die SBVg erneut mit der aktualisierten Front-End-Pool verbunden werden. Dies umfasst das Löschen des SBA aus der Legacy lync Server 2010-Topologie im Topologie-Generator und das anschließende Hinzufügen des SBA zur lync Server 2013-Topologie. Benutzer, die auf dem Legacy lync Server 2010 SBA verwaltet werden, müssen zunächst in eine andere Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Sobald die SBVg der lync Server 2013-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBVg verschoben werden. Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:

1.  Verlagern Sie Zweigstellenbenutzer, die in der Legacy-SBA-lync Server 2010 sind, in einen anderen Front-End-Pool

2.  Entfernen Sie SBA aus der Legacy lync Server 2010-Topologie, um die vorhandene Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.

3.  Fügen Sie SBA zur lync Server 2013-Topologie hinzu, und konfigurieren Sie diese neue Front-End-Pool als Sicherungs Registrierungsstelle.

4.  Stellen Sie die Zweigstellenbenutzer in den neuen lync Server 2013 SBA.

**Hinzufügen lync Server 2010 SBA-Zweigstellen Standorts zu Ihrer Topologie**

1.  Öffnen Sie den **Topologie-Generator**.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Zweigstellenstandorte**, und klicken Sie dann auf **Neue Zweigstelle**.

3.  Klicken Sie im Dialogfeld **Neuen Zweigstellenstandort definieren** auf **Name**, und geben Sie den Namen für den Zweigstellenstandort ein.

4.  (Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für den Zweigstellenstandort ein.

5.  Klicken Sie auf **Weiter**.

6.  (Optional) Führen Sie im nächsten Dialogfeld **Neuen Zweigstellenstandort definieren** einen der folgenden Schritte aus:
    
    1.  Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich der Zweigstellenstandort befindet.
    
    2.  Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich der Zweigstellenstandort befindet.
    
    3.  Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich der Zweigstellenstandort befindet.

7.  Klicken Sie auf **Weiter**, und führen Sie einen der folgenden Schritte aus:
    
    1.  Wenn Sie ein lync 2010-Survivable Branch Appliance oder-Server an dieser Website verwenden, deaktivieren Sie die Option Öffnen Sie den neuen übergebenen **Assistenten, wenn dieser Assistent geschlossen** wird. Klicken Sie auf **Fertig stellen**.

8.  So ordnen Sie das Legacy lync Server 2010 SBA dem lync Server 2013 Front-End-Pool zu:
    
    1.  Erweitern Sie den Zweigstellenstandort, der erstellt wurde.
    
    2.  Klicken Sie mit der rechten Maustaste auf **lync Server 2010** , und klicken Sie dann auf **neu**.
    
    3.  Klicken Sie auf **Survivable Branch Appliance...**

9.  Befolgen Sie die Anweisungen im Assistenten, der geöffnet wird. Informationen zu Assistenten Elementen finden Sie unter [define a Survivable Branch Appliance or Server in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Ein lync Server 2010 Survivable Branch Appliance kann nur einem lync Server 2010 Überwachungsspeicher zugeordnet werden.

    
    </div>

10. Wenn Sie an diesem Standort keinen Survivable Branch Appliance oder Server verwenden, deaktivieren Sie das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.

11. Wiederholen Sie die vorherigen Schritte für jeden Zweigstellenstandort, den Sie der Topologie hinzufügen möchten.

</div>

<span> </span>

</div>

</div>

</div>

