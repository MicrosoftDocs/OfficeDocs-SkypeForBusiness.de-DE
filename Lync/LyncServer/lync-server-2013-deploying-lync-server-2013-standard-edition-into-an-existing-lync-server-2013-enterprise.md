---
title: 'Lync Server 2013: Bereitstellen lync Server 2013 Standard Edition in einem vorhandenen lync Server 2013 Unternehmen'
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
ms.openlocfilehash: 76d7183e60c09729758d7297fd3b6db2cd6622d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Bereitstellen lync Server 2013 Standard Edition in einem vorhandenen lync Server 2013 Enterprise

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Das Bereitstelleneiner Standard Edition-Server in einer vorhandenen Enterprise Edition-Bereitstellung ähnelt dem Bereitstellen zusätzlicher Serverrollen. Ein Standard Edition-Server kann an einer anderen Website bereitgestellt werden, sodass Benutzer an dieser Website auf dem Standard Edition-Server statt auf der Front-End-Pool über ein WAN (Wide Area Network) hinweg verwaltet werden können. Die Verfahren zum Installieren der neuen Website und der Server an diesem Standort sind bereits in anderen Abschnitten der [Bereitstellung lync Server 2013](lync-server-2013-deploying-lync-server.md) Dokumentation definiert.

<div id="sectionSection0" class="section">

**So definieren Sie einen neuen Standort**

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **neuer zentraler Standort**.

3.  Geben Sie auf der Seite **Standort identifizieren** einen Namen für den Standort und optional eine Beschreibung ein.

4.  Führen Sie die erforderlichen Schritte zum Definieren der weiteren Komponenten der Standorttopologie aus. Ausführliche Informationen finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Veröffentlichen Sie die aktualisierte Topologie. Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Einrichten und Installieren eines Standard Edition-Server.
    
    <div>
    

    > [!Caution]  
    > Wenn Sie eine Umgebung mit nur einem Standard Edition-Server bereitgestellt haben, hätten Sie den Installationsvorgang mit dem lync Server-Bereitstellungs-Assistenten mithilfe des Links <STRONG>Prepare First Standard Edition-Server</STRONG> begonnen, um die anfänglichen Datenbankdateien im neuen Standard Edition-Server zu installieren. Führen Sie diesen Prozess <STRONG>nicht</STRONG> aus, wenn Sie einen Standard Edition-Server in einer vorhandenen lync Server 2013-Bereitstellung installieren.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

