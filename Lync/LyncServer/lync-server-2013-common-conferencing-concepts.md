---
title: 'Lync Server 2013: Allgemeine Konferenz Konzepte'
description: 'Lync Server 2013: Allgemeine Konferenz Konzepte.'
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
ms.openlocfilehash: e2eeea52070c65a8a037eb44e75ceb2d937b91a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577011"
---
# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Allgemeine Konferenz Konzepte in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-19_

Es gibt mehrere Konzepte, die für sämtliche Konferenztypen verwendet werden. Diese werden in den folgenden Abschnitten beschrieben.

<div>

## <a name="policies-and-bandwidth-management"></a>Richtlinien und Bandbreitenverwaltung

Lync Server 2013 ermöglicht es Administratoren, Richtlinien für die Besprechungstypen festzulegen, die Benutzer organisieren können. Auf diese Weise können Sie die in Ihrer Organisation geltenden Richtlinien durchsetzen und die Bandbreitennutzung steuern. Sie können eine Vielzahl von Besprechungsrichtlinien definieren und diese einzelnen Benutzern und Benutzergruppen zuweisen. Ferner können Sie Richtlinien festlegen, die Peer-zu-Peer-Unterhaltungen steuern. Ausführliche Informationen zum Festlegen von Konferenzrichtlinien finden Sie unter [Conferencing Policies in lync Server 2013](lync-server-2013-conferencing-policies.md) in der Betriebsdokumentation. Ausführliche Informationen zur Bandbreitenverwaltung finden Sie unter Übersicht über die [Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) und [Konfigurieren der Videobandbreite in lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Funktionen zur Archivierung und Einhaltung von Bestimmungen

Lync Server 2013 bietet Funktionen, die Sie verwenden können, wenn Ihre Organisation den Compliance-Vorschriften folgen muss. Mithilfe der Archivierungsfunktionen können Sie in Besprechungen präsentierte Inhalte sowie die Inhalte von Sofortnachrichtenunterhaltungen und Sofortnachrichtenkonferenzen archivieren. Ausführliche Informationen finden Sie unter [Planning for Archiving in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation. Mit den Funktionen zur Einhaltung von Bestimmungen des dauerhaften Chatservers können Sie themenbasierte Konversationen mit mehreren Teilnehmern archivieren, die im Verlauf erhalten bleiben. Ausführliche Informationen finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

</div>

<div>

## <a name="monitoring-feature"></a>Überwachungsfunktion

Das Monitoring Server-Feature kann Anruf Detaildatensätze (CDRs) erfassen, mit denen Sie nachverfolgen können, welche Benutzer mit welchen anderen Benutzern lync Server 2013 kommunizieren. Ausführliche Informationen zum Bereitstellen und Konfigurieren der Überwachung finden Sie unter [Deploying Monitoring in lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Aktivieren der Konferenzteilnahme durch externe Benutzer

Sie können den Nutzen Ihrer Investition in lync Server 2013 Konferenzen erheblich verbessern, indem Sie externen Benutzern die Möglichkeit bieten, auch an Konferenzen teilzunehmen, wenn Sie eingeladen werden. Externe Benutzer können Folgendes umfassen:

  - **Remote Benutzer**     Die eigenen Benutzer Ihrer Organisation, wenn Sie außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere lync Server 2013 Geräte verwenden.

  - Partner **Verbundbenutzer**     Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten und die auch lync Server 2013 ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.

  - **Anonyme Benutzer**     Alle anderen externen Benutzer, die speziell von Ihren Benutzern eingeladen werden, um an bestimmten Konferenzen teilzunehmen. Der Organisator einer Besprechung in Ihrem Unternehmen kann eine E-Mail-Einladung für eine Konferenz an einen externen Benutzer senden. Diese E-Mail enthält einen Link, über den der externe Benutzer an der Konferenz teilnehmen kann.

Zum Aktivieren eines oder aller dieser Szenarien müssen Sie eine Edgeserver bereitstellen, die die sichere Kommunikation zwischen Ihrer lync Server 2013-Bereitstellung und externen Benutzern unterstützt. Die lync Server 2013 Lösung, die Edgeserver verwendet, bietet Medien höherer Qualität als andere Lösungen wie ein VPN (virtuelles privates Netzwerk). Ausführliche Informationen finden Sie unter [Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Unabhängig davon, ob Sie Edgeserver bereitstellen oder nicht, können Sie für Benutzer (innerhalb oder außerhalb Ihrer Organisationen) zudem die Einwahl über standardmäßige Festnetztelefone zulassen, um an lokalen Audiokonferenzen teilzunehmen. Dies wird durch die Bereitstellung lync Server 2013 Einwahlkonferenzen erreicht.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Kompatibilität zwischen Besprechungstypen und Clientversionen

Wenn Sie lync Server 2013 mit früheren Versionen von Office Communications Server und seinen Clients zusammenarbeiten möchten, müssen Sie sich der folgenden Probleme bewusst sein:

  - Benutzer, die lync Server 2013 verwenden, können Live Meeting Konferenzen nicht planen oder keine migrierten Besprechungen dieses Typs ändern.

  - Benutzer von lync Server 2013, die Live Meeting Konferenzen, die auf Servern mit Office Communications Server 2007 R2 gehostet werden, teilnehmen müssen, müssen über den Live Meeting-Client auf dem Computer installiert sein (zusätzlich zu den lync Server 2013), um an diesen Besprechungen teilnehmen zu können.

  - Wenn Live Meeting Konferenzen zu lync Server 2013 migriert werden, werden Besprechungsinhalte nicht migriert. Wenn diese Inhalte benötigt werden, müssen sie erneut hochgeladen werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

