---
title: Überprüfen der Replikation in der Domäne
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Zum Überprüfen der Replikation der Vorbereitung der Domäne erreicht in Schritt 1: Schema vorbereiten, es ist erforderlich, um ein Cmdlet aus der Skype für Business Server Management Shell Lync Server-Verwaltungsshell ausführen. Um das Windows PowerShell-Cmdlet ausführen, melden Sie sich an einem Computer, der Mitglied der Domäne, die Sie vorbereitet haben, und als Mitglied der Gruppe Domänen-Admins ist. Gehen Sie wie folgt vor:'
ms.openlocfilehash: e3dca892ccb4937bcd84148a954270b4bd1362f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-in-the-domain"></a>Überprüfen der Replikation in der Domäne
 
Zum Überprüfen der Replikation der Vorbereitung der Domäne erreicht **Schritt 1: Schema vorbereiten**, es ist erforderlich, um ein Cmdlet aus der Skype für Business Server Management Shell Lync Server-Verwaltungsshell ausführen. Um das Windows PowerShell-Cmdlet ausführen, melden Sie sich an einem Computer, der Mitglied der Domäne, die Sie vorbereitet haben, und als Mitglied der Gruppe Domänen-Admins ist. Gehen Sie wie folgt vor:
  
1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie in Windows PowerShell Folgendes ein:
    
  ```
  Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
  ```

    Beispiel:
    
  ```
  Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
  ```

    > [!NOTE]
    > Über den Parameter „GlobalSettingsDomainController“ können Sie den Speicherort der globalen Einstellungen angeben. Wenn die Einstellungen im Systemcontainer gespeichert werden (die typische mit Upgrade-Bereitstellungen, die nicht bereits erfolgt sind die globale in den Konfigurationscontainer migrierten Einstellung ist), definieren Sie einen Domänencontroller im Stamm der Gesamtstruktur Active Directory-Domänendienste. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in Active Directory. 
  
    Wenn Sie den Parameter „Domain“ nicht angeben, wird die lokale Domäne verwendet. Dieses Cmdlet gibt den Wert **LC_DOMAIN_SETTINGS_STATE_READY** zurück, wenn die domänenvorbereitung erfolgreich war.
    

