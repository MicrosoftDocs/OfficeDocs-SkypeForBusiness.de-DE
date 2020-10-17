---
title: Lync Server 2013 anfängliche Planungsentscheidungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fdc9b9e2494078a8db4b524e9ffb6b2794c545d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512572"
---
# <a name="initial-planning-decisions-for-lync-server-2013"></a>Anfängliche Planungsentscheidungen für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Der erste Teil des Planungsprozesses entscheidet, welche lync Server Arbeitslasten und Hauptfunktionen für Ihre Organisation gewünscht werden.

1.  **Möchten Sie eine lokale oder Online-Bereitstellung?**     Lync Server unterstützt beide Bereitstellungsszenarien. Weitere Informationen zur Entscheidungsfindung finden Sie weiter oben in diesem Abschnitt unter [entscheiden, wie Sie lync Server 2013 bereitstellen](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md).

2.  **Möchten Sie eine physische oder virtualisierte Topologie?**     Lync Server unterstützt alle Arbeitsauslastungen und Server Rollen sowohl in physischen als auch in virtualisierten Topologien. Benutzerkapazität und Skalierbarkeit können zwischen physikalischen und virtuellen Topologien unterschiedlich sein. Weitere Informationen finden Sie unter [Running lync Server 2013 on Virtual Servers](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  **Instant Messaging *(* Sofortnachrichten) und *Anwesenheit* sind immer aktiviert.**     In jeder lync Server-Bereitstellung ist die Sofortnachrichten-und Anwesenheits Arbeitsauslastung standardmäßig installiert und aktiviert. Im ermöglicht es Ihren Benutzern, mit Echtzeitnachrichten zu kommunizieren, und durch Anwesenheit können Sie den Status anderer Benutzer im Netzwerk anzeigen. Der Anwesenheitsstatus eines Benutzers enthält Informationen, um anderen zu helfen, zu entscheiden, ob Sie versuchen sollen, den Benutzer zu kontaktieren, und mit welchen Mitteln. Ausführliche Informationen finden Sie unter [Planung für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) in der Planungsdokumentation.

4.  **Möchten Sie alle Modi für Konferenzen bereitstellen?**     Konferenzen sind ein weiteres Hauptfeature von lync Server. Es werden verschiedene Modi für Konferenzen unterstützt. Sie können auswählen, ob alle unterstützten Konferenztypen oder nur einige von Ihnen bereitgestellt werden sollen. Mithilfe von *Webkonferenzen* können Benutzer eine Datei anzeigen, beispielsweise ein mit Microsoft PowerPoint Präsentationsgrafikprogramm erstelltes Foliendeck, das angezeigt wird. Mit der *Anwendungsfreigabe* können Benutzer Ihren Desktop ganz oder teilweise in Echtzeit freigeben. Mit *A/V-Konferenzen*können Benutzer ihren Konferenzen und Peer-to-Peer-Kommunikationen Audio-(und möglicherweise Video) hinzufügen. *Einwahlkonferenzen* ermöglichen Benutzern die Verwendung von Standard-PSTN-Telefonen, um an dem Audioteil von Konferenzen teilzunehmen, die in Ihrer Organisation gehostet werden. Ausführliche Informationen finden Sie unter [Planning for Conferencing in lync Server 2013](lync-server-2013-planning-for-conferencing.md) in der Planungsdokumentation.
    
    In lync Server 2013 müssen Sie bei der Bereitstellung von Webkonferenzen auch die Integration mit Office-webapps Server planen, um die Freigabe von PowerPoint und die Anzeige in Besprechungen zu ermöglichen. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Wenn Sie A/V-Konferenzen bereitstellen, sollten Sie auch die Audioqualität dieser Konferenzen überwachen.**     Viele Faktoren beeinflussen die Audio-und Videoqualität von lync Server A/V-Konferenzen. Mithilfe der Überwachung können Sie die A/V-Qualität Ihrer Anrufe und Konferenzen überwachen. Sie können Probleme erkennen, die sich auf die Medienqualität auswirken, und sicherstellen, dass Ihre Benutzer die bestmögliche Medienerfahrung haben. Weitere Informationen finden Sie unter [Planning for Monitoring in lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **Möchten Sie hohe Verfügbarkeit für Chat-, Anwesenheits-und Konferenzserver?**     Wenn Sie nur über einen Server an einem Standort verfügen, der Sofortnachrichten-, Anwesenheits-und Konferenzfunktionen bereitstellt, ist die Produktivität Ihrer Benutzer stark betroffen, wenn dieser Server ausfällt. Wenn Sie einen Enterprise Edition- *Pool* mit mindestens drei Servern für diese Funktionen bereitstellen, können Sie lync Server mit all diesen Funktionen auch dann intakt arbeiten, wenn ein Server nicht verfügbar ist.
    
    Eine weitere Option für Organisationen mit 5000 oder weniger Benutzern, die hohe Verfügbarkeit wünschen, ist die Bereitstellung von zwei Servern, auf denen lync Server Standard Edition läuft, und die Kombination dieser Server. Weitere Informationen finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **Möchten Sie Notfallwiederherstellungsoptionen?**     Wenn Sie über zwei Rechenzentren verfügen und Notfallwiederherstellungsoptionen für die Benutzer in die Lage versetzen sollen, weiterhin zu arbeiten, wenn alle oder mehrere Server in einem Datencenter ausfallen, können Sie Ihre Server mit Notfallwiederherstellung im Hinterkopf bereitstellen. Für diese Bereitstellung koppeln Sie einen Serverpool in einem Datencenter mit einem entsprechenden Pool in einem anderen Datencenter. Wenn ein Datencenter ausfällt, kann der andere Pool im Paar die Benutzer in beiden Pools mit minimaler Unterbrechung der Dienste bedienen. Weitere Informationen finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **Möchten Sie, dass Ihre Benutzer mit externen Benutzern kommunizieren und zusammenarbeiten können?**     Durch die Aktivierung der Kommunikation und Zusammenarbeit mit externen Benutzern können Sie Ihren Return-on-Investment in lync Server verbessern. Dadurch können die eigenen Benutzer in Ihrer Organisation von lync Server Funktionen profitieren, auch wenn Sie außerhalb der Firewalls Ihrer Organisation arbeiten. Sie können auch mit Ihren Partner-oder Kundenorganisationen, die lync Server ausführen, einen Partnerverbund erstellen. Auf diese Weise können Benutzer und Partner von Verbundbenutzern ganz einfach Chatnachrichten senden und empfangen, sich gegenseitig zu Besprechungen einladen und die Anwesenheitsinformationen des jeweils anderen Benutzers anzeigen. Darüber hinaus können Ihre Benutzer eine e-Mail-Nachricht verwenden, um bestimmte externe Benutzer zu Konferenzen einzuladen, die Sie organisieren. Weitere Informationen finden Sie unter [Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **Möchten Sie Enterprise-VoIP bereitstellen?**     *Enterprise* -VoIP ist die VoIP-Lösung (Voice over IP), die von lync Server bereitgestellt wird. Sie bietet eine attraktive Alternative zu herkömmlicher PBX-basierter Telefonie. Enterprise-VoIP ermöglicht Benutzern das Platzieren von Anrufen von ihren Computern oder VoIP-Telefonen, indem Sie in Outlook oder lync Server auf einen Kontakt klicken. Sie können Anrufe über das IP-Netzwerk von Computer zu Computer, Computer zu Telefon oder Telefon an Computer abgeben. Benutzer profitieren davon, dass alle Ihre Kommunikationsoptionen-Voice, e-Mail, Chat und Konferenzen-verfügbar und auf ihren Computern integriert sind. Ausführliche Informationen finden Sie unter [Planning for Enterprise Voice in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) in der Planungsdokumentation.

10. **Wenn Sie Enterprise-VoIP bereitstellen, sollten Sie auch die Audioqualität dieser Anrufe überwachen.**     Wenn Sie Enterprise-VoIP bereitstellen, sollten Sie die Überwachung verwenden, um die Audioqualität Ihrer Enterprise-VoIP-Anrufe sicherzustellen. Weitere Informationen finden Sie unter [Planning for Monitoring in lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **Müssen Sie Chatinhalte oder Besprechungsinhalte für Compliance-Zwecke archivieren?**     Wenn Ihre Organisation Chatinhalte oder Besprechungsinhalte zu Kompatibilitätszwecken archivieren muss, können Sie die Archivierung bereitstellen. Weitere Informationen finden Sie unter [Planning for Archiving in lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **Möchten Sie den beständigen Chat bereitstellen?**     Wenn Sie möchten, dass Ihre Benutzer Echt Zeit Unterhaltungen haben, die sich im Laufe der Zeit fortsetzen können, können Sie den beständigen Chat bereitstellen. Weitere Informationen finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **Sind Microsoft Exchange bereitgestellt?**     Wenn Ihre Organisation Exchange Server für die e-Mail-Dienste verwendet, können Sie mehrere Features aktivieren, die die Nützlichkeit von lync Server und Exchange Server verbessern. Einige dieser Features, die Exchange Unified Messaging (um) genannt werden, ermöglichen Benutzern das Empfangen von Voicemail-Benachrichtigungen und das Abhören von Voicemail über Outlook oder Outlook Web Access, den Zugriff auf Ihre Microsoft Exchange-Postfächerüber ein Telefon und das Empfangen von Faxnachrichten in Ihren Microsoft Exchange Postfächern. Wenn Sie Exchange 2013 bereitgestellt haben, können Sie außerdem die Kontaktspeicher für Benutzer zwischen den beiden Systemen integrieren, Exchange zum Speichern von Kontaktfotos mit höherer Auflösung verwenden und die Archivierung von e-Mails und Sofortnachrichten integrieren. Weitere Informationen finden Sie unter [Planning for Exchange Server Integration in lync Server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **Verfügen Sie über Zweigstellen in Ihrer Organisation?**     Wenn Ihre Organisation über Zweigstellen verfügt, unterstützt lync Server eine Vielzahl von Möglichkeiten, diese zu unterstützen und die Ausfallsicherheit für VoIP-und andere Features sicherzustellen. Insbesondere bei einer Zweigstelle, die nicht über eine belastbare WAN-Verbindung mit einem Rechenzentrum verfügt, können Sie eine Survivable Branch Appliance oder Survivable Branch Server installieren, um Enterprise-VoIP-Unterstützung beizubehalten, wenn der WAN-Link (Wide Area Network) ausfällt. Weitere Informationen finden Sie unter [Planning for Branch-Site Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

