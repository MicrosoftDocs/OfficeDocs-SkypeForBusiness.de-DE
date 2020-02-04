---
title: 'Lync Server 2013: Allgemeine Konferenz Konzepte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d21526cfcd6d2c78cd67660136e8f7600d1841
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Allgemeine Konferenz Konzepte in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-19_

Verschiedene Konzepte sind für alle Arten von Konferenzen üblich. Diese werden in den folgenden Abschnitten beschrieben.

<div>

## <a name="policies-and-bandwidth-management"></a>Richtlinien und Bandbreitenverwaltung

Mit lync Server 2013 können Administratoren Richtlinien für die Besprechungstypen festzulegen, die von Benutzern organisiert werden können. Auf diese Weise können Sie die Richtlinien Ihrer Organisation durchsetzen und die Bandbreitennutzung kontrollieren. Sie können eine Vielzahl von Besprechungsrichtlinien definieren und diese einzelnen Benutzern und Benutzergruppen zuweisen. Ferner können Sie Richtlinien festlegen, die Peer-zu-Peer-Unterhaltungen steuern. Details zum Festlegen von Konferenzrichtlinien finden Sie unter [Konferenzrichtlinien in lync Server 2013](lync-server-2013-conferencing-policies.md) in der Betriebsdokumentation. Details zur Bandbreitenverwaltung finden Sie unter Übersicht über die [Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) und [Konfigurieren der Videobandbreite in lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Archivierungs-und Kompatibilitäts Features

Lync Server 2013 bietet Funktionen, die Sie verwenden können, wenn Ihre Organisation Konformitätsrichtlinien beachten muss. Sie können die Archivierungsfunktionen zum Archivieren von Inhalten verwenden, die in Besprechungen präsentiert werden, und auch den Inhalt von Chat Unterhaltungen und Chat Konferenzen. Ausführliche Informationen finden Sie unter [Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation. Sie können Kompatibilitätsfeatures des beständigen Chat Servers zum Archivieren von mehrteiligen, themenbasierten Konversationen verwenden, die über einen Zeitraum bestehen. Ausführliche Informationen finden Sie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

</div>

<div>

## <a name="monitoring-feature"></a>Überwachungs Feature

Das Feature "Überwachungs Server" kann Anruf Detaildatensätze (CDRs) erfassen, mit denen Sie nachverfolgen können, welche Benutzer mit welchen anderen Benutzern in lync Server 2013 sprechen. Details zum Bereitstellen und Konfigurieren der Überwachung finden Sie unter [Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Aktivieren der externen Teilnahme an Konferenzen

Sie können die Vorteile Ihrer Investition in lync Server 2013-Konferenzen erheblich steigern, indem Sie es externen Benutzern ermöglichen, bei der Einladung auch an Konferenzen teilzunehmen. Bei externen Benutzern sind unter anderem folgende Kategorien möglich:

  - **Remote Benutzer**   die eigenen Benutzer Ihrer Organisation, wenn Sie außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere lync Server 2013-Geräte verwenden.

  - **Benutzer von Verbundbenutzern**   aus Unternehmen, mit denen Sie zusammenarbeiten, die ebenfalls lync Server 2013 ausführen. Damit Ihre Benutzer problemlos Kontakt zu diesen Benutzern aufnehmen können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.

  - **Anonyme Benutzer**   alle anderen externen Benutzer, die speziell von Ihren Benutzern eingeladen werden, an bestimmten Konferenzen teilzunehmen. Der Organisator einer Besprechung in Ihrem Unternehmen kann eine E-Mail-Einladung für eine Konferenz an einen externen Benutzer senden. Diese E-Mail enthält einen Link, über den der externe Benutzer an der Konferenz teilnehmen kann.

Wenn Sie ein oder alle dieser Szenarien aktivieren möchten, müssen Sie einen Edgeserver bereitstellen, um die sichere Kommunikation zwischen Ihrer lync Server 2013-Bereitstellung und externen Benutzern zu ermöglichen. Die lync Server 2013-Lösung mit Edgeserver bietet Medien mit höherer Qualität als andere Lösungen wie ein virtuelles privates Netzwerk (VPN). Ausführliche Informationen finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Darüber hinaus können Sie, unabhängig davon, ob Sie Edgeserver bereitstellen, Benutzern (also innerhalb oder außerhalb Ihrer Organisation) das Einwählen von standardmäßigen PSTN-Telefonen ermöglichen, um an lokalen Audiokonferenzen teilzunehmen. Dazu wird die Bereitstellung von lync Server 2013-Einwahlkonferenzen durchgeführt.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Kompatibilität zwischen Besprechungstypen und Client Versionen

Wenn lync Server 2013 mit früheren Versionen von Office Communications Server und seinen Clients zusammenarbeiten soll, müssen Sie sich mit den folgenden Problemen vertraut machen:

  - Benutzer, die lync Server 2013 verwenden, können keine Live Meeting-Konferenzen planen oder migrierte Besprechungen dieses Typs ändern.

  - Benutzer, die lync Server 2013, die an Live Meeting-Konferenzen auf Servern mit Office Communications Server 2007 R2 teilnehmen müssen, müssen auf Ihrem Computer (zusätzlich zu lync Server 2013) den Live Meeting-Client installiert haben, um an diesen Besprechungen teilnehmen zu können.

  - Wenn Live Meeting-Konferenzen zu lync Server 2013 migriert werden, werden Besprechungsinhalte nicht migriert. Wenn dieser Inhalt benötigt wird, muss er erneut hochgeladen werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

