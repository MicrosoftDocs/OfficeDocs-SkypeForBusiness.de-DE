---
title: 'Lync Server 2013: Anfängliche Planungsentscheidungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd1359e27f6869dab1ead38da3716135a2468ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Anfängliche Planungsentscheidungen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Im ersten Teil des Planungsprozesses entscheiden Sie, welche lync Server-Arbeitsauslastungen und Hauptfeatures für Ihre Organisation Sie benötigen.

1.  **Möchten Sie eine lokale oder Onlinebereitstellung durchführen?**    Lync Server unterstützt beide Bereitstellungsszenarien. Weitere Informationen zum Treffen dieser Entscheidung finden Sie unter [entscheiden, wie lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)weiter oben in diesem Abschnitt bereitgestellt wird.

2.  **Möchten Sie eine physikalische oder virtualisierte Topologie?**    Lync Server unterstützt alle Arbeitslasten und Server Rollen sowohl in physikalischen als auch in virtualisierten Topologien. Benutzerkapazität und Skalierbarkeit können zwischen physikalischen und virtuellen Topologien unterschiedlich sein. Weitere Informationen finden Sie unter [Ausführen von lync Server 2013 auf virtuellen Servern](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  **Instant Messaging *(im)* und *Anwesenheit* sind immer aktiviert.**    Bei jeder lync Server-Bereitstellung sind die Sofortnachrichten (im) und die Anwesenheits Auslastung standardmäßig installiert und aktiviert. IM ermöglicht es Ihren Benutzern, mit Textnachrichten in Echtzeit zu kommunizieren, und die Anwesenheitsanzeige ermöglicht es Ihnen, den Status anderer Benutzer im Netzwerk anzuzeigen. Der Anwesenheitsstatus eines Benutzers bietet Informationen, um anderen zu helfen, zu entscheiden, ob er versuchen soll, den Benutzer zu kontaktieren, und auf welche Weise. Ausführliche Informationen finden Sie unter [Planen von Front-End-Servern, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) in der Planungsdokumentation.

4.  **Möchten Sie beliebige Konferenz Modi bereitstellen?**    Conferencing ist ein weiteres zentrales Feature von lync Server. Verschiedene Konferenz Modi werden unterstützt. Sie können auswählen, ob alle unterstützten Konferenztypen oder nur einige davon bereitgestellt werden sollen. ** Mit Webkonferenzen können Benutzer eine Datei anzeigen, beispielsweise ein mit Microsoft PowerPoint-Präsentationsgrafikprogramm erstelltes Foliendeck, das angezeigt wird. Mit der *Anwendungsfreigabe* können Benutzer ihren gesamten Desktop oder einen Teil davon in Echtzeit freigeben. Mit *A/V-Konferenzen*können Benutzer ihren Konferenzen und Peer-to-Peer-Kommunikationen Audio (und möglicherweise Video) hinzufügen. *Einwahlkonferenzen* ermöglicht Benutzern das Verwenden von standardmäßigen PSTN-Telefonen für die Teilnahme am Audioteil von Konferenzen, die in Ihrer Organisation gehostet werden. Ausführliche Informationen finden Sie unter [Planen von Konferenzen in lync Server 2013](lync-server-2013-planning-for-conferencing.md) in der Planungsdokumentation.
    
    Wenn Sie in lync Server 2013 Webkonferenzen bereitstellen, müssen Sie auch die Integration in Office Web Apps Server planen, um PowerPoint-Freigabe und-Anzeige in Besprechungen zu ermöglichen. Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Wenn Sie eine/V-Konferenz bereitstellen, sollten Sie auch die Audioqualität dieser Konferenzen überwachen.**    Viele Faktoren wirken sich auf die Audio-und Videoqualität von lync Server A/V-Konferenzen aus. Mithilfe der Überwachung können Sie die A/V-Qualität Ihrer Anrufe und Konferenzen überwachen. Sie können Probleme erkennen, die sich auf die Medienqualität auswirken, und sicherstellen, dass Ihre Benutzer das bestmögliche Medienerlebnis haben. Weitere Informationen finden Sie unter [Planen der Überwachung in lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **Möchten Sie eine höhere Verfügbarkeit für Ihre Chat-, Anwesenheits-und Konferenzserver?**    Wenn Sie nur über einen Server an einer Website mit Chat-, Anwesenheits-und Konferenzfeatures verfügen, ist die Produktivität Ihrer Benutzer stark betroffen, wenn der Server ausfällt. Durch die Bereitstellungeines Enterprise Edition- *Pools* von mindestens drei Servern für diese Funktionen ist es möglich, dass lync Server weiterhin mit allen diesen Funktionen intakt funktioniert, auch wenn ein Server nicht verfügbar ist.
    
    Eine weitere Option für Organisationen mit 5000 oder weniger Benutzern, die eine höhere Verfügbarkeit wünschen, besteht darin, zwei Server mit lync Server Standard Edition bereitzustellen und diese Server zusammen zu koppeln. Weitere Informationen finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **Möchten Sie Disaster Recovery-Optionen?**    Wenn Sie über zwei Rechenzentren verfügen und die Notfallwiederherstellungsoptionen verwenden möchten, damit Ihre Benutzer weiterhin arbeiten können, wenn alle oder viele Server in einem Rechenzentrum nach unten gehen, können Sie Ihre Server im Hinblick auf Disaster Recovery bereitstellen. Für diese Bereitstellung koppeln Sie einen Serverpool in einem Rechenzentrum mit einem entsprechenden Pool in einem anderen Rechenzentrum. Wenn ein Rechenzentrum ausfällt, kann der andere Pool des Paars Benutzer in beiden Pools mit minimaler Unterbrechung der Dienste bedienen. Weitere Informationen finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **Möchten Sie Ihre Benutzer für die Kommunikation und Zusammenarbeit mit externen Benutzern aktivieren?**    Durch die Aktivierung von Kommunikation und Zusammenarbeit mit externen Benutzern können Sie Ihre Rentabilität in lync Server erhöhen. Auf diese Weise können die eigenen Benutzer von den lync Server-Features profitieren, auch wenn Sie außerhalb der Firewalls Ihrer Organisation arbeiten. Sie können auch eine Föderation mit Ihren Partner-oder Kundenorganisationen führen, die lync Server ausführen. Auf diese Weise können Ihre Benutzer und Partner im Verbundpartner problemlos Chatnachrichten senden und empfangen, sich gegenseitig zu Besprechungen einladen und die Anwesenheitsinformationen der anderen Personen sehen. Darüber hinaus können Ihre Benutzer mithilfe einer e-Mail-Nachricht bestimmte externe Benutzer zu Konferenzen einladen, die Sie organisieren. Weitere Informationen finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **Möchten Sie Enterprise-VoIP bereitstellen?**     *Enterprise-VoIP* ist die VoIP-Lösung (Voice over IP), die von lync Server bereitgestellt wird. Sie bietet eine attraktive Alternative zu herkömmlicher PBX-basierter Telefonie. Enterprise-VoIP ermöglicht Benutzern, Anrufe von ihren Computern oder VoIP-Telefonen zu tätigen, indem Sie auf einen Kontakt in Outlook oder lync Server klicken. Sie können Anrufe über das IP-Netzwerk von Computer zu Computer, Computer zu Telefon oder per Telefon an den Computer ablegen. Benutzer profitieren davon, dass alle Ihre Kommunikationsoptionen – Sprache, e-Mail, Chat und Konferenz – verfügbar und auf ihren Computern integriert sind. Ausführliche Informationen finden Sie unter [Planen von Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) in der Planungsdokumentation.

10. **Wenn Sie Enterprise-VoIP bereitstellen, sollten Sie auch die Audioqualität dieser Anrufe überwachen.**    Wenn Sie Enterprise-VoIP bereitstellen, empfehlen wir, dass Sie die Audioqualität Ihrer Enterprise-Sprachanrufe mithilfe der Überwachung sicherstellen. Weitere Informationen finden Sie unter [Planen der Überwachung in lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **Müssen Chatinhalte oder Besprechungsinhalte für Compliance-Zwecke archiviert werden?**    Wenn Ihre Organisation Chatinhalte oder Besprechungsinhalte für Compliance-Zwecke archivieren muss, können Sie die Archivierung bereitstellen. Weitere Informationen finden Sie unter [Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **Möchten Sie den beständigen Chat bereitstellen?**    Wenn Sie Ihren Benutzern ermöglichen möchten, Echt Zeit Unterhaltungen zu führen, die im Laufe der Zeit beibehalten werden können, können Sie den beständigen Chat bereitstellen. Weitere Informationen finden Sie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **Haben Sie Microsoft Exchange bereitgestellt?**    Wenn Ihre Organisation Microsoft Exchange Server für Ihre e-Mail-Dienste verwendet, können Sie mehrere Features aktivieren, die den Nutzen von lync Server und Microsoft Exchange Server verbessern. Einige dieser Features, so genannte Exchange Unified Messaging (um), umfassen das Aktivieren von Voicemail-Benachrichtigungen und das Abhören von Voicemail in Outlook oder Outlook Web Access, den Zugriff auf Ihre Microsoft Exchange-Postfächer mithilfe eines Telefons und das Empfangen von Faxen in Ihre Microsoft Exchange-Postfächer Wenn Sie Exchange 2013 bereitgestellt haben, können Sie außerdem die Kontaktspeicher für Benutzer zwischen den beiden Systemen integrieren, Exchange zum Speichern von Kontaktfotos mit höherer Auflösung verwenden und die Archivierung von e-Mails und Sofortnachrichten integrieren. Weitere Informationen finden Sie unter [Planen der Exchange Server-Integration in lync Server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **Verfügen Sie über Niederlassungen in Ihrer Organisation?**    Wenn Ihre Organisation Niederlassungen hat, unterstützt lync Server verschiedene Möglichkeiten, diese zu unterstützen und ihre Widerstandsfähigkeit für Sprach-und andere Features zu gewährleisten. Insbesondere können Sie bei einer Zweigstelle, die keine elastische WAN-Verbindung zu einem Rechenzentrum hat, eine Survivable Branch-Appliance oder einen Überlebenden Branch-Server installieren, um Enterprise-VoIP-Unterstützung zu erhalten, wenn der WAN-Link (Wide Area Network) herunterfällt. Weitere Informationen finden Sie unter [Planen der sprach Sicherheit in der Zweigstelle in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

