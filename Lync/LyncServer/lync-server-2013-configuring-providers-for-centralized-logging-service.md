---
title: 'Lync Server 2013: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2428bd11e656d0f1b6295e63ca6106fa7edcbb15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-19_

Die Konzepte und die Konfiguration von *Anbietern* im zentralisierten Protokollierungsdienst sind eine der wichtigsten zu erfassen. Die *Anbieter* werden den lync Server-Rollen Komponenten direkt im lync Server-Ablaufverfolgungsmodell zugeordnet. Der Anbieter definiert die Komponenten eines lync Server 2013, die nachverfolgt werden, den Typ der Nachrichten (beispielsweise fatal, Fehler oder Warnung), die erfasst werden sollen, und die Flags (beispielsweise TF\_Connection oder TF\_Diag). Anbieter sind die nachvollziehbaren Komponenten in jeder lync Server-Serverrolle. Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Chat oder Anwesenheit). Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.

Wenn Sie die Funktionen für den zentralisierten Protokollierungsdienst mithilfe der lync Server-Verwaltungsshell ausführen möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control) oder einer benutzerdefinierten RBAC-Rolle sein, die eines der beiden Diese beiden Gruppen. Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Im weiteren Verlauf dieses Themas wird erläutert, wie Sie Anbieter definieren, einen Anbieter ändern und was eine Anbieter Definition enthält, um die Problembehandlung zu optimieren. Es gibt zwei Möglichkeiten zum Ausgeben von Befehlen für zentralisierte Protokollierungsdienste. Sie können\\die CLSController. exe verwenden, die sich standardmäßig im Verzeichnis C: Programmdateien\\allgemeine Dateien\\Microsoft lync Server 2013\\CLSAgent befindet. Oder Sie können die lync Server-Verwaltungsshell zum Ausgeben von Windows PowerShell-Befehlen verwenden. Der wichtige Unterschied besteht darin, dass bei der Verwendung von CLSController. exe in der Befehlszeile eine begrenzte Auswahl von Szenarien verfügbar ist, in denen die Anbieter bereits definiert sind und nicht änderbar sind, Sie aber die Protokollebene definieren können. Mithilfe von Windows PowerShell können Sie neue Anbieter für die Verwendung in ihren Protokollierungssitzungen definieren, die vollständige Kontrolle über ihre Erstellung, deren Erfassung und auf welcher Ebene Sie Daten sammeln.

<div class="">


> [!IMPORTANT]  
> Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss.<BR>Anstatt zu verlangen, dass Sie sich eingehend mit den Details von Anbietern befassen, bietet der zentralisierte Protokollierungsdienst eine Reihe von Szenarien, die bereits für Sie definiert sind. Die bereitgestellten Szenarien decken die meisten möglichen Probleme ab, die Ihnen auftreten können. In seltenen Fällen müssen Sie möglicherweise Anbieter erstellen und definieren und diese Szenarien zuweisen. Wir empfehlen Ihnen dringend, sich mit den einzelnen Szenarien vertraut zu machen, bevor Sie untersuchen, ob neue Anbieter und Szenarien erstellt werden müssen. Während Informationen zum Erstellen von Anbietern hier gefunden werden, um Sie mit den Szenarien vertraut zu machen, in denen die Anbieter Elemente zum Sammeln von Ablaufverfolgungsinformationen verwendet werden, werden zu diesem Zeitpunkt keine Details zu den Anbietern selbst bereitgestellt.



</div>

In der [Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)werden die wichtigsten Elemente zum Definieren eines Anbieters für die Verwendung in einem Szenario vorgestellt:

  - **Anbieter**   Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, um OCSLogger zu informieren, von welchem das Ablaufverfolgungsmodul Protokolle sammeln soll. Die Anbieter sind die gleichen Komponenten und haben in vielen Fällen denselben Namen wie die Komponenten in OCSLogger. Wenn Sie mit OCSLogger nicht vertraut sind, sind Anbieterserver rollenspezifische Komponenten, über die der zentralisierte Protokollierungsdienst Protokolle sammeln kann. Beim zentralisierten Protokollierungsdienst ist der CLSAgent der architektonische Teil des zentralen Protokollierungsdiensts, bei dem die Nachverfolgung der Komponenten erfolgt, die Sie in der Anbieterkonfiguration definieren.

  - **Protokollierungsstufen**   OCSLogger die Option zum Auswählen einer Reihe von Detailebenen für die gesammelten Daten. Dieses Feature ist ein integraler Bestandteil des zentralen Protokollierungsdiensts und der Szenarien und wird durch den **Type** -Parameter definiert. Sie haben folgende Auswahlmöglichkeiten:
    
      - **Alle**   sammelt Nachverfolgungsmeldungen vom Typ fatal, Fehler, Warnung und Informationen in das Protokoll des definierten Anbieters.
    
      - **Fatal**   sammelt nur die Ablaufverfolgungsmeldungen, die einen Fehler für den definierten Anbieter angeben.
    
      - **Fehler**   sammelt nur die Ablaufverfolgungsmeldungen, die einen Fehler für den definierten Anbieter angeben, sowie schwerwiegende Nachrichten.
    
      - **Warnung**   sammelt nur die Ablaufverfolgungsmeldungen, die eine Warnung für den definierten Anbieter sowie fatale und Fehlermeldungen angeben.
    
      - **Informationen**   sammelt nur die Ablaufverfolgungsmeldungen, die eine Informationsmeldung für den definierten Anbieter angeben, sowie fatale, Fehler-und Warnmeldungen.
    
      - **Verbose**   sammelt alle Ablaufverfolgungsmeldungen vom Typ fatal, Fehler, Warnung und Informationen für den definierten Anbieter.

  - **Flags**   OCSLogger hat die Option zum Auswählen von Flags für jeden Anbieter bereitgestellt, die definiert haben, welche Art von Informationen aus den Ablaufverfolgungsdateien abgerufen werden können. Auf der Grundlage des Anbieters können Sie die folgenden Flags auswählen:
    
      - **TF\_Connection**   bietet verbindungsbezogene Protokolleinträge. Diese Protokolle umfassen Informationen zu Verbindungen, die zu und von einer bestimmten Komponente hergestellt wurden. Dies kann auch wichtige Informationen auf Netzwerkebene enthalten (also für Komponenten ohne das Konzept einer Verbindung).
    
      - **TF\_Security**   stellt alle Ereignisse/Protokolleinträge in Bezug auf Sicherheit bereit. Bei SipStack handelt es sich beispielsweise um Sicherheitsereignisse wie Fehler bei der Domänenüberprüfung und Clientauthentifizierung/Autorisierungsfehler.
    
      - **TF\_Diag**   stellt Diagnoseereignisse bereit, die Sie zur Diagnose oder Problembehandlung der Komponente verwenden können. Bei SipStack handelt es sich beispielsweise um Zertifikat Fehler oder DNS-Warnungen/-Fehler.
    
      - **Das\_TF-Protokoll**   bietet Protokollnachrichten wie SIP-und kombinierte Community-Codec-Paket Nachrichten.
    
      - **Die\_TF-Komponente**   ermöglicht die Protokollierung an den als Teil der Anbieter angegebenen Komponenten.
    
      - **Alle**   legt alle verfügbaren Flags fest, die für den Anbieter verfügbar sind.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>So überprüfen Sie Informationen zu vorhandenen Szenario-Anbietern für zentralisierte Protokollierungsdienste

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf. Wenn die angezeigten Informationen nicht ausreichen oder die Liste für das standardmäßige Windows PowerShell-Listenformat zu lang ist, können Sie zusätzliche Informationen anzeigen, indem Sie eine andere Ausgabemethode definieren. Geben Sie dazu Folgendes ein:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, der Protokollierungstyp, die Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>So definieren Sie einen neuen szenariodienst für zentrale Protokollierungsdienste

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Geben Sie dazu Folgendes ein:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter „Lyss“ erfasst werden soll, sieht so aus:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

Die Stufe – sammelt fatale, Fehler-, Warnungs-und Informationsnachrichten. Bei den verwendeten Flags handelt es sich um alle für den Lyss-Anbieter definierten Flags\_, die TF\_Connection, TF\_diag und TF-Protokoll umfassen.

Nachdem die Variable „$LyssProvider“ definiert ist, können Sie sie mit dem Cmdlet **New-CsClsScenario** verwenden, um Ablaufverfolgungen vom Anbieter „Lyss“ zu sammeln. Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Hierbei ist „$LyssProvider“ die Variable, in der sich das definierte Szenario befindet, das mit **New-CsClsProvider** erstellt wurde.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>So ändern Sie einen vorhandenen szenariodienst für zentralisierte Protokollierungsdienste

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Aktualisieren Sie das Szenario anschließend mit der folgenden Eingabe, um den Anbieter zuzuweisen:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Dieser Befehl bewirkt, dass beim Szenariostandort „Redmond/RedmondLyssInfo“ die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von „Get-CsClsScenario“ anzeigen. Weitere Informationen dazu finden Sie unter [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> überprüft nicht, ob die Flags gültig sind. Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z. B. TF_DIAG oder TF_CONNECTION). Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.



</div>

Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Hierbei wurde jeder mit der „Add“-Anweisung festgelegte Anbieter bereits mithilfe des **New-CsClsProvider**-Prozesses definiert.

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>So entfernen Sie einen Szenarioanbieter

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Mithilfe der bereitgestellten Cmdlets können Sie vorhandene Anbieter aktualisieren und neue Anbieter erstellen. Wenn Sie einen Anbieter entfernen möchten, müssen Sie bei **Set-CsClsScenario** beim Parameter „-Provider“ die Anweisung „Replace“ verwenden. Die einzige Möglichkeit, einen Anbieter komplett zu entfernen, besteht darin, ihn durch einen neu definierten Anbieter mit dem gleichen Namen zu ersetzen und die Anweisung „Update“ zu verwenden. So wird beispielsweise unser Anbieter LyssProvider mit WPP als Protokolltyp definiert, auf Debugebene festgelegt, und Flags sind TF\_Connection und TF\_diag. Sie möchten die Flags auf „Alle“ ändern. Geben Sie dazu den folgenden Befehl ein, um den Anbieter zu ändern:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Wenn Sie ein Szenario mit den zugehörigen Anbietern vollständig entfernen möchten, geben Sie den folgenden Befehl ein:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Beispiel:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > Das Cmdlet <STRONG>Remove-CsClsScenario</STRONG> fordert Sie nicht zur Eingabe einer Bestätigung auf. Das Szenario wird einschließlich der zugewiesenen Anbieter gelöscht. Sie können das Szenario wieder neu erstellen, indem Sie die Befehle ausführen, mit denen das Szenario ursprünglich erstellt wurde. Ein Verfahren zum Wiederherstellen entfernter Szenarien oder Anbieter gibt es nicht.

    
    </div>

Wenn Sie ein Szenario mit dem Cmdlet**Remove-CsClsScenario** entfernen, wird es komplett aus dem Bereich entfernt. Wenn Sie die von Ihnen erstellten Szenarien mit den zugehörigen Anbietern verwenden möchten, müssen Sie neue Anbieter erstellen und diese einem neuen Szenario zuweisen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

