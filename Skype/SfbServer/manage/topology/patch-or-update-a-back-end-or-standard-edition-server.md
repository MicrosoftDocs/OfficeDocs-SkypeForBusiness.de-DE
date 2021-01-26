---
title: Patchen oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in Skype for Business Server
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Zusammenfassung: Informationen zum Installieren eines Updates oder Patches auf einem Back-End-Server in Skype for Business Server.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826305"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Patchen oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie ein Update oder einen Patch auf einem Back-End-Server in Skype for Business Server installieren.
  
In diesem Thema wird erläutert, wie Sie ein Update auf einem Back-End-Server der Enterprise Edition oder auf einem Standard Edition-Server installieren.
  
Wenn ein Back-End-Server während des Upgrades mindestens 30 Minuten aus ist, können Benutzer in den Ausfallsicherheitsmodus wechseln. Wenn das Upgrade abgeschlossen ist und die Back-End-Server wieder mit den Front-End-Servern im Pool verbunden sind, werden die Benutzer wieder voll funktionsgebunden. Wenn das Upgrade weniger als 30 Minuten dauert, sind die Benutzer nicht betroffen.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>So aktualisieren Sie einen Back-End-Server oder Standard Edition-Server

1. Melden Sie sich am Server, für den Sie das Upgrade vornehmen, als Mitglied der Rolle "CsAdministrator" an.
    
2. Laden Sie das Update herunter, und extrahieren Sie es auf die lokale Festplatte.
    
3. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie **auf "Start",**"Alle **Programme",** **"Skype for Business"** und dann auf **"Skype for Business Server Management Shell".**
    
4. Beenden Sie die Skype for Business Server-Dienste. Geben Sie in die Befehlszeile Folgendes ein:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Beenden Sie den WWW-Dienst (World Wide Web). Geben Sie an der Befehlszeile Folgendes ein:
    
    ```PowerShell
    net stop w3svc
   ```

6. Schließen Sie alle Fenster der Skype for Business Server-Verwaltungsshell.
    
7. Installieren Sie das Update.
    
8. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie **auf "Start",**"Alle **Programme",** **"Skype for Business"** und dann auf **"Skype for Business Server Management Shell".**
    
9. Beenden Sie die Skype for Business Server-Dienste erneut, um Assemblys des globalen Assemblycaches (GAC) -d abfangen. Geben Sie an der Eingabeaufforderung Folgendes ein:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Starten Sie den WWW-Dienst neu. Geben Sie an der Befehlszeile Folgendes ein:
    
    ```PowerShell
    net start w3svc
    ```

11. Wenden Sie die an den SQL Server vorgenommenen Änderungen an, indem Sie eine der folgenden Schritte vornehmen:
    
    - Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und auf diesem Server keine datenbanken, z. B. Archivierungs- oder Überwachungsdatenbanken, vorhanden sind, geben Sie an einer Befehlszeile Folgendes ein:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und auf diesem Server eine datenbankverknappte Datenbank vorhanden ist, geben Sie an einer Befehlszeile Folgendes ein:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Wenn es sich um einen Standard Edition-Server handelt, geben Sie an einer Befehlszeile Folgendes ein:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
