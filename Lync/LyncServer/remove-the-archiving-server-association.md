---
title: Entfernen der Zuordnung des Archivierungsservers
description: Entfernen Sie die Zuordnung des Archivierungsservers.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f6c34e49b0217a8318a83752b3878a7625e5d58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570221"
---
# <a name="remove-the-archiving-server-association"></a>Entfernen der Zuordnung des Archivierungsservers

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Zum Entfernen eines Archivierungsserver müssen Sie die Abhängigkeit von der zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.

<div>

## <a name="to-remove-the-archiving-server-association"></a>So entfernen Sie die Zuordnung des Archivierungsservers

1.  Öffnen Sie die lync Server 2013 Front-End-Server, öffnen Sie den Topologie-Generator.

2.  Navigieren Sie zum Knoten lync Server 2010.

3.  Erweitern Sie im Topologie-Generator die **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellenstandorte**basierend auf der Definition des Archivierungsserver.

4.  Wenn Sie Survivable Branch Server zugeordnet haben, erweitern Sie **Zweigstellenstandorte**, erweitern Sie den Namen der Zweigstelle, und erweitern Sie dann **Survivable Branch Appliances**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Survivable Branch Appliances</STRONG> in der Benutzeroberfläche gelten sowohl für Survivable Branch Server als auch für Survivable Branch Appliance.

    
    </div>

5.  Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, das dem Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.

6.  Deaktivieren Sie in **Eigenschaften bearbeiten**, unter **Allgemein**, unter **Zuordnungen** das Kontrollkästchen **Archivierungsserver zuordnen**, und klicken Sie dann auf **OK**.

7.  Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem zu entfernenden Archivierungsserver zugeordnet sind.

8.  Klicken Sie mit der rechten Maustaste auf den Archivierungsserver, und klicken Sie dann auf **Löschen**.

9.  Klicken Sie unter **Abhängige Speicher löschen** auf **OK**.

10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die lync Server-Bereitstellung bei Bedarf aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

