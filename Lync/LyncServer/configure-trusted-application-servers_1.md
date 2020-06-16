---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cbaba4f59a22de6fcee38ee51845d551033cfea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Konfigurieren von vertrauenswürdigen Anwendungsservern

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, nachdem Sie die Legacy Office Communications Server-Topologie mit lync Server 2013 zusammengeführt haben und einen neuen vertrauenswürdigen Anwendungsserver mithilfe des Topologie-Generators definiert haben, müssen Sie den Pool für den nächsten Hop als lync Server 2013 Pool festlegen. In einer zusammengeführten Umgebung werden sowohl der Legacy Office Communications Server Pool als auch der lync Server 2013-Pool in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird *nicht* unterstützt.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>So wählen Sie beim Erstellen eines vertrauenswürdigen Anwendungsservers lync Server 2013 als nächsten Hop aus

1.  Öffnen Sie eine bestehende Topologie im Topologie-Generator.

2.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie anschließend auf **Neuer Pool für vertrauenswürdige Anwendungen**.

3.  Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und legen Sie fest, ob es sich um eine Topologie mit einem einzelnen oder mehreren Servern handelt.

4.  Klicken Sie auf **Weiter**.

5.  Wählen Sie auf der Seite **nächsten Hop auswählen** in der Liste die lync Server 2013 Front-End-Pool aus.
    
    ![Dialogfeld "neuen vertrauenswürdigen Anwendungs Pool definieren"](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Dialogfeld "neuen vertrauenswürdigen Anwendungs Pool definieren"")  

6.  Klicken Sie auf **Fertig stellen**.

7.  Wählen Sie den obersten Knoten **Lync Server** aus, und wählen Sie im Bereich **Aktionen** die Aktion **Veröffentlichen** aus.

8.  Vergewissern Sie sich, dass der **Pool für vertrauenswürdige Anwendungen** erfolgreich erstellt wurde und mit dem richtigen Front-End-Pool verknüpft ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

