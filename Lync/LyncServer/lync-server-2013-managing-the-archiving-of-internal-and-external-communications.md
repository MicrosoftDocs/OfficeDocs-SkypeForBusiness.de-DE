---
title: Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013
TOCTitle: Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204977(v=OCS.15)
ms:contentKeyID: 49294316
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

In Lync Server 2013 verwenden Sie Archivierungsrichtlinien, um die Archivierung für die interne und externe Kommunikation zu aktivieren und zu deaktivieren, falls Sie ohne Microsoft Exchange-Integration arbeiten oder über Benutzer verfügen, die nicht in Exchange 2013 verwaltet werden und deren Postfächer auf "Compliance-Archiv" gesetzt wurden. Dies betrifft die folgenden Archivierungsrichtlinien:

  - Eine globale Richtlinie, die standardmäßig erstellt wird, wenn Sie Lync Server 2013 bereitstellen.

  - Optionale Richtlinien auf Standort- und Benutzerebene, die Sie erstellen können, um damit festzulegen, wie die Archivierung für bestimmte Standorte oder Benutzer implementiert wird.

Sie richten die Archivierungsrichtlinien zunächst bei der Bereitstellung der Archivierung ein, können diese aber nach der Bereitstellung ändern, hinzufügen und löschen. In der Systemsteuerung für Lync Server 2013 können Sie über die Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** Richtlinien auf globaler Ebene, Standortebene und Benutzerebene verwalten. Für den Fall, dass Sie Ihren Lync Server-Speicher in den Exchange 2013-Speicher integrieren, haben die Benutzerrichtlinien für Exchange Vorrang vor den Archivierungsrichtlinien in Lync Server 2013.

Ausführliche Informationen zur Implementierung von Richtlinien und auch zur Richtlinienhierarchie erhalten Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, der Bereitstellungsdokumentation oder der Betriebsdokumentation.


> [!NOTE]
> Zur Steuerung der Archivierungsimplementierung müssen Sie Optionen in den Archivierungskonfigurationen auswählen, beispielsweise um festzulegen, ob Sofortnachrichten oder Konferenzinhalte archiviert werden, wie der kritische Modus verwendet wird, sowie Löschoptionen. Standardmäßig sind in der globalen Archivierungskonfiguration oder in Standortarchivierungs- oder Poolarchivierungskonfigurationen keine Optionen aktiviert. Sie sollten alle geeigneten Optionen in den Archivierungskonfigurationen festlegen, bevor Sie die Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools</A> in der Betriebsdokumentation.<BR>Wenn Sie die Integration von Microsoft Exchange für Ihre Bereitstellung ermöglichen, wird über die Exchange-Richtlinien gesteuert, ob die Archivierung für die unter Exchange 2013 verwalteten Benutzer und deren auf "Compliance-Archiv" gesetzte Postfächer aktiviert wird. Ausführliche Informationen erhalten Sie im Abschnitt <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A> in der Bereitstellungsdokumentation.



## In diesem Abschnitt

  - [Erstellen einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für bestimmte Standorte oder Benutzer](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [Ändern einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für Ihre Organisation, Standorte oder Benutzer](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [Anwenden einer Archivierungsrichtlinie auf Benutzer](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Löschen einer Archivierungsrichtlinie](lync-server-2013-deleting-an-archiving-policy.md)

