---
title: 'Lync Server 2013: Definieren der Anforderungen Ihrer Organisation für die Archivierung'
TOCTitle: Definieren der Anforderungen Ihrer Organisation für die Archivierung
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205276(v=OCS.15)
ms:contentKeyID: 49295438
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Anforderungen Ihrer Organisation für die Archivierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Wenn Ihre Organisation rechtliche Vorschriften einhalten muss, können Sie zur Aktivierung der Archivierungsunterstützung für Chats und Konferenzen (Besprechungen) in Lync Server 2013 die Archivierung bereitstellen. Weitere Informationen zu Inhalten, die archiviert werden können, finden Sie unter [Übersicht über die Archivierung in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in der Planungsdokumentation.

Zum Implementieren der Archivierung müssen Sie zunächst bestimmen, wie die Archivierungsanforderungen Ihrer Organisation erfüllt werden sollen. Hierfür müssen Sie Folgendes festlegen:

  - **Wann die Archivierung bereitgestellt werden soll**. Sie können die Archivierung im Rahmen der anfänglichen Bereitstellung von Lync Server 2013 bereitstellen oder aber die Archivierung einer vorhandenen Bereitstellung hinzufügen. Zum Bereitstellen der Archivierung fügen Sie sie mit dem Topologie-Generator Ihrer Topologie hinzu und veröffentlichen anschließend die Topologie.

  - **Ob die interne oder externe Kommunikation archiviert werden soll**. Sie können die Archivierung für die interne Kommunikation (die Kommunikation zwischen internen Benutzern) und/oder die externe Kommunikation (die Kommunikation, bei der mindestens ein Benutzer außerhalb Ihres internen Netzwerks beteiligt ist) aktivieren. Diese Optionen können für die gesamte Organisation oder nur für bestimmte Standorte und Pools angegeben werden. Standardmäßig ist keine dieser Optionen aktiviert.
    

    > [!NOTE]
    > Wenn Sie die Microsoft Exchange-Integration zum Speichern archivierter Daten verwenden, bestimmen die Exchange-Einstellungen, ob die Lync-Kommunikation archiviert wird. Falls in Ihrer Bereitstellung mehrere Gesamtstrukturen vorhanden sind, müssen Sie die Einstellungen zwischen Lync Server und Exchange synchronisieren. Die Kontrolle der Archivierung für die interne oder externe Kommunikation ist nur für Lync-Richtlinien verfügbar. Für die integrierte Exchange-Archivierung werden beide Kommunikationstypen archiviert bzw. nicht archiviert.



  - **Warum die Archivierung aktiviert werden soll**. Sie können die Archivierung für die gesamte Bereitstellung auf globaler Ebene aktivieren bzw. deaktivieren. Die Archivierung können Sie auch für bestimmte Standorte und Benutzer aktivieren bzw. deaktivieren. Für jede Ebene geben Sie an, ob die Archivierung von Chatsitzungen (Peer-zu-Peer) und/oder Konferenzen (Besprechungen, die Sitzungen mit mehreren Teilnehmern sind) aktiviert werden soll. Standardmäßig ist die Archivierung deaktiviert.

  - **Wie wichtig die Archivierung für Benutzer in Ihrer Organisation ist**. Wenn die Archivierung in Ihrer Organisation unternehmenskritisch ist, können Sie angeben, dass Lync Server 2013 im kritischen Modus ausgeführt wird. In diesem Fall werden Chat- und Konferenzsitzungen blockiert, falls bei der Archivierung ein Fehler auftritt. Beispiel:
    
      - Wenn der Archivierungsdienst vorübergehend keine Nachrichten an die Datenbankwarteschlange senden oder keine Nachrichten in die Datenbank einfügen kann, wird sowohl die Chat- als auch die Konferenzfunktionalität in der Bereitstellung blockiert, bis die Archivierungsunterstützung wiederhergestellt ist.
    
      - Wenn ein Konferenzbenutzer eine Datei hochlädt, die nicht in den Archivierungsdateispeicher kopiert werden kann, wird die Konferenzfunktionalität in der Bereitstellung blockiert, bis das Problem behoben ist. Die Chatfunktionalität wird jedoch nicht blockiert.
    
    Diese Option können Sie auf globaler Ebene, Standortebene und Poolebene konfigurieren. Standardmäßig ist der kritische Modus nicht aktiviert.

  - **Ob die Microsoft Exchange-Integration verwendet werden soll**. Mit dieser Option wird Archivierungsspeicher in den Speicher von Exchange 2013 integriert, damit die archivierten Daten in Lync Server und Exchange 2013 zusammen in Exchange gespeichert werden. Die Microsoft Exchange-Integration können Sie zum Speichern von Archivierungsdaten für Benutzer verwenden, die in Exchange 2013 verwaltet werden, falls für ihre Postfächer "Compliance-Archiv" festgelegt wurde. Wenn Sie nicht über eine Exchange 2013-Bereitstellung verfügen, wenn Sie diese Integration nicht wünschen, oder wenn Sie über Lync-Benutzer verfügen, die nicht in Exchange 2013 verwaltet werden, können Sie separate Archivierungsdatenbanken bereitstellen, indem Sie mithilfe von SQL Server archivierte Daten aus Lync-Kommunikationen speichern. Die Microsoft Exchange-Integration können Sie auf globaler Ebene, Standortebene und Poolebene konfigurieren. Standardmäßig ist die Microsoft Exchange-Integration nicht aktiviert.

  - **Wie archivierte Daten verwaltet werden sollen**. Die Archivierungsdatenbank ist nicht für eine langfristige Aufbewahrung ausgelegt und Lync Server 2013 bietet keine E-Discovery-Lösung (Suche) für archivierte Daten, sodass Daten in einen anderen Speicher verschoben werden müssen. Lync Server stellt jedoch ein Sitzungsexporttool bereit, mit dem Sie archivierte Daten exportieren können und das durchsuchbare Aufzeichnungen der archivierten Daten erstellt. Für die globale Richtlinie sowie für jede von Ihnen erstellte Standort- und Benutzerrichtlinie können Sie das Bereinigen von Daten aktivieren und eine der folgenden Optionen angeben:
    
      - Sowohl exportierte Archivierungsdaten als auch gespeicherte Archivierungsdaten nach einer bestimmten Anzahl von Tagen löschen. Die Mindestanzahl von Tagen beträgt 1 Tag. Die Höchstzahl von Tagen beträgt 2562 Tage.
    
      - Nur exportierte Archivierungsdaten löschen. Mit dieser Option werden alle Datensätze gelöscht, die exportiert und für das Löschen durch das Exporttool für Sitzungen markiert wurden.
    
    Diese Option können Sie auf globaler Ebene, Standortebene und Poolebene konfigurieren. Standardmäßig ist das Bereinigen nicht aktiviert.

Die Archivierung können Sie mithilfe der folgenden Methoden steuern:

  - **Archivierungsrichtlinien**. Sie verwenden eine oder mehrere Archivierungsrichtlinien zum Aktivieren und Deaktivieren der Archivierung interner und externer Kommunikation. Standardmäßig ist keine Archivierung aktiviert. Die Archivierung für interne Kommunikation und/oder externer Kommunikation in Ihrer Bereitstellung aktivieren oder deaktivieren Sie mithilfe der standardmäßigen globalen Richtlinie. Die globale Richtlinie kann nicht gelöscht werden. Sie können eine oder mehrere optionale Standortrichtlinien zum Aktivieren oder Deaktivieren der Archivierung für die interne und externe Kommunikation für bestimmte Standorte angeben. Darüber hinaus können Sie eine oder mehrere Benutzerrichtlinien zum Aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer und Benutzergruppen angeben. Benutzerrichtlinien haben Vorrang vor Standortrichtlinien. Standortrichtlinien haben Vorrang vor den globalen Richtlinien. Benutzerrichtlinien werden nur für die Benutzer implementiert, für die die Verwendung der Richtlinien konfiguriert ist. Gruppenchats und -konferenzen werden nur archiviert, falls für mindestens einen Teilnehmer eine Richtlinie zur Aktivierung der Archivierung vorhanden ist.
    

    > [!NOTE]
    > Wenn Sie die Microsoft Exchange-Integration verwenden, haben Exchange 2013-Richtlinien Vorrang vor Lync Server-Archivierungsrichtlinien für alle Benutzer, die auf den Servern mit Exchange 2013 verwaltet werden.



  - **Archivierungskonfigurationen**. Sie verwenden eine oder mehrere Archivierungskonfigurationen, um die meisten Archivierungsoptionen anzugeben, die zuvor in diesem Thema beschrieben wurden. Eine Ausnahme stellt die Aktivierung der Archivierung für die interne und externe Kommunikation dar (wird wie im vorherigen Punkt beschrieben mithilfe von Archivierungsrichtlinien konfiguriert). Zu den Archivierungskonfigurationen zählen die standardmäßige globale Konfiguration und optionale Standort- und Poolkonfigurationen. Die globale Konfiguration kann nicht gelöscht werden. Poolkonfigurationen haben Vorrang vor Standortkonfigurationen. Standortkonfigurationen haben Vorrang vor der globalen Konfiguration.

Im Rahmen der Anforderungsanalyse müssen Sie bestimmen, wie die globale Archivierungskonfiguration und die globale Archivierungsrichtlinie konfiguriert werden sollen. Darüber hinaus müssen Sie Ihre Anforderungen für Archivierungskonfigurationen auf Standortebene, für Archivierungskonfigurationen auf Poolebene, für Archivierungsrichtlinien auf Standortebene und für Archivierungsrichtlinien auf Benutzerebene festlegen.

Wenn Sie die Archivierung für einen Front-End-Pool oder einen Standard Edition-Server aktivieren, sollten Sie sie für alle weiteren Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung ebenfalls aktivieren. Dies ist erforderlich, weil Benutzer, deren Kommunikation archiviert werden muss, zu Gruppenchatunterhaltungen oder Besprechungen eingeladen werden können, die in einem anderen Pool gehostet werden. Wenn im Pool, der die Unterhaltung oder Besprechung hostet, die Archivierung nicht aktiviert wurde, werden möglicherweise nicht alle Konferenzdaten archiviert. Die Archivierung funktioniert zwar für aktivierte Benutzer und alle Chatnachrichten, aber Konferenzinhalte und Ereignisse werden möglicherweise nicht archiviert.


> [!NOTE]
> In Lync Server 2013&nbsp;wird die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwendet, um das Delegieren von Verwaltungsaufgaben zu ermöglichen, während gleichzeitig die Sicherheitsstandards Ihrer Organisation gewährleistet sind. Bei der rollenbasierten Zugriffssteuerung werden Administratorrechte zugewiesen, indem Benutzer vordefinierten Administrationsrollen hinzugefügt werden. Zum Konfigurieren von Lync-Archivierungsrichtlinien und -Archivierungskonfigurationen muss der Benutzer der Rolle CsArchivingAdministrator zugewiesen werden (es sei denn, die Konfiguration wird nicht remote von einem anderen Computer aus, sondern direkt auf dem Archivierungsserver ausgeführt). Ausführliche Informationen zur rollenbasierten Zugriffssteuerung finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</A> in der Planungsdokumentation. Eine Liste der erforderlichen Benutzerrechte, -berechtigungen und -rollen für die Archivierungsbereitstellung finden Sie unter <A href="lync-server-2013-deployment-checklist-for-archiving.md">Prüfliste zur Bereitstellung für die Archivierung in Lync Server 2013</A> in der Planungs- oder in der Bereitstellungsdokumentation.<BR>Wenn Sie die Microsoft Exchange-Integration verwenden, sind für die Konfiguration von Exchange-Richtlinien entsprechende Administratorrechte und -berechtigungen erforderlich. Ausführliche Informationen finden Sie in der Dokumentation zu Exchange 2013.


