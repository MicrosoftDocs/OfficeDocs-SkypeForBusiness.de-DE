---
title: Patchen oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie ein Update oder Patch auf einem Back-End-Server in Skype for Business Server installieren.'
ms.openlocfilehash: 62c7a0c2e0c958e9f3e6c566d9e73a35d1dd945a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817096"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Patchen oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie ein Update oder Patch auf einem Back-End-Server in Skype for Business Server installieren.
  
In diesem Thema wird erläutert, wie Sie ein Update auf einem Enterprise Edition-Back-End-Server oder einem Standard Edition-Server installieren.
  
Wenn ein Back-End-Server während eines Upgrades für mindestens 30 Minuten nicht mehr zur Verfügung steht, können Benutzer dann in den Widerstands Modus wechseln. Wenn die Aktualisierung abgeschlossen ist und die Back-End-Server wieder mit den Front-End-Servern im Pool verbunden sind, werden die Benutzer an die vollständige Funktionalität zurückgegeben. Wenn das Upgrade weniger als 30 Minuten dauert, sind die Benutzer davon nicht betroffen.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Back-End-Server oder Standard Edition-Server aktualisieren

1. Melden Sie sich am Server, für den Sie das Upgrade vornehmen, als Mitglied der Rolle CsAdministrator an.
    
2. Laden Sie das Update herunter und extrahieren Sie es auf die lokale Festplatte.
    
3. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
    
4. Beenden Sie die Skype for Business Server-Dienste. Geben Sie in der Befehlszeile Folgendes ein:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Beenden Sie den WWW-Dienst (World Wide Web). Geben Sie in der Befehlszeile Folgendes ein:
    
    ```PowerShell
    net stop w3svc
   ```

6. Schließen Sie alle Skype for Business Server-Verwaltungsshell-Fenster.
    
7. Installieren Sie das Update.
    
8. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
    
9. Beenden Sie die Skype for Business Server-Dienste erneut, um globale Assemblycache-d-Assemblys zu erfassen. Geben Sie in der Befehlszeile Folgendes ein:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Starten Sie den WWW-Dienst neu. Geben Sie in der Befehlszeile Folgendes ein:
    
    ```PowerShell
    net start w3svc
    ```

11. Übernehmen Sie die vorgenommenen Änderungen für die SQL Server-Datenbanken, indem Sie einen der folgenden Schritte ausführen:
    
    - Wenn dies ein Enterprise Edition-Back-End-Server ist und auf diesem Server keine zusammengefassten Datenbanken wie Archivierungs-oder Überwachungsdatenbanken vorhanden sind, geben Sie Folgendes an einer Befehlszeile ein:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und auf diesem Server zusammengefasste Datenbanken vorhanden sind, geben Sie Folgendes an einer Befehlszeile ein:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Wenn es sich um einen Standard Edition-Server handelt, geben Sie Folgendes an einer Befehlszeile ein:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
