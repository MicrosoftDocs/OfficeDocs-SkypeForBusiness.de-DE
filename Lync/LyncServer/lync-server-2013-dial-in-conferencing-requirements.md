---
title: Voraussetzungen für Einwahlkonferenzen in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Anforderungen für Einwahlkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Bevor Sie den lync Server 2013-Bereitstellungsprozess starten, müssen Sie Folgendes planen:

  - Die Konfiguration, die zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) verwendet werden soll

  - Ihre Strategie für das Zuweisen von Einwahlkonferenz Regionen zu Einwahl Zugriffsnummern

  - Ihre Strategie zum Erstellen von Konferenz Verzeichnissen

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Planen der Einwahl PSTN-Konnektivität

Für Einwahlkonferenzen ist mindestens ein Vermittlungs Server und mindestens ein PSTN-Gateway erforderlich.

Sie können einen Vermittlungsserver an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem zentralen Standort kann ein Vermittlungsserver in einem Front-End-Pool oder auf einem Standard Edition-Server ausgeführt oder auf einem eigenständigen Server oder in einem eigenständigen Pool bereitgestellt werden. An einem Zweigstellenstandort können Sie einen Vermittlungsserver auf einem eigenständigen Server oder als Komponente der Survivable Branch Appliance bereitstellen.

Sie können ein PSTN-Gateway an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem Zweigstellenstandort kann das PSTN-Gateway eigenständig oder als Komponente der Survivable Branch Appliance eingesetzt werden.

<div>


> [!NOTE]  
> Einwahlkonferenzen verwenden keine medienumgehung, da ein/V-Konferenz Server keine medienumgehung unterstützt.



</div>

Ausführliche Informationen zum Planen Ihrer Konfiguration für den Vermittlungsserver und für PSTN-Gateways für Einwahlkonferenzen finden Sie unter [Komponenten und Topologien für den Vermittlungsserver in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Planen von Einwahlkonferenz Regionen

Während der Einwahl Konfiguration erstellen Sie Wählpläne und Zugriffsnummern für Einwahlkonferenzen. Wählpläne sind Sätze von Normalisierungsregeln, die die Anzahl und das Muster von Ziffern in einer Telefonnummer angeben und die Telefonnummer in das standardmäßige E. 164-Format für das Anrufrouting übersetzen. Zugriffsnummern für Einwahlkonferenzen sind die Nummern, die Benutzer zur Teilnahme an Konferenzen wählen.

Jede Zugriffsnummer für Einwahlkonferenzen muss mindestens einem Satz mit Wähleinstellungen zugeordnet sein. In den Regionen für Einwahlkonferenzen wird eine Zugriffsnummer für Einwahlkonferenzen mit ihren Wählplänen verknüpft. Wenn Sie einen Wählplan einrichten, geben Sie den Bereich für Einwahlkonferenzen an, der für die Wähleinstellungen gilt. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.

Wenn Sie einen Wählplan erstellen, geben Sie den Bereich des Wählplans an: Benutzerbereich, Poolbereich oder Website Bereich. Jedem Benutzer werden die Wähleinstellungen aus dem am engsten gefassten Gültigkeitsbereich zugeordnet, der für den Benutzer gilt. Beispielsweise werden dem Benutzer Wähleinstellungen auf Benutzerebene zugewiesen, falls solche gelten. Gelten keine Wähleinstellungen auf Benutzerebene, werden dem Benutzer Wähleinstellungen auf Poolebene zugewiesen. Gelten keine Wähleinstellungen auf Poolebene, werden dem Benutzer Wähleinstellungen auf Standortebene zugewiesen. Gelten keine Wähleinstellungen auf Standortebene, werden dem Benutzer die globalen Wähleinstellungen zugewiesen.

Bevor Sie die Wähleinstellungen konfigurieren, ist es wichtig zu planen, wie die Regionen benannt und verwendet werden sollen. Für die Regionen von Einwahlkonferenzen gelten folgende Überlegungen:

  - Eine Region ist in der Regel ein geografischer Bereich, der einem Büro oder einer Gruppe von Büros zugeordnet wird.

  - Den Einwahlnummern werden Sprachen zugeordnet. Wenn Sie geografische Bereiche mit mehreren Sprachen unterstützen, sollten Sie entscheiden, wie die Regionen für die Unterstützung der verschiedenen Sprachen definiert werden sollen. Beispielsweise können Sie mehrere Regionen basierend auf einer Kombination aus Geografie und Sprache definieren, oder Sie können eine einzige Region basierend auf der Geografie definieren und für jede Sprache eine eigene Einwahlnummer verwenden.

  - Wenn ein Benutzer eine Besprechung plant, wird für die Besprechung standardmäßig die Region verwendet, die durch die Wähleinstellungen des Benutzers festgelegt ist.

  - Standardmäßig sind alle Einwahl Zugriffsnummern für den Bereich in der Besprechungseinladung enthalten.

  - Regionen müssen unbedingt so benannt werden, dass sie klar erkennbar sind. Der Benutzer kann anhand der Regionsnamen die Region einer Besprechung ändern, damit in der Einladung andere Zugriffsnummern enthalten sind. (Wenn Benutzer Outlook zum Planen einer Besprechung verwenden, verwendet der Benutzer das Online Besprechungs-Add-in für lync 2013, um den Bereich zu ändern).

  - Regionen sollten so konzipiert werden, dass jedem eingeladenen Benutzer, der sich in eine Konferenz einwählen möchte, eine lokale Zugriffsnummer in der Konferenzeinladung angezeigt wird.

  - Sie können die Reihenfolge konfigurieren, in der Zugriffsnummern in einem Bereich auf der Seite Einstellungen für Einwahlkonferenzen angezeigt werden (und daher die Reihenfolge, in der Sie in der Konferenzeinladung angezeigt werden), mithilfe der lync Server-Verwaltungsshell-Cmdlets.

  - Jeder Benutzer kann an jedem beliebigen Standort eine beliebige Einwahlnummer wählen, um an einer Konferenz teilzunehmen.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Planen von Konferenz Verzeichnissen

Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz bei Verwendung von lync 2013 verwendet, und der numerischen Konferenz-ID, die ein Teilnehmer für Einwahlkonferenzen verwendet, um an der Konferenz teilzunehmen. Das Format der Konferenz-ID lautet folgendermaßen:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Mit dieser Richtlinie können die Konferenz-IDs in der Regel klein gehalten werden. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) 9 übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Vermittlungsserver Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

