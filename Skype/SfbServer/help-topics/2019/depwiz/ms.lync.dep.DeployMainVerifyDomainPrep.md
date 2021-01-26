---
title: Überprüfen der Replikation in der Domäne
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Um die Replikation der in Schritt 1: Schema vorbereiten durchgeführten Domänenvorbereitung zu überprüfen, muss ein Cmdlet aus der Lync Server-Verwaltungsshell der Skype for Business Server-Verwaltungsshell ausgeführt werden. Um das cmdlet Windows PowerShell ausführen zu können, melden Sie sich bei einem Computer an, der Mitglied der von Ihnen vorbereiteten Domäne ist, und als Mitglied der Gruppe "Domänen-Admins". Gehen Sie wie folgt vor:'
ms.openlocfilehash: 9ec39551702e0f3480671787536929863cb61f6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801655"
---
# <a name="verify-replication-in-the-domain"></a>Überprüfen der Replikation in der Domäne
 
Um die Replikation der in Schritt **1:** Schema vorbereiten durchgeführten Domänenvorbereitung zu überprüfen, muss ein Cmdlet aus der Lync Server-Verwaltungsshell der Skype for Business Server-Verwaltungsshell ausgeführt werden. Um das cmdlet Windows PowerShell ausführen zu können, melden Sie sich bei einem Computer an, der Mitglied der von Ihnen vorbereiteten Domäne ist, und als Mitglied der Gruppe "Domänen-Admins". Gehen Sie wie folgt vor:
  
1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie **auf "Start",**"Alle **Programme",** **"Skype for Business"** und dann auf **"Skype for Business Server Management Shell".**
    
2. Geben Windows PowerShell Folgenden ein:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Beispiel:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > Über den Parameter "GlobalSettingsDomainController" können Sie den Speicherort der globalen Einstellungen angeben. Wenn Ihre Einstellungen im Systemcontainer gespeichert werden (dies ist typisch für Upgradebereitstellungen, bei denen die globale Einstellung nicht zum Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stammverzeichnis der Active Directory Domain Services-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind und verweist auf einen beliebigen Domänencontroller in Active Directory. 
  
    Wenn Sie den Parameter "Domain" nicht angeben, wird die lokale Domäne verwendet. Bei erfolgreicher Domänenvorbereitung gibt dieses Cmdlet den Wert **LC_DOMAIN_SETTINGS_STATE_READY** zurück.
    

