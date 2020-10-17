---
title: 'Lync Server 2013: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst'
description: 'Lync Server 2013: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst.'
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
ms.openlocfilehash: 9146865b3856f7956c6ae393ef38614b0fea168e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547951"
---
# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-19_

Die Konzepte und die Konfiguration von *Anbietern* im zentralisierten Protokollierungsdienst sind eine der wichtigsten, die Sie erfassen müssen. Die *Anbieter* werden lync Server-Server Rollen Komponenten im lync Server-Ablaufverfolgungsmodell direkt zugeordnet. Der Anbieter definiert die Komponenten einer lync Server 2013, die nachverfolgt werden, den Typ der Nachrichten (beispielsweise tödlich, Fehler oder Warnung), die erfasst werden sollen, und die Flags (beispielsweise TF \_ Connection oder TF \_ Diag). Anbieter sind die nachvollziehbaren Komponenten in jeder lync Server Server Rolle. Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Instant Messaging oder Anwesenheit). Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.

Zum Ausführen der Funktionen für den zentralisierten Protokollierungsdienst mit dem lync Server-Verwaltungsshell müssen Sie ein Mitglied der CsAdministrator-oder der CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder eine benutzerdefinierte RBAC-Rolle sein, die eine dieser beiden Gruppen enthält. Zum Zurückgeben einer Liste aller rollenbasierten zugriffssteuerungsrollen, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Im Rest dieses Themas geht es darum, wie Anbieter definiert oder geändert werden und welche Elemente eine Anbieterdefinition enthält (was bei Fehlerbehebungen hilfreich ist). Es gibt zwei Möglichkeiten zum Ausgeben von Befehlen für den zentralisierten Protokollierungsdienst. Sie können die CLSController.exe verwenden, die sich standardmäßig im Verzeichnis C: \\ Programmdateien \\ Allgemeine Dateien \\ Microsoft lync Server 2013 \\ CLSAgent befindet. Sie können auch die lync Server-Verwaltungsshell verwenden, um Windows PowerShell Befehle auszugeben. Bei Verwendung der nm-winshell-2nd können Sie neue Anbieter definieren, die in Ihren Protokollierungssitzungen verwendet werden sollen. Durch die Verwendung von Windows PowerShell können Sie neue Anbieter für die Verwendung in ihren Protokollierungssitzungen definieren, die vollständige Kontrolle über ihre Erstellung, Ihre Sammlung und auf welcher Ebene Sie Daten erfassen.

<div class="">


> [!IMPORTANT]  
> Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss.<BR>Anstatt sich eingehend mit den Details von Anbietern zu befassen, stellt der zentralisierte Protokollierungsdienst eine Reihe von Szenarien bereit, die bereits für Sie definiert sind. Die bereitgestellten Szenarien decken die meisten möglichen Probleme ab, auf die Sie stoßen werden. In seltenen Fällen müssen Sie möglicherweise Anbieter erstellen und definieren und Szenarien zuweisen. Es wird dringend empfohlen, dass Sie sich mit den einzelnen Szenarien vertraut machen, bevor Sie untersuchen, ob neue Anbieter und Szenarien erstellt werden müssen. Während Informationen zum Erstellen von Anbietern hier gefunden werden, um Sie darüber zu informieren, wie die Szenarien die Anbieter Elemente zum Sammeln von Ablaufverfolgungsinformationen verwenden, werden zu diesem Zeitpunkt keine Details zu den Anbietern selbst bereitgestellt.



</div>

In der [Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)werden die wichtigsten Elemente zur Definition eines Anbieters für die Verwendung in einem Szenario wie folgt vorgestellt:

  - **Anbieter**     Wenn Sie mit OCSLogger vertraut sind, handelt es sich bei Anbietern um die Komponenten, die Sie OCSLogger mitteilen, welche Protokolle von dem Ablaufverfolgungsmodul erfasst werden sollen. Die Anbieter entsprechen den Komponenten in OCSLogger und haben in vielen Fällen auch dieselben Namen. Wenn Sie mit OCSLogger nicht vertraut sind, handelt es sich bei Anbietern um Serverrollen spezifische Komponenten, von denen der zentralisierte Protokollierungsdienst Protokolle erfassen kann. Im Fall des zentralisierten Protokollierungsdiensts ist der CLSAgent der Architektur Teil des zentralisierten Protokollierungsdiensts, der die Ablaufverfolgung der in der Anbieterkonfiguration definierten Komponenten ausführt.

  - **Protokollierungsstufen**     OCSLogger hat die Option zum Auswählen einer Reihe von Detailebenen für die gesammelten Daten bereitgestellt. Dieses Feature ist ein integraler Bestandteil des zentralisierten Protokollierungsdiensts und der Szenarien und wird durch den **Type** -Parameter definiert. Es stehen folgende Optionen zur Auswahl:
    
      - **Alle**     Sammelt Ablaufverfolgungsmeldungen vom Typ "Fatal", "Error", "Warning" und "Info" im Protokoll für den definierten Anbieter.
    
      - **Fatal**     Erfasst nur die Ablaufverfolgungsmeldungen, die auf einen Fehler für den definierten Anbieter hindeuten.
    
      - **Fehlermeldung**     Erfasst nur die Ablaufverfolgungsmeldungen, die einen Fehler für den definierten Anbieter sowie fatale Nachrichten angeben.
    
      - **Warnung**     Erfasst nur die Ablaufverfolgungsmeldungen, die eine Warnung für den definierten Anbieter sowie fatale und Fehlermeldungen angeben.
    
      - **Informationen**     Erfasst nur die Ablaufverfolgungsmeldungen, die eine Informationsmeldung für den definierten Anbieter angeben, sowie fatale, fehlerhafte und Warnmeldungen.
    
      - **Ausführlich**     Erfasst alle Ablaufverfolgungsmeldungen vom Typ "Fatal", "Error", "Warning" und "Info" für den definierten Anbieter.

  - **Flags**     OCSLogger hat die Option zum Auswählen von Flags für jeden Anbieter bereitgestellt, die definiert haben, welche Art von Informationen aus den Ablaufverfolgungsdateien abgerufen werden können. Sie können die folgenden Flags basierend auf dem Anbieter auswählen:
    
      - **Tf \_ Connection**     stellt verbindungsbezogene Protokolleinträge bereit. Diese Protokolle enthalten Informationen über Verbindungen, die mit und von einer bestimmten Komponente hergestellt werden. Dies kann auch wichtige Informationen auf Netzwerkebene beinhalten (also für Komponenten ohne das Konzept einer Verbindung).
    
      - **Tf \_ Security**     stellt alle Ereignisse/Protokolleinträge im Zusammenhang mit der Sicherheit bereit. Bei SipStack handelt es sich beispielsweise um Sicherheitsereignisse wie etwa einen Domänen Überprüfungsfehler und Clientauthentifizierung/Autorisierungsfehler.
    
      - **Tf \_ Diag**     stellt Diagnoseereignisse bereit, die Sie zum diagnostizieren oder Problembehandlung der Komponente verwenden können. Bei SipStack handelt es sich beispielsweise um Zertifikat Fehler oder DNS-Warnungen/-Fehler.
    
      - **Tf \_ Protocol**     stellt Protokollnachrichten wie SIP-und kombinierte Community-Codec-Paket Nachrichten bereit.
    
      - **Tf \_ Komponente**     aktiviert die Protokollierung für die Komponenten, die als Teil der Anbieter angegeben werden.
    
      - **Alle**     Legt alle verfügbaren Flags fest, die für den Anbieter verfügbar sind.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>So überprüfen Sie die Informationen zu vorhandenen Szenarien für den zentralisierten Protokollierungsdienst

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf. Wenn die angezeigten Informationen nicht ausreichen oder die Liste für das Standard Windows PowerShell Listenformat zu lang ist, können Sie zusätzliche Informationen anzeigen, indem Sie eine andere Ausgabemethode definieren. Geben Sie dazu Folgendes ein:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, Typ von Protokollierung, Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>So definieren Sie einen neuen Szenario-Anbieter für den zentralisierten Protokollierungsdienst

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Dazu geben Sie Folgendes ein:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter "Lyss" erfasst werden soll, sieht so aus:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

Auf der Ebene "–" werden fatale, Fehler-, Warn-und Informationsmeldungen gesammelt. Die verwendeten Flags sind alle für den Lyss-Anbieter definierten und enthalten TF \_ Connection, TF \_ diag und TF \_ Protocol.

Nachdem die Variable "$LyssProvider" definiert ist, können Sie sie beim **New-CsClsScenario**-Cmdlet verwenden, um Ablaufverfolgungen vom Anbieter "Lyss" zu sammeln. Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Hierbei ist "$LyssProvider" die Variable, in der sich das definierte Szenario befindet, das mit **New-CsClsProvider** erstellt wurde.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>So ändern Sie einen vorhandenen Anbieter für zentralisierte Protokollierungsdienste

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Dann aktualisieren Sie das Szenario mit der folgenden Eingabe, um den Anbieter zuzuweisen:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Dieser Befehl bewirkt, dass beim Szenariostandort "Redmond/RedmondLyssInfo" die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von "Get-CsClsScenario" anzeigen. Nähere Informationen dazu finden Sie unter [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> überprüft nicht, ob die Flags gültig sind. Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z. B. TF_DIAG oder TF_CONNECTION). Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.



</div>

Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Hierbei wurde jeder mit der "Add"-Anweisung festgelegte Anbieter bereits mithilfe des **New-CsClsProvider**-Prozesses definiert.

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>So entfernen Sie einen Szenarioanbieter

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Mithilfe der bereitgestellten Cmdlets können Sie vorhandene Anbieter aktualisieren und neue Anbieter erstellen. Wenn Sie einen Anbieter entfernen möchten, müssen Sie bei **Set-CsClsScenario** beim Parameter "-Provider" die Anweisung "Replace" verwenden. Die einzige Möglichkeit, einen Anbieter komplett zu entfernen, besteht darin, ihn durch einen neu definierten Anbieter mit dem gleichen Namen zu ersetzen und die Anweisung "Update" zu verwenden. Beispielsweise ist unser Anbieter lyssprovider "mit WPP definiert, da der Protokolltyp, der auf Debugebene festgelegte Wert und die Flags festgelegt TF \_ Connection und TF \_ Diag sind. Sie möchten die Flags auf "Alle" ändern. Geben Sie dazu den folgenden Befehl ein, um den Anbieter zu ändern:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Wenn Sie ein Szenario mit den zugehörigen Anbietern vollständig entfernen möchten, geben Sie den folgenden Befehl ein:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Beispiel:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > Das <STRONG>Remove-CsClsScenario</STRONG>-Cmdlet fordert Sie nicht zur Eingabe einer Bestätigung auf. Das Szenario wird, einschließlich der zugewiesenen Anbieter, gelöscht. Sie können das Szenario wieder neu erstellen, indem Sie die Befehle ausführen, mit denen das Szenario ursprünglich erstellt wurde. Ein Verfahren zum Wiederherstellen entfernter Szenarien oder Anbieter gibt es nicht.

    
    </div>

Wenn Sie ein Szenario mit dem **Remove-CsClsScenario**-Cmdlet entfernen, wird es komplett aus dem Bereich entfernt. Wenn Sie die von Ihnen erstellten Szenarien mit den zugehörigen Anbietern verwenden möchten, müssen Sie neue Anbieter erstellen und diese einem neuen Szenario zuweisen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Gruppe-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

