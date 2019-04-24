---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Ihre Benutzer in Skype für Business Server 2019 Pools verschoben werden, können Sie Ihre reaktionsgruppen migrieren. Migrieren von Antwort Gruppen enthält, agentgruppen, Warteschlangen, Workflows, Audiodateien kopieren und Verschieben von Kontaktobjekten Response Group aus der Bereitstellung der Vorversion in der Skype für Business Server 2019 Pool. Nach dem Migrieren von reaktionsgruppen von Vorversionen werden Anrufe an die reaktionsgruppen von der Anwendung "Reaktionsgruppe" in der Skype für Business Server 2019 Pool behandelt. Aufrufe von reaktionsgruppen werden nicht mehr vom vorversionspool behandelt.
ms.openlocfilehash: 17ba19be3b574436f3a175457264654d8c28ebd0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231651"
---
# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

Nachdem Ihre Benutzer in Skype für Business Server 2019 Pools verschoben werden, können Sie Ihre reaktionsgruppen migrieren. Migrieren von Antwort Gruppen enthält, agentgruppen, Warteschlangen, Workflows, Audiodateien kopieren und Verschieben von Kontaktobjekten Response Group aus der Bereitstellung der Vorversion in der Skype für Business Server 2019 Pool. Nach dem Migrieren von reaktionsgruppen von Vorversionen werden Anrufe an die reaktionsgruppen von der Anwendung "Reaktionsgruppe" in der Skype für Business Server 2019 Pool behandelt. Aufrufe von reaktionsgruppen werden nicht mehr vom vorversionspool behandelt.
  
> [!NOTE]
> Obwohl Sie reaktionsgruppen migrieren können, bevor Sie alle Benutzer in der Skype für Business Server 2019 Pool verschieben, wird empfohlen, zunächst alle Benutzer zu verschieben. Insbesondere haben Benutzer, die reaktionsgruppen-Agenten sind keinen vollen Funktionsumfang von neuen Features, bis sie an der Skype für Business Server 2019 Pool verschoben werden. 
  
Bevor Sie reaktionsgruppen migrieren, Sie müssen einen Skype für Business Server 2019 Pool bereitgestellt worden sein, die die Anwendung "Reaktionsgruppe" enthält. Die Anwendung "Reaktionsgruppe" wird installiert, und bei der Bereitstellung von Enterprise-VoIP standardmäßig aktiviert. Sie können sicherstellen, dass die Anwendung "Reaktionsgruppe" durch Ausführen des Cmdlets **Get-CsService-ApplicationServer** installiert ist. 
  
> [!NOTE]
> Sie können neue Skype für reaktionsgruppen Business Server 2019 vor der Migration von reaktionsgruppen von Vorversionen in der Skype für Business Server 2019 Pool erstellen. 
  
Um reaktionsgruppen aus einem vorversionspool zum der Skype für Business Server 2019 zu migrieren, führen Sie das Cmdlet **Move-CsRgsConfiguration** aus. 
  
> [!IMPORTANT]
> Das Cmdlet "Migration" Reaktionsgruppe "" wird die reaktionsgruppenkonfiguration für den gesamten Pool verschoben. Sie können keine bestimmte Gruppen, Warteschlangen oder Workflows zum Migrieren auswählen. 
  
Nach der Migration der reaktionsgruppen müssen Sie Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell-Cmdlets verwenden, um sicherzustellen, dass alle agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden. 
  
Beim Migrieren von reaktionsgruppen werden die Vorversion reaktionsgruppen nicht entfernt. Wenn Sie reaktionsgruppen nach der Migration mit entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell verwalten, können Sie die Vorversion reaktionsgruppen und die Skype für reaktionsgruppen Business Server 2019 sehen. Sie sollten nur für die Skype für reaktionsgruppen Business Server 2019 Updates anwenden. Die Vorversion reaktionsgruppen werden nur für Wiederherstellungszwecke beibehalten. 
  
> [!CAUTION]
> Nach die Migration abgeschlossen wurde und die neue reaktionsgruppen erstellt wurden, der Skype Business Server-Systemsteuerung und die Skype für Business Server-Verwaltungsshell zeigt der Vorgängerversion und Skype für Business Server 2019 Versionen von Antwort Mitglied der Gruppe. Verwenden Sie die Skype nicht für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell, um die Vorversion reaktionsgruppen zu entfernen. Wenn Sie eine entfernen, wird die entsprechende Antwort-Gruppe, die während der Migration erstellt wurde arbeiten beendet. Legacy reaktionsgruppen werden entfernt, wenn Sie Pool den Vorgängerversion außer Betrieb nehmen. 
  
> [!IMPORTANT]
> Es wird empfohlen, dass Sie keine Daten aus der ursprünglichen Bereitstellung entfernen, bis Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, unmittelbar nach dem Migrieren von reaktionsgruppen zu exportieren. Wenn eine ältere reaktionsgruppe entfernt erhalten möchten sollte, können Sie aus der Sicherung zum Abrufen von Skype für Business Server 2019 reaktionsgruppen erneut ausführen Ihrer reaktionsgruppen wiederherstellen. 
  
Skype für Business Server 2019 führt eine neue Reaktionsgruppe-Funktion, die **Für den Workflow**aufgerufen. **Workflowtyp** können **verwaltete** oder **nicht verwaltet**werden. Alle reaktionsgruppen werden mit **Workflowtyp** **nicht verwaltet** festgelegt und eine leere managerliste migriert. 
  
Wenn Sie das **Move-CsRgsConfiguration** -Cmdlet ausführen, bleiben die agentgruppen, Warteschlangen, Workflows und Audiodateien in den Pool der Vorgängerversion für Wiederherstellungszwecke. Wenn Sie einen Rollback zu Pool der Vorgängerversion benötigen, müssen Sie jedoch mit dem Cmdlet **Move-CsApplicationEndpoint** zum Verschieben von Kontaktobjekten wieder in Pool der Vorgängerversion ausführen. 
  
Migrieren von Reaktionsgruppen Konfigurationen im folgende Verfahren wird davon ausgegangen, dass Sie eine 1: 1-Beziehung zwischen Pools der Vorversion und die Skype für Business Server 2019 Pools verfügen. Wenn Sie beabsichtigen, konsolidieren oder Pools während der Migration und Bereitstellung aufgeteilt, müssen Sie planen, welche Skype für Business Server 2019 Pool welchen legacy-Pool zugeordnet ist.
  
## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppen-Konfigurationen

1. Melden Sie sich an dem Computer mit einem Konto an, das Mitglied der Gruppe RTCUniversalServerAdmins oder über entsprechende Administratorrechte und-Berechtigungen verfügt.
    
2. Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.
    
3. Führen Sie folgenden Befehl aus:
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Beispiel:
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Nach dem Migrieren der reaktionsgruppen und Agents zu den Skype für Business Server 2019 Pool, die URL, die Agents an-und Abmelden verwenden einen Skype für Business Server 2019 URL und steht im Menü **Extras** . Erinnern Sie Agents alle Verweise, wie Lesezeichen, in die neue URL zu aktualisieren. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>So überprüfen Sie die reaktionsgruppenmigration mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich an dem Computer mit einem Konto an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von Skype Business Server-Systemsteuerung verwenden können, finden Sie unter [Open Skype für Business Server 2019 Verwaltungstools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.
    
4. Stellen Sie sicher, dass alle Workflows in der vorgängerumgebung in der Liste enthalten sind, klicken Sie auf der Registerkarte **Workflow** . 
    
5. Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in der vorgängerumgebung in der Liste enthalten sind. 
    
6. Klicken Sie auf der Registerkarte **Gruppe** , und stellen Sie sicher, dass alle agentgruppen in Ihrer legacy-Umgebung in der Liste enthalten sind. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>So überprüfen Sie die reaktionsgruppenmigration mithilfe von Skype für Business Server-Verwaltungsshell

1. Melden Sie sich an dem Computer mit einem Konto an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.
    
2. Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.
    
    Ausführliche Informationen zu den folgenden Cmdlets führen Sie Folgendes aus:
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. Führen Sie folgenden Befehl aus:
    
   ```
   Get-CsRgsAgentGroup
   ```

4. Stellen Sie sicher, dass alle agentgruppen in Ihrer legacy-Umgebung in der Liste enthalten sind.
    
5. Führen Sie folgenden Befehl aus:
    
   ```
   Get-CsRgsQueue
   ```

6. Stellen Sie sicher, dass alle Warteschlangen in der vorgängerumgebung in der Liste enthalten sind.
    
7. Führen Sie folgenden Befehl aus:
    
   ```
   Get-CsRgsWorkflow
   ```

8. Stellen Sie sicher, dass alle Workflows in der vorgängerumgebung in der Liste enthalten sind.
    

