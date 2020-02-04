---
title: Übersicht über lync Server 2013 A/V-Konferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 405d44f9128ef4c8120a6a8389f8d566b6880b2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Übersicht über A/V-Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-13_

A/V-Konferenzen ermöglichen Audio-und Videokommunikation in Echtzeit zwischen Ihren Benutzern. Wenn Sie Konferenzen bereitstellen, können Sie auswählen, ob Sie Webkonferenzen und A/V-Konferenzen oder nur Webkonferenzen aktivieren und verwenden möchten.

Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden. Dies könnten z. B. Audio, Video und Panoramavideo sein.

Bevor Sie Benutzer für A/V-Konferenzen aktivieren, stellen Sie sicher, dass Ihr Netzwerk die resultierende Last verarbeiten kann. Eine zu geringe Netzwerkbandbreite kann zu einem stark beeinträchtigten Benutzererlebnis führen. Sie können die Anrufsteuerung (Call Admission Control, CAC) verwenden, um die von A/V-Konferenzen verwendete Netzwerkbandbreite zu verwalten. Dies ist für eingeschränkte Netzwerke wichtig, beispielsweise bei Verbindungen mit beschränkter Bandbreite zwischen Zentrale und Niederlassungen. Ausführliche Informationen finden Sie unter Übersicht über die [Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Details zu den Anforderungen an die Medien Bandbreite finden Sie unter Anforderungen an die [Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Bei Bereitstellung der Audiokonferenzfunktion in Ihrem Netzwerk benötigen Ihre Benutzer Audiogeräte (z. B. Headsets), um an einer Audiokonferenz teilzunehmen. Wenn Sie Videokonferenzen bereitstellen, benötigen die Benutzer Videogeräte, wie Webcams. Wir empfehlen die Verwendung von UC-Geräten (Unified Communications), die von Microsoft für alle Gerätetypen zertifiziert sind, um eine optimale Benutzererfahrung zu gewährleisten. Details zu UC-zertifizierten Geräten finden Sie unter "Telefone und Geräte für lync" [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)unter. Für Audio-oder Videogeräte, die Gerätebereitstellung und die Benutzerschulung sind wichtige Schritte, die Sie beachten und planen können.

In den folgenden Abschnitten werden die Features für Audio-und Videokonferenzen beschrieben, einschließlich Informationen zum Verwalten der Bandbreite und zum Auswählen der entsprechenden Clients.

<div>

## <a name="audio-conferencing-features"></a>Audiokonferenz-Features

Lync Server 2013 bietet verschiedene Features, die Sie zum Konfigurieren der Audiokonferenz-Oberfläche für den Benutzer verwenden können, einschließlich der folgenden:

  - **Zuschauer Stummschaltung**   der Referent kann diese Einstellung verwenden, um alle Audio-Teilnehmer in der Konferenz stummzuschalten und die Konferenz in einen Zustand zu versetzen, in dem nicht Referenten die Stummschaltung selbst aufheben können.

  - **Conferencing Entry/Exit-Ankündigungen**   Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten diese Einstellung verwenden, um ein-und ausgehende Ankündigungen zu aktivieren oder zu deaktivieren, um Ablenkungen zu minimieren, während eine Konferenz läuft.

  - **Wenn Sie einen Benutzer hinzufügen, indem Sie**   Referenten und Teilnehmer auswählen, denen die Berechtigung erteilt wurde, können Sie den Konferenzen PSTN-Nummern hinzufügen und die Konferenz an diese Nummern anwählen.

</div>

<div>

## <a name="video-conferencing-features"></a>Video Konferenz Features

Lync Server 2013 bietet verschiedene Features, mit denen Sie die Videokonferenzfunktionalität für den Benutzer konfigurieren können, einschließlich der folgenden:

  - **Katalogansicht**   in Videokonferenzen, die mehr als zwei Personen aufweisen, sehen Benutzer automatisch alle Teilnehmer der Konferenz. Wenn die Konferenz mehr als fünf Teilnehmer hat, werden in der ersten Zeile die Videos der aktivsten Teilnehmer angezeigt und für die übrigen Teilnehmer Fotos. Die Videoaushandlung ist standardmäßig aktiviert. Details zum Konfigurieren oder Deaktivieren von mehrteiligen Videos finden Sie unter [Konfigurieren der Videobandbreite in lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Panorama Video**   wenn ein RoundTable-Videokonferenz Gerät im Konferenzraum installiert ist, bietet dieses Feature eine vollständige 360-Grad-Ansicht des Konferenzraums. Panoramavideo ist nur mit Round Table verfügbar.

  - **Referenten nur Videomodus**   Referenten können die Besprechung so konfigurieren, dass nur das Video des Referenten angezeigt wird. Dies verhindert bei großen Besprechungen Ablenkungen, wenn mehrere Videostreams verfügbar und mit verschiedenen Quellen verbunden sind. Dieser Modus wird auch auf Videos angewendet, die mit Round Table-Geräte aufgenommen und bereitgestellt werden.

  - **HD-Video**   Benutzer können Auflösungen bis zu HD 1080p in zwei-Parteien-anrufen und mehrteiligen Konferenzen erleben.

  - **Video Spotlight**   -Referenten können die Besprechung so konfigurieren, dass nur das Video von einem ausgewählten Teilnehmer, der eine Videoquelle ist, von den anderen Teilnehmern der Konferenz gesehen wird. Dieser Modus wird auch auf Videos angewendet, die mit Round Table-Geräten aufgenommen und bereitgestellt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

