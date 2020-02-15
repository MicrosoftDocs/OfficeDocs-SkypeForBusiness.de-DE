---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows, Audiodateien und Kontaktobjekten der beweglichen Reaktionsgruppe aus der Legacy Bereitstellung in den Skype for Business Server 2019-Pool. Nachdem Sie Ihre Legacy-Reaktionsgruppen migriert haben, werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Pool Skype for Business Server 2019 verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.
ms.openlocfilehash: 2d439462fa103cc16fd7ae70b79364be7d79803a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016106"
---
# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows, Audiodateien und Kontaktobjekten der beweglichen Reaktionsgruppe aus der Legacy Bereitstellung in den Skype for Business Server 2019-Pool. Nachdem Sie Ihre Legacy-Reaktionsgruppen migriert haben, werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Pool Skype for Business Server 2019 verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.
  
> [!NOTE]
> Obwohl Sie Reaktionsgruppen migrieren können, bevor Sie alle Benutzer in den Pool Skype for Business Server 2019 verschieben, wird empfohlen, dass Sie zuerst alle Benutzer verschieben. Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, verfügen erst dann über die vollständige Funktionalität der neuen Features, wenn Sie in den Pool Skype for Business Server 2019 verschoben werden. 
  
Bevor Sie Reaktionsgruppen migrieren, müssen Sie einen Skype for Business Server 2019-Pool bereitgestellt haben, der das Reaktionsgruppenanwendung enthält. Das Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert. Sie können sicherstellen, dass die Reaktionsgruppenanwendung installiert wird, indem Sie das Cmdlet **Get-CsService-ApplicationServer** ausführen. 
  
> [!NOTE]
> Sie können neue Skype for Business Server 2019-Reaktionsgruppen im Pool Skype for Business Server 2019 erstellen, bevor Sie Ihre Legacy-Reaktionsgruppen migrieren. 
  
Um Reaktionsgruppen von einem Legacy Pool zu Skype for Business Server 2019 zu migrieren, führen Sie das Cmdlet " **verschieben-CsRgsConfiguration** " aus. 
  
> [!IMPORTANT]
> Das Cmdlet für die Reaktionsgruppen Migration verschiebt die Reaktionsgruppen Konfiguration für den gesamten Pool. Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich. 
  
Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie Skype for Business Server Systemsteuerung oder Skype for Business Server Cmdlets der Verwaltungsshell verwenden, um zu überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden. 
  
Wenn Sie Reaktionsgruppen migrieren, werden die Legacy-Reaktionsgruppen nicht entfernt. Wenn Sie Reaktionsgruppen nach der Migration mithilfe von Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell verwalten, können Sie sowohl die Legacy-Reaktionsgruppen als auch die Skype for Business Server 2019-Reaktionsgruppen anzeigen. Sie sollten Updates nur auf die Skype for Business Server 2019-Reaktionsgruppen anwenden. Die Legacy-Reaktionsgruppen werden nur für Rollback-Zwecke beibehalten. 
  
> [!CAUTION]
> Nachdem die Migration abgeschlossen ist und die neuen Reaktionsgruppen erstellt wurden, werden in der Skype for Business Server-Systemsteuerung und in der Skype for Business Server-Verwaltungsshell die Versionen Legacy und Skype for Business Server 2019 der einzelnen Antworten angezeigt. Gruppe. Verwenden Sie nicht Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell, um die Vorgänger Reaktionsgruppen zu entfernen. Wenn Sie eine entfernen, wird die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr funktionieren. Die Legacy-Reaktionsgruppen werden entfernt, wenn Sie den Legacy Pool außer Betrieb nehmen. 
  
> [!IMPORTANT]
> Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren. Wenn eine ältere Reaktionsgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, um wieder Skype for Business Server 2019-Reaktionsgruppen zu erhalten. 
  
In Skype for Business Server 2019 wird ein neues Reaktionsgruppen Feature mit dem Namen **Workflowtyp**eingeführt. Der **Workflowtyp** kann **Verwaltet** oder **Nicht veraltet** sein. Alle Reaktionsgruppen werden mit dem **Workflowtyp****Nicht verwaltet** und mit leerer Manager-Liste migriert. 
  
Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, bleiben die Agent-Gruppen, Warteschlangen, Workflows und Audiodateien zu Wiederherstellungszwecken im Vorversionspool. Wenn Sie jedoch keinen Rollback zum Vorversionspool durchführen müssen, müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte wieder in den Vorversionspool zu verschieben. 
  
Bei der folgenden Vorgehensweise für die Migration von Reaktionsgruppen Konfigurationen wird vorausgesetzt, dass Sie eine 1:1-Beziehung zwischen Ihren Legacy Pools und den Skype for Business Server 2019-Pools haben. Wenn Sie während der Migration und Bereitstellung Pools konsolidieren oder aufteilen möchten, müssen Sie planen, welche Legacy-Poolkarten Skype for Business Server Pool 2019.
  
## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppen Konfigurationen

1. Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe RTCUniversalServerAdmins ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Ausführen
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Beispiel:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Nachdem Sie Reaktionsgruppen und Agents in den Skype for Business Server 2019-Pool migriert haben, ist die URL, die Agents zur Anmeldung und Abmeldung verwenden, eine Skype for Business Server 2019-URL und steht im Menü **Extras** zur Verfügung. Erinnern Sie Agents daran, sämtliche Referenzen, beispielsweise Lesezeichen, auf die neue URL zu aktualisieren. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>So überprüfen Sie die Migration von Reaktionsgruppen mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von Skype for Business Server Systemsteuerung verwenden können, finden Sie unter [Open Skype for Business Server 2019 Administrative Tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.
    
4. Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in ihrer Legacyumgebung in der Liste enthalten sind. 
    
5. Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in ihrer Legacyumgebung in der Liste enthalten sind. 
    
6. Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentgruppen in ihrer Legacyumgebung in der Liste enthalten sind. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>So überprüfen Sie die Migration von Reaktionsgruppen mithilfe von Skype for Business Server Management Shell

1. Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
    Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Ausführen
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Stellen Sie sicher, dass alle Agentengruppen in ihrer Legacyumgebung in der Liste enthalten sind.
    
5. Ausführen
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Stellen Sie sicher, dass alle Warteschlangen in ihrer Legacyumgebung in der Liste enthalten sind.
    
7. Ausführen
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Stellen Sie sicher, dass alle Workflows in ihrer Legacyumgebung in der Liste enthalten sind.
    

