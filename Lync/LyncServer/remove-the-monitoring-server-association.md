---
title: Entfernen der Zuordnung der Monitoring Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5703153bb1034f1318fbe14ca3583ad5744ffdb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Entfernen der Zuordnung der Monitoring Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Zum Entfernen des Überwachungsservers müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable-Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>So entfernen Sie die Monitoring Server-Zuordnung

1.  Öffnen Sie den lync Server 2013-Front-End-Server, öffnen Sie den Topologie-Generator.

2.  Navigieren Sie zum lync Server 2010-Knoten.

3.  Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellen**, basierend auf der Definition des Überwachungsservers.

4.  Wenn Sie über einen Überlebenden Branch Server verfügen, erweitern Sie **Zweigstellen**, erweitern Sie den Namen der Verzweigungs Website, und erweitern Sie dann **Survivable Branch Appliances**.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Survivable-Branch</STRONG> -Appliances auf der Benutzeroberfläche gelten sowohl für Survival Branch-Server als auch für Survivable Branch-Appliance.

    
    </div>

5.  Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, der dem Überwachungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.

6.  Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemein**unter **Zuordnungen**das Kontrollkästchen **Überwachungs Server zuordnen** , und klicken Sie dann auf **OK**.

7.  Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Überwachungsserver zugeordnet sind.

8.  Klicken Sie mit der rechten Maustaste auf den Überwachungs Server, und klicken Sie dann auf **Löschen**.

9.  Klicken Sie unter **abhängige Speicher löschen**auf **OK**.

10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den lync Server-Bereitstellungs-Assistenten nach Bedarf aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

