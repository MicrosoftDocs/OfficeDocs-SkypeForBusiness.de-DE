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
localization_priority: Normal
description: Nachdem Ihre Benutzer zu Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows, Audiodateien und das Verschieben von Reaktionsgruppenkontaktobjekten aus der Legacybereitstellung in den Skype for Business Server 2019-Pool. Nach der Migration Ihrer Legacyantwortgruppen werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Skype for Business Server 2019-Pool verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.
ms.openlocfilehash: bf4087440fb112cb1af906e1a0915531eea08456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113271"
---
# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

Nachdem Ihre Benutzer zu Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows, Audiodateien und das Verschieben von Reaktionsgruppenkontaktobjekten aus der Legacybereitstellung in den Skype for Business Server 2019-Pool. Nach der Migration Ihrer Legacyantwortgruppen werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Skype for Business Server 2019-Pool verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.
  
> [!NOTE]
> Obwohl Sie Reaktionsgruppen migrieren können, bevor Sie alle Benutzer in den Skype for Business Server 2019-Pool verschieben, wird empfohlen, zuerst alle Benutzer zu verschieben. Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, verfügen erst dann über die volle Funktionalität neuer Features, wenn sie in den Skype for Business Server 2019-Pool verschoben werden. 
  
Bevor Sie Reaktionsgruppen migrieren, müssen Sie einen Skype for Business Server 2019-Pool bereitgestellt haben, der die Reaktionsgruppenanwendung enthält. Die Reaktionsgruppe-Anwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP. Sie können sicherstellen, dass die Reaktionsgruppeanwendung installiert ist, indem Sie das **Cmdlet Get-CsService -ApplicationServer** ausführen. 
  
> [!NOTE]
> Sie können neue Skype for Business Server 2019-Reaktionsgruppen im Skype for Business Server 2019-Pool erstellen, bevor Sie Ihre älteren Reaktionsgruppen migrieren. 
  
Zum Migrieren von Reaktionsgruppen aus einem Legacypool zu Skype for Business Server 2019 führen Sie das **Cmdlet Move-CsRgsConfiguration** aus. 
  
> [!IMPORTANT]
> Das Migrations-Cmdlet Reaktionsgruppe verschiebt die Konfiguration der Reaktionsgruppe für den gesamten Pool. Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich. 
  
Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell-Cmdlets überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden. 
  
Wenn Sie Reaktionsgruppen migrieren, werden die Legacyantwortgruppen nicht entfernt. Wenn Sie Reaktionsgruppen nach der Migration mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell verwalten, werden sowohl die Legacyantwortgruppen als auch die Skype for Business Server 2019-Reaktionsgruppen angezeigt. Sie sollten Updates nur auf die Skype for Business Server 2019-Reaktionsgruppen anwenden. Die Legacyantwortgruppen werden nur zu Rollbackzwecken beibehalten. 
  
> [!CAUTION]
> Nachdem die Migration abgeschlossen und die neuen Reaktionsgruppen erstellt wurden, werden in der Skype for Business Server-Systemsteuerung und in der Skype for Business Server-Verwaltungsshell die Versionen legacy und Skype for Business Server 2019 jeder Reaktionsgruppe angezeigt. Verwenden Sie keine Skype for Business Server-Systemsteuerung oder Skype for Business Server-Verwaltungsshell, um die älteren Reaktionsgruppen zu entfernen. Wenn Sie eine entfernen, funktioniert die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr. Die Legacyantwortgruppen werden entfernt, wenn Sie den Legacypool außer Betrieb gesetzt haben. 
  
> [!IMPORTANT]
> Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren. Wenn eine ältere Reaktionsgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, um skype for Business Server 2019-Reaktionsgruppen erneut ausführen zu lassen. 
  
Skype for Business Server 2019 führt ein neues Reaktionsgruppe-Feature namens **Workflowtyp ein.** Der **Workflowtyp** kann **Verwaltet** oder **Nicht veraltet** sein. Alle Reaktionsgruppen werden mit dem **Workflowtyp****Nicht verwaltet** und mit leerer Manager-Liste migriert. 
  
Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, bleiben die Agent-Gruppen, Warteschlangen, Workflows und Audiodateien zu Wiederherstellungszwecken im Vorversionspool. Wenn Sie jedoch keinen Rollback zum Vorversionspool durchführen müssen, müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte wieder in den Vorversionspool zu verschieben. 
  
Bei dem folgenden Verfahren zum Migrieren von Reaktionsgruppekonfigurationen wird davon ausgegangen, dass Sie eine 1:1-Beziehung zwischen Ihren Legacypools und den Skype for Business Server 2019-Pools haben. Wenn Sie planen, Während Der Migration und Bereitstellung Pools zu konsolidieren oder aufteilen, müssen Sie planen, welcher Legacypool welchem Skype for Business Server 2019-Pool zu ordnet.
  
## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppe-Konfigurationen

1. Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe RTCUniversalServerAdmins ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** klicken Sie **auf Microsoft Skype for Business Server 2019,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie  aus.
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Beispiel:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Nachdem Sie Reaktionsgruppen und Agents zum Skype for Business Server 2019-Pool migriert haben, ist die URL, die Agents zum Anmelden und Abmelden verwenden, eine Skype for Business Server 2019-URL und steht im Menü **Extras** zur Verfügung. Erinnern Sie Agents daran, sämtliche Referenzen, beispielsweise Lesezeichen, auf die neue URL zu aktualisieren. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>So überprüfen Sie die Migration der Reaktionsgruppe mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden zum Starten der Skype for Business Server-Systemsteuerung finden Sie unter [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.
    
4. Überprüfen Sie **auf** der Registerkarte Workflow, ob alle Workflows in Ihrer Legacyumgebung in der Liste enthalten sind. 
    
5. Klicken Sie **auf die** Registerkarte Warteschlange, und stellen Sie sicher, dass alle Warteschlangen in Ihrer Legacyumgebung in der Liste enthalten sind. 
    
6. Klicken Sie **auf die** Registerkarte Gruppe, und vergewissern Sie sich, dass alle Agentgruppen in Ihrer Legacyumgebung in der Liste enthalten sind. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>So überprüfen Sie die Migration der Reaktionsgruppe mithilfe der Skype for Business Server-Verwaltungsshell

1. Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** klicken Sie **auf Microsoft Skype for Business Server 2019,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
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

8. Stellen Sie sicher, dass alle Workflows in Ihrer Legacyumgebung in der Liste enthalten sind.
