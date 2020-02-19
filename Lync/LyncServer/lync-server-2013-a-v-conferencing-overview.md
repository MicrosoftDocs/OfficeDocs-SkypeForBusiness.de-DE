---
title: Lync Server 2013 A/V-Konferenzen (Übersicht)
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
ms.openlocfilehash: 4d77d39cfa1483db9251d038f876f8e91428ae23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Übersicht über A/V-Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-13_

A/V-Konferenzen ermöglichen die Echtzeit-Audio-und Videokommunikation zwischen Ihren Benutzern. Wenn Sie die Konferenzfunktion bereitstellen, können Sie entweder sowohl Webkonferenzen als auch A/V-Konferenzen oder nur Webkonferenzen aktivieren.

Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden. Dies kann Audio-, Video-und Panorama Video umfassen.

Bevor Sie Benutzer für A/V-Konferenzen aktivieren, müssen Sie sicherstellen, dass Ihr Netzwerk die resultierende Last verarbeiten kann. Ohne ausreichende Netzwerkbandbreite kann die Benutzeroberfläche stark beeinträchtigt werden. Sie können die Anrufsteuerung (Call Admission Control, CAC) verwenden, um die von A/V-Konferenzen verwendete Netzwerkbandbreite zu verwalten. Dies ist für eingeschränkte Netzwerke wichtig, beispielsweise für Verbindungen mit beschränkter Bandbreite zwischen zentralen und Zweigstellenstandorten. Ausführliche Informationen finden Sie unter [Overview of Call Admission Control in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Ausführliche Informationen zu den Anforderungen an die Medien Bandbreite finden Sie unter Anforderungen an die [Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Wenn Sie Audiokonferenzen in Ihrem Netzwerk bereitstellen, benötigen Ihre Benutzer Audiogeräte wie Headsets, um an einer Audiokonferenz teilzunehmen. Bei der Bereitstellung von Videokonferenzen müssen Sie Videogeräte wie Webcams für Benutzer bereitstellen. Es wird empfohlen, UC-Geräte (Unified Communications) zu verwenden, die von Microsoft für alle Gerätetypen zertifiziert sind, um eine optimale Benutzerfreundlichkeit sicherzustellen. Ausführliche Informationen zu UC-zertifizierten Geräten finden Sie unter "Telefone und Geräte für lync [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861)" unter. Für Audio-oder Videogeräte sind die Gerätebereitstellung und die Benutzerschulung wichtige Schritte, die Sie berücksichtigen und planen müssen.

In den folgenden Abschnitten werden die Funktionen für Audio-und Videokonferenzen beschrieben, einschließlich Informationen zum Verwalten der Bandbreite und zum Auswählen der entsprechenden Clients.

<div>

## <a name="audio-conferencing-features"></a>Audiokonferenz-Features

Lync Server 2013 bietet verschiedene Features, mit denen Sie die Audiokonferenz-Benutzeroberfläche für den Benutzer konfigurieren können, einschließlich der folgenden:

  - **Benutzergruppe stumm**   der Referent kann diese Einstellung verwenden, um alle Audioteiler in der Konferenz stummzuschalten und die Konferenz in einen Zustand versetzen, in dem nicht-Referenten sich selbst nicht entmuten können.

  - **Conferencing Entry/Exit Announcements**   Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten diese Einstellung verwenden, um die Eingabe-und Beendigungs Ankündigungen zu aktivieren oder zu deaktivieren, um Ablenkungen während einer Konferenz zu minimieren.

  - **Durch das Hinzufügen eines Benutzers durch das anwählen**   von Referenten und Teilnehmern, denen die Berechtigung erteilt wurde, können den Konferenzen PSTN-Nummern hinzugefügt werden, und die Konferenz kann für diese Nummern gewählt werden.

</div>

<div>

## <a name="video-conferencing-features"></a>Video Konferenzfunktionen

Lync Server 2013 bietet verschiedene Features, mit denen Sie die Videokonferenzumgebung für den Benutzer konfigurieren können, einschließlich der folgenden:

  - **Galerieansicht**   in Videokonferenzen mit mehr als zwei Personen sehen Benutzer automatisch alle Mitglieder der Konferenz. Wenn die Konferenz über mehr als fünf Teilnehmer verfügt, wird das Video der aktivsten Teilnehmer in der obersten Zeile angezeigt, und für die anderen Teilnehmer wird nur das Foto angezeigt. Video mit mehreren Teilern ist standardmäßig aktiviert. Ausführliche Informationen zum Konfigurieren oder Deaktivieren von Video für mehrteilige Videos finden Sie unter [Konfigurieren der Videobandbreite in lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Panorama Video**   wenn im Konferenzraum ein RoundTable-Videokonferenz Gerät installiert ist, bietet dieses Feature eine vollständige 360 Grad Ansicht des Konferenzraums. Der Panorama-Video Strip ist nur für RoundTable-Geräte verfügbar.

  - **Referent nur Videomodus**   Referenten können die Besprechung so konfigurieren, dass nur das Video des Referenten angezeigt wird. Dadurch werden Ablenkungen in großen Besprechungen verhindert, wenn mehrere Videostreams verfügbar sind und verschiedene Quellen gesperrt werden. Dieser Modus gilt auch für von RoundTable-Geräten erfasste und bereitgestellte Videos.

  - **HD-Video**   Benutzer können Auflösungen bis zu HD 1080p in Gesprächen mit zwei Teilnehmern und Konferenzen mit mehreren Teilnehmern durchführen.

  - ****   Referenten für Video Spotlight können die Besprechung so konfigurieren, dass nur das Video eines ausgewählten Teilnehmers, der eine Videoquelle ist, von den anderen Teilnehmern in der Konferenz angezeigt wird. Dieser Modus gilt auch für Videos, die von RoundTable-Geräten für Panorama Video erfasst und bereitgestellt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

