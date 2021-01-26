---
title: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Zusammenfassung: Informationen zum Konfigurieren von Szenarioanbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015.'
ms.openlocfilehash: c96a87ea76930dbd99341667852a9731e56b88b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835165"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Szenarioanbieter für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 konfigurieren.
  
Die Konzepte und die Konfiguration von Anbietern im zentralisierten Protokollierungsdienst sind eines der wichtigsten zu verstehen. DieProvider werden im Ablaufverfolgungsmodell von Skype for Business Server direkt den Komponenten der Skype for Business Server-Serverrolle gegliedert. Der Anbieter definiert die Komponenten eines Skype for Business Server 2015-Servers, die nachverfolgt werden, den Typ der zu erfassenden Nachrichten (z. B. "schwerwiegende", "Fehler" oder "Warnung") und die Kennzeichen (z. B. TF_Connection oder TF_Diag). Anbieter sind die nachverfolgbaren Komponenten in jeder Skype for Business Server-Serverrolle. Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Instant Messaging oder Anwesenheit). Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.
  
Zum Ausführen der Funktionen des zentralisierten Protokollierungsdiensts mithilfe der Skype for Business Server-Verwaltungsshell müssen Sie Mitglied der Sicherheitsgruppen "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält. Wenn Sie eine Liste aller rollenbasierten Zugriffssteuerungsrollen (ROLE-Based Access Control, RBAC) zurückgeben möchten, denen dieses Cmdlet zugewiesen wurde (einschließlich benutzerdefinierter rollenbasierter Zugriffssteuerungsrollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl über die Skype for Business Server-Verwaltungsshell oder die Eingabeaufforderung Windows PowerShell aus:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Im Rest dieses Themas geht es darum, wie Anbieter definiert oder geändert werden und welche Elemente eine Anbieterdefinition enthält (was bei Fehlerbehebungen hilfreich ist). Es gibt zwei Möglichkeiten, Befehle des zentralisierten Protokollierungsdiensts aus zu senden. Sie können die CLSController.exe, die sich standardmäßig im Verzeichnis "C:\Programme\Gemeinsame Dateien\Skype for Business Server 2015\CLSAgent" befindet. Sie können auch die Skype for Business Server-Verwaltungsshell verwenden, um Windows PowerShell aus. Mithilfe von Windows PowerShell können Sie neue Anbieter für die Verwendung in Ihren Protokollierungssitzungen definieren und haben vollständige Kontrolle über deren Erstellung, was sie sammeln und auf welcher Ebene sie Daten sammeln.
  
> [!IMPORTANT]
> Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss. 
  
Der zentralisierte Protokollierungsdienst erfordert nicht, dass Sie sich tief mit den Details der Anbieter ausstatten, sondern bietet eine Reihe von Szenarien, die bereits für Sie definiert sind. Die bereitgestellten Szenarien decken die meisten möglichen Probleme ab, die auftreten werden. In seltenen Fällen müssen Sie möglicherweise Anbieter erstellen und definieren und sie Szenarien zuweisen. Es wird dringend empfohlen, sich mit jedem der bereitgestellten Szenarien vertraut zu machen, bevor Sie die Notwendigkeit der Erstellung neuer Anbieter und Szenarien untersuchen. Hier finden Sie Zwar Informationen zum Erstellen von Anbietern, um Sie mit der Verwendung der Anbieterelemente in Szenarien zum Sammeln von Ablaufverfolgungsinformationen vertraut zu machen, Details zu den Anbietern selbst werden derzeit jedoch nicht bereitgestellt. 
  
Die wichtigsten Elemente der Definition eines Anbieters für die Verwendung in einem Szenario wurden in [Skype for Business 2015](centralized-logging-service.md)in den zentralisierten Protokollierungsdienst eingeführt:
  
- **Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, von derEn Auswahl Sie OCSLogger mitteilen, von welchem Ablaufverfolgungsmodul Protokolle erfasst werden sollen. Die Anbieter entsprechen den Komponenten in OCSLogger und haben in vielen Fällen auch dieselben Namen. Wenn Sie mit OCSLogger nicht vertraut sind, handelt es sich bei Anbietern um serverrollespezifische Komponenten, von deren Protokollierungsdienst Protokolle erfassen kann. Im Fall des zentralisierten Protokollierungsdiensts ist der CLSAgent der Architekturteil des zentralisierten Protokollierungsdiensts, der die Ablaufverfolgung der Komponenten vortrat, die Sie in der Anbieterkonfiguration definieren.
    
- **Protokolliergrade** OCSLogger bot die Möglichkeit, eine Reihe von Detailebenen für die gesammelten Daten zu wählen. Dieses Feature ist ein integraler Bestandteil des zentralisierten Protokollierungsdiensts und der Szenarien und wird durch den Parameter **"Type"** definiert. Es stehen folgende Optionen zur Auswahl:
    
  - **Alle** Erfasst Ablaufverfolgungsmeldungen vom Typ "Schwerwiegende", "Fehler", "Warnung", "Ausführlich" und "Debuggen" im Protokoll für den definierten Anbieter.
    
  - **Fatal** Sammelt nur die Ablaufverfolgungsmeldungen, die als "Fatal" definiert sind.
    
  - **Fehler** Sammelt nur die Ablaufverfolgungsmeldungen, die als "Fehler" oder "Fatal" definiert sind.
    
  - **Warnung** Sammelt nur Ablaufverfolgungsmeldungen vom Typ "Warnung", "Fehler" und "Fatal".
    
  - **Info** Sammelt nur ablaufverfolgungsmeldungen, die eine Informationsmeldung für den definierten Anbieter sowie schwerwiegende, Fehler- und Warnmeldungen angeben.
    
  - **Ausführlich** Sammelt alle Ablaufverfolgungsmeldungen vom Typ "Schwerwiegender Fehler", "Fehler", "Warnung" und "Ausführlich" für den definierten Anbieter.
    
  - **Debuggen** Sie dies im Wesentlichen mit "Alle" – erfasst Ablaufverfolgungen vom Typ "Fatal", "Error", "Warning", "Info", "Verbose" und "Debug" für den definierten Anbieter.
    
- **Flags** OCSLogger bot die Option zum Auswählen von Flags für jeden Anbieter, der definiert hat, welche Art von Informationen Sie aus den Ablaufverfolgungsdateien abrufen können. Sie können die folgenden Flags basierend auf dem Anbieter wählen:
    
  - **TF_Connection** Stellt verbindungsbezogene Protokolleinträge zur Verf nkung zur Verf nkung. Diese Protokolle enthalten Informationen zu Verbindungen, die mit und von einer bestimmten Komponente hergestellt wurden. Dies kann auch wichtige Informationen auf Netzwerkebene enthalten (d. h. für Komponenten ohne das Konzept einer Verbindung).
    
  - **TF_Security** Stellt alle Ereignisse/Protokolleinträge im Zusammenhang mit der Sicherheit zur Verfügung. Für SipStack sind dies beispielsweise Sicherheitsereignisse wie Domänenüberprüfungsfehler und Clientauthentifizierungs-/Autorisierungsfehler.
    
  - **TF_Diag** Stellt Diagnoseereignisse zur Verfügung, die Sie zum Diagnostizieren oder Beheben von Problemen mit der Komponente verwenden können. Für SipStack sind dies z. B. Zertifikatfehler oder DNS-Warnungen/-Fehler.
    
  - **TF_Protocol** Stellt Protokollmeldungen wie SIP- und kombinierte Communitycodec-Pack-Nachrichten zur Verf ckung.
    
  - **TF_Component** Aktiviert die Protokollierung für die Komponenten, die als Teil der Anbieter angegeben sind.
    
  - **Alle** Legt alle verfügbaren Flags fest, die für den Anbieter verfügbar sind.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>So überprüfen Sie Informationen zu vorhandenen Szenarioanbietern für den zentralisierten Protokollierungsdienst

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf. Wenn die angezeigten Informationen nicht ausreichen oder die Liste für das standardmäßige Windows PowerShell zu lang ist, können Sie zusätzliche Informationen anzeigen, indem Sie eine andere Ausgabemethode definieren. Geben Sie dazu Folgendes ein:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, Typ von Protokollierung, Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>So definieren Sie einen neuen Szenarioanbieter für den zentralisierten Protokollierungsdienst

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Dazu geben Sie Folgendes ein:
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter "Lyss" erfasst werden soll, sieht so aus:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

The -Level collects fatal, error, warning, and information messages. Die verwendeten Flags sind alle für den Lyss-Anbieter definierten Flags und enthalten TF_Connection, TF_Diag und TF_Protocol.Nachdem die Variable $LyssProvider definiert wurde, können Sie sie mit dem **Cmdlet "New-CsClsScenario"** verwenden, um Ablaufverfolgungen vom Anbieter "Lyss" zu erfassen. Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Hierbei ist "$LyssProvider" die Variable, in der sich das definierte Szenario befindet, das mit **New-CsClsProvider** erstellt wurde.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>So ändern Sie einen vorhandenen Szenarioanbieter für den zentralisierten Protokollierungsdienst

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Dann aktualisieren Sie das Szenario mit der folgenden Eingabe, um den Anbieter zuzuweisen:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

Dieser Befehl bewirkt, dass beim Szenariostandort "Redmond/RedmondLyssInfo" die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von "Get-CsClsScenario" anzeigen. Nähere Informationen dazu finden Sie unter [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** überprüft nicht, ob die Flags gültig sind. Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z. B. TF_DIAG oder TF_CONNECTION). Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.
  
Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Hierbei wurde jeder mit der "Add"-Anweisung festgelegte Anbieter bereits mithilfe des **New-CsClsProvider**-Prozesses definiert.
### <a name="to-remove-a-scenario-provider"></a>So entfernen Sie einen Szenarioanbieter

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Mithilfe der bereitgestellten Cmdlets können Sie vorhandene Anbieter aktualisieren und neue Anbieter erstellen. Wenn Sie einen Anbieter entfernen möchten, müssen Sie bei **Set-CsClsScenario** beim Parameter "-Provider" die Anweisung "Replace" verwenden. Die einzige Möglichkeit, einen Anbieter komplett zu entfernen, besteht darin, ihn durch einen neu definierten Anbieter mit dem gleichen Namen zu ersetzen und die Anweisung "Update" zu verwenden. Beispiel: Der Anbieter "LyssProvider" ist mit dem Protokollierungstyp "WPP", der Protokollierungsebene "Debug" und den gesetzten Flags "TF_CONNECTION" und "TF_DIAG" definiert. Sie müssen die Flags in "Alle" ändern. Geben Sie dazu den folgenden Befehl ein, um den Anbieter zu ändern:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Wenn Sie ein Szenario mit den zugehörigen Anbietern vollständig entfernen möchten, geben Sie den folgenden Befehl ein:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Beispiel:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > Das **Remove-CsClsScenario**-Cmdlet fordert Sie nicht zur Eingabe einer Bestätigung auf. Das Szenario wird, einschließlich der zugewiesenen Anbieter, gelöscht. Sie können das Szenario wieder neu erstellen, indem Sie die Befehle ausführen, mit denen das Szenario ursprünglich erstellt wurde. Ein Verfahren zum Wiederherstellen entfernter Szenarien oder Anbieter gibt es nicht.
  
Wenn Sie ein Szenario mit dem **Remove-CsClsScenario**-Cmdlet entfernen, wird es komplett aus dem Bereich entfernt. Wenn Sie die von Ihnen erstellten Szenarien mit den zugehörigen Anbietern verwenden möchten, müssen Sie neue Anbieter erstellen und diese einem neuen Szenario zuweisen.
## <a name="see-also"></a>Siehe auch

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
