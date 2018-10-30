---
title: Standardmigrationsszenario – Übersicht
TOCTitle: Standardmigrationsszenario – Übersicht
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205354(v=OCS.15)
ms:contentKeyID: 49295738
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Standardmigrationsszenario – Übersicht

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Verwenden Sie die folgenden Punkte als Ausgangspunkt für die Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2Gruppenchat zu Lync Server 2013, Server für beständigen Chat. Der Migrationspfad für Lync Server 2013 sieht standardmäßig wie folgt aus:

  - Ihre Organisation hat zuvor Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2Gruppenchat bereitgestellt, und Sie möchten Lync Server 2013, Server für beständigen Chat bereitstellen.

  - Stellen Sie Lync Server 2013 und anschließend Serverpool für beständigen Chat bereit.

  - Führen Sie die Schritte zur Vorbereitung und Planung der Migration Ihrer Beständiger Chatrooms aus, und bestimmen Sie einen geeigneten Zeitpunkt zum Herunterfahren des Systems für die Migration.

  - Führen Sie die Windows PowerShell-Cmdlets für die Migration aus ( **Export-CsPersistentChatData** und **Import-CsPersistentChatData**), um Inhalte zum Server für beständigen Chat zu verschieben.

  - Überprüfen Sie, ob die Migration erfolgreich ausgeführt wurde.

  - Nehmen Sie die Vorversionsbereitstellung außer Betrieb.

  - Konfigurieren Sie den Server für beständigen Chat so, dass Vorversionsclients eine Verbindung mit Lync Server 2013, Server für beständigen Chat herstellen können. Dies ist erforderlich, weil die Bereitstellung neuer Clients Zeit benötigt und Sie vorhandenen Benutzern mit Vorversionsclients sobald wie möglich den Zugriff auf ihre Chatrooms ermöglichen möchten.

  - Stellen Sie neue Clients bereit, und stellen Sie gleichzeitig sicher, dass Benutzer mit Gruppenchatclients der Vorversion Zugriff auf ihre Chatrooms haben.

