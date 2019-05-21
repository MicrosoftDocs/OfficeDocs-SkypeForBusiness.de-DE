---
title: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server 2015 Szenario-Anbieter für den zentralisierten Protokollierungsdienst konfigurieren.'
ms.openlocfilehash: a9987d99b2caf00acc92de92a8d997845ad8f921
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274450"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie in Skype for Business Server 2015 Szenario-Anbieter für den zentralisierten Protokollierungsdienst konfigurieren.
  
Die Konzepte und die Konfiguration von Anbietern im zentralisierten Protokollierungsdienst sind eine der wichtigsten zu erfassen. Theproviders Sie den Skype for Business Server-Rollen Komponenten direkt im Skype for Business Server-Ablaufverfolgungsmodell zugeordnet. Der Anbieter definiert die Komponenten eines Skype for Business Server 2015, die nachverfolgt werden, die Art der Nachrichten (beispielsweise fatal, Fehler oder Warnung), die erfasst werden sollen, und die Flags (beispielsweise TF_Connection oder TF_Diag). Anbieter sind die nachvollziehbaren Komponenten in jeder Skype for Business Server-Serverrolle. Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Chat oder Anwesenheit). Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.
  
Wenn Sie die Funktionen für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell ausführen möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die enthält eine dieser beiden Gruppen. Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell oder der Windows PowerShell aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen (einschließlich aller benutzerdefinierten RBAC-Rollen) zurückzugeben, die Sie selbst erstellt haben. Aufforderung
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Im weiteren Verlauf dieses Themas wird erläutert, wie Sie Anbieter definieren, einen Anbieter ändern und was eine Anbieter Definition enthält, um die Problembehandlung zu optimieren. Es gibt zwei Möglichkeiten zum Ausgeben von Befehlen für zentralisierte Protokollierungsdienste. Sie können die CLSController. exe verwenden, die sich standardmäßig im Verzeichnis C:\Program Files\Skype for Business Server 2015 \ CLSAgent. Oder Sie können die Skype for Business Server-Verwaltungsshell verwenden, um Windows PowerShell-Befehle auszugeben. Mithilfe von Windows PowerShell können Sie neue Anbieter für die Verwendung in ihren Protokollierungssitzungen definieren, die vollständige Kontrolle über ihre Erstellung, deren Erfassung und auf welcher Ebene Sie Daten sammeln.
  
> [!IMPORTANT]
> Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss. 
  
Anstatt zu verlangen, dass Sie sich eingehend mit den Details von Anbietern befassen, bietet der zentralisierte Protokollierungsdienst eine Reihe von Szenarien, die bereits für Sie definiert sind. Die bereitgestellten Szenarien decken die meisten möglichen Probleme ab, die Ihnen auftreten können. In seltenen Fällen müssen Sie möglicherweise Anbieter erstellen und definieren und diese Szenarien zuweisen. Wir empfehlen Ihnen dringend, sich mit den einzelnen Szenarien vertraut zu machen, bevor Sie untersuchen, ob neue Anbieter und Szenarien erstellt werden müssen. Während Informationen zum Erstellen von Anbietern hier gefunden werden, um Sie mit den Szenarien vertraut zu machen, in denen die Anbieter Elemente zum Sammeln von Ablaufverfolgungsinformationen verwendet werden, werden zu diesem Zeitpunkt keine Details zu den Anbietern selbst bereitgestellt. 
  
Im [zentralisierten Protokollierungsdienst in Skype for Business 2015](centralized-logging-service.md)eingeführt, sind die wichtigsten Elemente zum Definieren eines Anbieters für die Verwendung in einem Szenario:
  
- **Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, um OCSLogger zu informieren, von welchem das Ablaufverfolgungsmodul Protokolle sammeln soll. Die Anbieter sind die gleichen Komponenten und haben in vielen Fällen denselben Namen wie die Komponenten in OCSLogger. Wenn Sie mit OCSLogger nicht vertraut sind, sind Anbieterserver rollenspezifische Komponenten, über die der zentralisierte Protokollierungsdienst Protokolle sammeln kann. Beim zentralisierten Protokollierungsdienst ist der CLSAgent der architektonische Teil des zentralen Protokollierungsdiensts, bei dem die Nachverfolgung der Komponenten erfolgt, die Sie in der Anbieterkonfiguration definieren.
    
- **Protokollierungsstufen** OCSLogger bot die Möglichkeit, eine Reihe von Detailebenen für die gesammelten Daten auszuwählen. Dieses Feature ist ein integraler Bestandteil des zentralen Protokollierungsdiensts und der Szenarien und wird durch den **Type** -Parameter definiert. Sie haben folgende Auswahlmöglichkeiten:
    
  - **Alle** Sammelt Nachverfolgungsmeldungen vom Typ fatal, Fehler, Warnung, ausführlich und Debuginformationen in das Protokoll des definierten Anbieters.
    
  - **Fatal** Sammelt nur die Ablaufverfolgungsmeldungen, die als "Fatal" definiert sind.
    
  - **Fehlermeldung** Sammelt nur die Ablaufverfolgungsmeldungen, die als "Fehler" oder "Fatal" definiert sind.
    
  - **Warnung** Sammelt nur die Ablaufverfolgungsmeldungen vom Typ "Warnung", "Fehler" und "Fatal".
    
  - Weitere **Informationen** Sammelt nur die Ablaufverfolgungsmeldungen, die eine Informationsmeldung für den definierten Anbieter angeben, sowie fatale, Fehler-und Warnmeldungen.
    
  - **Ausführlich** Sammelt alle Ablaufverfolgungsmeldungen des Typs fatal, Error, Warning und Verbose für den definierten Anbieter.
    
  - **Debuggen** Dies ist im Grunde ein Äquivalent von "alle" – sammelt Spuren des Typs fatal, Error, Warning, Info, verbose und Debug für den definierten Anbieter.
    
- **Flags** OCSLogger hat die Option zur Auswahl von Flags für jeden Anbieter bereitgestellt, die definiert haben, welche Art von Informationen aus den Ablaufverfolgungsdateien abgerufen werden können. Auf der Grundlage des Anbieters können Sie die folgenden Flags auswählen:
    
  - **TF_Connection** Enthält verbindungsbezogene Protokolleinträge. Diese Protokolle umfassen Informationen zu Verbindungen, die zu und von einer bestimmten Komponente hergestellt wurden. Dies kann auch wichtige Informationen auf Netzwerkebene enthalten (also für Komponenten ohne das Konzept einer Verbindung).
    
  - **TF_Security** Stellt alle Ereignisse/Protokolleinträge in Bezug auf Sicherheit bereit. Bei SipStack handelt es sich beispielsweise um Sicherheitsereignisse wie Fehler bei der Domänenüberprüfung und Clientauthentifizierung/Autorisierungsfehler.
    
  - **TF_Diag** Stellt Diagnoseereignisse bereit, die Sie verwenden können, um die Komponente zu diagnostizieren oder zu beheben. Bei SipStack handelt es sich beispielsweise um Zertifikat Fehler oder DNS-Warnungen/-Fehler.
    
  - **TF_Protocol** Bietet Protokollnachrichten wie SIP-und kombinierte Nachrichtenpakete für Community-Codecs.
    
  - **TF_Component** Aktiviert die Protokollierung an den als Teil der Anbieter angegebenen Komponenten.
    
  - **Alle** Legt alle verfügbaren Flags fest, die für den Anbieter verfügbar sind.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>So überprüfen Sie Informationen zu vorhandenen Szenario-Anbietern für zentralisierte Protokollierungsdienste

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf. Wenn die angezeigten Informationen nicht ausreichen oder die Liste für das standardmäßige Windows PowerShell-Listenformat zu lang ist, können Sie zusätzliche Informationen anzeigen, indem Sie eine andere Ausgabemethode definieren. Geben Sie dazu Folgendes ein:
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, der Protokollierungstyp, die Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>So definieren Sie einen neuen szenariodienst für zentrale Protokollierungsdienste

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Geben Sie dazu Folgendes ein:
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter „Lyss“ erfasst werden soll, sieht so aus:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

Die-Ebene sammelt fatale, Fehler-, Warnungs-und Informationsnachrichten. Die verwendeten Flags sind alle für den Lysser-Anbieter definierten Flags und umfassen TF_Connection, TF_Diag und TF_Protocol. Nachdem die Variable $LyssProvider definiert wurde, können Sie Sie mit dem Cmdlet **New-CsClsScenario** verwenden, um Ablaufverfolgungen des Lysser Anbieters zu erfassen. Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Hierbei ist „$LyssProvider“ die Variable, in der sich das definierte Szenario befindet, das mit **New-CsClsProvider** erstellt wurde.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>So ändern Sie einen vorhandenen szenariodienst für zentralisierte Protokollierungsdienste

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Aktualisieren Sie das Szenario anschließend mit der folgenden Eingabe, um den Anbieter zuzuweisen:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

Dieser Befehl bewirkt, dass beim Szenariostandort „Redmond/RedmondLyssInfo“ die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von „Get-CsClsScenario“ anzeigen. Weitere Informationen dazu finden Sie unter [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** überprüft nicht, ob die Flags gültig sind. Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z. B. TF_DIAG oder TF_CONNECTION). Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.
  
Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Hierbei wurde jeder mit der „Add“-Anweisung festgelegte Anbieter bereits mithilfe des **New-CsClsProvider**-Prozesses definiert.
### <a name="to-remove-a-scenario-provider"></a>So entfernen Sie einen Szenarioanbieter

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Mithilfe der bereitgestellten Cmdlets können Sie vorhandene Anbieter aktualisieren und neue Anbieter erstellen. Wenn Sie einen Anbieter entfernen möchten, müssen Sie bei **Set-CsClsScenario** beim Parameter „-Provider“ die Anweisung „Replace“ verwenden. Die einzige Möglichkeit, einen Anbieter komplett zu entfernen, besteht darin, ihn durch einen neu definierten Anbieter mit dem gleichen Namen zu ersetzen und die Anweisung „Update“ zu verwenden. Beispiel: Der Anbieter „LyssProvider“ ist mit dem Protokollierungstyp „WPP“, der Protokollierungsebene „Debug“ und den gesetzten Flags „TF_CONNECTION“ und „TF_DIAG“ definiert. Sie müssen die Flags in "alle" ändern. Geben Sie dazu den folgenden Befehl ein, um den Anbieter zu ändern:
    
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
    > Das Cmdlet **Remove-CsClsScenario** fordert Sie nicht zur Eingabe einer Bestätigung auf. Das Szenario wird einschließlich der zugewiesenen Anbieter gelöscht. Sie können das Szenario wieder neu erstellen, indem Sie die Befehle ausführen, mit denen das Szenario ursprünglich erstellt wurde. Ein Verfahren zum Wiederherstellen entfernter Szenarien oder Anbieter gibt es nicht.
  
Wenn Sie ein Szenario mit dem Cmdlet**Remove-CsClsScenario** entfernen, wird es komplett aus dem Bereich entfernt. Wenn Sie die von Ihnen erstellten Szenarien mit den zugehörigen Anbietern verwenden möchten, müssen Sie neue Anbieter erstellen und diese einem neuen Szenario zuweisen.
## <a name="see-also"></a>Siehe auch

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
