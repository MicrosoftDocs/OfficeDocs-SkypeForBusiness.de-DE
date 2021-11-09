---
title: Installieren und Erstellen von Datenbanken
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Sie wählen die Datenbanken aus, die Sie für die Bereitstellung erstellen möchten. Standardmäßig wird die Datenbank auf der definierten SQL Server am definierten Standort erstellt und stellt die Datenbankdateien automatisch basierend auf dem SQL Server bereit, auf dem Sie die Datenbanken platzieren, und konfiguriert sie.
ms.openlocfilehash: 9dd5e0f0ce800489ab937feae1cda68809540d81
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849108"
---
# <a name="install-and-create-databases"></a>Installieren und Erstellen von Datenbanken

Sie wählen die Datenbanken aus, die Sie für die Bereitstellung erstellen möchten. Standardmäßig wird die Datenbank auf der definierten SQL Server am definierten Standort erstellt und stellt die Datenbankdateien automatisch basierend auf dem SQL Server bereit, auf dem Sie die Datenbanken platzieren, und konfiguriert sie.

 **Zu erstellende Datenbanken auswählen**: Aktivieren Sie die Kontrollkästchen aller Datenbanken, die Sie bereitstellen und konfigurieren möchten. Sie können beliebige einzelne oder alle Datenbanken für die Bereitstellung markieren.

> [!CAUTION]
> Die SQL Server muss bereits für die Instanz konfiguriert sein (falls vorhanden), und Firewallports müssen geöffnet sein, um die Instanz aufzunehmen, in der Sie die Datenbanken bereitstellen. Ausführliche Informationen finden Sie unter [Konfigurieren SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **Erweitert:** Klicken Sie auf die SQL Server, und klicken Sie auf die Schaltfläche **"Erweitert",** um Optionen für die Speicherorte der Datenbankdateien auf Ihrem SQL Server auszuwählen. Ausführliche Informationen zu den erweiterten Optionen für die Anordnung von Datenbankdateien finden Sie unter [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **Zurück**: Wenn Sie auf diese Schaltfläche klicken, gelangen Sie zurück zum vorherigen Bildschirm (je nach Navigation zu diesem Dialogfeld nicht immer verfügbar).

 **Weiter**: Wenn Sie auf diese Schaltfläche klicken, wird Ihre Auswahl im aktuellen Dialogfeld übernommen, und Sie gelangen zum nächsten Dialogfeld, in dem Sie weitere Informationen konfigurieren können.

 **Abbrechen**: Wenn Sie auf diese Schaltfläche klicken, wird die Konfiguration beendet, und Ihre Änderungen werden verworfen. Auf einigen Konfigurationsbildschirmen werden Sie in einer Meldung gefragt, ob Sie den Vorgang beenden und Ihre Änderungen verwerfen möchten. Wenn Sie **"Ja"** auswählen, wird die aktuelle Konfiguration geschlossen, die aktuelle Konfiguration geschlossen und Sie zum Topologie-Generator zurückgesetzt. Wenn Sie **Nein** wählen, gelangen Sie zum aktuellen Dialogfeld für die Konfiguration zurück und können die Konfiguration fortsetzen.

 **Hilfe**: Wenn Sie auf die Schaltfläche **Hilfe** klicken, werden diese Hilfeinformationen zum aktuellen Konfigurationsdialogfeld angezeigt.