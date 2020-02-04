---
title: Überprüfen der Replikation in der Domäne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Um die Replikation der Domänenvorbereitung zu überprüfen, die in Schritt 1: Vorbereiten eines Schemas durchgeführt wurde, muss ein Cmdlet aus der lync Server-Verwaltungsshell der Skype for Business Server-Verwaltungsshell ausgeführt werden. Wenn Sie das Windows PowerShell-Cmdlet ausführen möchten, melden Sie sich bei einem Computer an, der Mitglied der von Ihnen vorbereiteten Domäne und als Mitglied der Gruppe der Domänenadministratoren ist. Gehen Sie wie folgt vor:'
ms.openlocfilehash: 7a9b8e90ce3c7c65f5f4b3d160ca7379b3bf8910
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705414"
---
# <a name="verify-replication-in-the-domain"></a>Überprüfen der Replikation in der Domäne
 
Um die Replikation der Domänenvorbereitung zu überprüfen, die in **Schritt 1: Vorbereiten eines Schemas**durchgeführt wurde, muss ein Cmdlet aus der lync Server-Verwaltungsshell der Skype for Business Server-Verwaltungsshell ausgeführt werden. Wenn Sie das Windows PowerShell-Cmdlet ausführen möchten, melden Sie sich bei einem Computer an, der Mitglied der von Ihnen vorbereiteten Domäne und als Mitglied der Gruppe der Domänenadministratoren ist. Gehen Sie wie folgt vor:
  
1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie in Windows PowerShell Folgendes ein:
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Beispiel:
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > Über den Parameter „GlobalSettingsDomainController“ können Sie den Speicherort der globalen Einstellungen angeben. Wenn Ihre Einstellungen im System Container gespeichert sind (typisch für Upgrade-Bereitstellungen, bei denen die globale Einstellung nicht zum Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Domänendienste-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in Active Directory. 
  
    Wenn Sie den Parameter „Domain“ nicht angeben, wird die lokale Domäne verwendet. Bei erfolgreicher Domänenvorbereitung gibt dieses Cmdlet den Wert **LC_DOMAIN_SETTINGS_STATE_READY** zurück.
    

