---
title: 'Lync Server 2013: Definieren der Anforderungen für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 982643a33a2855075eac5372fa0140c3a69b39bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Definieren der Anforderungen für Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-30_

Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. Die nachfolgenden Fragen führen Sie durch den Konferenzplanungsprozess und helfen Ihnen, herauszufinden, welche Konferenzfunktionen aufgrund der Anforderungen Ihrer Organisation benötigt werden.

  - **Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**
    
    Wenn dies der Fall ist, müssen Sie die Konferenz für Ihre Front-End-Pool im Microsoft lync Server 2013, im Planungs Tool oder im Topologie-Generator aktivieren. Durch das Aktivieren von Konferenzen werden sowohl Webkonferenzen als auch A/V-Konferenzen aktiviert.
    
    Bei der Anwendungsfreigabe wird eine höhere Netzwerkbandbreite als bei der Dokumentzusammenarbeit benötigt und belegt. Lync Server 2013 stellt einen Einschränkungsmechanismus zum Steuern der einzelnen Anwendungsfreigabesitzungen bereit. In der Standardeinstellung ist für jede Sitzung 1,5 KB/s festgelegt.
    
    Wenn Sie die Anwendungsfreigabe nicht aktivieren, die Funktion zur Dokumentzusammenarbeit jedoch bereitstellen möchten, können Sie die Konferenzfunktionen aktivieren und die Anwendungsfreigabe mithilfe von Besprechungsrichtlinien deaktivieren. Ausführliche Informationen zum Konfigurieren von Besprechungsrichtlinien finden Sie unter [Conferencing Policies in lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Um Benutzern die Freigabe von PowerPoint-Präsentationen zu ermöglichen, müssen Sie Office-webapps-Server konfigurieren. Ausführliche Informationen zum Konfigurieren von Office-webapps Server finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Sollen A/V-Konferenzen aktiviert werden?**
    
    Wenn dies der Fall ist, müssen Sie die Konferenz für Ihre Front-End-Pool im lync Server 2013, im Planungs Tool oder im Topologie-Generator aktivieren. Durch das Aktivieren von Konferenzen werden sowohl Webkonferenzen als auch A/V-Konferenzen aktiviert.
    
    Für A/V-Konferenzen ist eine höhere Netzwerkbandbreite erforderlich als für Webkonferenzen (diese umfassen Dokumentzusammenarbeit und Anwendungsfreigabe). Wenn Sie A/V-Konferenzen nicht aktivieren, das Feature für Webkonferenzen jedoch bereitstellen möchten, können Sie die Konferenzfunktionen aktivieren und A/V-Konferenzen mithilfe von Besprechungsrichtlinien deaktivieren.
    
    Wenn Sie Audiokonferenzen, jedoch keine Videokonferenzen zulassen möchten, können Sie die A/V-Konferenzfunktion aktivieren und Videokonferenzen mithilfe von Besprechungsrichtlinien verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen.
    
    <div>
    

    > [!NOTE]  
    > Enterprise-VoIP ist für die Verwendung von A/V-Konferenzen nicht erforderlich. Wenn Sie a/V-Konferenzen aktivieren, können Ihre Benutzer Ihrer Konferenzen Audiodaten hinzufügen, wenn Sie über Audiogeräte verfügen, selbst wenn Sie eine Nebenstellenanlage für Ihre Telefonlösung verwenden.

    
    </div>

  - **Sollen Benutzer bei Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen können?**
    
    Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.

  - **Möchten Sie externen Benutzern mit lync Server 2013 Clients die Teilnahme an den von Ihnen aktivierten Konferenztypen ermöglichen?**
    
    Wenn ja, müssen Sie Edgeserver bereitstellen. Indem Sie externe Teilnahme an Besprechungen ermöglichen, maximieren Sie Ihre Investitionen in lync Server 2013. Beispielsweise können Benutzer mit Laptops mit lync Server 2013 an Konferenzen von überall aus teilnehmen – zu Hause, im Flughafen oder an Kundenstandorten.
    
    Wenn Sie Edgeserver bereitstellen, können Sie zudem Partnerverbundbeziehungen mit anderen Organisationen – z. B. Ihren Kunden oder Lieferanten – einrichten, sodass Benutzer dieser Organisationen einfacher mit Ihren Benutzern zusammenarbeiten können.
    
    Ausführliche Informationen zum Bereitstellen von Edgeserver finden Sie unter [Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md). Ausführliche Informationen zum Aktivieren von externem Zugriff für Office-webapps-Server finden Sie unter [Veröffentlichen von Office-webapps Server in lync Server 2013 mithilfe eines Reverse-Proxyservers](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Möchten Sie die Clients steuern, die an lync Server 2013 Besprechungen teilnehmen können?**
    
    Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen. Jedes Mal, wenn ein Benutzer auf einen Link klickt, um einer geplanten Besprechung beizutreten, erkennt lync Server 2013, ob ein Client bereits auf dem Computer installiert ist. Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt wird geöffnet, auf der Links für alternative Clients angezeigt werden. Die Seite für den Besprechungsbeitritt enthält immer die Option zur Verwendung der Microsoft Lync Web App. Zusätzlich zu dieser Option können Sie entscheiden, ob Sie Links für Teilnehmer und frühere Versionen von Communicator einschließen möchten. Ausführliche Informationen finden Sie unter [Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Webkonferenz Anforderungen in lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [A/V-Konferenz Anforderungen in lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Anforderungen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Konferenzen in lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Prüfliste für die Bereitstellung für Konferenzen in lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

