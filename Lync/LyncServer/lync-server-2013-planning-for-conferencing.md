---
title: 'Lync Server 2013: Planen von Konferenzen'
TOCTitle: Planen von Konferenzen
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398781(v=OCS.15)
ms:contentKeyID: 49294839
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen von Konferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-01-29_

Lync Server 2013 bietet einen umfassenden Satz an Konferenzfunktionen:

  - Webkonferenzen, zu denen Dokumentzusammenarbeit, Anwendungs- und Desktopfreigabe gehören. Lync Server 2013 nutzt Office Web Apps und Office Web Apps-Server, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu handhaben. Detaillierte Informationen zur Installation und Konfiguration des Office Web Apps-Servers finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Audio/Video-Konferenzfunktion (A/V), mit der Benutzer Audio- oder Videokonferenzen in Echtzeit durchführen können, ohne externe Dienste wie den Microsoft Live Meeting-Dienst oder die Audiobrücke eines Drittanbieters verwenden zu müssen.

  - Einwahlkonferenzfunktion, die Benutzern die Teilnahme am Audioteil einer Lync Server 2013-Konferenz über ihr Festnetztelefon ermöglicht, sodass kein Audiokonferenzanbieter erforderlich ist.

  - Instant Messaging-Konferenzfunktion, bei der mehr als zwei Parteien in einer einzigen Sofortnachrichtensitzung miteinander kommunizieren. Ausführliche Informationen zu Instant Messaging-Konferenzen finden Sie unter [Planen für Front-End-Server, Chat und Anwesenheit in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

Lync Server 2013 unterstützt sowohl geplante als auch spontane Konferenzen.

Bei der Bereitstellung eines Lync Server 2013- Front-End-Servers können Sie wählen, ob Sie auch die Webkonferenzfunktion, die A/V-Konferenzfunktion und die Einwahlkonferenzfunktion bereitstellen. Die Instant Messaging-Konferenzfunktionen werden immer automatisch zusammen mit den Sofortnachrichten-Unterhaltungsfunktionen auf dem Lync Server 2013- Front-End-Server bereitgestellt.


> [!NOTE]
> Wenn Ihre Bereitstellung Besprechungen umfasst, die mithilfe von Office Communicator 2007 R2-Clients (einschließlich der Live Meeting-Konsole oder dem Konferenz-Add-In für Microsoft Office Outlook) organisiert wurden, bestehen für die Besprechungen nach der Migration zu Lync Server 2013 folgende Einschränkungen: 
> <UL>
> <LI>
> <P>Benutzer in der Besprechung können keine Datenzusammenarbeitsfunktionen (darunter Dokumentzusammenarbeit, Anwendungs- und Desktopfreigabe) nutzen.</P>
> <LI>
> <P>Möglicherweise treten Stabilitätsprobleme auf, da Office Communicator 2007 R2-Clients von Lync Server 2013 nicht unterstützt werden.</P></LI></UL>Um diese Probleme zu vermeiden, planen Sie alle Besprechungen neu, die mithilfe von Office Communicator 2007 R2-Clients mit Outlook 2010 oder Outlook 2013 organisiert wurden. Verwenden Sie dazu entweder das Onlinebesprechungs-Add-In für Lync&nbsp;2010 oder das Onlinebesprechungs-Add-In für Lync&nbsp;2013.



In den folgenden Abschnitten werden die Anforderungen für die Bereitstellung der verschiedenen Typen von Konferenzfunktionen beschrieben, einschließlich des Planungsprozesses, der Komponenten, der Hardware- und Softwareanforderungen und des Bereitstellungsprozesses.

## In diesem Abschnitt

  - [Übersicht über Konferenzen in Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Definieren der Anforderungen für Konferenzen in Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Komponenten und Topologien für Konferenzen in Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Technische Anforderungen für Konferenzen in Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Prüfliste zur Bereitstellung für Konferenzen in Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Unterstützung für große Besprechungen in Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

