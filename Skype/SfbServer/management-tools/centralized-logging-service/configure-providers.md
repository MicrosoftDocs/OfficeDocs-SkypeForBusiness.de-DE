---
title: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Zusammenfassung: Erfahren Sie, wie Sie Szenarioanbieter für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 konfigurieren.'
ms.openlocfilehash: 526c42e1a6fd741b228cd99450b9d11bc3152670
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855452"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Szenarioanbieter für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 konfigurieren.
  
Die Konzepte und die Konfiguration von Anbietern im zentralisierten Protokollierungsdienst sind eines der wichtigsten Konzepte und Konfigurationen, die Sie verstehen müssen. Die Anbieter ordnen Skype for Business Server Serverrollenkomponenten im Skype for Business Server Ablaufverfolgungsmodell direkt zu. Der Anbieter definiert die Komponenten eines zu erfassenden Skype for Business Server 2015, den Typ der zu erfassenden Nachrichten (z. B. schwerwiegend, Fehler oder Warnung) und die Flags (z. B. TF_Connection oder TF_Diag). Anbieter sind die nachverfolgbaren Komponenten in jeder Skype for Business Server Serverrolle. Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Instant Messaging oder Anwesenheit). Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.
  
Um die Funktionen des zentralisierten Protokollierungsdiensts mithilfe der Skype for Business Server Verwaltungsshell auszuführen, müssen Sie entweder Mitglied der Rollenbasierten Zugriffssteuerungsgruppen (Role-Based Access Control, RBAC) "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält. Um eine Liste aller rollenbasierten Zugriffssteuerungsrollen (Role-Based Access Control, RBAC) zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell oder an der Windows PowerShell Eingabeaufforderung aus:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Im Rest dieses Themas geht es darum, wie Anbieter definiert oder geändert werden und welche Elemente eine Anbieterdefinition enthält (was bei Fehlerbehebungen hilfreich ist). Es gibt zwei Möglichkeiten, befehle des zentralisierten Protokollierungsdiensts auszustellen. Sie können die CLSController.exe verwenden, die sich standardmäßig im Verzeichnis "C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent" befindet. Sie können auch die Skype for Business Server-Verwaltungsshell verwenden, um Windows PowerShell Befehle auszugeben. Mithilfe von Windows PowerShell können Sie neue Anbieter für die Verwendung in Ihren Protokollierungssitzungen definieren und die vollständige Kontrolle über deren Erstellung, die gesammelten Daten und auf welcher Ebene sie Daten sammeln.
  
> [!IMPORTANT]
> Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss. 
  
Anstatt zu verlangen, dass Sie sich mit den Details der Anbieter befassen müssen, bietet der zentralisierte Protokollierungsdienst eine Reihe von Szenarien, die bereits für Sie definiert sind. In den bereitgestellten Szenarien werden die meisten möglichen Probleme behandelt, auf die Sie stoßen werden. In seltenen Fällen müssen Sie möglicherweise Anbieter erstellen und definieren und sie Szenarien zuweisen. Es wird dringend empfohlen, sich mit jedem der bereitgestellten Szenarien vertraut zu machen, bevor Sie die Notwendigkeit untersuchen, neue Anbieter und Szenarien zu erstellen. Hier finden Sie Zwar Informationen zum Erstellen von Anbietern, um Sie mit der Verwendung der Anbieterelemente zum Sammeln von Ablaufverfolgungsinformationen vertraut zu machen, Details zu den Anbietern selbst werden jedoch zu diesem Zeitpunkt nicht bereitgestellt. 
  
Im [zentralisierten Protokollierungsdienst in Skype for Business 2015](centralized-logging-service.md)eingeführt, sind die wichtigsten Elemente zum Definieren eines Anbieters für die Verwendung in einem Szenario:
  
- **Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, aus denen Sie OCSLogger mitteilen, von welchem Protokollierungsmodul Protokolle erfasst werden sollen. Die Anbieter entsprechen den Komponenten in OCSLogger und haben in vielen Fällen auch dieselben Namen. Wenn Sie nicht mit OCSLogger vertraut sind, sind Anbieter serverrollenspezifische Komponenten, aus denen der zentralisierte Protokollierungsdienst Protokolle erfassen kann. Im Fall des zentralisierten Protokollierungsdiensts ist CLSAgent der Architekturteil des zentralisierten Protokollierungsdiensts, der die Ablaufverfolgung der Komponenten durchführt, die Sie in der Anbieterkonfiguration definieren.
    
- **Protokollierungsstufen** OCSLogger bot die Möglichkeit, eine Reihe von Detailebenen für die erfassten Daten auszuwählen. Dieses Feature ist ein integraler Bestandteil des zentralisierten Protokollierungsdiensts und der Szenarien und wird durch den **Parameter Type** definiert. Es stehen folgende Optionen zur Auswahl:
    
  - **Alle** Erfasst Ablaufverfolgungsmeldungen vom Typ "schwerwiegend", "Fehler", "Warnung", "Ausführlich" und "Debuginformationen" im Protokoll für den definierten Anbieter.
    
  - **Schwerwiegend** Sammelt nur die Als "Schwerwiegend" definierten Ablaufverfolgungsmeldungen.
    
  - **Fehler** Sammelt nur die Ablaufverfolgungsmeldungen, die als "Fehler" oder "Schwerwiegend" definiert sind.
    
  - **Warnung** Sammelt nur die Ablaufverfolgungsmeldungen vom Typ "Warnung", "Fehler" und "Schwerwiegend".
    
  - **Info und Info** Sammelt nur die Ablaufverfolgungsmeldungen, die eine Informationsnachricht für den definierten Anbieter sowie schwerwiegende, Fehler- und Warnmeldungen angeben.
    
  - **Ausführlich** Sammelt alle Ablaufverfolgungsmeldungen vom Typ "schwerwiegend", "Fehler", "Warnung" und "Ausführlich" für den definierten Anbieter.
    
  - **Debuggen** ist im Wesentlichen ein Äquivalent von "Alle" – erfasst Ablaufverfolgungen vom Typ "Schwerwiegend", "Fehler", "Warnung", "Info", "Ausführlich" und "Debuggen" für den definierten Anbieter.
    
- **Flags** OCSLogger hat die Option zum Auswählen von Flags für jeden Anbieter bereitgestellt, der definiert hat, welche Art von Informationen Sie aus den Ablaufverfolgungsdateien abrufen können. Sie können basierend auf dem Anbieter die folgenden Flags auswählen:
    
  - **TF_Connection** Stellt verbindungsbezogene Protokolleinträge bereit. Diese Protokolle enthalten Informationen zu Verbindungen, die zu und von einer bestimmten Komponente hergestellt wurden. Dies kann auch wichtige Informationen auf Netzwerkebene umfassen (d. b. für Komponenten ohne das Konzept einer Verbindung).
    
  - **TF_Security** Stellt alle Ereignisse/Protokolleinträge im Zusammenhang mit der Sicherheit bereit. Bei SipStack sind dies z. B. Sicherheitsereignisse wie Domänenüberprüfungsfehler und Clientauthentifizierungs-/Autorisierungsfehler.
    
  - **TF_Diag** Stellt Diagnoseereignisse bereit, die Sie zum Diagnostizieren oder Beheben von Problemen mit der Komponente verwenden können. Bei SipStack sind dies z. B. Zertifikatfehler oder DNS-Warnungen/-Fehler.
    
  - **TF_Protocol** Stellt Protokollmeldungen wie SIP- und kombinierte Community Codec Pack-Nachrichten bereit.
    
  - **TF_Component** Aktiviert die Protokollierung für die als Teil der Anbieter angegebenen Komponenten.
    
  - **Alle** Legt alle für den Anbieter verfügbaren Flags fest.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>So überprüfen Sie Informationen zu vorhandenen Szenarioanbietern für den zentralisierten Protokollierungsdienst

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf. Wenn die angezeigten Informationen nicht ausreichend sind oder die Liste für das Standardformat Windows PowerShell Liste zu lang ist, können Sie zusätzliche Informationen anzeigen, indem Sie eine andere Ausgabemethode definieren. Geben Sie dazu Folgendes ein:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, Typ von Protokollierung, Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>So definieren Sie einen neuen Szenarioanbieter für den zentralisierten Protokollierungsdienst

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Dazu geben Sie Folgendes ein:
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter "Lyss" erfasst werden soll, sieht so aus:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

Die Ebene "-Level" sammelt Schwerwiegendes, Fehler-, Warnungs- und Informationsmeldungen. Die verwendeten Flags sind alle für den Lyss-Anbieter definierten Flags und enthalten TF_Connection, TF_Diag und TF_Protocol.Nachdem die Variable $LyssProvider definiert wurde, können Sie sie mit dem Cmdlet **New-CsClsScenario** verwenden, um Ablaufverfolgungen vom Lyss-Anbieter zu erfassen. Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Hierbei ist "$LyssProvider" die Variable, in der sich das definierte Szenario befindet, das mit **New-CsClsProvider** erstellt wurde.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>So ändern Sie einen vorhandenen Szenarioanbieter für den zentralisierten Protokollierungsdienst

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Dann aktualisieren Sie das Szenario mit der folgenden Eingabe, um den Anbieter zuzuweisen:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

Dieser Befehl bewirkt, dass beim Szenariostandort "Redmond/RedmondLyssInfo" die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von "Get-CsClsScenario" anzeigen. Nähere Informationen dazu finden Sie unter [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** überprüft nicht, ob die Flags gültig sind. Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z. B. TF_DIAG oder TF_CONNECTION). Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.
  
Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Hierbei wurde jeder mit der "Add"-Anweisung festgelegte Anbieter bereits mithilfe des **New-CsClsProvider**-Prozesses definiert.
### <a name="to-remove-a-scenario-provider"></a>So entfernen Sie einen Szenarioanbieter

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
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

[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps)