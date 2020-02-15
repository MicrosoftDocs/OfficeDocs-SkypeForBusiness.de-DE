---
title: Konfigurieren lync Server 2013 für die Verwendung mit Office-webapps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a5cd13b139cb2544e1d89971a8480d1e1fb296
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Konfigurieren lync Server 2013 für die Verwendung mit Office-webapps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-04-22_

Bevor Sie lync Server 2013 für die Verwendung von Office-webapps Server konfigurieren können, müssen Office-webapps-Server bereitgestellt und konfiguriert werden. Ausführliche Informationen über die Installation und Konfiguration eines einzelnen Office Web Apps-Servers oder einer Office Web Apps-Serverfarm für Hochverfügbarkeitszwecke finden Sie im **Handbuch zur Bereitstellung von Office Web Apps-Server und Office Web Apps**.

Nachdem Sie den Office-webapps-Server erfolgreich installiert und die Webfarm ordnungsgemäß konfiguriert haben, müssen Sie lync Server für die Kommunikation mit dem neuen Server konfigurieren. Fügen Sie dazu die Office-webapps Server Discovery-URL zu ihrer lync Server-Topologie hinzu. Gehen Sie dazu wie folgt vor:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus einer vorhandenen Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.

3.  Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) in **Dateiname** ein, und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.

4.  Erweitern Sie im Topologie-Generator **lync Server 2013**, erweitern Sie den Namen Ihres Standorts, erweitern Sie **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen eines Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.

5.  Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen**, und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).

6.  Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
    Wenn der Office Web Apps-Server lokal und in der gleichen Netzwerkzone wie lync Server 2013 installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (d. "Perimeter/Internet")** sollte nicht ausgewählt werden.
    
    Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.

7.  Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK**, und klicken Sie dann auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Office Web Apps-Such-URL wird dann unter den Zuordnungen des Pools aufgeführt.

Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.

Nachdem Sie die Such-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:

1.  Klicken Sie auf **Aktion**, und klicken Sie dann auf **Topologie veröffentlichen**.

2.  Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

3.  Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.

4.  Schließen Sie den Topologie-Generator.

</div>

<span> </span>

</div>

</div>

</div>

