---
title: 'Lync Server 2013: Definieren der Anforderungen Ihrer Organisation für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75ed62d577cc6b382509f83e53088973e16b6827
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Definieren der Anforderungen Ihrer Organisation für die Archivierung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Wenn Ihre Organisation Konformitätsrichtlinien beachten muss, können Sie die Archivierung bereitstellen, um die Archivierungsunterstützung für lync Server 2013 Instant Messaging (im) und Konferenzen (Besprechungen) zu ermöglichen. Details zu dem Inhaltstyp, der archiviert werden kann, finden Sie unter [Übersicht über die Archivierung in lync Server 2013](lync-server-2013-overview-of-archiving.md) in der Planungsdokumentation.

Um die Archivierung zu implementieren, müssen Sie zunächst entscheiden, wie die Anforderungen Ihrer Organisation für die Archivierung erfüllt werden. Dazu muss Folgendes festgelegt werden:

  - **Zeitpunkt der Bereitstellung der Archivierung** Sie können die Archivierung im Rahmen ihrer anfänglichen lync Server 2013-Bereitstellung bereitstellen, oder Sie können Sie einer vorhandenen Bereitstellung hinzufügen. Sie stellen die Archivierung mithilfe des Topologie-Generators bereit, um Sie Ihrer Topologie hinzuzufügen und dann die Topologie zu veröffentlichen.

  - **Archivierung der internen oder externen Kommunikation**. Sie können die Archivierung für die interne Kommunikation (die Kommunikation zwischen internen Benutzern) und/oder die externe Kommunikation (Kommunikationen, an denen mindestens ein Benutzer außerhalb Ihres internen Netzwerks beteiligt ist) aktivieren. Diese Optionen können für die gesamte Organisation oder nur für bestimmte Standorte und Pools angegeben werden. Standardmäßig ist keine dieser Optionen aktiviert.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie archivierte Daten mithilfe der Microsoft Exchange-Integration speichern, steuern Ihre Exchange-Einstellungen, ob die lync-Kommunikation archiviert wird. Wenn Ihre Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Einstellungen zwischen lync Server und Exchange synchronisieren. Die Steuerung der Archivierung für die interne oder externe Kommunikation ist nur für die lync-Richtlinie verfügbar. Für die Exchange-integrierte Archivierung werden beide archiviert oder nicht archiviert.

    
    </div>

  - **Gründe**für das Aktivieren der Archivierung Sie können die Archivierung für die gesamte Bereitstellung auf globaler Ebene aktivieren und deaktivieren, und Sie können die Archivierung für bestimmte Websites und Benutzer aktivieren und deaktivieren. Auf jeder dieser Ebenen geben Sie an, ob die Archivierung von Chatsitzungen (Peer-to-Peer), Konferenzen (Besprechungen, die mehr Parteien Sitzungen sind) oder beides aktiviert werden soll. Standardmäßig ist die Archivierung deaktiviert.

  - **Die kritische Archivierung für Benutzer in Ihrer Organisation**. Wenn die Archivierung in Ihrer Organisation unternehmenskritisch ist, können Sie angeben, dass lync Server 2013 im kritischen Modus ausgeführt wird, wodurch Chats und Konferenzsitzungen blockiert werden, wenn die Archivierung fehlschlägt. Beispiel:
    
      - Wenn der Archivierungsdienst vorübergehend keine Nachricht an die Datenbankwarteschlange senden oder eine Nachricht in die Datenbank einfügen kann, werden die Chat-und Konferenzfunktionen in der Bereitstellung blockiert, bis die Archivierungsunterstützung wiederhergestellt wird.
    
      - Wenn ein Konferenzbenutzer eine Datei hochlädt, die Datei jedoch nicht in den Archivierungsdatei Speicher kopiert werden kann, ist die Konferenzfunktionalität in der Bereitstellung blockiert, bis das Problem behoben ist, die Chatfunktionalität aber nicht blockiert ist.
    
    Sie können diese Option auf globaler Ebene, Websiteebene und Poolebene konfigurieren. Der kritische Modus ist standardmäßig nicht aktiviert.

  - **Ob Sie die Microsoft Exchange-Integration verwenden möchten**. Mit dieser Option wird der Archivierungsspeicher in Ihren Exchange 2013-Speicher integriert, sodass die archivierten Daten und Exchange 2013-Daten von lync Server in Exchange zusammen gespeichert werden. Sie können die Microsoft Exchange-Integration für die Speicherung von Archivierungsdaten für Benutzer verwenden, die sich in Exchange 2013 befinden, wenn ihre Postfächer in-situ-Speicher abgelegt wurden. Wenn Sie keine Exchange 2013-Bereitstellung haben, oder wenn Sie es vorziehen, sich nicht in die Integration zu integrieren, oder wenn Sie über lync-Benutzer verfügen, die nicht in Exchange 2013 gespeichert sind, können Sie separate Archivierungsdatenbanken mithilfe von SQL Server zum Speichern archivierter Daten aus lync Communications bereitstellen. Sie können die Microsoft Exchange-Integrations Option auf globaler Ebene, Websiteebene und Poolebene konfigurieren. Standardmäßig ist die Microsoft Exchange-Integration nicht aktiviert.

  - **Wie archivierte Daten verwaltet werden sollen**. Die Archivierungsdatenbank ist nicht für die langfristige Aufbewahrung vorgesehen, und lync Server 2013 bietet keine e-Discovery-Lösung (Suche) für archivierte Daten, sodass Daten in andere Speicher verschoben werden müssen. Lync Server bietet ein Sitzungs Export Tool, mit dem Sie archivierte Daten exportieren und durchsuchbare Abschriften der archivierten Daten erstellen können. Für die globale Richtlinie und für jede von Ihnen erstellte Website-und Benutzerrichtlinie können Sie die Datenbereinigung aktivieren und eine der folgenden Optionen angeben:
    
      - Bereinigen Sie die exportierten Archivierungsdaten und die gespeicherten Archivierungsdaten nach einer bestimmten Anzahl von Tagen. Die Mindestanzahl von Tagen, die Sie angeben können, ist ein Tag. Die maximale Anzahl von Tagen, die Sie angeben können, ist 2562 Tage.
    
      - Nur exportierte Archivierungsdaten löschen. Mit dieser Option werden alle Datensätze, die exportiert und als sicher markiert wurden, vom Sitzungs Export Tool gelöscht.
    
    Sie können diese Option auf globaler Ebene, Websiteebene und Poolebene konfigurieren. Standardmäßig ist "bereinigen" nicht aktiviert.

Sie können die Archivierung mithilfe der folgenden Methoden steuern:

  - **Archivierungsrichtlinien**. Sie verwenden eine oder mehrere Archivierungsrichtlinien, um die Archivierung interner und externer Kommunikation zu aktivieren und zu deaktivieren. Standardmäßig ist keine Archivierung aktiviert. Sie können die Archivierung für die interne Kommunikation, die externe Kommunikation oder beides in Ihrer Bereitstellung mithilfe der globalen Standardrichtlinie aktivieren oder deaktivieren. Sie können die globale Richtlinie nicht löschen. Sie können eine oder mehrere optionale Website Richtlinien angeben, um die Archivierung für die interne und externe Kommunikation für bestimmte Websites zu aktivieren oder zu deaktivieren. Sie können auch eine oder mehrere Benutzerrichtlinien angeben, um die Archivierung für bestimmte Benutzer und Benutzergruppen zu aktivieren oder zu deaktivieren. Richtlinien auf Benutzerebene überschreiben Website Richtlinien. Richtlinien auf Websiteebene setzen die Richtlinien auf globaler Ebene außer Kraft. Richtlinien auf Benutzerebene werden nur für bestimmte Benutzer implementiert, die für die Verwendung der Richtlinie konfiguriert sind. Gruppen-Sofortnachrichten und-Konferenzen werden nur archiviert, wenn eine Richtlinie für mindestens einen Teilnehmer so konfiguriert ist, dass die Archivierung aktiviert wird.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Microsoft Exchange-Integration verwenden, überschreiben Exchange 2013-Richtlinien lync Server-Archivierungsrichtlinien für alle Benutzer, die auf den Exchange 2013-Servern verwaltet werden.

    
    </div>

  - **Archivierungs Konfigurationen** Sie verwenden eine oder mehrere Archivierungs Konfigurationen, um die meisten der zuvor in diesem Thema beschriebenen Archivierungsoptionen anzugeben, mit Ausnahme der Aktivierung der Archivierung interner und externer Kommunikation (Konfiguration mithilfe von Archivierungsrichtlinien, wie im Abschnitt Vorheriges Aufzählungszeichen). Zu den Archivierungs Konfigurationen gehören die standardmäßige globale Konfiguration sowie optionale Website-und Poolkonfigurationen. Sie können die globale Konfiguration nicht löschen. Konfigurationen auf Poolebene überschreiben Konfigurationen auf Websiteebene. Konfigurationen auf Websiteebene überschreiben die Konfiguration auf globaler Ebene.

Im Rahmen Ihrer Anforderungsanalyse müssen Sie festlegen, wie die globale Archivierungskonfiguration und die globale Archivierungsrichtlinie konfiguriert werden. Darüber hinaus müssen Sie Ihre Anforderungen für alle Archivierungs Konfigurationen auf Websiteebene, Archivierungs Konfigurationen auf Poolebene, Archivierungsrichtlinien auf Websiteebene und Archivierungsrichtlinien auf Benutzerebene ermitteln.

Wenn Sie die Archivierung für einen Front-End-Pool oder Standard Edition-Server bereitstellen, sollten Sie Sie für alle anderen Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung aktivieren. Sie müssen dies tun, da Benutzer, deren Kommunikation archiviert werden muss, zu einer Gruppenunterhaltung oder Besprechungen eingeladen werden können, die in einem anderen Pool gehostet werden. Wenn die Archivierung in dem Pool, in dem die Unterhaltung oder Besprechung gehostet wird, nicht aktiviert ist, werden möglicherweise nicht alle Konferenzdaten archiviert. Die Archivierung funktioniert weiterhin für die Archivierung aktivierter Benutzer und alle Chatnachrichten, aber Konferenzinhalte und-Ereignisse werden möglicherweise nicht archiviert.

<div>


> [!NOTE]  
> Um die Delegierung von administrativen Aufgaben unter Beibehaltung der Sicherheitsstandards Ihrer Organisation zu aktivieren,&nbsp;verwendet lync Server 2013 die rollenbasierte Zugriffssteuerung. Bei der rollenbasierten Zugriffssteuerung werden Administratorrechte zugewiesen, indem Benutzer vordefinierten Administrationsrollen hinzugefügt werden. Zum Konfigurieren von lync-Archivierungsrichtlinien und Archivierungs Konfigurationen muss der Benutzer der CsArchivingAdministrator-Rolle zugewiesen werden (es sei denn, die Konfiguration erfolgt direkt auf dem Server, auf dem die Archivierung statt Remote von einem anderen Computer bereitgestellt wird). Details zu RBAC finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation. Eine Liste der Benutzerrechte, Berechtigungen und Rollen, die für die Archivierungs Bereitstellung erforderlich sind, finden Sie unter <A href="lync-server-2013-deployment-checklist-for-archiving.md">Bereitstellungscheckliste für die Archivierung in lync Server 2013</A>, die sowohl in der Planungsdokumentation als auch in der Bereitstellungsdokumentation zur Verfügung steht.<BR>Wenn Sie die Microsoft Exchange-Integration verwenden, erfordert die Konfiguration von Exchange-Richtlinien geeignete Administratorrechte und-Berechtigungen. Ausführliche Informationen finden Sie in der Exchange 2013-Dokumentation.



</div>

</div>

<span> </span>

</div>

</div>

</div>

