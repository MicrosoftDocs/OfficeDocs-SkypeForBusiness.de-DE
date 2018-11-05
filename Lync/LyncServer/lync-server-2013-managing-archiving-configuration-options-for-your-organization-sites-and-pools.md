---
title: Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools
TOCTitle: Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204802(v=OCS.15)
ms:contentKeyID: 49293678
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In Systemsteuerung für Lync Server 2013 verwenden Sie Archivierungskonfigurationen, um anzugeben, wie die Archivierung implementiert wird. Hierzu gehören folgende Archivierungskonfigurationen:

  - Eine globale Konfiguration, die bei der Bereitstellung von Lync Server 2013 standardmäßig erstellt wird.

  - Optionale Konfigurationen auf Standort- und Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Standorte oder Pools implementiert wird.

Die Archivierungskonfigurationen werden anfänglich bei der Bereitstellung der Archivierung eingerichtet. Nach der Bereitstellung können Sie aber Konfigurationen ändern, hinzufügen und löschen. In Systemsteuerung für Lync Server 2013 können Sie die Seite **Archivierungskonfiguration** der Archivierungs- und Überwachungsgruppe verwenden, um Konfigurationen auf globaler Ebene, Standortebene und Poolebene zu verwalten. Detaillierte Informationen darüber, wie Archivierungskonfigurationen implementiert werden, einschließlich verfügbarer Optionen und Hierarchie der Archivierungskonfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.


> [!NOTE]
> Zur Verwendung der Archivierung müssen Sie mithilfe von Archivierungsrichtlinien angeben, ob die Archivierung für alle Benutzer, die auf in Lync Server 2013 verwaltet werden, für die interne Kommunikation, für die externe Kommunikation oder für beide Kommunikationsarten aktiviert wird. In der Standardeinstellung ist die Archivierung der internen oder externen Kommunikation nicht aktiviert. Wenn Sie die Microsoft Exchange-Integration verwenden, müssen Sie Exchange 2013 aktivieren und so konfigurieren, dass die Archivierung für alle in Exchange 2013 verwalteten Benutzer unterstützt wird, deren Postfächer sich im Compliance-Archiv befanden.<BR>Bevor Sie die Archivierung aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional auch für bestimmte Standorte und Pools festlegen, so wie in diesem Abschnitt beschrieben. Ausführliche Informationen zur Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien</A> in der Bereitstellungsdokumentation.



**So zeigen Sie Archivierungskonfigurationsinformationen mithilfe der Lync Server-Verwaltungsshell-Cmdlets an**

  - Sie können die Archivierungskonfigurationsinformationen auch mithilfe der Lync Server-Windows PowerShell und des **Get-CsArchivingConfiguration**-Cmdlets anzeigen. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder eine Windows PowerShell-Remotesitzung ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Verwenden Sie in der Lync Server-Verwaltungsshell den folgenden Befehl, um Informationen zu all Ihren Archivierungskonfigurationseinstellungen anzuzeigen:
    
        Get-CsArchivingConfiguration

## In diesem Abschnitt

  - [Erstellen einer Archivierungskonfiguration zum Verwalten der Archivierung für bestimmte Standorte oder Pools](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Aktivieren oder Deaktivieren der Archivierung von Instant Messaging- oder Konferenzsitzungen](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Aktivieren oder Deaktivieren der Löschung von archivierten Daten](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Aktivieren oder Deaktivieren des kritischen Modus, um Instant Messaging- und Webkonferenzsitzungen bei Archivierungsfehlern zu blockieren oder zuzulassen](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Aktivieren oder Deaktivieren der Integration mit Exchange-Speicher](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Löschen einer Archivierungskonfiguration](lync-server-2013-deleting-an-archiving-configuration.md)

## Siehe auch

#### Weitere Ressourcen

[Verwalten der Lync Server 2013-Archivierung](lync-server-2013-managing-archiving.md)

