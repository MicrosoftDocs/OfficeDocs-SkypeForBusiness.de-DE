---
title: 'Lync Server 2013: VoIP-Routen'
description: 'Lync Server 2013: VoIP-Routen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f3c548890c6d2a8c16808eebd9dd50e3ed2715
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554051"
---
# <a name="voice-routes-in-lync-server-2013"></a>VoIP-Routen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Anrufrouten geben an, wie lync Server ausgehende Anrufe von Enterprise-VoIP-Benutzern abwickelt. Wenn ein Benutzer eine Nummer wählt, normalisiert der Front-End-Server die Wählzeichenfolge bei Bedarf in das E. 164-Format und versucht, diese mit einem SIP-URI abzugleichen. Wenn keine Zuordnung möglich ist, wendet der Server eine auf der Nummer basierende Routinglogik für ausgehende Anrufe an. Der letzte Schritt zum Definieren der Logik besteht darin, eine separate benannte Anrufroute für jeden Satz von Zielrufnummern zu erstellen, die in den einzelne Wählplänen aufgeführt sind.

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

Sie können Anrufrouten im lync Server-Systemsteuerung angeben. Bei diesen Anrufrouten wird die Server Routingtabelle aufgefüllt, die lync Server zum Weiterleiten von Anrufen verwendet, die für das PSTN bestimmt sind.

<div>

## <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Lync Server bietet Flexibilität bei der Weiterleitung von Anrufen an das PSTN. Eine VoIP-Route gibt eine Reihe von Trunks für das PSTN an, die für einen bestimmten Sprachanruf verwendet werden können. Ein trunk ordnet eine Vermittlungsserver und eine Portnummer einem PSTN-Gateway und einer Überwachungs Portnummer zu. Durch diese logische Zuordnung kann ein Vermittlungsserver mehreren Gateways zugeordnet werden und über mehrere Verbindungen mit demselben Gateway verfügen. Beim Definieren einer Anrufroute geben Sie die Trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver der Route zugeordnet sind. Verwenden Sie den Topologie-Generator, um Trunks zu erstellen, indem Sie die Beziehungen zwischen Vermittlungsservern und PSTN-Gateways, IP-Nebenstellenanlagen und Sitzungs Rahmen Controllern (SBCS) definieren.

</div>

<div>

## <a name="least-cost-routing"></a>Kostenoptimierter Verbindungsaufbau

Durch das Festlegen von Trunks, an die verschiedene Rufnummern weitergeleitet werden, können Sie die Routen bestimmen, die die geringsten Kosten verursachen, und sie entsprechend implementieren. Normalerweise wählen Sie Trunks aus, indem Sie den Trunk mit dem nächst gelegenen Gateway zum Standort der Zielrufnummer auswählen, um die Gebühren für Ferngespräche möglichst gering zu halten. Wenn Sie sich z. B. in New York befinden und eine Rufnummer in Rom wählen, leiten Sie den Anruf über das IP-Netzwerk an den Trunk mit dem Gateway in Ihrer Niederlassung in Rom weiter, sodass nur Gebühren für ein Ortsgespräch anfallen.

Das folgende Beispiel zeigt eine Verwendungsmöglichkeit des kostenoptimierten Verbindungsaufbaus: Fabrikam beschließt, dass deutsche Benutzer Rufnummern in den USA über den US-Trunk wählen sollen. Außerdem möchte Fabrikam das System so konfigurieren, dass alle Anrufe von US-lync Server Benutzern nach Deutschland und angrenzende Länder/Regionen mit dem Gateway in Deutschland auf dem trunk enden. Durch dieses Routing wird Geld gespart, da ein Anruf von Deutschland nach Österreich beispielsweise weniger kostspielig ist als ein Anruf aus den USA nach Österreich.

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>Übersetzen ausgehender Wählzeichenfolgen

Lync Server 2013 wie seine unmittelbaren Vorgänger erfordert, dass alle Wählzeichenfolgen zum E. 164-Format normalisiert werden, um eine rückwärts Nummernsuche durchführen zu können (können). Für Trunks mit Gateways oder Private Branch Exchanges (PBX), die Nummern in lokalen Wähl Formaten übersetzt erfordern, ermöglicht lync Server 2013 Ihnen, eine oder mehrere Regeln zu erstellen, die das Manipulieren der angerufenen Nummer (also Anforderungs-URI) vor dem Weiterleiten an den trunk unterstützen. Sie können beispielsweise eine Regel schreiben, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.

Mit lync Server 2013 ist es möglich, eine oder mehrere Regeln zu erstellen, die die Manipulation der anrufenden Nummer vor dem Weiterleiten an den trunk unterstützen.

Bei der Planung Ihrer Trunks, die Gateways: Port Pairs mit Vermittlungsserver: Port Pairs zuordnen, kann es hilfreich sein, Trunks mit ähnlichen lokalen wählanforderungen zu gruppieren und somit die Anzahl der erforderlichen Übersetzungsregeln und die Zeit zu verringern, die für das Schreiben der Übersetzung erforderlich ist.

</div>

<div>

## <a name="configuring-caller-id"></a>Konfigurieren der Anrufer-ID

Lync Server bietet eine Möglichkeit zum Bearbeiten der Anrufer-ID für ausgehende Anrufe. Wenn beispielsweise eine Organisation die Durchwahl Durchwahl von Mitarbeitern maskieren und durch die generische Firmen-oder Abteilungsnummer ersetzen möchte, kann ein Administrator dies mithilfe von lync Server-Systemsteuerung durchführen, um die Anrufer-ID zu unterdrücken und durch eine angegebene alternative Anrufer-ID zu ersetzen. Denken Sie bei der Planung der Routinglogik darüber nach, für welche Einzelpersonen, Gruppen oder Standorte Sie diese Optionen verwenden möchten oder ob Sie sie sogar für alle Mitarbeiter verwenden möchten.

<div>


> [!NOTE]  
> Für Anrufe, die über das Telefonfestnetz (PSTN) umgeleitet werden, wird die allgemeine Anrufer-ID anstelle der ursprünglichen Anrufer-ID angezeigt. Dies kann dazu führen, dass "Nicht stören"- oder Privatsphäreeinstellungen umgangen werden, die der angerufene Teilnehmer möglicherweise konfiguriert hat.



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>Zusätzliche Routinglogik

Beachten Sie bei der Erstellung von Routen für ausgehende Anrufe die folgenden Faktoren, die sich auf die Routinglogik auswirken können:

  - Wenn ein Anruf über eine Verbundgrenze hinweg eingerichtet wird, wird der Anruf mithilfe der Domäne im URI an das Unternehmen weitergeleitet, das für die Anwendung der Ausgangsroutinglogik verantwortlich ist.

  - Wenn die im Anforderungs-URI angegebene Domäne nicht für das Unternehmen unterstützt wird, verarbeitet die Ausgangsroutingkomponente auf dem Server den Anruf nicht.

  - Wenn ein Benutzer nicht für Enterprise-VoIP aktiviert ist, wendet der Server nach Bedarf andere Routinglogik an.

  - Wenn der Anruf an ein vollständig besetztes Gateway (bei dem alle Trunkleitungen belegt sind) geroutet wird, weist das Gateway den Anruf zurück, und die Ausgangsroutingkomponente leitet ihn an die Route mit den zweitgeringsten Kosten um. Bedenken Sie dies sorgfältig, da ein Gateway, dessen Größe auf ein kleines Büro in Europa (im Beispiel: Zürich) ausgerichtet ist, möglicherweise einen umfangreichen nicht lokalen Datenverkehr für Auslandsgespräche mit der Schweiz übertragen muss. Wenn das Gateway nicht die richtige Größe für diesen zusätzlichen Datenverkehr aufweist, werden Anrufe aus den USA in die Schweiz möglicherweise über ein Gateway in Deutschland weitergeleitet, was höhere Telefongebühren bedeutet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

