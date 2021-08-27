---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Das Migrieren von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschleifen, Workflows, Audiodateien und das Verschieben von Reaktionsgruppenkontaktobjekten aus der Legacybereitstellung in den Skype for Business Server 2019-Pool. Nachdem Sie Ihre älteren Reaktionsgruppen migriert haben, werden Aufrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Pool Skype for Business Server 2019 verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.
ms.openlocfilehash: 96eecb0ad10a900a9d00d26383e149ceec4cbfe8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588027"
---
# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Das Migrieren von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschleifen, Workflows, Audiodateien und das Verschieben von Reaktionsgruppenkontaktobjekten aus der Legacybereitstellung in den Skype for Business Server 2019-Pool. Nachdem Sie Ihre älteren Reaktionsgruppen migriert haben, werden Aufrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Pool Skype for Business Server 2019 verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.
  
> [!NOTE]
> Sie können zwar Reaktionsgruppen migrieren, bevor Sie alle Benutzer in den Skype for Business Server 2019-Pool verschieben, es wird jedoch empfohlen, alle Benutzer zuerst zu verschieben. Insbesondere haben Benutzer, die Reaktionsgruppen-Agents sind, erst dann die volle Funktionalität neuer Features, wenn sie in den Pool Skype for Business Server 2019 verschoben werden. 
  
Bevor Sie Reaktionsgruppen migrieren, müssen Sie einen Skype for Business Server 2019-Pool bereitgestellt haben, der die Reaktionsgruppenanwendung enthält. Die Reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen. Sie können sicherstellen, dass die Reaktionsgruppenanwendung installiert ist, indem Sie das Cmdlet **"Get-CsService -ApplicationServer"** ausführen. 
  
> [!NOTE]
> Sie können neue Skype for Business Server 2019-Reaktionsgruppen im Skype for Business Server 2019-Pool erstellen, bevor Sie Ihre älteren Reaktionsgruppen migrieren. 
  
Zum Migrieren von Reaktionsgruppen aus einem Legacypool zum Skype for Business Server 2019 führen Sie das Cmdlet **Move-CsRgsConfiguration** aus. 
  
> [!IMPORTANT]
> Das Migrations-Cmdlet "Reaktionsgruppe" verschiebt die Reaktionsgruppenkonfiguration für den gesamten Pool. Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich. 
  
Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden. 
  
Wenn Sie Reaktionsgruppen migrieren, werden die älteren Reaktionsgruppen nicht entfernt. Wenn Sie Reaktionsgruppen nach der Migration mithilfe Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell verwalten, können Sie sowohl die älteren Reaktionsgruppen als auch die Skype for Business Server 2019-Reaktionsgruppen anzeigen. Sie sollten Updates nur auf die Skype for Business Server 2019-Reaktionsgruppen anwenden. Die älteren Reaktionsgruppen werden nur für Rollbackzwecke beibehalten. 
  
> [!CAUTION]
> Nachdem die Migration abgeschlossen und die neuen Reaktionsgruppen erstellt wurden, zeigen die Skype for Business Server Systemsteuerung und die Skype for Business Server-Verwaltungsshell die Legacy- und Skype for Business Server 2019-Versionen jeder Reaktionsgruppe an. Verwenden Sie Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell nicht, um die älteren Reaktionsgruppen zu entfernen. Wenn Sie eine Gruppe entfernen, funktioniert die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr. Die Legacyantwortgruppen werden entfernt, wenn Sie den Legacypool außer Betrieb genommen haben. 
  
> [!IMPORTANT]
> Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren. Wenn eine ältere Reaktionsgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, um Skype for Business Server 2019-Reaktionsgruppen erneut auszuführen. 
  
Skype for Business Server 2019 wird ein neues Reaktionsgruppenfeature namens **Workflowtyp** eingeführt. Der **Workflowtyp** kann **Verwaltet** oder **Nicht veraltet** sein. Alle Reaktionsgruppen werden mit dem **Workflowtyp****Nicht verwaltet** und mit leerer Manager-Liste migriert. 
  
Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, verbleiben die Agentgruppen, Warteschlangen, Workflows und Audiodateien für mögliche Rollbacks im Vorversionspool. Wenn Sie jedoch keinen Rollback zum Vorversionspool durchführen müssen, müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte wieder in den Vorversionspool zu verschieben. 
  
Im folgenden Verfahren für die Migration von Reaktionsgruppenkonfigurationen wird davon ausgegangen, dass Sie eine 1:1-Beziehung zwischen Ihren älteren Pools und den pools Skype for Business Server 2019 haben. Wenn Sie planen, Pools während der Migration und Bereitstellung zu konsolidieren oder aufzuteilen, müssen Sie planen, welcher Legacypool welchem Pool Skype for Business Server 2019 zugeordnet ist.
  
## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppenkonfigurationen

1. Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe RTCUniversalServerAdmins ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Microsoft Skype for Business Server 2019"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie  aus.
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Beispiel:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Nach der Migration von Reaktionsgruppen und Agents zum pool Skype for Business Server 2019 ist die URL, die Agents zum Anmelden und Abmelden verwenden, eine Skype for Business Server 2019-URL und steht im Menü **"Extras"** zur Verfügung. Erinnern Sie Agents daran, sämtliche Referenzen, beispielsweise Lesezeichen, auf die neue URL zu aktualisieren. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>So überprüfen Sie die Migration von Reaktionsgruppen mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten Skype for Business Server Systemsteuerung verwenden können, finden Sie unter [Open Skype for Business Server 2019 administrative Tools.](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools) 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.
    
4. Überprüfen Sie auf der Registerkarte **"Workflow",** ob alle Workflows in Ihrer Legacyumgebung in der Liste enthalten sind. 
    
5. Klicken Sie auf die Registerkarte **"Warteschlange",** und stellen Sie sicher, dass alle Warteschlangen in Ihrer Legacyumgebung in der Liste enthalten sind. 
    
6. Klicken Sie auf die Registerkarte **"Gruppe",** und stellen Sie sicher, dass alle Agentgruppen in Ihrer Legacyumgebung in der Liste enthalten sind. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>So überprüfen Sie die Reaktionsgruppenmigration mithilfe Skype for Business Server-Verwaltungsshell

1. Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Microsoft Skype for Business Server 2019"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
    Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Führen Sie  aus.
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Stellen Sie sicher, dass alle Agentgruppen in Ihrer Legacyumgebung in der Liste enthalten sind.
    
5. Führen Sie  aus.
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Stellen Sie sicher, dass alle Warteschlangen in Ihrer Legacyumgebung in der Liste enthalten sind.
    
7. Führen Sie  aus.
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Stellen Sie sicher, dass alle Workflows in Ihrer älteren Umgebung in der Liste enthalten sind.
