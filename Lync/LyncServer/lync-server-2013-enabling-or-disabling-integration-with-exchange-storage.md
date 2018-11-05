---
title: Aktivieren oder Deaktivieren der Integration mit Exchange-Speicher
TOCTitle: Aktivieren oder Deaktivieren der Integration mit Exchange-Speicher
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205228(v=OCS.15)
ms:contentKeyID: 49295289
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren der Integration mit Exchange-Speicher

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

In der Systemsteuerung für Lync Server 2013 aktivieren bzw. deaktivieren Sie mithilfe von Archivierungskonfigurationen die Integration von Exchange-Speicher. Dies beinhaltet die folgenden Archivierungskonfigurationen:

  - Eine globale Konfiguration, die beim Bereitstellen von Lync Server 2013 standardmäßig erstellt wird.

  - Optionale Konfigurationen auf Standard- und Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Standorte oder Pools implementiert wird.

Ausführliche Informationen zur Implementierung der Archivierungskonfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungskonfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation.

## So aktivieren oder deaktivieren Sie die Integration von Microsoft Exchange-Speicher

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie in der Liste mit den Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details einblenden**, und führen Sie eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration**, um die Integration von Exchange 2013-Speicher zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration**, um die Integration von Exchange 2013-Speicher zu deaktivieren.

5.  Klicken Sie auf **Commit ausführen**.

## Siehe auch

#### Konzepte

[Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Weitere Ressourcen

[Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

