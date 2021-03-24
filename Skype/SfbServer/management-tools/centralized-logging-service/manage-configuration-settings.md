---
title: Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Zusammenfassung: Informationen zum Abrufen, Aktualisieren und Erstellen von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015.'
ms.openlocfilehash: fb2d66e6ff72bc5fb5a4c8c987713f3ca7030ab5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098861"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015

**Zusammenfassung:** Erfahren Sie, wie Sie Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 abrufen, aktualisieren und erstellen.

Der zentralisierte Protokollierungsdienst wird durch Einstellungen und Parameter gesteuert und konfiguriert, die vom clSController (Centralized Logging Service Controller) erstellt und verwendet werden, um Befehle an den zentralen Protokollierungsdienst-Agent (Centralized Logging Service Agent, CLSAgent) des einzelnen Computers zu senden. Der Agent verarbeitet die Befehle, die an ihn gesendet werden, und verwendet (im Fall eines Startbefehls) die Konfiguration der Szenarien, Anbieter, Ablaufverfolgungsdauer und Flags, um mit dem Sammeln von Ablaufverfolgungsprotokollen gemäß den bereitgestellten Konfigurationsinformationen zu beginnen.

> [!IMPORTANT]
>  Nicht alle Windows PowerShell für den zentralisierten Protokollierungsdienst sind für die Verwendung mit lokalen Skype for Business Server 2015-Bereitstellungen vorgesehen. Obwohl sie möglicherweise funktionieren, sind die folgenden Cmdlets nicht für die Funktion mit lokalen Skype for Business Server 2015-Bereitstellungen ausgelegt:

-  **CsClsRegion-Cmdlets:** [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps)und [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **CsClsSearchTerm-Cmdlets:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) und [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **CsClsSecurityGroup-Cmdlets:** [Get-CsClsSecurityGroup](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)und [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Die in diesen Cmdlets definierten Einstellungen behindern oder verursachen keine negativen Verhaltensweisen, sie sind jedoch für die Verwendung mit Microsoft 365 oder Office 365 konzipiert und führen nicht zu den erwarteten Ergebnissen in lokalen Bereitstellungen. Dies bedeutet nicht, dass diese Cmdlets in lokalen Bereitstellungen nicht verwendet werden, aber ihre Verwendung ist ein fortgeschritteneres Thema, das in dieser Dokumentation nicht behandelt wird.

Der zentralisierte Protokollierungsdienst kann auf einem Bereich ausgeführt werden, der einen einzelnen Computer oder einen Pool von Computern umfasst, auf Standortbereich (d. h. an einem definierten Standort wie dem Standort Redmond, der eine Sammlung von Computern und Pools in Ihrer Bereitstellung enthält) oder auf globaler Ebene (d. h. auf alle Computer und Pools in Ihrer Bereitstellung).

Zum Konfigurieren des Bereichs für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell müssen Sie Mitglied der Sicherheitsgruppen "CsAdministrator" oder "CsServerAdministrator" (Role-Based Access Control, RBAC) oder einer benutzerdefinierten ROLLENAC-Rolle sein, die eine dieser beiden Gruppen enthält. Führen Sie den folgenden Befehl in der Skype for Business Server Management Windows PowerShell Shell oder an der eingabeaufforderung aus, um eine Liste aller rollenspezifischen Verwaltungsrollen zurückzukehren, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenspezifischen Rollen, die Sie selbst erstellt haben):

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Zum Beispiel:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Es gibt grundlegende Unterschiede zwischen den Befehlszeilenbefehlen, die Sie in Windows PowerShell oder CLSController ausführen können. Windows PowerShell bietet eine umfassende Methode zum Konfigurieren und Definieren von Szenarien und zum Wiederverwendung dieser Szenarien auf sinnvolle Weise für Ihre Problembehandlungsszenarien. Während der CLSController eine schnelle und effiziente Möglichkeit bietet, Befehle einzugeben und Ergebnisse zu erhalten, ist der Befehlssatz für den CLSController auf die begrenzte Anzahl der über die Befehlszeile verfügbaren Befehle beschränkt. Im Gegensatz zu Windows PowerShell cmdlets kann CLSController keine neuen Szenarien definieren, den Bereich auf Standort- oder globaler Ebene verwalten und viele andere Einschränkungen eines begrenzten Befehlssatzes, der nicht dynamisch konfiguriert werden kann. Während CLSController eine Möglichkeit für eine schnelle Ausführung bietet, bietet Windows PowerShell eine Möglichkeit, die Funktionalität des zentralisierten Protokollierungsdiensts über das hinaus zu erweitern, was mit CLSController möglich ist.

Ein einzelner Computerbereich kann während der Ausführung eines [Search-CsClsLogging-,](/powershell/module/skype/search-csclslogging?view=skype-ps) [Show-CsClsLogging-,](/powershell/module/skype/show-csclslogging?view=skype-ps) [Start-CsClsLogging-,](/powershell/module/skype/start-csclslogging?view=skype-ps) [Stop-CsClsLogging-,](/powershell/module/skype/stop-csclslogging?view=skype-ps) [Sync-CsClsLogging-](/powershell/module/skype/sync-csclslogging?view=skype-ps) und [Update-CsClsLogging-Befehls](/powershell/module/skype/update-csclslogging?view=skype-ps) mithilfe des Parameters -Computers definiert werden. Der Parameter -Computers akzeptiert eine durch Kommas getrennte Liste vollqualifizierter Domänennamen (Fully Qualified Domain Names, FQDNs) für den Zielcomputer.

> [!TIP]
> Sie können auch -Pools und eine durch Kommas getrennte Liste von Pools definieren, für die Sie die Protokollierungsbefehle ausführen möchten.

Website- und globale Bereiche werden in den **Cmdlets New-**, **Set-** und **Remove-** Centralized Logging Service definiert. Die folgenden Beispiele zeigen, wie ein Standortbereich und ein globaler Bereich festgelegt werden.

> [!IMPORTANT]
> Die angezeigten Befehle können Parameter und Konzepte enthalten, die in anderen Abschnitten behandelt werden. Die Beispielbefehle sollen die Verwendung des **-Identity-Parameters** zum Definieren des Bereichs demonstrieren, und die anderen Parameter werden zur Vollständigkeit einbezogen und geben den Bereich an. Ausführliche Informationen zu **den Cmdlets Set-CsClsConfiguration** finden Sie unter [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in der Betriebsdokumentation.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>So rufen Sie die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts ab

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Verwenden Sie **die Cmdlets New-CsClsConfiguration** und **Set-CsClsConfiguration,** um eine neue Konfiguration zu erstellen oder eine vorhandene Konfiguration zu aktualisieren. Wenn Sie **Get-CsClsConfiguration** ausführen, werden Informationen ähnlich dem folgenden Screenshot angezeigt, in dem die Bereitstellung derzeit die globale Standardkonfiguration hat, aber keine Standortkonfigurationen definiert sind:

![Beispielausgabe von Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>So rufen Sie die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts aus dem lokalen Computerspeicher ab

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Wenn Sie das erste Beispiel verwenden, in dem **Get-CsClsConfiguration** keine Parameter anfordert, verweist der Befehl auf den zentralen Verwaltungsspeicher für die Daten. Wenn Sie den Parameter -LocalStore angeben, verweist der Befehl auf den Computer LocalStore anstelle des zentralen Verwaltungsspeichers.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>So rufen Sie eine Liste der aktuell definierten Szenarien ab

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Um z. B. die für den globalen Bereich definierten Szenarien abzurufen:

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Das Cmdlet **Get-CsClsConfiguration** zeigt immer die Szenarien an, die Teil der Konfiguration eines bestimmten Bereichs sind. In den meisten Fällen werden nicht alle Szenarien angezeigt, und es wird gekürzt. Der hier verwendete Befehl erstellt eine Liste aller Szenarien mit Teilinformationen darüber, welche Anbieter, Einstellungen und Flags verwendet werden.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>So aktualisieren Sie einen globalen Bereich für den zentralisierten Protokollierungsdienst mithilfe Windows PowerShell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Beispiel:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

Der Befehl teilt dem CLSAgent auf allen Computern und in allen Pools der Bereitstellung mit, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Dieser Befehl wirkt sich auf alle Computer und Pools an allen Standorten aus und ändert deren konfigurierten Rollover-Wert in 40 MB.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>So aktualisieren Sie einen Websitebereich für den zentralisierten Protokollierungsdienst mithilfe Windows PowerShell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Beispiel:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Wie im Beispiel gezeigt, ist der Standardspeicherort der Protokolldateien "%TEMP%\Tracing". Da es jedoch der CLSAgent ist, der die Datei tatsächlich schreibt, und da der CSLAgent als Netzwerkdienst ausgeführt wird, wird die Variable %TEMP% zu "%WINDIR%\ServiceProfiles\NetworkService\AppData\Local" erweitert.

Der Befehl teilt dem CLSAgent auf allen Computern und in allen Pools am Standort Redmond mit, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Computer und Pools an anderen Standorten sind von dem Befehl nicht betroffen und verwenden weiterhin den aktuell konfigurierten Rollover-Wert für die Tracing-Datei - der entweder durch den Standardwert (20 MB) oder bei der Anmeldung definiert wird.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>So erstellen Sie eine neue Konfiguration des zentralisierten Protokollierungsdiensts

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > "New-CsClsConfiguration" bietet Zugriff auf eine Vielzahl optionaler Konfigurationseinstellungen. Weitere Informationen zu den Konfigurationsoptionen finden Sie unter [Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings).

Wenn Sie z. B. eine neue Konfiguration erstellen möchten, die einen Netzwerkordner für Cachedateien, den Rollover-Zeitraum für die Protokolldateien und die Rollover-Größe für die Protokolldateien definiert, können Sie folgenden Befehl eingeben:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Sie sollten die Erstellung neuer Konfigurationen und die Definition neuer Eigenschaften für den zentralisierten Protokollierungsdienst sorgfältig planen. Gehen Sie vorsichtig vor, wenn Sie Änderungen durchführen, und stellen Sie sicher, dass Ihnen die Auswirkungen auf die Möglichkeit, Problemszenarien richtig zu protokollieren, bewusst sind. Änderungen an der Konfiguration sollten Sie durchführen, um Ihre Möglichkeiten zur Verwaltung der Protokolle mit einer Größe und einem Rollover-Zeitraum so zu verbessern, dass Sie Probleme bei ihrem Auftreten lösen können.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>So entfernen Sie eine vorhandene Konfiguration des zentralisierten Protokollierungsdiensts

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Um beispielsweise eine Konfiguration des zentralisierten Protokollierungsdiensts zu entfernen, die Sie zum Erhöhen der Protokolldateirolloverzeit erstellt haben, erhöhen Sie die Größe der Rolloverprotokolldatei, und legen Sie den Speicherort des Protokolldateicaches wie folgt auf eine Netzwerkfreigabe fest:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Dies ist die neue Konfiguration, die im Verfahren "So erstellen Sie eine neue Konfiguration des zentralisierten Protokollierungsdiensts" erstellt wurde.

Wenn Sie eine Konfiguration auf Standortebene löschen, verwendet der Standort anschließend die globalen Einstellungen.
## <a name="see-also"></a>Siehe auch

[Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015](configure-providers.md)

[Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015](configure-scenarios.md)

[Zentraler Protokollierungsdienst in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)