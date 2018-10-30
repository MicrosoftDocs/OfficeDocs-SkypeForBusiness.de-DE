---
title: 'Lync Server 2013: Definieren der Anforderungen für Front-End-Server, Chat und Anwesenheit'
TOCTitle: Definieren der Anforderungen für Front-End-Server, Chat und Anwesenheit
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412956(v=OCS.15)
ms:contentKeyID: 49295303
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Anforderungen für Front-End-Server, Chat und Anwesenheit in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die Hauptaufgabe beim Planen von Chat- und Anwesenheitsfunktionen ist sicherzustellen, dass ausreichend Front-End-Server für Ihre Benutzer verfügbar sind.

## Aktivieren der Kommunikation mit externen Benutzern

Um zusätzlich von Ihrer Investition in Lync Server zu profitieren, können Sie Ihre Benutzer für die Kommunikation mit externen Benutzern aktivieren. Bei externen Benutzern handelt es sich u. a. um folgende Benutzertypen:

  - **Remotebenutzer**   Benutzer Ihrer Organisation, die außerhalb der Organisationsfirewalls arbeiten und Laptops oder andere Lync Server-Geräte verwenden.

  - **Partnerbenutzer**   Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten und die Lync Server ebenfalls ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.

  - **Öffentliche Benutzer**   Benutzer öffentlicher Instant Messaging-Dienste (z. B. die von Windows Live, Yahoo\! und AOL bereitgestellten Chatdienste) sowie Benutzer von Anbietern und Servern, die XMPP (Extensible Messaging and Presence Protocol) verwenden (z. B. Google Talk).
    

    > [!NOTE]
    > Beachten Sie, dass für Verbindungen mit öffentlichen Instant Messaging-Diensten wie Windows Live, AOL und Yahoo! möglicherweise eine separate Lizenz erforderlich ist.

    

    > [!IMPORTANT]
    > <UL>
    > <LI>
    > <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
    > <LI>
    > <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
    > <LI>
    > <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



Zum Aktivieren eines oder aller dieser Szenarien müssen Sie einen Edgeserver für die sichere Kommunikation zwischen Ihrer Lync Server-Bereitstellung und externen Benutzern bereitstellen. Remotebenutzer Ihrer Organisation und Benutzer in Partnerorganisationen können ihre Anwesenheitsinformationen ansehen und über Instant Messaging miteinander kommunizieren. Weitere Informationen zum Aktivieren der Kommunikation mit externen Benutzern finden Sie unter [Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation.

## Archivieren von Chatinhalten

Lync Server bietet Features, die Sie bei der Einhaltung rechtlicher Vorschriften unterstützen. Mithilfe der Archivierung können Sie Chatinhalte für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer archivieren. Ausführliche Informationen finden Sie unter [Planen der Archivierung in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.

Wenn Sie auch Microsoft Exchange Server 2013 bereitgestellt haben, können Sie die Archivierung von Exchange-Daten in die Archivierung von Lync Server-Daten integrieren und mithilfe eines einzigen Tools beide archivierten Datentypen durchsuchen. Weitere Informationen finden Sie unter [Konfigurieren von Microsoft Lync Server 2013 für die Verwendung der Microsoft Exchange Server 2013-Archivierung](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

