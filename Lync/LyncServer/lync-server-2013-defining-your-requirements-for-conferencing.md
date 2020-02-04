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
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Definieren der Anforderungen für Konferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. Die folgende Liste der Fragen führt Sie durch den Konferenz Planungsprozess, um zu ermitteln, welche Features von Konferenzen Sie basierend auf den Anforderungen Ihrer Organisation bereitstellen sollten.

  - **Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**
    
    In diesem Fall müssen Sie die Konferenz für Ihren Front-End-Pool im Microsoft lync Server 2013, Planungs Tool oder im Topologie-Generator aktivieren. Wenn Sie Konferenzen aktivieren, aktivieren Sie sowohl Webkonferenzen als auch A/V-Konferenzen.
    
    Bei der Anwendungsfreigabe wird eine höhere Netzwerkbandbreite als bei der Dokumentzusammenarbeit benötigt und belegt. Lync Server 2013 bietet einen Drosselungsmechanismus zum Steuern jeder Anwendungsfreigabesitzung. In der Standardeinstellung sind für jede Sitzung 1,5 KB/s festgelegt.
    
    Wenn Sie die Anwendungsfreigabe nicht aktivieren möchten, Sie jedoch die Zusammenarbeit mit Dokumenten verwenden möchten, können Sie Konferenzen aktivieren und Besprechungsrichtlinien verwenden, um die Anwendungsfreigabe zu deaktivieren. Details zum Konfigurieren von Besprechungsrichtlinien finden Sie unter [Konferenzrichtlinien in lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Um Benutzern das Freigeben von PowerPoint-Präsentationen zu ermöglichen, müssen Sie den Office Web Apps-Server konfigurieren. Weitere Informationen zum Konfigurieren von Office Web Apps Server finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Möchten Sie eine/V-Konferenz aktivieren?**
    
    In diesem Fall müssen Sie die Konferenz für Ihren Front-End-Pool im lync Server 2013, Planungs Tool oder im Topologie-Generator aktivieren. Wenn Sie Konferenzen aktivieren, aktivieren Sie sowohl Webkonferenzen als auch A/V-Konferenzen.
    
    A/V-Konferenzen erfordern und verwenden mehr Netzwerkbandbreite als Webkonferenzen (einschließlich Dokument Zusammenarbeit und Anwendungsfreigabe). Wenn Sie keine a/v-Konferenzen aktivieren, aber Webkonferenzen aktivieren möchten, können Sie Konferenzen aktivieren und Besprechungsrichtlinien verwenden, um a/v-Konferenzen zu deaktivieren.
    
    Wenn Sie Audiokonferenzen, aber keine Videokonferenzen aktivieren möchten, können Sie eine/V-Konferenz aktivieren und mithilfe von Besprechungsrichtlinien Videokonferenzen verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen.
    
    <div>
    

    > [!NOTE]  
    > Enterprise Voice wird für A/V-Konferenzen nicht benötigt. Wenn Sie A/V-Konferenzen aktivieren, können Benutzer ihren Konferenzen Audiofunktionen hinzufügen, falls sie über entsprechende Geräte verfügen. Dies gilt auch bei Verwendung eines Nebenstellensystems als Telefonlösung.

    
    </div>

  - **Möchten Sie Benutzern die Teilnahme am Audioteil von Konferenzen ermöglichen, wenn Sie ein PSTN-Telefon verwenden?**
    
    Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.

  - **Möchten Sie externen Benutzern mit lync Server 2013-Clients ermöglichen, an den von Ihnen aktivierten Konferenztypen teilzunehmen?**
    
    In diesem Fall sollten Sie Edgeserver bereitstellen. Indem Sie externe Teilnahme an Besprechungen zulassen, maximieren Sie Ihre Investition in lync Server 2013. Benutzer mit Laptops mit lync Server 2013 können beispielsweise an Konferenzen teilnehmen, egal, wo Sie sich befinden – zu Hause, im Flughafen oder auf Kunden Websites.
    
    Darüber hinaus können Sie mit Edgeserver, die bereitgestellt werden, Verbundbeziehungen mit anderen Organisationen wie Ihren Kunden oder Lieferanten erstellen, und Benutzer aus diesen Organisationen können einfacher mit ihren Benutzern zusammenarbeiten.
    
    Details zum Bereitstellen von Edgeserver finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md). Details zum Aktivieren von externem Zugriff für Office Web Apps Server finden Sie unter [Veröffentlichen von Office Web Apps Server in lync Server 2013 mit einem Reverse Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Möchten Sie die Clients steuern, die an lync Server 2013-Besprechungen teilnehmen können?**
    
    Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen. Jedes Mal, wenn ein Benutzer auf einen Link klickt, um an einer geplanten Besprechung teilzunehmen, erkennt lync Server 2013, ob ein Client bereits auf dem Computer installiert ist. Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt mit Links zu alternativen Clients wird geöffnet. Die Seite "Besprechungsteilnahme" enthält immer die Option, Microsoft lync Web App zu verwenden. Ferner können Sie entscheiden, ob Links für Teilnehmer und frühere Versionen von Communicator eingeschlossen werden sollen. Ausführliche Informationen finden Sie unter [Konfigurieren der Besprechungsteilnahme Seite in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Webkonferenz Anforderungen in lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [A/V-Konferenz Anforderungen in lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Anforderungen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Konferenzen in Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Prüfliste zur Bereitstellung für Konferenzen in Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

