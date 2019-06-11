---
title: Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Office Web Apps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-04-22_

Bevor Sie lync Server 2013 für die Verwendung von Office Web Apps Server konfigurieren können, muss Office Web Apps Server bereitgestellt und konfiguriert werden. Im Dokument **Handbuch zum Bereitstellen von Office Web Apps Server und Office Web Apps** finden Sie ausführliche Informationen zum Installieren und Konfigurieren eines einzelnen Office Web Apps-Servers oder Informationen zum Installieren und Konfigurieren einer Office Web Apps-Server Farm für eine höhere Verfügbarkeit.

Nachdem Office Web Apps Server erfolgreich installiert und die Webfarm ordnungsgemäß konfiguriert wurde, müssen Sie lync Server für die Kommunikation mit dem neuen Server konfigurieren. Dies erfolgt durch Hinzufügen der Office Web Apps Server Discovery-URL zu ihrer lync Server-Topologie. Gehen Sie dazu wie folgt vor:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus und klicken Sie dann auf **OK**.

3.  Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) im Feld **Dateiname** ein und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.

4.  Erweitern Sie im Topologie-Generator **lync Server 2013**, erweitern Sie den Namen Ihrer Website, erweitern Sie **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen eines Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.

5.  Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen** und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).

6.  Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
    Wenn der Office Web Apps-Server lokal und in derselben Netzwerkzone wie lync Server 2013 installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (also Umkreis/Internet)** , nicht ausgewählt werden.
    
    Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.

7.  Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK** und klicken Sie anschließend auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Office Web Apps Discovery-URL wird dann als eine der Assoziationen des Pools aufgelistet.

Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.

Nachdem Sie die Discovery-URL zur Topologie hinzugefügt haben, müssen Sie diese aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:

1.  Klicken Sie auf **Aktion** und klicken Sie anschließend auf **Topologie veröffentlichen**.

2.  Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

3.  Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertigstellen**.

4.  Schließen Sie den Topologie-Generator.

</div>

<span> </span>

</div>

</div>

</div>

