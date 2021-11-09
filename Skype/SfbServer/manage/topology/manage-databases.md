---
title: Verwalten von Datenbanken mit einer AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Zusammenfassung: Erfahren Sie, wie Sie einer vorhandenen AlwaysOn-Verfügbarkeitsgruppe weitere Skype for Business Server Datenbanken hinzufügen und welche zusätzlichen Schritte erforderlich sind, nachdem Sie einen Back-End-Server gepatcht oder aktualisiert haben, der Teil einer AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server ist.'
ms.openlocfilehash: fe74cd804aff746a3d6c52163ed96d6b270703ce
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827508"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Verwalten von Datenbanken mit einer AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server

Führen Sie die Schritte in diesem Artikel aus, um einer vorhandenen AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server weitere Skype for Business Server Datenbanken hinzuzufügen, und erfahren Sie mehr über die erforderlichen zusätzlichen Schritte nach dem Patchen oder Aktualisieren eines Back-End-Servers, der Teil einer AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server ist.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe 

1. Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AlwaysOn-Verfügbarkeitsgruppe. Fail it over to the primary replica.
    
2. Legen Sie im Topologie-Generator den SQL Server FQDN der AlwaysOn-Verfügbarkeitsgruppe auf den FQDN des primären Knotens dieser Gruppe fest.
    
   - Öffnen Sie den Topologie-Generator, wählen Sie **"Topologie aus vorhandener Bereitstellung herunterladen" aus,** und klicken Sie auf **"OK".**
    
   - Erweitern Sie Skype for Business Server, erweitern Sie Ihre Topologie, und erweitern Sie **SQL Server Stores.** Klicken Sie mit der rechten Maustaste auf den SQL Speicher der neuen AlwaysOn-Verfügbarkeitsgruppe, und klicken Sie auf **"Eigenschaften bearbeiten".**
    
   - Geben Sie unten auf der Seite im **Feld SQL Server FQDN** den FQDN des primären Knotens der AlwaysOn-Verfügbarkeitsgruppe ein.
    
3. Veröffentlichen Sie die Topologie. Klicken Sie im Menü **"Aktion"** auf **"Topologie"** und dann auf **"Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".**
    
4. Verwenden Sie SQL Server Management Studio, um die neue Datenbank der AlwaysOn-Verfügbarkeitsgruppe hinzuzufügen.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Patchen oder Aktualisieren eines SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe

Nach dem Patchen eines Back-End-Servers, der Teil einer AlwaysOn-Verfügbarkeitsgruppe ist, müssen Sie die Topologie erneut veröffentlichen.

1. Installieren Sie das Update auf Ihrem Skype for Business Server oder Servern.
    
2. Führen Sie den folgenden PowerShell-Befehl in ihrer Skype for Business-Verwaltungsshell aus (mit einem Konto angemeldet, das entsprechend berechtigt ist, Änderungen an den SQL AlwaysOn-Datenbanken anzuwenden):
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Dabei wird [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (FQDN) Ihrer AlwaysOn-Verfügbarkeitsgruppe ersetzt.
