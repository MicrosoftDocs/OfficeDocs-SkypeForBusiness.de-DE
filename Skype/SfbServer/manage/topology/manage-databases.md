---
title: Verwalten von Datenbanken mit einer AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Zusammenfassung: Informationen zum Hinzufügen weiterer Skype for Business Server-Datenbanken zu einer vorhandenen AlwaysOn-Verfügbarkeitsgruppe und zu den erforderlichen zusätzlichen Schritten nach dem Patchen oder Aktualisieren eines Back-End-Servers, der Teil einer AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server ist.'
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826365"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Verwalten von Datenbanken mit einer AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server

Führen Sie die Schritte in diesem Artikel aus, um einer vorhandenen AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server weitere Skype for Business Server-Datenbanken hinzuzufügen, und erfahren Sie mehr über die erforderlichen zusätzlichen Schritte, nachdem Sie einen Back-End-Server gepatcht oder aktualisiert haben, der Teil einer AlwaysOn-Verfügbarkeitsgruppe in Skype for Business Server ist.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe 

1. Öffnen SQL Server Management Studio, und navigieren Sie zur AlwaysOn-Verfügbarkeitsgruppe. Führen Sie ein Failover zum primären Replikat durch.
    
2. Legen Sie im Topologie-Generator den SQL Server FQDN der Verfügbarkeitsgruppe "AlwaysOn" auf den FQDN des primären Knotens dieser Gruppe fest.
    
   - Öffnen Sie den Topologie-Generator, wählen **Sie "Topologie aus vorhandener Bereitstellung herunterladen"** aus, und klicken Sie auf **"OK".**
    
   - Erweitern Sie Skype for Business Server, Erweitern Sie Ihre Topologie und SQL Server **Stores**. Klicken Sie mit der rechten maustaste SQL speicher der neuen AlwaysOn-Verfügbarkeitsgruppe, und klicken Sie dann **auf "Eigenschaften bearbeiten".**
    
   - Geben Sie unten auf der Seite im Feld **SQL Server FQDN** den FQDN des primären Knotens der Verfügbarkeitsgruppe "AlwaysOn" ein.
    
3. Veröffentlichen Sie die Topologie. Klicken Sie **im Menü "Aktion"** **auf "Topologie"** und dann **auf "Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".**
    
4. Verwenden SQL Server Management Studio, um die neue Datenbank der Verfügbarkeitsgruppe "AlwaysOn" hinzuzufügen.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Patchen oder Aktualisieren eines SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe

Nach dem Patchen eines Back-End-Servers, der Teil einer AlwaysOn-Verfügbarkeitsgruppe ist, müssen Sie die Topologie erneut veröffentlichen.

1. Installieren Sie das Update auf Ihrem Skype for Business-Server.
    
2. Führen Sie den folgenden PowerShell-Befehl in Ihrer Skype for Business-Verwaltungsshell aus (angemeldet mit einem Konto, das über die entsprechenden Berechtigungen zum Anwenden von Änderungen an den SQL AlwaysOn-Datenbanken verfügt) wie folgt:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Dabei wird [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Verfügbarkeitsgruppe AlwaysOn ersetzt.
