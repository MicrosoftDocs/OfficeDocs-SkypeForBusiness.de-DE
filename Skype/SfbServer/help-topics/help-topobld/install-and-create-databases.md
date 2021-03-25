---
title: Installieren und Erstellen von Datenbanken
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Sie wählen die Datenbanken aus, die Sie für die Bereitstellung erstellen möchten. Standardmäßig wird die Datenbank auf dem definierten SQL Server am definierten Standort erstellt und stellt die Datenbankdateien automatisch basierend auf dem SQL Server, auf dem Sie die Datenbanken platzieren, und konfiguriert sie.
ms.openlocfilehash: 3e7e2e0aaec55c595a4f538238c431feb9173152
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120927"
---
# <a name="install-and-create-databases"></a>Installieren und Erstellen von Datenbanken

Sie wählen die Datenbanken aus, die Sie für die Bereitstellung erstellen möchten. Standardmäßig wird die Datenbank auf dem definierten SQL Server am definierten Standort erstellt und stellt die Datenbankdateien automatisch basierend auf dem SQL Server, auf dem Sie die Datenbanken platzieren, und konfiguriert sie.

 **Zu erstellende Datenbanken auswählen**: Aktivieren Sie die Kontrollkästchen aller Datenbanken, die Sie bereitstellen und konfigurieren möchten. Sie können beliebige einzelne oder alle Datenbanken für die Bereitstellung markieren.

> [!CAUTION]
> Die SQL Server muss bereits für die Instanz konfiguriert worden sein (sofern vorhanden), und Firewallports müssen geöffnet werden, um die Instanz zu verwenden, in der Sie die Datenbanken bereitstellen. Ausführliche Informationen finden Sie unter [Configure SQL Server for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **Erweitert**: Klicken Sie auf SQL Server  und klicken Sie auf die Schaltfläche Erweitert, um Optionen für die Speicherorte der Datenbankdatei auf Ihrem SQL Server. Ausführliche Informationen zu den erweiterten Optionen für die Anordnung von Datenbankdateien finden Sie unter [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **Zurück**: Wenn Sie auf diese Schaltfläche klicken, gelangen Sie zurück zum vorherigen Bildschirm (je nach Navigation zu diesem Dialogfeld nicht immer verfügbar).

 **Weiter**: Wenn Sie auf diese Schaltfläche klicken, wird Ihre Auswahl im aktuellen Dialogfeld übernommen, und Sie gelangen zum nächsten Dialogfeld, in dem Sie weitere Informationen konfigurieren können.

 **Abbrechen**: Wenn Sie auf diese Schaltfläche klicken, wird die Konfiguration beendet, und Ihre Änderungen werden verworfen. Auf einigen Konfigurationsbildschirmen werden Sie in einer Meldung gefragt, ob Sie den Vorgang beenden und Ihre Änderungen verwerfen möchten. Wenn **Sie Ja** auswählen, wird die aktuelle Konfiguration geschlossen und die aktuelle Konfiguration geschlossen, und Sie kehren zum Topologie-Generator zurück. Wenn Sie **Nein** wählen, gelangen Sie zum aktuellen Dialogfeld für die Konfiguration zurück und können die Konfiguration fortsetzen.

 **Hilfe**: Wenn Sie auf die Schaltfläche **Hilfe** klicken, werden diese Hilfeinformationen zum aktuellen Konfigurationsdialogfeld angezeigt.