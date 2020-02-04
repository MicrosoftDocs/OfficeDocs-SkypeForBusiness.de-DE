---
title: 'Lync Server 2013: Bereitstellen von Lync Server 2013 Standard Edition in einer vorhandenen Lync Server 2013 Enterprise-Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6467ae9eb3c4d5159181a2d022c060b0b9f1fec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Bereitstellen von Lync Server 2013 Standard Edition in einer vorhandenen Lync Server 2013 Enterprise-Bereitstellung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Die Bereitstellungeines Standard Edition-Servers in einer vorhandenen Enterprise Edition-Bereitstellung ähnelt der Bereitstellung zusätzlicher Serverrollen. Ein Standard Edition-Server kann auf einer anderen Website bereitgestellt werden, sodass die Benutzer auf dieser Website auf dem Standard Edition-Server statt im Front-End-Pool über ein WAN (Wide Area Network) verwaltet werden können. Die Verfahren zum Installieren der neuen Website und der neuen Server auf dieser Website sind bereits in anderen Abschnitten der [Bereitstellung von lync Server 2013](lync-server-2013-deploying-lync-server.md) -Dokumentation definiert.

<div id="sectionSection0" class="section">

**So definieren Sie eine neue Website**

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **neue zentrale Website**.

3.  Geben Sie auf der Seite **Website identifizieren** einen Namen für die Website ein, und geben Sie optional eine Beschreibung ein.

4.  Befolgen Sie die Verfahren zum Definieren der restlichen Website Topologie. Ausführliche Informationen finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Veröffentlichen der aktualisierten Topologie Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Einrichten und Installieren eines Standard Edition-Servers
    
    <div>
    

    > [!Caution]  
    > Wenn Sie eine Umgebung mit nur einem Standard Edition-Server bereitgestellt haben, hätten Sie den Setup-Vorgang mit dem lync Server-Bereitstellungs-Assistenten begonnen, indem Sie den Link <STRONG>First Standard Edition-Server vorbereiten</STRONG> verwenden, um die anfänglichen Datenbankdateien auf dem neuen Standard Edition-Server zu installieren. Führen Sie diesen Vorgang <STRONG>nicht</STRONG> aus, wenn Sie einen Standard Edition-Server in einer vorhandenen lync Server 2013-Bereitstellung installieren.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

