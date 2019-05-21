---
title: Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 abrufen, aktualisieren und erstellen.'
ms.openlocfilehash: e6c1f9c893d0b5e745e558ed37570429689259d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274429"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015

**Zusammenfassung:** Hier erfahren Sie, wie Sie Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 abrufen, aktualisieren und erstellen.

Der zentralisierte Protokollierungsdienst wird von Einstellungen und Parametern gesteuert und konfiguriert, die vom zentralen Protokollierungsdienst Controller (CLSController) erstellt und verwendet werden, um Befehle an den zentralen Protokollierungsdienst-Agent des einzelnen Computers zu senden ( CLSAgent). Der Agent verarbeitet die an ihn gesendeten Befehle und verwendet (im Falle eines Start-Befehls) die Konfiguration der Szenarien, Anbieter, Ablaufverfolgungsdauer und Flags, um mit der Erfassung von Ablaufverfolgungsprotokollen gemäß den bereitgestellten Konfigurationsinformationen zu beginnen.

> [!IMPORTANT]
>  Nicht alle Windows PowerShell-Cmdlets, die für den zentralisierten Protokollierungsdienst aufgelistet sind, sind für die Verwendung in lokalen Bereitstellungen von Skype for Business Server 2015 vorgesehen. Obwohl Sie anscheinend funktionieren, sind die folgenden Cmdlets nicht für die Funktion mit Skype for Business Server 2015-lokalen Bereitstellungen vorgesehen:

-  **CsClsRegion-Cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)und [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **CsClsSearchTerm-Cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) und [CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **CsClsSecurityGroup-Cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)und [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Die in diesen Cmdlets definierten Einstellungen werden nicht behindert oder führen zu unerwünschten Verhaltensweisen, sind aber für die Verwendung mit Microsoft Office 365 konzipiert und liefern in lokalen Bereitstellungen keine erwarteten Ergebnisse. Das bedeutet nicht, dass diese Cmdlets in lokalen Bereitstellungen nicht von Nutzen sind, ihre Verwendung ist aber ein komplexes Thema, dessen Beschreibung den Rahmen dieser Dokumentation sprengen würde.

Der zentralisierte Protokollierungsdienst kann in einem Bereich ausgeführt werden, der einen einzelnen Computer oder einen Pool von Computern umfasst, und zwar bei einem Website Bereich (also einer definierten Website wie der Website Redmond, die eine Sammlung von Computern und Pools in Ihrer Bereitstellung enthält) oder bei einem globalen Bereich (d. , alle Computer und Pools in Ihrer Bereitstellung).

Wenn Sie den Bereich für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die enthält eine dieser beiden Gruppen. Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Beispiel:

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Es gibt grundlegende Unterschiede zwischen den Befehlszeilenbefehlen, die in Windows PowerShell oder CLSController ausgeführt werden können. Windows PowerShell bietet eine umfassende Methode zum Konfigurieren und Definieren von Szenarien sowie zum zweckmäßigen wieder verwenden dieser Szenarien für Ihre Problembehandlungsszenarien. Während der CLSController eine schnelle und effiziente Möglichkeit bietet, Befehle einzugeben und Ergebnisse zu erhalten, ist der Befehlssatz für den CLSController auf die begrenzte Anzahl der über die Befehlszeile verfügbaren Befehle beschränkt. Im Gegensatz zu den Windows PowerShell-Cmdlets kann CLSController keine neuen Szenarien definieren, den Bereich auf einer Website oder auf globaler Ebene verwalten, und viele andere Einschränkungen eines begrenzten Befehlssatzes, die nicht dynamisch konfiguriert werden können. Obwohl CLSController ein Mittel zur schnellen Ausführung bietet, bietet Windows PowerShell eine Möglichkeit, die Funktionalität des zentralen Protokollierungsdiensts über das hinaus zu erweitern, was mit CLSController möglich ist.

Ein einzelner Computerbereich kann während der Ausführung einer [Suchfunktion](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)definiert werden: CsClsLogging, [CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) und [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) Befehl mit dem Parameter "-Computer". Der Parameter-Computers akzeptiert eine durch trennzeichengetrennte Liste der vollqualifizierten Domänennamen (FQDNs) für den Zielcomputer.

> [!TIP]
> Sie können auch-Pools und eine durch trennzeichengetrennte Liste der Pools definieren, auf denen Sie die Protokollierungs Befehle ausführen möchten.

Website-und globale Bereiche werden in den Cmdlets für **neu-**, **fest**gelegte und **entfernte** zentralisierte Protokollierungsdienste definiert. Die folgenden Beispiele zeigen, wie ein Standortbereich und ein globaler Bereich festgelegt werden.

> [!IMPORTANT]
> Die angezeigten Befehle können Parameter und Konzepte enthalten, die in anderen Abschnitten behandelt werden. Die Beispielbefehle dienen dazu, die Verwendung des **-Identity-** Parameters zum Definieren des Bereichs zu veranschaulichen, und die anderen Parameter werden zur Vollständigkeit und zum Angeben des Bereichs hinzugefügt. Ausführliche Informationen zu den Cmdlets für Cmdlets für **festgelegte CsClsConfiguration** finden Sie unter [CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in der Betriebsdokumentation.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>So rufen Sie die aktuelle Konfiguration für den zentralisierten Protokollierungsdienst ab

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```
   Get-CsClsConfiguration
   ```

Verwenden Sie die Cmdlets **New-CsClsConfiguration** und **CsClsConfiguration** , um eine neue Konfiguration zu erstellen oder eine vorhandene Konfiguration zu aktualisieren. Wenn Sie **Get-CsClsConfiguration**ausführen, werden Informationen ähnlich der folgenden Bildschirmabbildung angezeigt, in der die Bereitstellung derzeit über die globale Standardkonfiguration verfügt, aber keine Websitekonfigurationen definiert sind:

![Beispielausgabe von Get-CsClsConfiguration](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>So rufen Sie die aktuelle Konfiguration für den zentralisierten Protokollierungsdienst vom lokalen Computerspeicher ab

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```
   Get-CsClsConfiguration -LocalStore
   ```

Wenn Sie das erste Beispiel verwenden, in dem **Get-CsClsConfiguration** keine Parameter angibt, verweist der Befehl auf den zentralen Verwaltungsspeicher für die Daten. Wenn Sie den Parameter-localstore angeben, verweist der Befehl auf den Computer localstore anstelle des zentralen Verwaltungsspeichers.
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

Das Cmdlet **Get-CsClsConfiguration** zeigt immer die Szenarien an, die Teil der Konfiguration eines bestimmten Bereichs sind. In den meisten Fällen werden nicht alle Szenarien angezeigt und es wird gekürzt. Der hier verwendete Befehl erstellt eine Liste aller Szenarien mit Teilinformationen darüber, welche Anbieter, Einstellungen und Flags verwendet werden.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>So aktualisieren Sie einen globalen Bereich für den zentralisierten Protokollierungsdienst mithilfe von Windows PowerShell

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
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>So aktualisieren Sie einen Website Bereich für den zentralisierten Protokollierungsdienst mithilfe von Windows PowerShell

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>So erstellen Sie eine neue Konfiguration für den zentralisierten Protokollierungsdienst

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > „New-CsClsConfiguration“ bietet Zugriff auf eine Vielzahl optionaler Konfigurationseinstellungen. Details zu den Konfigurationsoptionen finden Sie unter [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) und [Grundlegendes zu den Konfigurationseinstellungen](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)für den zentralisierten Protokollierungsdienst.

Wenn Sie z. B. eine neue Konfiguration erstellen möchten, die einen Netzwerkordner für Cachedateien, den Rollover-Zeitraum für die Protokolldateien und die Rollover-Größe für die Protokolldateien definiert, können Sie folgenden Befehl eingeben:

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Sie sollten die Erstellung neuer Konfigurationen sorgfältig planen und festlegen, wie Sie neue Eigenschaften für den zentralisierten Protokollierungsdienst definieren. Gehen Sie vorsichtig vor, wenn Sie Änderungen durchführen, und stellen Sie sicher, dass Ihnen die Auswirkungen auf die Möglichkeit, Problemszenarien richtig zu protokollieren, bewusst sind. Änderungen an der Konfiguration sollten Sie durchführen, um Ihre Möglichkeiten zur Verwaltung der Protokolle mit einer Größe und einem Rollover-Zeitraum so zu verbessern, dass Sie Probleme bei ihrem Auftreten lösen können.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>So entfernen Sie eine vorhandene Konfiguration für den zentralisierten Protokollierungsdienst

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:

   ```
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Um beispielsweise eine von Ihnen erstellte zentralisierte Protokollierungsdienst Konfiguration zu entfernen, um die rolloverzeit der Protokolldatei zu erhöhen, erhöhen Sie die Größe der Rollover-Protokolldatei, und legen Sie den Speicherort für den Protokolldatei Cache auf eine Netzwerkfreigabe wie folgt fest:

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Dies ist die neue Konfiguration, die im Verfahren "So erstellen Sie eine neue zentralisierte Protokollierungsdienst Konfiguration" erstellt wurde.

Wenn Sie eine Konfiguration auf Standortebene löschen, verwendet der Standort anschließend die globalen Einstellungen.
## <a name="see-also"></a>Siehe auch

[Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015](configure-providers.md)

[Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
