---
title: Verwalten von Datenbanken mit einer AlwaysOn-verfügbarkeitsgruppe in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Zusammenfassung: erfahren Sie, wie Sie weitere Skype for Business Server-Datenbanken zu einer vorhandenen AlwaysOn-verfügbarkeitsgruppe hinzufügen, und erfahren Sie mehr über die erforderlichen zusätzlichen Schritte, nachdem Sie einen Back-End-Server, der Teil einer AlwaysOn-verfügbarkeitsgruppe ist, in Skype for installieren oder aktualisieren. Business Server.'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275185"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Verwalten von Datenbanken mit einer AlwaysOn-verfügbarkeitsgruppe in Skype for Business Server

Führen Sie die Schritte in diesem Artikel aus, um weitere Skype for Business Server-Datenbanken zu einer vorhandenen AlwaysOn-verfügbarkeitsgruppe in Skype for Business Server hinzuzufügen, und informieren Sie sich über die erforderlichen zusätzlichen Schritte, nachdem Sie einen Back-End-Server, der Teil eines AlwaysOn ist, Patchen oder aktualisieren. Verfügbarkeitsgruppe in Skype for Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Hinzufügen von Datenbanken zu einer AlwaysOn-verfügbarkeitsgruppe 

1. Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AlwaysOn-verfügbarkeitsgruppe. Führen Sie einen Failover für das primäre Replikat durch.
    
2. Setzen Sie im Topologie-Generator den SQL Server-FQDN der AlwaysOn-verfügbarkeitsgruppe auf den FQDN des primären Knotens dieser Gruppe.
    
   - Öffnen Sie den Topologie-Generator, wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie auf **OK**.
    
   - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Klicken Sie mit der rechten Maustaste auf den SQL Store der neuen AlwaysOn-verfügbarkeitsgruppe, und klicken Sie auf **Eigenschaften bearbeiten**.
    
   - Geben Sie unten auf der Seite im Feld **SQL Server-FQDN** den FQDN des primären Knotens der AlwaysOn-verfügbarkeitsgruppe ein.
    
3. Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.
    
4. Verwenden Sie SQL Server Management Studio, um die neue Datenbank zur AlwaysOn-verfügbarkeitsgruppe hinzuzufügen.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Patchen oder Aktualisieren eines SQL-Servers in einer AlwaysOn-verfügbarkeitsgruppe

Nachdem Sie einen Back-End-Server gepatcht haben, der Teil einer AlwaysOn-verfügbarkeitsgruppe ist, müssen Sie die Topologie erneut veröffentlichen.

1. Installieren Sie das Update auf Ihrem Skype for Business-Server oder-Server.
    
2. Führen Sie den folgenden PowerShell-Befehl in Ihrer Skype for Business-Verwaltungsshell aus (angemeldet mit einem Konto, das entsprechend berechtigt ist, Änderungen auf die SQL AlwaysOn-Datenbanken anzuwenden) wie folgt:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Wobei [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer AlwaysOn-verfügbarkeitsgruppe ersetzt wird.
