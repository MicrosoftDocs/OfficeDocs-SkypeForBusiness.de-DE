---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4245efe0faf5dfe947cc52fb22a447e46c0b3e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Bereitstellen eines Pilot-Edgeservers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

In diesem Thema werden Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihrer lync Server 2013 Edgeserver beachten sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotedgepools hervorgehoben. Ausführliche Anweisungen finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird und der auch Konfigurationsinformationen für den Zugriff durch externe Benutzer enthält.

As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.

**Definieren eines Edgepools**

1.  Öffnen Sie mithilfe des Topologie-Generators die Pilotpooltopologie.

2.  Navigieren Sie zum Knoten lync Server 2013. Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.
    
    ![Definieren des Dialogfelds "neuer Edge-Pool"](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definieren des Dialogfelds "neuer Edge-Pool"")

3.  Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer**.
    
    ![Definieren des Dialogfelds für den FQDN des Edge-Pools](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definieren des Dialogfelds für den FQDN des Edge-Pools")

4.  Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Verbund oder den XMPP-Partnerverbund. Der Verbund und der XMPP-Verbund werden derzeit über die Legacy Office Communications Server 2007 R2 Edgeserver weitergeleitet. Diese Funktionen werden in einer späteren Phase der Migration konfiguriert.
    
    ![Dialogfeld ' Features auswählen '](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Dialogfeld ' Features auswählen '")

5.  Bearbeiten Sie anschließend die folgenden Seiten des Assistenten: **IP-Optionen auswählen**, **Externe FQDNs**, **Interne IP-Adresse definieren** und **Externe IP-Adresse definieren**.

6.  Wählen Sie auf der Seite **nächsten Hop definieren** den Director für den nächsten Hop des lync Server 2013 Edgepool aus.
    
    ![Dialogfeld "neuen Edge-Pool definieren", Liste "Nächster Hop-Pool"](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Dialogfeld "neuen Edge-Pool definieren", Liste "Nächster Hop-Pool"")

7.  Ordnen Sie diesem Edgepool auf der Seite **Front-End-Pools zuordnen** keinen Pool zu diesem Zeitpunkt zu. Der externe Mediendatenverkehr wird derzeit über die Legacy Office Communications Server 2007 R2 Edgeserver weitergeleitet. Diese Einstellung wird in einer späteren Phase der Migration konfiguriert.
    
    ![Dialogfeld "neuen Edge-Pool definieren"](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Dialogfeld "neuen Edge-Pool definieren"")

8.  Klicken Sie auf **Fertig stellen**, und **veröffentlichen** Sie anschließend die Topologie.

9.  Führen Sie die Schritte unter [install Edge Servers for lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.

Es ist sehr wichtig, dass Sie die Richtlinien in den Themen befolgen, in denen der [externe Benutzer Zugriff in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation bereitgestellt wird. Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar.

Sie sollten nun eine Legacy Office Communications Server 2007 R2-Edgeserver-Bereitstellung haben, die durch das vorhanden sein des BackCompatSite-Servers parallel zu einer lync Server 2013-Edge-Server-Bereitstellung angezeigt wird. Der Verbund ist für die Verwendung des Office Communications Server 2007 R2 Directors konfiguriert. Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren.

![Topologie-Generator mit OCS-Edgeserver](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topologie-Generator mit OCS-Edgeserver")

</div>

<span> </span>

</div>

</div>

</div>

