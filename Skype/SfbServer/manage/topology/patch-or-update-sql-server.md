---
title: Patchen oder Aktualisieren einer SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Zusammenfassung: Informieren Sie sich über die erforderlichen zusätzlichen Schritte nach dem Sie den Patch oder aktualisieren Sie einen Back End-Server, der Teil einer AlwaysOn Availability Group in Skype für Business Server ist.'
ms.openlocfilehash: 8f5c9131e59ccedd7f590f696fe53aa6c18c7d22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>Patchen oder Aktualisieren einer SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server 2015
 
**Zusammenfassung:** Erfahren Sie mehr über die erforderlichen zusätzlichen Schritte nach dem Patchen oder aktualisieren Sie einen Back End-Server, der Teil einer AlwaysOn Availability Group in Skype für Business Server ist.
  
Nach dem Patchen einer Back End-Server, der Teil einer AlwaysOn Availability Group ist, müssen Sie die Topologie veröffentlichen.
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a>Patchen oder Aktualisieren einer SQL Server, die Teil einer AlwaysOn Availability Group ist

1. Installieren des Updates auf Ihre Skype für Business Server oder Server.
    
2. Führen Sie den folgenden PowerShell-Befehl in Ihrer Skype für Business-Verwaltungsshell (mit einem Konto an, entsprechend Berechtigung zum Anwenden von Änderungen auf die SQL-AlwaysOn-Datenbanken ist, angemeldet) wie folgt:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Wobei [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (FQDN) Ihrer AlwaysOn Availability Group ersetzt wird.
    

