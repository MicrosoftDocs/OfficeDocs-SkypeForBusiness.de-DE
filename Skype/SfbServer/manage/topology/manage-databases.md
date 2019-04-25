---
title: Verwalten von Datenbanken mit einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Zusammenfassung: Informationen Sie zum Hinzufügen von weitere Skype für Business Server-Datenbanken zu einer vorhandenen AlwaysOn Availability Group und erfahren Sie mehr über die erforderlichen zusätzlichen Schritte nach dem Sie den Patch oder aktualisieren Sie einen Back End-Server, der Teil einer AlwaysOn Availability Group in Skype für ist Business-Server.'
ms.openlocfilehash: 8d25e7d3aa1e840be7eb246e6aaa3065b65b7ff7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214694"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Verwalten von Datenbanken mit einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server

Verwenden Sie die Schritte in diesem Artikel zu einer vorhandenen AlwaysOn Availability Group in Skype für Business Server weitere Skype für Business Server-Datenbanken hinzu, und erfahren Sie mehr über die erforderlichen zusätzlichen Schritte nach dem Patchen oder aktualisieren Sie einen Back End-Server, die Teil einer AlwaysOn ist Availability Group in Skype für Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe 

1. Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AlwaysOn Availability Group. Failover es auf das primäre Replikat.
    
2. Legen Sie die SQL Server-FQDN der AlwaysOn Availability Group im Topologie-Generator auf den vollqualifizierten Domänennamen des primären Knotens der Gruppe.
    
   - Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.
    
   - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf **Eigenschaften bearbeiten**.
    
   - Geben Sie am unteren Rand der Seite in das Feld **SQL Server-FQDN** in den FQDN des primären Knoten die AlwaysOn Availability Group.
    
3. Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.
    
4. Verwenden Sie SQL Server Management Studio die AlwaysOn Availability Group die neue Datenbank hinzu.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Patchen oder Aktualisieren einer SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe

Nach dem Patchen einer Back End-Server, der Teil einer AlwaysOn Availability Group ist, müssen Sie die Topologie veröffentlichen.

1. Installieren des Updates auf Ihre Skype für Business Server oder Server.
    
2. Führen Sie den folgenden PowerShell-Befehl in Ihrer Skype für Business-Verwaltungsshell (mit einem Konto an, entsprechend Berechtigung zum Anwenden von Änderungen auf die SQL-AlwaysOn-Datenbanken ist, angemeldet) wie folgt:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Wobei [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (FQDN) Ihrer AlwaysOn Availability Group ersetzt wird.
