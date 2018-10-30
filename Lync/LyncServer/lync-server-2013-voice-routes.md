---
title: 'Lync Server 2013: VoIP-Routen'
TOCTitle: VoIP-Routen
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412757(v=OCS.15)
ms:contentKeyID: 49294955
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VoIP-Routen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Anrufrouten legen fest, wie Lync Server ausgehende Anrufe verarbeitet, die von Enterprise-VoIP-Benutzern getätigt werden. Wenn ein Benutzer eine Nummer wählt, normalisiert der Front-End-Server die Wählzeichenfolge bei Bedarf, indem er diese in das E.164-Format übersetzt und versucht, sie einem SIP-URI zuzuordnen. Wenn keine Zuordnung möglich ist, wendet der Server eine auf der Nummer basierende Routinglogik für ausgehende Anrufe an. Der letzte Schritt zum Definieren der Logik besteht darin, eine separate benannte Anrufroute für jeden Satz von Zielrufnummern zu erstellen, die in den einzelne Wählplänen aufgeführt sind.

Vor dem Definieren von Routen für ausgehende Anrufe sollten Sie die folgenden Schritte abschließen:

  - Stellen Sie einen oder mehrere Trunks bereit.

  - Erstellen Sie nach Bedarf Wähleinstellungen für Standorte, Einzelpersonen und Kontaktobjekte.

  - Erstellen Sie PSTN-Verwendungsdatensätze (Public Switched Telephone Network, Telefonfestnetz)

Sie müssen außerdem eine oder mehrere VoIP-Richtlinien erstellen und zuweisen, um das Routen ausgehender Anrufe zu aktivieren. Diese Aktion kann entweder vor oder nach der Definition ausgehender Anrufrouten durchgeführt werden.

Für jede Route müssen Sie Folgendes angeben:

  - Einen Namen, mit dem die Route leicht identifiziert werden kann

  - Eine optionale Beschreibung in Fällen, in denen der Name allein möglicherweise nicht als Beschreibung der Route ausreicht

  - Den regulären Ausdruck für das Vergleichsmuster, das die Zielrufnummern identifiziert, auf welche die Route angewendet wird, sowie Ausnahmen, auf die das Vergleichsmuster nicht angewendet wird

  - Einen oder mehrere Trunks, den Sie der Route zuweisen möchten

  - Die PSTN-Verwendungsdatensätze, über die Benutzer verfügen müssen, um Rufnummern anzurufen, die dem regulären Ausdruck für die Zielrufnummer entsprechen

Sie können Anrufrouten in der Lync Server-Systemsteuerung festlegen. Diese Anrufrouten werden in die Serverroutingtabelle eingetragen, welche von Lync Server zum Routen von Anrufen an das PSTN verwendet wird.

## M:N-Trunkunterstützung

In Lync Server können Anrufe flexibel an das PSTN geleitet werden. Mithilfe einer VoIP-Route werden eine Reihe von Trunks für den PSTN angegeben, die für einen bestimmten VoIP-Anruf verwendet werden können. Ein Trunk ordnet einen Vermittlungsserver und eine Portnummer mit einem PSTN-Gateway und einer Überwachungsportnummer zu. Durch diese logische Zuordnung kann ein Vermittlungsserver mehreren Gateways zugeordnet werden und mehrere Verbindungen mit demselben Gateway aufweisen. Beim Definieren einer Anrufroute geben Sie die Trunks an, die der jeweiligen Route zugeordnet sind. Sie geben jedoch nicht an, welche Vermittlungsserver der Route zugeordnet sind. Verwenden Sie zum Erstellen von Trunks durch Definieren der Beziehungen zwischen Vermittlungsservern und PSTN-Gateways, IP-PBXs und Session Border Controllers (SBCs) den Topologie-Generator.

## Kostenoptimierter Verbindungsaufbau

Durch das Festlegen von Trunks, an die verschiedene Rufnummern weitergeleitet werden, können Sie die Routen bestimmen, die die geringsten Kosten verursachen, und sie entsprechend implementieren. Normalerweise wählen Sie Trunks aus, indem Sie den Trunk mit dem nächst gelegenen Gateway zum Standort der Zielrufnummer auswählen, um die Gebühren für Ferngespräche möglichst gering zu halten. Wenn Sie sich z. B. in New York befinden und eine Rufnummer in Rom wählen, leiten Sie den Anruf über das IP-Netzwerk an den Trunk mit dem Gateway in Ihrer Niederlassung in Rom weiter, sodass nur Gebühren für ein Ortsgespräch anfallen.

Das folgende Beispiel zeigt eine Verwendungsmöglichkeit des kostenoptimierten Verbindungsaufbaus: Fabrikam beschließt, dass deutsche Benutzer Rufnummern in den USA über den US-Trunk wählen sollen. Fabrikam möchte das System außerdem so konfigurieren, dass alle Anrufe von Lync Server-Benutzern in den USA nach Deutschland und die Nachbarländer/-regionen am Trunk mit dem deutschen Gateway eingehen sollen. Durch dieses Routing wird Geld gespart, da ein Anruf von Deutschland nach Österreich beispielsweise weniger kostspielig ist als ein Anruf aus den USA nach Österreich.

## Übersetzen ausgehender Wählzeichenfolgen

Wie in vorherigen Versionen erfordert auch Lync Server 2013 eine Normalisierung aller Wählzeichenfolgen in das E.164-Format, um eine umgekehrte Nummernsuche durchführen zu können. Für Trunks mit Gateways oder Nebenstellenanlagen, für die Nummern in lokale Wählformate übersetzt werden müssen, ermöglicht Ihnen Lync Server 2013 das Erstellen einer oder mehrerer Regeln, die Änderungen der angerufenen Nummer (d. h. des Anforderungs-URI) vor der Weiterleitung an den Trunk erleichtern. Sie können beispielsweise eine Regel schreiben, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.

Mit Lync Server 2013 haben Sie die Möglichkeit, eine oder mehrere Regeln zu erstellen, die Sie bei der Änderung der Rufnummer vor der Weiterleitung an den Trunk unterstützen.

Bei der Planung der Trunks zur Zuordnung von Gateway:Port-Paaren mit Vermittlungsserver:Port-Paaren kann es nützlich sein, Trunks mit ähnlichen lokalen Wählanforderungen zu gruppieren und somit die Anzahl erforderlicher Übersetzungsregeln und den Zeitaufwand für das Schreiben dieser Regeln zu reduzieren.

## Konfigurieren der Anrufer-ID

Lync Server bietet die Möglichkeit, die Anrufer-ID bei ausgehenden Anrufen zu ändern. Wenn eine Organisation beispielsweise die direkten Durchwahlen der Mitarbeiter maskieren und durch die allgemeine Nummer des Unternehmens oder der Abteilung ersetzen möchte, kann ein Administrator jetzt mithilfe der Lync Server-Systemsteuerung die Anrufer-ID unterdrücken und sie durch eine angegebene alternative Anrufer-ID ersetzen. Denken Sie bei der Planung der Routinglogik darüber nach, für welche Einzelpersonen, Gruppen oder Standorte Sie diese Optionen verwenden möchten oder ob Sie sie sogar für alle Mitarbeiter verwenden möchten.


> [!NOTE]
> Für Anrufe, die über das Telefonfestnetz (PSTN) umgeleitet werden, wird die allgemeine Anrufer-ID anstelle der ursprünglichen Anrufer-ID angezeigt. Dies kann dazu führen, dass "Nicht stören"- oder Privatsphäreeinstellungen umgangen werden, die der angerufene Teilnehmer möglicherweise konfiguriert hat.



## Zusätzliche Routinglogik

Beachten Sie bei der Erstellung von Routen für ausgehende Anrufe die folgenden Faktoren, die sich auf die Routinglogik auswirken können:

  - Wenn ein Anruf über eine Verbundgrenze hinweg eingerichtet wird, wird der Anruf mithilfe der Domäne im URI an das Unternehmen weitergeleitet, das für die Anwendung der Ausgangsroutinglogik verantwortlich ist.

  - Wenn die im Anforderungs-URI angegebene Domäne nicht für das Unternehmen unterstützt wird, verarbeitet die Ausgangsroutingkomponente auf dem Server den Anruf nicht.

  - Wenn für einen Benutzer Enterprise-VoIP nicht aktiviert ist, wendet der Server ggf. eine andere geeignete Routinglogik an.

  - Wenn der Anruf an ein vollständig besetztes Gateway (bei dem alle Trunkleitungen belegt sind) geroutet wird, weist das Gateway den Anruf zurück, und die Ausgangsroutingkomponente leitet ihn an die Route mit den zweitgeringsten Kosten um. Bedenken Sie dies sorgfältig, da ein Gateway, dessen Größe auf ein kleines Büro in Europa (im Beispiel: Zürich) ausgerichtet ist, möglicherweise einen umfangreichen nicht lokalen Datenverkehr für Auslandsgespräche mit der Schweiz übertragen muss. Wenn das Gateway nicht die richtige Größe für diesen zusätzlichen Datenverkehr aufweist, werden Anrufe aus den USA in die Schweiz möglicherweise über ein Gateway in Deutschland weitergeleitet, was höhere Telefongebühren bedeutet.

