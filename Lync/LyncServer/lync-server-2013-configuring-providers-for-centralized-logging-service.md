---
title: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst
TOCTitle: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49890779
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst

 

_**Letztes Änderungsdatum des Themas:** 2014-03-19_

Der Begriff und die Konfiguration von *Anbietern* in Zentraler Protokollierungsdienst sollten unbedingt verstanden werden. Die *Anbieter* sind Lync Server-Serverrollenkomponenten im Ablaufverfolgungsmodell von Lync Server direkt zugeordnet. Der Anbieter legt fest, welche Komponenten von Lync Server 2013 verfolgt, welcher Typ von Nachrichten (z. B. schwerwiegende, Fehler- oder Warnnachrichten) erfasst und welche Flags (z. B. "TF\_Connection" oder "TF\_Diag") überwacht werden sollen. Anbieter stellen die nachverfolgbaren Komponenten in jeder Lync Server-Serverrolle dar. Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Instant Messaging oder Anwesenheit). Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.

Zum Ausführen der Zentraler Protokollierungsdienst-Funktionen mithilfe der Lync Server-Verwaltungsshell müssen Sie Mitglied der RBAC-Sicherheitsgruppe "CsAdministrator" oder "CsServerAdministrator oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält. Für eine Liste aller RBAC-Rollen, denen dieses Cmdlet zugewiesen ist (einschließlich aller RBAC-Rollen, die Sie selbst erstellt haben), führen Sie in der Lync Server-Verwaltungsshell oder an der Windows PowerShell-Eingabeaufforderung den folgenden Befehl aus:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Im Rest dieses Themas geht es darum, wie Anbieter definiert oder geändert werden und welche Elemente eine Anbieterdefinition enthält (was bei Fehlerbehebungen hilfreich ist). Es gibt zwei Möglichkeiten, Befehle für den Zentraler Protokollierungsdienst auszustellen: Sie können die Datei CLSCONTROLLER.EXE verwenden, die sich standardmäßig im Verzeichnis "C:\\Programme\\Gemeinsame Dateien\\Microsoft Lync Server 2013\\CLSAgent" befindet. Oder Sie verwenden die Lync Server-Verwaltungsshell, um Windows PowerShell-Befehle zu erteilen. Der wichtigste Unterschied besteht darin, dass es bei Verwendung der Datei CLSCONTROLLER.EXE an der Befehlszeile nur eine begrenzte Auswahl von Szenarien gibt, in denen die Anbieter bereits definiert sind und nicht geändert werden können, Sie jedoch die Protokollierungsstufe festlegen können. Bei Verwendung der Windows PowerShell können Sie neue Anbieter definieren, die in Ihren Protokollierungssitzungen verwendet werden sollen. Außerdem haben Sie die vollständige Kontrolle darüber, wie diese Anbieter erstellt werden, was sie erfassen und auf welcher Ebene Daten erfasst werden sollen.


> [!IMPORTANT]
> Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss.<BR>Damit Sie sich nicht mit sämtlichen Details von Anbietern befassen müssen, stellt Ihnen der Zentraler Protokollierungsdienst eine Reihe von bereits fertig definierten Szenarien bereit. Diese Szenarien decken die allermeisten Probleme ab, die bei Ihnen auftreten könnten. In seltenen Fällen müssen Sie möglicherweise Anbieter definieren, erstellen und zu Szenarien zuweisen. Bevor Sie sich jedoch mit der Erstellung neuer Anbieter und Szenarien befassen, wird dringend empfohlen, dass Sie sich mit den bereits vorhandenen Szenarien gut vertraut machen. Hier sind nur Informationen über das Erstellen von Anbietern aufgeführt, damit Sie verstehen, wie Anbieterelemente in Szenarien genutzt werden, um Ablaufverfolgungsinformationen zu sammeln. Ausführliche Informationen über Anbieter selbst sind hier nicht angegeben.



Wie bereits unter [Übersicht über den zentralisierten Protokollierungsdienst](lync-server-2013-overview-of-the-centralized-logging-service.md) vorgestellt, lauten die wichtigsten Elemente beim Definieren eines Anbieters zwecks Verwendung in einem Szenario wie folgt:

  - **Anbieter:** Wenn Sie mit OCSLogger vertraut sind, können Sie sich Anbieter als die Komponenten vorstellen, durch deren Auswahl Sie OCSLogger mitteilen, aus welchen Protokollen das Ablaufverfolgungsmodul Daten sammeln soll. Die Anbieter sind die gleichen Komponenten und haben in vielen Fällen sogar die gleichen Namen wie in OCSLogger. Wenn Sie sich mit OCSLogger nicht auskennen, können Sie sich Anbieter als serverrollenspezifische Komponenten vorstellen, aus denen der Zentraler Protokollierungsdienst Protokolle sammeln kann. Im Fall des Zentraler Protokollierungsdienst bildet der CLSAgent den architektonischen Teil des Zentraler Protokollierungsdienst, der die Komponenten nachverfolgt, die Sie in der Konfiguration des Anbieters festlegen.

  - **Protokollierungsstufen:** In OCSLogger gab es Möglichkeit, eine Reihe von Detailstufen für die zu sammelnden Daten auszuwählen. Diese Funktion, die ein wichtiger Bestandteil des Zentraler Protokollierungsdienst und der Szenarien ist, wird mit dem **Typ**-Parameter definiert. Sie können unter den folgenden Optionen auswählen:
    
      - **Alle:** Es werden Ablaufverfolgungsmeldungen vom Typ "Schwerwiegend", "Fehler", "Warnung" und "Information" in der Protokolldatei für den festgelegten Anbieter erfasst.
    
      - **Schwerwiegend:** Es werden nur Ablaufverfolgungsmeldungen für den festgelegten Anbieter gesammelt, die einen Ausfall anzeigen.
    
      - **Fehler:** Es werden nur Ablaufverfolgungsmeldungen für den festgelegten Anbieter gesammelt, die einen Fehler anzeigen.
    
      - **Warnung:** Es werden nur solche Ablaufverfolgungsmeldungen gesammelt, die eine Warnung für den festgelegten Anbieter oder Meldungen vom Typ "Schwerwiegend" und "Fehler" sind.
    
      - **Information:** Es werden nur Ablaufverfolgungsmeldungen gesammelt, die eine Informationsmeldung für den festgelegten Anbieter oder Meldungen vom Typ "Schwerwiegend", "Fehler" und "Warnung" sind.
    
      - **Ausführlich:** Es werden alle Ablaufverfolgungsmeldungen vom Typ "Schwerwiegend", "Fehler", "Warnung" und "Information" für den festgelegten Anbieter erfasst.

  - **Flags:** In OCSLogger gab es die Möglichkeit, zu jedem Anbieter Flags auszuwählen, die festlegten, welchen Typ von Informationen Sie aus den Ablaufverfolgungsdateien abrufen konnten. Sie können je nach Anbieter die folgenden Flags auswählen:
    
      - **TF\_Connection:** Für verbindungsbezogene Protokolleinträge. Diese Protokolle enthalten Informationen über Verbindungen, die zu oder aus einer bestimmten Komponente hergestellt wurden. Dazu können auch aussagekräftige Informationen auf Netzwerkebene gehören (d. h. für Komponenten ohne das Konzept einer Verbindung).
    
      - **TF\_Security:** Für alle Ereignisse oder Protokolleinträge bezüglich Sicherheit. Bei "SipStack" zum Beispiel wären das Sicherheitsereignisse wie Domänenvalidierungsfehler und Clientauthentifizierungs-/autorisierungsfehler.
    
      - **TF\_Diag:** Für Diagnoseereignisse, mit deren Hilfe Sie bei Komponenten eine Diagnose oder Problembehandlung durchführen können. Bei "SipStack" zum Beispiel wären das Zertifikatfehler oder DNS-Warnungen/-Fehler.
    
      - **TF\_Protocol:** Für Protokollmeldungen wie SIP- und CCCP-Meldungen.
    
      - **TF\_Component:** Aktiviert die Protokollierung für die Komponenten, die als Bestandteil der Anbieter angegeben sind.
    
      - **All:** Setzt alle Flags, die für den Anbieter verfügbar sind.

## So überprüfen Sie Informationen über vorhandene Zentraler Protokollierungsdienst-Szenarioanbieter

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:
    
        Get-CsClsScenario -Identity <scope and scenario name>
    
    Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf. Wenn die angezeigten Informationen nicht ausreichend sind oder die Liste für das standardmäßige Listenformat der Windows PowerShell zu lang ist, können Sie mehr Informationen anzeigen, indem Sie eine andere Ausgabemethode festlegen. Geben Sie dazu Folgendes ein:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, Typ von Protokollierung, Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden.

## So definieren Sie einen neuen Zentraler Protokollierungsdienst-Szenarioanbieter

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Dazu geben Sie Folgendes ein:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter "Lyss" erfasst werden soll, sieht so aus:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

Die Angabe "–Level "Info"" besagt, dass Meldungen vom Typ "Schwerwiegend", "Fehler", "Warnung" und "Information" gesammelt werden sollen. Mit "-Flags "All"" werden alle für den Anbieter "Lyss" definierten Flags erfasst, d. h. TF\_Connection, TF\_Diag und TF\_Protocol.

Nachdem die Variable "$LyssProvider" definiert ist, können Sie sie beim **New-CsClsScenario**-Cmdlet verwenden, um Ablaufverfolgungen vom Anbieter "Lyss" zu sammeln. Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Hierbei ist "$LyssProvider" die Variable, in der sich das definierte Szenario befindet, das mit **New-CsClsProvider** erstellt wurde.

## So ändern Sie einen vorhandenen Zentraler Protokollierungsdienst-Szenarioanbieter

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Dann aktualisieren Sie das Szenario mit der folgenden Eingabe, um den Anbieter zuzuweisen:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Dieser Befehl bewirkt, dass beim Szenariostandort "Redmond/RedmondLyssInfo" die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von "Get-CsClsScenario" anzeigen. Nähere Informationen dazu finden Sie unter [Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario).


> [!WARNING]
> <STRONG>New-ClsCsProvider</STRONG> überprüft nicht, ob die Flags gültig sind. Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z.&nbsp;B. TF_DIAG oder TF_CONNECTION). Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.



Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Hierbei wurde jeder mit der "Add"-Anweisung festgelegte Anbieter bereits mithilfe des **New-CsClsProvider**-Prozesses definiert.

## So entfernen Sie einen Szenarioanbieter

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Mithilfe der bereitgestellten Cmdlets können Sie vorhandene Anbieter aktualisieren und neue Anbieter erstellen. Wenn Sie einen Anbieter entfernen möchten, müssen Sie bei **Set-CsClsScenario** beim Parameter "-Provider" die Anweisung "Replace" verwenden. Die einzige Möglichkeit, einen Anbieter komplett zu entfernen, besteht darin, ihn durch einen neu definierten Anbieter mit dem gleichen Namen zu ersetzen und die Anweisung "Update" zu verwenden. Beispiel: Der Anbieter "LyssProvider" ist mit dem Protokollierungstyp "WPP", der Protokollierungsebene "Debug" und den gesetzten Flags "TF\_CONNECTION" und "TF\_DIAG" definiert. Sie möchten die Flags auf "Alle" ändern. Geben Sie dazu den folgenden Befehl ein, um den Anbieter zu ändern:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

       &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Wenn Sie ein Szenario mit den zugehörigen Anbietern vollständig entfernen möchten, geben Sie den folgenden Befehl ein:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Beispiel:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    

    > [!WARNING]
    > Das <STRONG>Remove-CsClsScenario</STRONG>-Cmdlet fordert Sie nicht zur Eingabe einer Bestätigung auf. Das Szenario wird, einschließlich der zugewiesenen Anbieter, gelöscht. Sie können das Szenario wieder neu erstellen, indem Sie die Befehle ausführen, mit denen das Szenario ursprünglich erstellt wurde. Ein Verfahren zum Wiederherstellen entfernter Szenarien oder Anbieter gibt es nicht.



Wenn Sie ein Szenario mit dem **Remove-CsClsScenario**-Cmdlet entfernen, wird es komplett aus dem Bereich entfernt. Wenn Sie die von Ihnen erstellten Szenarien mit den zugehörigen Anbietern verwenden möchten, müssen Sie neue Anbieter erstellen und diese einem neuen Szenario zuweisen.

## Siehe auch

#### Weitere Ressourcen

[Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider)

