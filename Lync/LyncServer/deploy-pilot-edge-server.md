---
title: Bereitstellen eines Pilot-Edgeservers
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
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729945"
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

In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihres lync Server 2013-Edgeserver beachten sollten. Die Bereitstellungs-und Konfigurationsprozesse für lync Server 2013 sind mit lync Server 2010 sehr ähnlich. In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten. Detaillierte Anweisungen finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird, sowie Konfigurationsinformationen für den Zugriff durch externe Benutzer.

Wenn Sie im Assistenten zum **Definieren eines neuen Edge-Pools** navigieren, überprüfen Sie die wichtigsten Konfigurationseinstellungen, die in den folgenden Schritten gezeigt werden. Beachten Sie, dass nur wenige Seiten des Assistenten zum **Definieren eines neuen Edge-Pools** angezeigt werden.

**Definieren eines Edge-Pools**

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Navigieren Sie zum lync Server 2013-Knoten. Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie auf **neuer Edge-Pool**.
    
    ![Dialogfeld ' neuen Edge-Pool definieren '](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Dialogfeld ' neuen Edge-Pool definieren '")

3.  Ein Edge-Pool kann ein Pool mit **mehreren Computern** oder ein **einzelner Computerpool**sein.
    
    ![Definieren des Dialogfelds "FQDN des Edge-Pools"](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definieren des Dialogfelds "FQDN des Edge-Pools"")

4.  Aktivieren Sie auf der Seite **"Features auswählen** " die Föderation oder den XMPP-Verbund nicht. Föderation und XMPP-Föderation sind beide derzeit über den Legacy-Edgeserver von lync Server 2010 weitergeleitet. Diese Features werden in einer späteren Migrationsphase konfiguriert.
    
    ![Dialogfeld ' Features auswählen '](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Dialogfeld ' Features auswählen '")

5.  Führen Sie als nächstes die folgenden Assistentenseiten aus: **externe FQDNs**, **definieren Sie die interne IP-Adresse**, und definieren Sie **die externe IP-Adresse**.

6.  Wählen Sie auf der Seite **Nächster Hop definieren** den Director für den nächsten Hop des lync Server 2010-Edge-Pools aus.
    
    ![Dialogfeld ' nächster Hop definieren '](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Dialogfeld ' nächster Hop definieren '")

7.  Verbinden Sie auf der Seite **Front-End-oder Mediations Pools zuordnen** keinen Pool mit diesem Edge-Pool zu diesem Zeitpunkt. Der externe Mediendatenverkehr wird derzeit über den Legacy-Edgeserver von lync Server 2010 weitergeleitet. Diese Einstellung wird in einer späteren Migrationsphase konfiguriert.
    
    ![Dialogfeld ' Front-End-Pools zuordnen '](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Dialogfeld ' Front-End-Pools zuordnen '")

8.  Klicken Sie auf **Fertig stellen** , und **veröffentlichen** Sie die Topologie.

9.  Führen Sie die Schritte unter [Installieren von Edge-Servern für lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.

Es ist sehr wichtig, dass Sie die Richtlinien in den Themen zum [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation befolgen. Dieser Abschnitt enthält lediglich einige Anleitungen zu Konfigurationseinstellungen beim Installieren dieser Serverrollen.

Sie sollten jetzt einen Legacy-lync Server 2010-Edgeserver parallel zu einer lync Server 2013-Edgeserver-Bereitstellung bereitstellen. Überprüfen Sie, ob beide Bereitstellungen ordnungsgemäß ausgeführt werden, Dienste gestartet sind, und Sie können jede Bereitstellung verwalten, bevor Sie in die nächste Phase wechseln.

</div>

<span> </span>

</div>

</div>

</div>

