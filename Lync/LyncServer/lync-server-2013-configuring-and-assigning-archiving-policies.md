---
title: Konfigurieren und Zuweisen von Archivierungsrichtlinien
TOCTitle: Konfigurieren und Zuweisen von Archivierungsrichtlinien
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205175(v=OCS.15)
ms:contentKeyID: 49295069
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren und Zuweisen von Archivierungsrichtlinien

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

In Lync Server 2013 können Sie mithilfe von Richtlinien die Archivierung für die interne und externe Kommunikation von Benutzern aktivieren und deaktivieren, die in Lync Server 2013 verwaltet werden. Dies schließt die folgenden Archivierungsrichtlinien ein:

  - Ein globale Richtlinie, die standardmäßig beim Bereitstellen von Lync Server 2013 erstellt wird.

  - Optionale Richtlinien auf Standort- und Benutzerebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Benutzer erstellen und verwenden können.

Die Archivierungsrichtlinien werden erstmals beim Bereitstellen der Archivierung eingerichtet. Sie können Richtlinien jedoch nach der Bereitstellung ändern, hinzufügen und löschen. In der Systemsteuerung für Lync Server 2013 können Sie auf der Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** Richtlinien auf globaler Ebene, auf Standortebene und auf Benutzerebene verwalten.


> [!NOTE]
> Wenn Sie die Implementierung der Archivierung steuern möchten, müssen Sie in den Archivierungskonfigurationen Optionen angeben. Dabei geben Sie beispielsweise an, ob Sofortnachrichten (Instant Messaging, IM) oder Konferenzen archiviert werden sollen, und Sie geben die Verwendung des kritischen Modus und Löschoptionen an. Standardmäßig sind in der globalen Archivierungskonfiguration oder in der Archivierungskonfiguration auf Standort- oder Benutzerebene keine Optionen aktiviert. Vor dem Aktivieren der Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien sollten Sie alle entsprechenden Optionen in den Archivierungskonfigurationen angeben. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools</A> in der Betriebsdokumentation.<BR>Wenn Sie den Lync Server-Speicher in den Exchange 2013-Speicher integrieren, haben die Benutzerrichtlinien für Exchange Vorrang vor den Archivierungsrichtlinien für Lync Server 2013. Dies gilt jedoch nur für die Benutzer, die in Exchange 2013 verwaltet werden und die ihre Postfächer in Compliance-Archive verschoben haben.



Ausführliche Informationen zum Implementieren von Richtlinien, einschließlich der Hierarchie von Richtlinien, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation. Einzelheiten zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in der Betriebsdokumentation.

## In diesem Abschnitt

  - [Konfigurieren der globalen Richtlinie für die Archivierung](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Einrichten von Standortrichtlinien für die Archivierung](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Einrichten von Archivierungsrichtlinien für Benutzer](lync-server-2013-setting-up-archiving-policies-for-users.md)

