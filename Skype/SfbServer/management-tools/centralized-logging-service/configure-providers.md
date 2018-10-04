---
title: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Zusammenfassung: Erfahren Sie, wie der zentralisierte Protokollierungsdienst szenarioanbieter in Skype für Business Server 2015 zu konfigurieren.'
ms.openlocfilehash: e67a1dee9227624ecc94c50437f60781435b2fe8
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372492"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie der zentralisierte Protokollierungsdienst szenarioanbieter in Skype für Business Server 2015 zu konfigurieren.
  
Die Konzepte und die Konfiguration der Anbieter in Centralized Logging Service ist der wichtigste zu verstehen. Theproviders direkt Skype für Business Server-Role Serverkomponenten in der Skype für Business Server Tracing Modell zugeordnet. Der Anbieter definiert die Komponenten einer Skype für Business Server 2015, die verfolgt werden, die Art der Nachrichten (z. B., schwerwiegende Fehler, oder Warnung) zu sammeln und die Kennzeichen (beispielsweise TF_Connection oder TF_Diag). Anbieter sind die nachverfolgbaren Komponenten in jedem Skype für Business Server-Rolle. Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Chat oder Anwesenheit). Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.
  
Um die Centralized Logging Service-Funktionen verwenden die Skype für Business Server-Verwaltungsshell ausgeführt werden soll, müssen Sie Mitglied der Administratorrolle CsAdministrator oder der Sicherheitsgruppen CsServerAdministrator rollenbasierten Zugriffssteuerung (RBAC) oder eine benutzerdefinierte RBAC-Rolle sein, enthält eine der beiden Gruppen. Zum Zurückgeben einer Liste aller führen die rollenbasierten Zugriffssteuerung (RBAC) Rollen, die dieses Cmdlet zugewiesen wurden, (einschließlich alle benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), Sie folgenden Befehl aus der Skype für Business Server-Verwaltungsshell oder die Windows PowerShell auffordern:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Der Rest dieses Themas befasst sich wie Anbieter definieren, ändern einen Anbieter und was eine Definition Anbieter zur Optimierung der Problembehandlung enthält. Es gibt zwei Methoden zum Centralized Logging Service-Befehlen aus. Sie können die CLSController.exe verwenden, die standardmäßig im Verzeichnis C:\Program Files\Common Files\Skype für 2015\CLSAgent Business Server gespeichert ist. Oder Sie können die Skype für Business Server-Verwaltungsshell verwenden, um Windows PowerShell-Befehlen. Mithilfe von Windows PowerShell, können Sie neue Anbieter für die Verwendung in Ihrer protokollierungssitzungen definieren, haben vollständige Kontrolle über ihre Erstellung was sie sammeln und auf welcher Ebene sie Sammeln von Daten.
  
> [!IMPORTANT]
> Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss. 
  
Anstatt Sie in den Details der Anbieter tief einsteigen, bietet der zentralisierte Protokollierungsdienst eine Reihe von Szenarien, die bereits definiert sind. Die bereitgestellten Szenarien beschäftigen sich mit den meisten mögliche Probleme, die verwendet werden. In seltenen Fällen müssen Sie erstellen und Anbietern zu definieren, und weisen Sie diese Szenarien. Es wird dringend empfohlen, dass Sie mit jedes der Szenarien bereitgestellt werden, bevor Sie die Notwendigkeit zum Erstellen von neuen Anbieter und Szenarien untersuchen vertraut. Solange Informationen zum Erstellen von Anbietern hier gefunden wird, machen Sie mit wie die Szenarien die Elemente der Anbieter nutzen, um Ablaufverfolgungsinformationen zu erfassen, werden Details zu den Anbieter selbst zu diesem Zeitpunkt nicht bereitgestellt. 
  
Eingeführt in [Centralized Logging Service in Skype für Business 2015](centralized-logging-service.md), sind die wichtigsten Elemente beim Definieren eines Anbieters für die Verwendung in einem Szenario:
  
- **Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, dass OCSLogger feststellen, welche die Verfolgung Engine Protokolle erfassen sollten. Der Anbieter sind die gleichen Komponenten und in vielen Fällen haben, die denselben Namen wie die Komponenten in OCSLogger. Wenn Sie nicht mit OCSLogger vertraut sind, Server-Role sind bestimmte Komponenten, die der zentralisierte Protokollierungsdienst sammeln können Protokolle aus. Im Fall von the Centralized Logging Service ist die CLSAgent der Architektur Teil der zentralisierte Protokollierungsdienst, die wie folgt die Protokollierung der Komponenten, die Sie in der Konfiguration der Anbieter definieren.
    
- **Protokollierungsstufen** OCSLogger bereitgestellt, die Möglichkeit, eine Anzahl von Detailebenen für die gesammelten Daten auszuwählen. Dieses Feature ist ein integraler Bestandteil der zentralisierte Protokollierungsdienst und Szenarios und wird von der **Type** -Parameter definiert. Sie können aus den folgenden wählen:
    
  - **Alle** : Es werden Ablaufverfolgungsmeldungen Nachrichten vom Typ "schwerwiegend", Fehler, Warnung, verbose und Debuginfo in das Protokoll für den festgelegten Anbieter.
    
  - **"Schwerwiegend"** Sammelt nur Ablaufverfolgungsmeldungen definiert als "Schwerwiegend".
    
  - **Fehler** Sammelt nur Ablaufverfolgungsmeldungen definiert als "Fehler" oder "Schwerwiegend".
    
  - **Warnung** : Es werden nur die Ablaufverfolgungsmeldungen vom Typ "Warnung", "Fehler" und "Schwerwiegend".
    
  - **Info** : Es werden nur die Ablaufverfolgungsmeldungen, die eine informationsmeldung für den festgelegten Anbieter plus Schwerwiegender Fehler und Warnung Nachrichten angeben.
    
  - **"Ausführlich"** Alle Trace Nachrichten vom Typ "schwerwiegend", Fehler, Warnung und ausführlich für den festgelegten Anbieter erfasst.
    
  - **Debuggen** im Wesentlichen eine Entsprechung eines ist "All" - sammelt Spuren von Typ Fatal, Fehler, Warnung, Info, ausführlich und Debuggen für den festgelegten Anbieter.
    
- **Flags** OCSLogger bereitgestellt, die Option Flags für jeden Anbieter auswählen, die die Art der Informationen definiert, die Sie von der Ablaufverfolgungsdateien abrufen können. Sie können die folgenden Kennzeichen, basierend auf den Anbieter ausgewählt haben:
    
  - **TF_Connection** Verbindung-bezogene Protokolleinträge enthält. Diese Protokolle enthalten Informationen über Verbindungen zu und von einer bestimmten Komponente. Dies kann auch beträchtliche auf Netzwerkebene Informationen enthalten (d. h., für Komponenten ohne das Konzept einer Verbindung).
    
  - **TF_Security** Enthält alle Ereignisse/Protokolleinträge im Zusammenhang mit der Sicherheit. Beispielsweise sind für SipStack, diese Sicherheitsereignisse wie Domäne Validierungsfehler und Client-Authentifizierung/Autorisierungsfehler.
    
  - **TF_Diag** Diagnose-Ereignisse, die Sie verwenden können, um diagnostizieren oder eine Problembehandlung für die Komponente enthält. Für SipStack sind diese beispielsweise Zertifikat Fehler oder Warnungen/Fehler DNS.
    
  - **Tl_protocol** Enthält für protokollmeldungen wie SIP- und Community-Codec-Paket kombiniert Nachrichten.
    
  - **TF_Component** Aktiviert die Protokollierung auf den Komponenten, die als Bestandteil der Anbieter angegeben.
    
  - **Alle** Aller verfügbare Kennzeichen festgelegt für den Anbieter.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Um Informationen zu vorhandenen Centralized Logging Service-szenarioanbieter prüfen

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf. Die angezeigten Informationen sind nicht genügend oder die Liste ist zu lang für das Standardformat für Windows PowerShell Listen, können Sie zusätzliche Informationen anzeigen, indem definieren eine anderes Seitenausgabe-Methode. Geben Sie dazu Folgendes ein:
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, der Protokollierungstyp, die Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>So definieren Sie einen neuen Centralized Logging Service-szenarioanbieter

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Geben Sie dazu Folgendes ein:
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter „Lyss“ erfasst werden soll, sieht so aus:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

Die - Ebene sammelt schwerwiegenden Fehler, Fehler, Warnung und Informationen Nachrichten. Die verwendeten Flags werden alle für den Anbieter Lyss definiert und gehören TF_Connection, TF_Diag und TF_Protocol.After der $LyssProvider-Variablen definiert ist, können Sie sie mit dem Cmdlet **New-CsClsScenario** das Erfassen von ablaufverfolgungen vom Anbieter Lyss. Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

In der $LyssProvider der Variablen, enthält das definierte Szenario mit **New-CsClsProvider**erstellt wird.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>So ändern Sie eine vorhandene Centralized Logging Service-szenarioanbieter

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Aktualisieren Sie das Szenario anschließend mit der folgenden Eingabe, um den Anbieter zuzuweisen:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

Dieser Befehl bewirkt, dass beim Szenariostandort „Redmond/RedmondLyssInfo“ die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von „Get-CsClsScenario“ anzeigen. Weitere Informationen hierzu finden Sie unter [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** wird nicht überprüft, um festzustellen, ob die Kennzeichen gültig sind. Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z. B. TF_DIAG oder TF_CONNECTION). Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.
  
Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Mit jedem Provider definiert hat die Richtlinie hinzufügen bereits mithilfe des **New-CsClsProvider** -Prozesses definiert wurde.
### <a name="to-remove-a-scenario-provider"></a>So entfernen Sie einen Szenarioanbieter

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Mithilfe der bereitgestellten Cmdlets können Sie vorhandene Anbieter aktualisieren und neue Anbieter erstellen. Um einen Anbieter zu entfernen, müssen Sie die Replace-Direktive für den Anbieter-Parameter zum **Set-CsClsScenario**verwenden. Die einzige Möglichkeit, einen Anbieter komplett zu entfernen, besteht darin, ihn durch einen neu definierten Anbieter mit dem gleichen Namen zu ersetzen und die Anweisung „Update“ zu verwenden. Beispiel: Der Anbieter „LyssProvider“ ist mit dem Protokollierungstyp „WPP“, der Protokollierungsebene „Debug“ und den gesetzten Flags „TF_CONNECTION“ und „TF_DIAG“ definiert. So ändern Sie die Flags, die benötigten "All". Geben Sie dazu den folgenden Befehl ein, um den Anbieter zu ändern:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Wenn Sie ein Szenario mit den zugehörigen Anbietern vollständig entfernen möchten, geben Sie den folgenden Befehl ein:
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Beispiel:
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > Das Cmdlet **Remove-CsClsScenario** werden nicht zur Bestätigung aufgefordert. Das Szenario wird einschließlich der zugewiesenen Anbieter gelöscht. Sie können das Szenario wieder neu erstellen, indem Sie die Befehle ausführen, mit denen das Szenario ursprünglich erstellt wurde. Ein Verfahren zum Wiederherstellen entfernter Szenarien oder Anbieter gibt es nicht.
  
Wenn Sie ein Szenario mit dem Cmdlet **Remove-CsClsScenario** entfernen, entfernen Sie das Szenario vollständig aus dem Bereich. Wenn Sie die von Ihnen erstellten Szenarien mit den zugehörigen Anbietern verwenden möchten, müssen Sie neue Anbieter erstellen und diese einem neuen Szenario zuweisen.
## <a name="see-also"></a>Siehe auch

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[Neue CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)