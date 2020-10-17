---
title: 'Lync Server 2013: Server Richtlinie für beständigen Chat aktivieren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794fe378f9e7d8024f4bc06000d6d7d1cd89481e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528572"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Aktivieren der Server Richtlinie für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

In der lync Server 2013-Systemsteuerung können Sie die Seite **Richtlinie** für beständigen Chat der Gruppe **beständiger Chat** verwenden, um Richtlinien auf globaler Ebene, auf Pool-, Standort-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Standortrichtlinien für Ihre Bereitstellung. Wenn ein Benutzer für den Server für beständigen Chat nach Richtlinien aktiviert ist, wird die Server Umgebung für beständigen Chat in Ihrem lync 2013-Client angezeigt.

<div>


> [!NOTE]  
> In der Topologie gelten die Standortrichtlinien für beständigen Chat Server global, pro Pool des Benutzers oder pro Standort des Benutzers oder pro Benutzer.



</div>

Die globale Richtlinie wird automatisch erstellt, wenn Sie den Server für beständigen Chat bereitstellen, und Sie kann konfiguriert, jedoch nicht gelöscht werden. Da die globale Richtlinie für alle Benutzer gilt, muss sie nicht pro Benutzer festgelegt werden.

Sie können mehrere Standort-und Benutzerrichtlinien erstellen und konfigurieren, die zusammen mit der globalen Richtlinie Benutzer für den Server für beständigen Chat aktivieren. Server Richtlinien für Pool-und Website-beständigen Chat setzen die globale Richtlinie für beständigen Chat außer Kraft, jedoch nur für Benutzer dieser Website. Benutzerrichtlinien setzen globale Richtlinien, Poolrichtlinien und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.

<div>


> [!NOTE]  
> Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um die Unterstützung für beständigen Chat Server zur Topologie hinzuzufügen und die Topologie dann zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigen Chat Servern zur Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren der globalen Richtlinie für den beständigen Chat in lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Erstellen einer Standortrichtlinie für den beständigen Chat in lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Erstellen einer Benutzerrichtlinie für den beständigen Chat in lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe in lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

