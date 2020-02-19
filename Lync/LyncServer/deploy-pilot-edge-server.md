---
title: Bereitstellen von Pilot Edgeserver
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b519256d254b5862dae904830620ba09d184d5df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Bereitstellen von Pilot Edgeserver

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

In diesem Thema werden Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihrer lync Server 2013 Edgeserver beachten sollten. Die Bereitstellungs-und Konfigurationsprozesse für lync Server 2013 ähneln lync Server 2010. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Anweisungen finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird und der auch Konfigurationsinformationen für den Zugriff durch externe Benutzer enthält.

Überprüfen Sie beim Navigieren durch den Assistenten zum **Definieren eines neuen Edgepools** die in den folgenden Schritten dargestellten wichtigen Konfigurationseinstellungen. Beachten Sie, dass nur einige der Seiten des Assistenten zum **Definieren eines neuen Edgepools** abgebildet sind.

**Definieren eines Edgepools**

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Navigieren Sie zum Knoten lync Server 2013. Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.
    
    ![Definieren des Dialogfelds "neuer Edge-Pool"](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definieren des Dialogfelds "neuer Edge-Pool"")

3.  Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer**.
    
    ![Definieren des Dialogfelds für den FQDN des Edge-Pools](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definieren des Dialogfelds für den FQDN des Edge-Pools")

4.  Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Verbund oder den XMPP-Partnerverbund. Der Partnerverbund und der XMPP-Verbund werden derzeit über die Legacy lync Server 2010 Edgeserver weitergeleitet. Diese Funktionen werden in einer späteren Phase der Migration konfiguriert.
    
    ![Dialogfeld ' Features auswählen '](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Dialogfeld ' Features auswählen '")

5.  Bearbeiten Sie anschließend die folgenden Seiten des Assistenten: **Externe FQDNs**, **	Interne IP-Adresse definieren** und **Externe IP-Adresse definieren**.

6.  Wählen Sie auf der Seite **nächsten Hop definieren** den Director für den nächsten Hop des lync Server 2010 Edgepool aus.
    
    ![Definieren des nächsten Hops (Dialogfeld)](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Definieren des nächsten Hops (Dialogfeld)")

7.  Verknüpfen Sie auf der Seite **Front-End-oder Vermittlungs Pools zuordnen** keinen Pool mit diesem Edgepool zu diesem Zeitpunkt. Der externe Mediendatenverkehr wird derzeit über die Legacy lync Server 2010 Edgeserver weitergeleitet. Diese Einstellung wird in einer späteren Phase der Migration konfiguriert.
    
    ![Dialogfeld "Front-End-Pools zuordnen"](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Dialogfeld "Front-End-Pools zuordnen"")

8.  Klicken Sie auf **Fertig stellen**, und **veröffentlichen** Sie anschließend die Topologie.

9.  Führen Sie die Schritte unter [install Edge Servers for lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.

Es ist sehr wichtig, dass Sie die Richtlinien in den Themen befolgen, in denen der [externe Benutzer Zugriff in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation bereitgestellt wird. Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar.

Sie sollten nun über ein Legacy-lync Server 2010 verfügen, Edgeserver parallel mit einer lync Server 2013-Edge-Server-Bereitstellung bereitgestellt wird. Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren.

</div>

<span> </span>

</div>

</div>

</div>

