---
title: 'Lync Server 2013: Veröffentlichen Ihrer Topologie'
description: 'Lync Server 2013: veröffentlichen Sie die Topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4d27d2d3644eb1f174e2f3fab47197f2c122a97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571751"
---
# <a name="publish-your-topology-in-lync-server-2013"></a>Veröffentlichen Ihrer Topologie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Jedes Mal, wenn Sie die Topologie mithilfe des Topologie-Generators erstellen, müssen Sie die Topologie in einer Datenbank im zentralen Verwaltungsspeicher veröffentlichen, damit die Daten für die Bereitstellung von lync Server 2013 verwendet werden können. Führen Sie die folgenden Schritte aus, um Ihre Topologie zu veröffentlichen.

<div>

## <a name="to-publish-the-topology"></a>So veröffentlichen Sie die Topologie

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Klicken Sie im Topologie-Generator in der Konsolenstruktur mit der rechten Maustaste auf **lync 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.

3.  Klicken Sie auf der Seite **Willkommen** des Assistenten auf **Weiter**.

4.  Klicken Sie auf der Seite **Topologie-Generator hat einen zentralen Verwaltungsspeicher gefunden** auf **Weiter**.

5.  Klicken Sie auf der Seite **Weitere Datenbanken erstellen** auf **Weiter**.

6.  Wenn die erfolgreiche Erstellung der Datenbank angezeigt wird, führen Sie folgende Schritte aus:
    
      - Klicken Sie zum Anzeigen des Protokolls auf **Protokoll anzeigen**.
    
      - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.
        
        <div>
        

        > [!IMPORTANT]  
        > Wenn es sich um eine Neuinstallation eines Edgeserver oder Edgepool handelt, müssen Sie die Edgeserver Konfiguration aus einer vorhandenen Front-End-Server, Front-End-Pool oder Standard Edition-Server exportieren. Informationen zum Exportieren der Konfiguration finden Sie unter <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Exportieren der lync Server 2013 Topologie und Kopieren der Konfiguration auf externe Medien für die Edge-Installation</A>. Sie importieren die Konfigurationsdatei von der externen Medien-oder Netzwerkfreigabe während der Setup-und Bereitstellungsphase der Edgeserver über den lync Server-Bereitstellungs-Assistenten.<BR>Sobald die Edgeserver betriebsbereit sind und die lokale Konfigurations Verwaltungsspeicher-Datenbank mit der internen Bereitstellung repliziert wird, werden nachfolgende Updates für die lync Server 2013 Konfiguration veröffentlicht und auf die Edgeserver repliziert.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

