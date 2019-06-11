---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Bereitstellen eines Pilot-Edgeservers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihres lync Server 2013-Edgeserver beachten sollten. In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie als Teil der Bereitstellung des Pilot Edge-Pools berücksichtigen sollten. Detaillierte Anweisungen finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird, sowie Konfigurationsinformationen für den Zugriff durch externe Benutzer.

Wenn Sie im Assistenten zum **Definieren eines neuen Edge-Pools** navigieren, überprüfen Sie die wichtigsten Konfigurationseinstellungen, die in den folgenden Schritten gezeigt werden. Beachten Sie, dass nur wenige Seiten des Assistenten zum **Definieren eines neuen Edge-Pools** angezeigt werden.

**Definieren eines Edge-Pools**

1.  Öffnen Sie die Topologie des pilotpools mithilfe des Topologie-Generators.

2.  Navigieren Sie zum lync Server 2013-Knoten. Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie auf **neuer Edge-Pool**.
    
    ![Dialogfeld ' neuen Edge-Pool definieren] ' (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Dialogfeld ' neuen Edge-Pool definieren") '

3.  Ein Edge-Pool kann ein Pool mit **mehreren Computern** oder ein **einzelner Computerpool**sein.
    
    ![Definieren des Dialogfelds "FQDN des Edge-Pools"] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definieren des Dialogfelds \"FQDN des Edge-Pools\"")

4.  Aktivieren Sie auf der Seite **"Features auswählen** " die Föderation oder den XMPP-Verbund nicht. Föderations-und XMPP-Föderation werden derzeit über den Legacy Office Communications Server 2007 R2 Edge-Server weitergeleitet. Diese Features werden in einer späteren Migrationsphase konfiguriert.
    
    ![Dialogfeld ' Features auswählen] ' (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Dialogfeld ' Features auswählen") '

5.  Führen Sie als nächstes die folgenden Assistentenseiten **aus: Wählen Sie IP-Optionen**, **externe FQDNs**aus, **definieren Sie die interne IP-Adresse**, und definieren Sie **die externe IP-Adresse**.

6.  Wählen Sie auf der Seite **Nächster Hop definieren** den Director für den nächsten Hop des lync Server 2013-Edge-Pools aus.
    
    ![Dialogfeld "neuen Edge-Pool definieren", Liste des nächsten Hop-Pools] (images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Dialogfeld \"neuen Edge-Pool definieren\", Liste des nächsten Hop-Pools")

7.  Verbinden Sie auf der Seite **Front-End-Pools zuordnen** keinen Pool mit diesem Edge-Pool zu diesem Zeitpunkt. Der externe Mediendatenverkehr wird derzeit über den Legacy Office Communications Server 2007 R2-Edgeserver weitergeleitet. Diese Einstellung wird in einer späteren Migrationsphase konfiguriert.
    
    ![Dialogfeld "neuen Edge-Pool definieren"] (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Dialogfeld \"neuen Edge-Pool definieren\"")

8.  Klicken Sie auf **Fertig stellen** , und **veröffentlichen** Sie die Topologie.

9.  Führen Sie die Schritte unter [Installieren von Edge-Servern für lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.

Es ist sehr wichtig, dass Sie die Richtlinien in den Themen zum [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation befolgen. Dieser Abschnitt enthält lediglich einige Anleitungen zu Konfigurationseinstellungen beim Installieren dieser Serverrollen.

Sie sollten nun über eine Legacy Office Communications Server 2007 R2 Edge Server-Bereitstellung verfügen, die durch das vorhanden sein des BackCompatSite parallel zu einer lync Server 2013-Edgeserver-Bereitstellung angegeben wird. Der Verbund ist für die Verwendung des Office Communications Server 2007 R2-Directors konfiguriert. Überprüfen Sie, ob beide Bereitstellungen ordnungsgemäß ausgeführt werden, Dienste gestartet sind, und Sie können jede Bereitstellung verwalten, bevor Sie in die nächste Phase wechseln.

![Topologie-Generator mit OCS] -Edgeserver (images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topologie-Generator mit OCS") -Edgeserver

</div>

<span> </span>

</div>

</div>

</div>

