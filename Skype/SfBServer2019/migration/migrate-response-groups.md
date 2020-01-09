---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Zum Migrieren von Reaktionsgruppen gehören das Kopieren von Agentengruppen, Warteschlangen, Workflows, Audiodateien und Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den Skype for Business Server 2019-Pool. Nachdem Sie Ihre Legacy-Antwortgruppen migriert haben, werden die Anrufe an die Reaktionsgruppen von der Antwortgruppen Anwendung im Skype for Business Server 2019-Pool abgewickelt. Anrufe an Reaktionsgruppen werden nicht mehr vom Legacy Pool verarbeitet.
ms.openlocfilehash: 148fbe2ca547c3bd7e3d240e687b37c94d10270b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991110"
---
# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

Nachdem Ihre Benutzer in Skype for Business Server 2019-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Zum Migrieren von Reaktionsgruppen gehören das Kopieren von Agentengruppen, Warteschlangen, Workflows, Audiodateien und Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den Skype for Business Server 2019-Pool. Nachdem Sie Ihre Legacy-Antwortgruppen migriert haben, werden die Anrufe an die Reaktionsgruppen von der Antwortgruppen Anwendung im Skype for Business Server 2019-Pool abgewickelt. Anrufe an Reaktionsgruppen werden nicht mehr vom Legacy Pool verarbeitet.
  
> [!NOTE]
> Obwohl Sie Antwortgruppen migrieren können, bevor Sie alle Benutzer in den Skype for Business Server 2019-Pool verschieben, empfiehlt es sich, alle Benutzer zuerst zu verschieben. Insbesondere haben Benutzer, die Reaktionsgruppen-Agents sind, nicht die vollständige Funktionalität der neuen Features, bis Sie in den Skype for Business Server 2019-Pool verschoben werden. 
  
Bevor Sie Antwortgruppen migrieren, müssen Sie einen Skype for Business Server 2019-Pool bereitgestellt haben, der die reaktionsgruppenanwendung umfasst. Die reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen. Mit dem Cmdlet **Get-CsService-ApplicationServer** können Sie sicherstellen, dass die reaktionsgruppenanwendung installiert ist. 
  
> [!NOTE]
> Sie können neue Skype for Business Server 2019-Antwortgruppen im Skype for Business Server 2019-Pool erstellen, bevor Sie Ihre Legacy-Antwortgruppen migrieren. 
  
Führen Sie das Cmdlet **Move-CsRgsConfiguration** aus, um Reaktionsgruppen aus einem Legacy Pool in den Skype for Business Server 2019 zu migrieren. 
  
> [!IMPORTANT]
> Mit dem Cmdlet "Migration der Reaktionsgruppe" wird die Reaktionsgruppen Konfiguration für den gesamten Pool verschoben. Sie können keine bestimmten Gruppen, Warteschlangen oder Workflows auswählen, die migriert werden sollen. 
  
Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentengruppen,-Warteschlangen und-Workflows erfolgreich verschoben wurden. 
  
Wenn Sie Antwortgruppen migrieren, werden die Legacy Antwortgruppen nicht entfernt. Wenn Sie Antwortgruppen nach der Migration mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell verwalten, können Sie sowohl die Legacy-Antwortgruppen als auch die Skype for Business Server 2019-Reaktionsgruppen anzeigen. Sie sollten Updates nur für die Skype for Business Server 2019-Reaktionsgruppen anwenden. Die Legacy-Antwortgruppen werden nur für Rollback-Zwecke aufbewahrt. 
  
> [!CAUTION]
> Nachdem die Migration abgeschlossen und die neuen Reaktionsgruppen erstellt wurden, werden in der Skype for Business Server-Systemsteuerung und der Skype for Business Server-Verwaltungsshell die Legacy-und Skype for Business Server 2019-Versionen jeder Antwort angezeigt. Gruppe. Verwenden Sie die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell nicht, um die Legacy-Antwortgruppen zu entfernen. Wenn Sie eine entfernen, wird die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr funktionieren. Die Legacy-Antwortgruppen werden entfernt, wenn Sie den Legacy Pool außer Betrieb nehmen. 
  
> [!IMPORTANT]
> Wir empfehlen, dass Sie keine Daten aus Ihrer vorherigen Bereitstellung entfernen, bevor Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, dass Sie Reaktionsgruppen unmittelbar nach der Migration exportieren. Wenn eine ältere Antwortgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, damit die Skype for Business Server 2019-Reaktionsgruppen erneut ausgeführt werden. 
  
Skype for Business Server 2019 führt eine neue Reaktionsgruppen Funktion mit dem Namen **Workflowtyp**ein. Der **Workflowtyp** kann **verwaltet** oder **nicht verwaltet**werden. Alle Antwortgruppen werden migriert, wobei der **Workflowtyp** auf **nicht verwaltet** und mit einer leeren Manager Liste gesetzt ist. 
  
Wenn Sie das Cmdlet **Move-CsRgsConfiguration** ausführen, verbleiben die Agentengruppen,-Warteschlangen,-Workflows und-Audiodateien im Legacy Pool für Rollback-Zwecke. Wenn Sie jedoch einen Rollback zum Legacy Pool durchführen müssen, müssen Sie das Cmdlet **Move-CsApplicationEndpoint** ausführen, um die Kontaktobjekte wieder in den Legacy Pool zu verschieben. 
  
Das folgende Verfahren zum Migrieren von Reaktionsgruppen Konfigurationen setzt voraus, dass Sie über eine 1:1-Beziehung zwischen Ihren Legacy Pools und den Skype for Business Server 2019-Pools verfügen. Wenn Sie während der Migration und Bereitstellung Pools konsolidieren oder aufteilen möchten, müssen Sie die Karten für Legacy Pools planen, die dem Skype for Business Server 2019-Pool zugeordnet sind.
  
## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppen Konfigurationen

1. Melden Sie sich bei dem Computer mit einem Konto an, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über entsprechende Administratorrechte und-Berechtigungen verfügt.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie folgenden Befehl aus:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Beispiel:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Nachdem Sie Antwortgruppen und Agents in den Skype for Business Server 2019-Pool migriert haben, ist die URL, die die Agents zum Anmelden und Abmelden verwenden, eine Skype for Business Server 2019-URL und steht im Menü **Extras** zur Verfügung. Erinnern Sie die Agents daran, alle Verweise wie Textmarken auf die neue URL zu aktualisieren. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich bei dem Computer mit einem Konto an, das Mitglied der RTCUniversalReadOnlyAdmins-Gruppe ist, oder wenn es sich um eine minimale Mitgliedschaft in der CsViewOnlyAdministrator-Rolle handelt.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten von Skype for Business Server Control Panel verwenden können, finden Sie unter [Öffnen von Skype for Business Server 2019-Verwaltungstools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.
    
4. Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in ihrer Legacyumgebung in der Liste enthalten sind. 
    
5. Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in ihrer Legacyumgebung in der Liste enthalten sind. 
    
6. Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentengruppen in ihrer Legacyumgebung in der Liste enthalten sind. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der Skype for Business Server-Verwaltungsshell

1. Melden Sie sich bei dem Computer mit einem Konto an, das Mitglied der RTCUniversalReadOnlyAdmins-Gruppe ist, oder wenn es sich um eine minimale Mitgliedschaft in der CsViewOnlyAdministrator-Rolle handelt.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
    
    Ausführliche Informationen zu den folgenden Cmdlets finden Sie unter:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Führen Sie folgenden Befehl aus:
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Überprüfen Sie, ob alle Agentengruppen in ihrer Legacyumgebung in der Liste enthalten sind.
    
5. Führen Sie folgenden Befehl aus:
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Überprüfen Sie, ob alle Warteschlangen in ihrer Legacyumgebung in der Liste enthalten sind.
    
7. Führen Sie folgenden Befehl aus:
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Überprüfen Sie, ob alle Workflows in ihrer Legacyumgebung in der Liste enthalten sind.
    

