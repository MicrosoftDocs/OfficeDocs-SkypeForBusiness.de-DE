---
title: Lync Server 2013 Anforderungen für Einwahlkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dcdf30ac0fc35f470e74991b2127cd81b05c5c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Anforderungen für Einwahlkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-30_

Bevor Sie mit dem lync Server 2013 Bereitstellungsprozess beginnen, müssen Sie Folgendes planen:

  - Die für die Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) zu verwendende Konfiguration

  - Ihre Strategie für die Zuweisung von Regionen für Einwahlkonferenzen zu Einwahlnummern

  - Ihre Strategie für die Erstellung von Konferenzverzeichnissen

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Planen der Einwahl-PSTN-Konnektivität

Einwahlkonferenzen erfordern mindestens eine Vermittlungsserver und mindestens ein PSTN-Gateway.

Sie können eine Vermittlungsserver an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem zentralen Standort können Sie ein Vermittlungsserver auf einem Front-End-Pool oder Standard Edition-Server collocate oder auf einem eigenständigen Server oder Pool bereitstellen. In einem Zweigstellenstandort können Sie eine Vermittlungsserver auf einem eigenständigen Server oder als Komponente des Survivable Branch Appliance bereitstellen.

Sie können ein PSTN-Gateway an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem Zweigstellenstandort kann das PSTN-Gateway eigenständig oder eine Komponente des Survivable Branch Appliance sein.

<div>


> [!NOTE]  
> Bei Einwahlkonferenzen wird die medienumgehung nicht verwendet, da A/V-Konferenzserver keine medienumgehung unterstützen.



</div>

Ausführliche Informationen zum Planen der Konfiguration für Vermittlungsserver-und PSTN-Gateways für Einwahlkonferenzen finden Sie unter [Components and Topologies for Vermittlungsserver in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Planen von Regionen für Einwahlkonferenzen

Während der Einwahlkonfiguration erstellen Sie Wähleinstellungen und Zugriffsnummern für Einwahlkonferenzen. Wähleinstellungen sind Sätze von Normalisierungsregeln, in welchen die Anzahl und das Muster von Ziffern in einer Telefonnummern festgelegt wird und die die Telefonnummer in das Standard-E.164-Format zur Anrufweiterleitung übersetzen. Zugriffsnummern für Einwahlkonferenzen sind die Nummern, die Benutzer zur Teilnahme an Konferenzen wählen.

Jede Zugriffsnummer für Einwahlkonferenzen muss mindestens einem Satz mit Wähleinstellungen zugeordnet sein. Regionen für Einwahlkonferenzen ordnen eine Zugriffsnummer für Einwahlkonferenzen den entsprechenden Wähleinstellungen zu. Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.

Beim Erstellen von Wähleinstellungen geben Sie den Gültigkeitsbereich der Wähleinstellungen an: Benutzer, Pool oder Standort. Jedem Benutzer werden die Wähleinstellungen aus dem am engsten gefassten Gültigkeitsbereich zugeordnet, der für den Benutzer gilt. Beispielsweise werden dem Benutzer Wähleinstellungen auf Benutzerebene zugewiesen, falls solche gelten. Gelten keine Wähleinstellungen auf Benutzerebene, werden dem Benutzer Wähleinstellungen auf Poolebene zugewiesen. Gelten keine Wähleinstellungen auf Poolebene, werden dem Benutzer Wähleinstellungen auf Standortebene zugewiesen. Gelten keine Wähleinstellungen auf Standortebene, werden dem Benutzer die globalen Wähleinstellungen zugewiesen.

Bevor Sie die Wähleinstellungen konfigurieren, ist es wichtig zu planen, wie die Regionen benannt und verwendet werden sollen. Für die Regionen von Einwahlkonferenzen gelten folgende Überlegungen:

  - Eine Region ist in der Regel ein geografischer Bereich, der einem Büro oder einer Gruppe von Büros zugeordnet wird.

  - Den Einwahlnummern werden Sprachen zugeordnet. Wenn Sie geografische Bereiche mit mehreren Sprachen unterstützen, sollten Sie entscheiden, wie die Regionen für die Unterstützung der verschiedenen Sprachen definiert werden sollen. Beispielsweise können Sie mehrere Regionen basierend auf einer Kombination aus Geografie und Sprache definieren, oder Sie können eine einzige Region basierend auf der Geografie definieren und für jede Sprache eine eigene Einwahlnummer verwenden.

  - Wenn ein Benutzer eine Besprechung plant, wird für die Besprechung standardmäßig die Region verwendet, die durch die Wähleinstellungen des Benutzers festgelegt ist.

  - Standardmäßig sind in der Besprechungseinladung alle Einwahlnummern für die Region enthalten.

  - Regionen müssen unbedingt so benannt werden, dass sie klar erkennbar sind. Der Benutzer kann anhand der Regionsnamen die Region einer Besprechung ändern, damit in der Einladung andere Zugriffsnummern enthalten sind. (Wenn Benutzer Outlook verwenden, um eine Besprechung zu planen, verwendet der Benutzer das Online-Besprechungs-Add-in für lync 2013, um die Region zu ändern).

  - Regionen sollten so konzipiert werden, dass jedem eingeladenen Benutzer, der sich in eine Konferenz einwählen möchte, eine lokale Zugriffsnummer in der Konferenzeinladung angezeigt wird.

  - Sie können die Reihenfolge konfigurieren, in der Zugriffsnummern in einem Bereich in der Seite "Einstellungen für Einwahlkonferenzen" (und daher in der Reihenfolge, in der Sie in der Konferenzeinladung angezeigt werden) mithilfe von lync Server-Verwaltungsshell-Cmdlets angezeigt werden.

  - Jeder Benutzer kann an jedem beliebigen Standort eine beliebige Einwahlnummer wählen, um an einer Konferenz teilzunehmen.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Planen von Konferenzverzeichnissen

Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz bei Verwendung von lync 2013 verwendet, und der numerischen Konferenz-ID, die ein Teilnehmer für Einwahlkonferenzen verwendet, um an der Konferenz teilzunehmen. Das Format der Konferenz-ID lautet folgendermaßen:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) neun übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.

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

