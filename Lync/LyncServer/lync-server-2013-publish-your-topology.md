---
title: 'Lync Server 2013: Veröffentlichen der Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>Veröffentlichen der Topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Jedes Mal, wenn Sie die Topologie mithilfe des Topologie-Generators erstellen, müssen Sie die Topologie in einer Datenbank im zentralen Verwaltungsspeicher veröffentlichen, damit die Daten für die Bereitstellung von lync Server 2013 verwendet werden können. Gehen Sie wie folgt vor, um Ihre Topologie zu veröffentlichen.

<div>

## <a name="to-publish-the-topology"></a>So veröffentlichen Sie die Topologie

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Klicken Sie im Topologie-Generator in der Konsolenstruktur mit der rechten Maustaste auf **lync 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.

3.  Klicken Sie auf der Seite **Willkommen** des Assistenten auf **Weiter**.

4.  Klicken Sie auf der Seite " **Topologie-Generator** " auf " **weiter**".

5.  Klicken Sie auf der Seite **Weitere Datenbanken erstellen** auf **Weiter**.

6.  Wenn der Status angibt, dass die Daten Bank Erstellung erfolgreich war, gehen Sie folgendermaßen vor:
    
      - Klicken Sie zum Anzeigen des Protokolls auf **Protokoll anzeigen**.
    
      - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.
        
        <div>
        

        > [!IMPORTANT]  
        > Wenn es sich um eine neue Installation eines Edge-Servers oder eines Edge-Pools handelt, müssen Sie die Edgeserver-Konfiguration von einem vorhandenen Front-End-Server, Front-End-Pool oder Standard Edition-Server exportieren. Informationen zum Exportieren der Konfiguration finden Sie unter <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Exportieren Ihrer lync Server 2013-Topologie und Kopieren der Konfiguration auf externe Medien für die Edge-Installation</A>. Sie importieren die Konfigurationsdatei aus der externen Medien-oder Netzwerkfreigabe während der Setup-und Bereitstellungsphase der Edgeserver über den lync Server-Bereitstellungs-Assistenten.<BR>Sobald die Edgeserver in Betrieb sind und die lokale Configuration Management Store-Datenbank mit der internen Bereitstellung repliziert wird, werden nachfolgende Updates der lync Server 2013-Konfiguration veröffentlicht und auf die Edgeserver repliziert.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

