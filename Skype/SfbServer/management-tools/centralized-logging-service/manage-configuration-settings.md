---
title: Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Zusammenfassung: Informationen Sie zum Abrufen, aktualisieren und Erstellen von Konfigurationseinstellungen für den Dienst für die zentralisierte Protokollierung in Skype für Business Server 2015.'
ms.openlocfilehash: 8fe02cc4d2c04f9433736c4bced429f84f84d915
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Abrufen, aktualisieren und Erstellen von Konfigurationseinstellungen für den Dienst für die zentralisierte Protokollierung in Skype für Business Server 2015.
  
Der zentralisierte Protokollierungsdienst ist gesteuert und von Einstellungen und Parameter, die erstellt und von der Centralized Logging Service: Controller (CLSController) verwendet, um Befehle senden an den einzelnen Computern Centralized Logging Service Agent (konfiguriert CLSAgent). Der Agent verarbeitet die an ihn gesendeten Befehle und verwendet (im Falle eines Start-Befehls) die Konfiguration der Szenarien, Anbieter, Ablaufverfolgungsdauer und Flags, um mit der Erfassung von Ablaufverfolgungsprotokollen gemäß den bereitgestellten Konfigurationsinformationen zu beginnen.
  
> [!IMPORTANT]
>  Nicht alle Windows PowerShell-Cmdlets für die zentralisierte Protokollierungsdienst aufgeführt sind für die Verwendung mit Skype für lokale Bereitstellungen Business Server 2015 vorgesehen. Obwohl sie angezeigt werden können, arbeiten die folgenden Cmdlets nicht geeignet für Business Server 2015 lokale Bereitstellungen mit Skype-Funktion:

-  **"Csclsregion"-Cmdlets:** ["Get-csclsregion"](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,["Set-csclsregion"](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), ["New-csclsregion"](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)und ["Remove-csclsregion"](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps). 
-  **"Csclssearchterm"-Cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) und [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).  
-  **"Csclssecuritygroup"-Cmdlets:** ["Get-csclssecuritygroup"](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), ["Set-csclssecuritygroup"](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), ["New-csclssecuritygroup"](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)und ["Remove-csclssecuritygroup"](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps). 

Die in diesen Cmdlets definierten Einstellungen nicht beeinträchtigen oder nachteiligen Verhalten verursachen, aber für die Verwendung mit Microsoft Office 365 vorgesehen sind und ergibt nicht die erwarteten Ergebnisse in lokalen Bereitstellungen. Das bedeutet nicht, dass diese Cmdlets in lokalen Bereitstellungen nicht von Nutzen sind, ihre Verwendung ist aber ein komplexes Thema, dessen Beschreibung den Rahmen dieser Dokumentation sprengen würde.
  
In einem Bereich, der einem einzelnen Computer oder einen Pool von Computern enthält, eine auf Standortebene (d. h., einer definierten Site wie etwa dem Standort "Redmond", die eine Sammlung von Computer und Pools in Ihrer Bereitstellung enthält) oder in einem globalen Gültigkeitsbereich (das ist, kann der zentralisierte Protokollierungsdienst ausgeführt werden alle Computer und Pools in Ihrer Bereitstellung).
  
Um den Bereich Centralized Logging Service konfigurieren, indem Sie die Skype für Business Server-Verwaltungsshell verwenden, müssen Sie Mitglied der Administratorrolle CsAdministrator oder der Sicherheitsgruppen CsServerAdministrator rollenbasierten Zugriffssteuerung (RBAC) oder eine benutzerdefinierte RBAC-Rolle sein, enthält eine der beiden Gruppen. Um eine Liste aller RBAC-Rollen, die mit diesem Cmdlet zugewiesen wurde (auch alle benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl aus der Skype für Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung ein:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Beispiel:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Es gibt grundlegende Unterschiede zwischen die Befehle des Befehlszeilentools, die Sie in Windows PowerShell oder CLSController ausführen können. Windows PowerShell bietet eine umfassende-Methode zum Konfigurieren und Szenarien definieren und diese Szenarien auf sinnvolle Weise für Ihre Szenarien der Problembehandlung wiederverwenden. Während der CLSController eine schnelle und effiziente Möglichkeit bietet, Befehle einzugeben und Ergebnisse zu erhalten, ist der Befehlssatz für den CLSController auf die begrenzte Anzahl der über die Befehlszeile verfügbaren Befehle beschränkt. Im Gegensatz zu Windows PowerShell-Cmdlets können nicht CLSController neue Szenarien definieren, verwalten Bereich auf einer Website oder globaler Ebene und viele andere Nachteile einer endlichen Befehlssatz, der dynamisch konfiguriert werden können. CLSController bietet eine Möglichkeit für die schnelle Ausführung bietet Windows PowerShell eine Möglichkeit zum Erweitern der Funktionalität Centralized Logging Service jenseits was mit CLSController möglich ist. 
  
Ein einzelner Computer Bereich kann während der Ausführung von ["Search-csclslogging"](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), ["Show-csclslogging"](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), ["Start-csclslogging"](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), ["Stop-csclslogging"](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), ["Sync-csclslogging"](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) und ["Update-csclslogging"](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) definiert werden Befehl mit den Computern-Parameter. Die - Computer Parameter akzeptiert eine durch Kommas getrennte Liste der vollqualifizierten Domänennamen (FQDNs) für den Zielcomputer.
  
> [!TIP]
> Sie können auch - Pools und definieren eine durch Kommas getrennte Liste von Pools, die die protokollierungsbefehle ausgeführt werden soll. 
  
Website- und Global Bereiche sind in die Cmdlets **New-**, **Set-** und **Remove -** Centralized Logging Service definiert. Die folgenden Beispiele zeigen, wie ein Standortbereich und ein globaler Bereich festgelegt werden.
  
> [!IMPORTANT]
> Parameter und Konzepte, die in anderen Abschnitten besprochen werden, können mit den Befehlen enthalten. Die Beispielbefehle sollen veranschaulichen die Verwendung von der **-Identität** Parameter Bereich zu definieren, und die anderen Parameter auf Vollständigkeit und an den Bereich enthalten sind. Ausführliche Informationen zu den Cmdlets **"Set-csclsconfiguration"** finden Sie unter [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in der Betriebsdokumentation.
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Abrufen die aktuelle Centralized Logging Service-Konfiguration

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
  ```
  Get-CsClsConfiguration
  ```

Verwenden Sie die Cmdlets **New-CsClsConfiguration** und **Set-CsClsConfiguration** , um eine neue Konfiguration zu erstellen oder eine vorhandene Konfiguration zu aktualisieren. Beim Ausführen von **"Get-csclsconfiguration"** werden Informationen ähnlich dem folgenden Screenshot, bei die Bereitstellung aktuell die standardmäßige globale Konfiguration, aber keine Standortkonfigurationen definiert hat angezeigt:
  
![Beispielausgabe von Get-CsClsConfiguration](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Abrufen die aktuelle Centralized Logging Service-Konfiguration aus dem lokalen Speicher des Computers

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

Wenn Sie verwenden im ersten Beispiel, in dem gibt **"Get-csclsconfiguration"** beliebigen Parametern, die Befehl Verweise keinen zentralen Verwaltungsspeichers für die Daten. Wenn Sie angeben, dass den Parameter verweist auf - LokalerSpeicher, den Befehl auf den Computer LokalerSpeicher anstelle des zentralen Verwaltungsspeichers aus.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>So rufen Sie eine Liste der aktuell definierten Szenarien ab

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    Um z. B. die für den globalen Bereich definierten Szenarien abzurufen:
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

Das Cmdlet **"Get-csclsconfiguration"** werden die Szenarien, die Teil der Konfiguration eines bestimmten Bereichs sind immer angezeigt. In den meisten Fällen werden nicht alle Szenarien angezeigt und es wird gekürzt. Der hier verwendete Befehl erstellt eine Liste aller Szenarien mit Teilinformationen darüber, welche Anbieter, Einstellungen und Flags verwendet werden.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>So aktualisieren Sie einen globalen Bereich für die zentralisierte Protokollierungsdienst mithilfe von Windows PowerShell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  Beispiel:
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

Der Befehl trägt dem CLSAgent auf allen Computern und in allen Pools der Bereitstellung auf, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Dieser Befehl wirkt sich auf alle Computer und Pools an allen Standorten aus und ändert deren konfigurierten Rollover-Wert in 40 MB.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>So aktualisieren Sie einen standortbereich für die zentralisierte Protokollierungsdienst mithilfe von Windows PowerShell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  Beispiel:
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> Wie im Beispiel gezeigt ist der Standardspeicherort der Protokolldateien „%TEMP%\Tracing“. Da es jedoch der CLSAgent ist, der die Datei tatsächlich schreibt, und da der CSLAgent als Netzwerkdienst ausgeführt wird, wird die Variable %TEMP% zu „%WINDIR%\ServiceProfiles\NetworkService\AppData\Local“ erweitert. 
  
Der Befehl trägt dem CLSAgent auf allen Computern und in allen Pools am Standort Redmond auf, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Computer und Pools an anderen Standorten sind von dem Befehl nicht betroffen und verwenden weiterhin den aktuell konfigurierten Rollover-Wert für die Tracing-Datei – der entweder durch den Standardwert (20 MB) oder bei der Anmeldung definiert wird.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>So erstellen Sie eine neue Centralized Logging Service-Konfiguration

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > „New-CsClsConfiguration“ bietet Zugriff auf eine Vielzahl optionaler Konfigurationseinstellungen. Ausführliche Informationen zu den Konfigurationsoptionen finden Sie unter [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) und [Grundlegendes zu Centralized Logging Service Configuration Settings](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx). 
  
Wenn Sie z. B. eine neue Konfiguration erstellen möchten, die einen Netzwerkordner für Cachedateien, den Rollover-Zeitraum für die Protokolldateien und die Rollover-Größe für die Protokolldateien definiert, können Sie folgenden Befehl eingeben:
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Sie sollten sorgfältig planen die Erstellung von neuen Konfigurationen und wie Sie neue Eigenschaften für den Dienst für die zentralisierte Protokollierung definieren. Gehen Sie vorsichtig vor, wenn Sie Änderungen durchführen, und stellen Sie sicher, dass Ihnen die Auswirkungen auf die Möglichkeit, Problemszenarien richtig zu protokollieren, bewusst sind. Änderungen an der Konfiguration sollten Sie durchführen, um Ihre Möglichkeiten zur Verwaltung der Protokolle mit einer Größe und einem Rollover-Zeitraum so zu verbessern, dass Sie Probleme bei ihrem Auftreten lösen können.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>So entfernen eine vorhandene Konfiguration des Centralized Logging Service

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

Um eine zentralisierte Protokollierungsdienst Konfiguration entfernen, die Sie erstellt haben, um die Zeit des Protokolls Datei Rollover zu erhöhen, erhöhen Sie die Größe der Protokolldatei Rollover, und legen Sie den Speicherort der Protokolldatei Cache wie folgt auf einer Netzwerkfreigabe aus:
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Dies ist die neue Konfiguration, die im Verfahren "So"erstellen Sie eine neue Konfiguration der zentralisierte Protokollierungsdienst. erstellt wurde 
  
Wenn Sie eine Konfiguration auf Standortebene löschen, verwendet der Standort anschließend die globalen Einstellungen.
## <a name="see-also"></a>Siehe auch

#### 

[Konfigurieren von Anbietern für zentralisierte Protokollierungsdienst in Skype für Business Server 2015](configure-providers.md)
  
[Konfigurieren von Szenarien für die zentralisierte Protokollierungsdienst in Skype Business Server 2015](configure-scenarios.md)

[Zentraler Protokollierungsdienst in Skype für Business 2015](centralized-logging-service.md)

["Set-csclsconfiguration"](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
["Get-csclsconfiguration"](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
["New-csclsconfiguration"](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
["Remove-csclsconfiguration"](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

