---
title: 'Lync Server 2013: Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung'
TOCTitle: Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205007(v=OCS.15)
ms:contentKeyID: 49294433
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Die Lösung zur Notfallwiederherstellung für Server für beständigen Chat basiert auf einem ausgedehnten Serverpool für beständigen Chat. Diese Lösung ähnelt einer Ausfallsicherheitslösung für innerstädtische Standorte in Lync Server 2010; es ist jedoch kein ausgedehntes virtuelles LAN (Local Area Network) erforderlich. Durch die Ausdehnung des Serverpool für beständigen Chats konfigurieren Sie grundsätzlich einen logischen Pool in der Topologie, physisch betrachtet werden die Server im Pool jedoch in zwei verschiedenen Rechenzentren platziert. Konfigurieren Sie die SQL Server-Spiegelung für die Datenbank auf dieselbe Weise, und stellen Sie die Datenbank und den Spiegel im selben Rechenzentrum bereit. Sie müssen im sekundären Rechenzentrum eine Sicherungsdatenbank konfigurieren (mit einem optionalen Spiegel, um eine hohe Verfügbarkeit im Fall einer Notfallwiederherstellung zu gewährleisten). Dies ist die Sicherungsdatenbank, die bei der Notfallwiederherstellung für das Failover verwendet wird.

Ausführliche Informationen zum Konfigurieren einer SQL Server-Spiegelung zur Gewährleistung der hohen Verfügbarkeit finden Sie im Abschnitt [SQL Server-Spiegelung in Lync Server 2013](lync-server-2013-sql-server-mirroring.md). Ausführlichen Informationen zum Failover der Datenbank bei einer Notfallwiederherstellung finden Sie in den Abschnitten [Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) und [Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank des Protokollversands in Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).

