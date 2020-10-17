---
title: 'Lync Server 2013: Definieren der Anforderungen für die Archivierung'
description: 'Lync Server 2013: Definieren der Anforderungen für die Archivierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b9f3257c56241ce921a18e16932689053ef430
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545531"
---
# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Definieren der Anforderungen für die Archivierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Wenn Ihre Organisation Compliance-Vorschriften einhalten muss, können Sie die Archivierung bereitstellen, um die Archivierungsunterstützung für lync Server 2013 Instant Messaging (Chat) und Konferenzen (Besprechungen) zu ermöglichen. Ausführliche Informationen zum Inhaltstyp, der archiviert werden kann, finden Sie unter [Overview of Archiving in lync Server 2013](lync-server-2013-overview-of-archiving.md) in der Planungsdokumentation.

Zum Implementieren der Archivierung müssen Sie zunächst bestimmen, wie die Archivierungsanforderungen Ihrer Organisation erfüllt werden sollen. Hierfür müssen Sie Folgendes festlegen:

  - **Wann die Archivierung bereitgestellt werden soll**. Sie können die Archivierung im Rahmen ihrer anfänglichen lync Server 2013-Bereitstellung bereitstellen oder Sie einer vorhandenen Bereitstellung hinzufügen. Sie stellen die Archivierung bereit, indem Sie den Topologie-Generator verwenden, um Sie Ihrer Topologie hinzuzufügen und die Topologie dann zu veröffentlichen.

  - **Ob die interne oder externe Kommunikation archiviert werden soll**. Sie können die Archivierung für die interne Kommunikation (die Kommunikation zwischen internen Benutzern) und/oder die externe Kommunikation (die Kommunikation, bei der mindestens ein Benutzer außerhalb Ihres internen Netzwerks beteiligt ist) aktivieren. Diese Optionen können für die gesamte Organisation oder nur für bestimmte Standorte und Pools angegeben werden. Standardmäßig ist keine dieser Optionen aktiviert.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Microsoft Exchange Integration zum Speichern archivierter Daten verwenden, steuern Ihre Exchange-Einstellungen, ob die lync-Kommunikation archiviert wird. Wenn Ihre Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Einstellungen zwischen lync Server und Exchange synchronisieren. Die Steuerung der Archivierung für die interne oder externe Kommunikation steht nur für die lync-Richtlinie zur Verfügung. Für die Exchange-integrierte Archivierung werden beide archiviert oder nicht archiviert.

    
    </div>

  - **Warum die Archivierung aktiviert werden soll**. Sie können die Archivierung für die gesamte Bereitstellung auf globaler Ebene aktivieren bzw. deaktivieren. Die Archivierung können Sie auch für bestimmte Standorte und Benutzer aktivieren bzw. deaktivieren. Für jede Ebene geben Sie an, ob die Archivierung von Chatsitzungen (Peer-zu-Peer) und/oder Konferenzen (Besprechungen, die Sitzungen mit mehreren Teilnehmern sind) aktiviert werden soll. Standardmäßig ist die Archivierung deaktiviert.

  - Die **kritische Archivierung für Benutzer in Ihrer Organisation**. Wenn die Archivierung geschäftskritisch in Ihrer Organisation ist, können Sie angeben, dass lync Server 2013 im kritischen Modus ausgeführt werden, wodurch Sofortnachrichten-und Konferenzsitzungen blockiert werden, wenn die Archivierung fehlschlägt. Beispiel:
    
      - Wenn der Archivierungsdienst vorübergehend keine Nachrichten an die Datenbankwarteschlange senden oder keine Nachrichten in die Datenbank einfügen kann, wird sowohl die IM- als auch die Konferenzfunktionalität in der Bereitstellung blockiert, bis die Archivierungsunterstützung wiederhergestellt ist.
    
      - Wenn ein Konferenzbenutzer eine Datei hochlädt, die nicht in den Archivierungsdateispeicher kopiert werden kann, wird die Konferenzfunktionalität in der Bereitstellung blockiert, bis das Problem behoben ist. Die Chatfunktionalität wird jedoch nicht blockiert.
    
    Diese Option können Sie auf globaler Ebene, Standortebene und Poolebene konfigurieren. Standardmäßig ist der kritische Modus nicht aktiviert.

  - Gibt **an, ob Microsoft Exchange Integration verwendet werden soll**. Mit dieser Option wird der Archivierungsspeicher in Ihren Exchange 2013 Speicher integriert, sodass Ihre lync Server archivierten Daten und Exchange 2013 archivierten Daten in Exchange zusammen gespeichert werden. Sie können Microsoft Exchange Integration zum Speichern von Archivierungsdaten für Benutzer verwenden, die in Exchange 2013 verwaltet werden, wenn ihre Postfächer in In-Place Aufbewahrungsspeicher gesetzt wurden. Wenn Sie nicht über eine Exchange 2013-Bereitstellung verfügen oder keine Integration in das Programm wünschen oder wenn Sie lync-Benutzer haben, die nicht in Exchange 2013 verwaltet werden, können Sie separate Archivierungsdatenbanken bereitstellen, indem Sie mithilfe von SQL Server archivierte Daten aus lync Communications speichern. Sie können die Option Microsoft Exchange Integration auf globaler Ebene, auf Standortebene und auf Poolebene konfigurieren. Microsoft Exchange Integration ist standardmäßig nicht aktiviert.

  - **Wie archivierte Daten verwaltet werden sollen**. Die Archivierungsdatenbank ist nicht für die langfristige Aufbewahrung vorgesehen, und lync Server 2013 stellt keine e-Discovery-Lösung (Search) für archivierte Daten bereit, sodass Daten in andere Speicher verschoben werden müssen. Lync Server stellt ein Sitzungs Export Tool bereit, mit dem Sie archivierte Daten exportieren und durchsuchbare Transkripte der archivierten Daten erstellen können. Für die globale Richtlinie sowie für jede von Ihnen erstellte Standort- und Benutzerrichtlinie können Sie das Bereinigen von Daten aktivieren und eine der folgenden Optionen angeben:
    
      - Sowohl exportierte Archivierungsdaten als auch gespeicherte Archivierungsdaten nach einer bestimmten Anzahl von Tagen löschen. Die Mindestanzahl von Tagen beträgt 1 Tag. Die Höchstzahl von Tagen beträgt 2562 Tage.
    
      - Nur exportierte Archivierungsdaten löschen. Mit dieser Option werden alle Datensätze gelöscht, die exportiert und für das Löschen durch das Exporttool für Sitzungen markiert wurden.
    
    Diese Option können Sie auf globaler Ebene, Standortebene und Poolebene konfigurieren. Standardmäßig ist das Bereinigen nicht aktiviert.

Die Archivierung können Sie mithilfe der folgenden Methoden steuern:

  - **Archivierungsrichtlinien**. Sie verwenden eine oder mehrere Archivierungsrichtlinien zum Aktivieren und Deaktivieren der Archivierung interner und externer Kommunikation. Standardmäßig ist keine Archivierung aktiviert. Die Archivierung für interne Kommunikation und/oder externer Kommunikation in Ihrer Bereitstellung aktivieren oder deaktivieren Sie mithilfe der standardmäßigen globalen Richtlinie. Die globale Richtlinie kann nicht gelöscht werden. Sie können eine oder mehrere optionale Standortrichtlinien zum Aktivieren oder Deaktivieren der Archivierung für die interne und externe Kommunikation für bestimmte Standorte angeben. Darüber hinaus können Sie eine oder mehrere Benutzerrichtlinien zum Aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer und Benutzergruppen angeben. Benutzerrichtlinien haben Vorrang vor Standortrichtlinien. Standortrichtlinien haben Vorrang vor den globalen Richtlinien. Benutzerrichtlinien werden nur für die Benutzer implementiert, für die die Verwendung der Richtlinien konfiguriert ist. Gruppenchats und ‑konferenzen werden nur archiviert, falls für mindestens einen Teilnehmer eine Richtlinie zur Aktivierung der Archivierung vorhanden ist.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie Microsoft Exchange Integration verwenden, überschreiben Exchange 2013-Richtlinien lync Server Archivierungsrichtlinien für alle Benutzer, die auf den Exchange 2013 Servern verwaltet werden.

    
    </div>

  - **Archivierungskonfigurationen**. Sie verwenden eine oder mehrere Archivierungskonfigurationen, um die meisten Archivierungsoptionen anzugeben, die zuvor in diesem Thema beschrieben wurden. Eine Ausnahme stellt die Aktivierung der Archivierung für die interne und externe Kommunikation dar (wird wie im vorherigen Punkt beschrieben mithilfe von Archivierungsrichtlinien konfiguriert). Zu den Archivierungskonfigurationen zählen die standardmäßige globale Konfiguration und optionale Standort- und Poolkonfigurationen. Die globale Konfiguration kann nicht gelöscht werden. Poolkonfigurationen haben Vorrang vor Standortkonfigurationen. Standortkonfigurationen haben Vorrang vor der globalen Konfiguration.

Im Rahmen der Anforderungsanalyse müssen Sie bestimmen, wie die globale Archivierungskonfiguration und die globale Archivierungsrichtlinie konfiguriert werden sollen. Darüber hinaus müssen Sie Ihre Anforderungen für Archivierungskonfigurationen auf Standortebene, für Archivierungskonfigurationen auf Poolebene, für Archivierungsrichtlinien auf Standortebene und für Archivierungsrichtlinien auf Benutzerebene festlegen.

Wenn Sie die Archivierung für einen Front-End-Pool oder einen Standard Edition-Server aktivieren, sollten Sie sie für alle weiteren Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung ebenfalls aktivieren. Dies ist erforderlich, weil Benutzer, deren Kommunikation archiviert werden muss, zu Gruppenchatunterhaltungen oder Besprechungen eingeladen werden können, die in einem anderen Pool gehostet werden. Wenn im Pool, der die Unterhaltung oder Besprechung hostet, die Archivierung nicht aktiviert wurde, werden möglicherweise nicht alle Konferenzdaten archiviert. Die Archivierung funktioniert zwar für aktivierte Benutzer und alle Chatnachrichten, aber Konferenzinhalte und Ereignisse werden möglicherweise nicht archiviert.

<div>


> [!NOTE]  
> Um die Delegierung von administrativen Aufgaben unter Beibehaltung der Sicherheitsstandards Ihrer Organisation zu aktivieren, verwendet lync Server 2013 die &nbsp; rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC). Mit RBAC werden Administratorrechte erteilt, indem Benutzer vordefinierten Administratorrollen zugewiesen werden. Zum Konfigurieren von lync-Archivierungsrichtlinien und Archivierungs Konfigurationen muss der Benutzer der csarchivingadministrator "-Rolle zugewiesen sein (es sei denn, die Konfiguration erfolgt direkt auf dem Server, auf dem die Archivierung statt Remote von einem anderen Computer bereitgestellt wird). Ausführliche Informationen zu RBAC finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation. Eine Liste der für die Archivierungs Bereitstellung erforderlichen Benutzerrechte, Berechtigungen und Rollen finden Sie unter <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment Checkliste for Archiving in lync Server 2013</A>, die sowohl in der Planungsdokumentation als auch in der Bereitstellungsdokumentation zur Verfügung steht.<BR>Wenn Sie Microsoft Exchange Integration verwenden, erfordert die Konfiguration von Exchange-Richtlinien entsprechende Administratorrechte und-Berechtigungen. Ausführliche Informationen finden Sie in der Exchange 2013 Dokumentation.



</div>

</div>

<span> </span>

</div>

</div>

</div>

