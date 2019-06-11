---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60aef8ea63d4feb0e874f72d37670c3b06860758
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Konfigurieren von vertrauenswürdigen Anwendungsservern

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, nachdem Sie die Legacy Office Communications Server-Topologie mit lync Server 2013 zusammengeführt haben, und Sie einen neuen vertrauenswürdigen Anwendungsserver mithilfe des Topologie-Generators definieren, müssen Sie den Pool für den nächsten Hop so festlegen, dass er ein Lync Server 2013-Pool In einer zusammengeführten Umgebung werden sowohl der Legacy-Office Communications Server-Pool als auch der lync Server 2013-Pool in der Dropdownliste angezeigt. Das Auswählen des Legacy Pools wird *nicht* unterstützt.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>So wählen Sie lync Server 2013 als nächster Hop aus, wenn Sie einen vertrauenswürdigen Anwendungs Server erstellen

1.  Öffnen Sie im Topologie-Generator eine vorhandene Topologie.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **neuer vertrauenswürdiger Anwendungs Pool**.

3.  Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und wählen Sie aus, ob es sich um eine Bereitstellung mit einem oder mehreren Servern handelt.

4.  Klicken Sie auf **Weiter**.

5.  Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den lync Server 2013-Front-End-Pool aus.
    
    ![Dialogfeld "neuen vertrauenswürdigen Anwendungs Pool definieren"] (images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Dialogfeld \"neuen vertrauenswürdigen Anwendungs Pool definieren\"")  

6.  Klicken Sie auf **Fertig stellen**.

7.  Wählen Sie den obersten Knoten **lync Server** aus, und wählen Sie im Bereich **Aktionen** die Option **veröffentlichen**aus.

8.  Überprüfen Sie, ob der **Vertrauenswürdige Anwendungspool** erfolgreich erstellt wurde und dem richtigen Front-End-Pool zugeordnet ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

