---
title: 'Lync Server 2013: Wählpläne und Normalisierungsregeln'
description: 'Lync Server 2013: Wählpläne und Normalisierungsregeln.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559741"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Wählpläne und Normalisierungsregeln in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.

Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt. Die gleiche Wählzeichenfolge kann unterschiedlich interpretiert und übersetzt werden, je nach Standort, von dem Sie gewählt wird, und der Person oder dem Kontaktobjekt, die den Anruf tätigen.

<div>

## <a name="dial-plan-scope"></a>Wähl Plan Bereich

Der *Bereich* eines Wähl Plans bestimmt die hierarchische Ebene, auf der die Wähleinstellungen angewendet werden können. In lync Server kann ein Benutzer einen bestimmten Wählplan für einzelne Benutzer zuweisen. Wenn kein Benutzer Wähl Plan zugewiesen ist, wird der Wählplan für den registrierungsstellenpool angewendet. Wenn kein Wählplan für einen registrierungsstellenpool vorhanden ist, wird der Standort Wähl Plan angewendet. Wenn keine anderen Wähleinstellungen für den Benutzer gelten, wird der globale Wählplan angewendet.

Clients erhalten Wähl planbereichs Ebenen durch in-Band-Bereitstellung Einstellungen, die bereitgestellt werden, wenn sich Benutzer bei lync Server anmelden. Als Administrator können Sie Bereichsebenen für Wähleinstellungen mithilfe von lync Server-Systemsteuerung verwalten und zuweisen.

<div>


> [!NOTE]  
> Die Wähleinstellungen für das öffentliche Telefonnetz (PSTN) auf Dienstebene werden auf eingehende Anrufe von einem bestimmten Gateway angewendet.



</div>

Bereichsebenen für Wähleinstellungen sind wie folgt definiert:

  - **Benutzerwähleinstellungen:** Kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. VoIP-Anwendungen können einen benutzerbezogenen Wählplan nachschlagen, wenn ein Anruf mit dem auf Benutzer Standard festgelegten Telefonkontext empfangen wird. Für den Zweck der Zuweisung eines Wählplans wird ein Kontaktobjekt als einzelner Benutzer behandelt.

  - **Pool Wähl Plan:** Kann auf Dienstebene für ein beliebiges PSTN-Gateway oder eine Registrierungsstelle in Ihrer Topologie erstellt werden. Um einen Wählplan für einen Pool zu definieren, müssen Sie den jeweiligen Dienst (PSTN-Gateway oder registrierungsstellenpool) angeben, auf den der Wählplan angewendet wird.

  - **Website Wähl Plan:** Kann für eine gesamte Website erstellt werden, mit Ausnahme von Benutzern, Gruppen oder Kontaktobjekten, denen ein Pool Wähl Plan oder Benutzer Wähl Plan zugewiesen ist. Zum Definieren eines Website Wähl Plans müssen Sie den Standort angeben, auf den der Wählplan angewendet wird.

  - **Globale Wähleinstellungen:** Die Standard Wähleinstellungen, die mit dem Produkt installiert sind. Sie können die globalen Wähleinstellungen bearbeiten, jedoch nicht löschen. Dieser Wählplan gilt für alle Enterprise-VoIP-Benutzer,-Gruppen und-Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen einen Wählplan mit einem spezifischeren Bereich zu.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Planen von Wählplänen

Führen Sie die folgenden Schritte aus, um einen Wählplan zu planen:

  - Auflisten aller Gebietsschemas, in denen Ihre Organisation über ein Office verfügt.
    
    Die Liste muss auf dem neuesten Stand und vollständig sein. Es muss überarbeitet werden, wenn sich die Unternehmensorganisation entwickelt. In einem großen multinationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann dies eine zeitaufwändige Aufgabe sein.

  - Identifizieren gültiger Zahlenmuster für jede Website.
    
    Der zeitaufwändigste Teil der Planung Ihrer Wählpläne ist die Ermittlung gültiger Nummernmuster für jeden Standort. In einigen Fällen können Sie möglicherweise Normalisierungsregeln, die Sie für einen Wählplan geschrieben haben, in andere Wählpläne kopieren, insbesondere dann, wenn sich die entsprechenden Standorte innerhalb desselben Landes/einer Region oder sogar eines Kontinents befinden. In anderen Fällen können kleine Änderungen an Zahlen in einem Wählplan ausreichen, um Sie in anderen Wählplänen zu verwenden.

  - Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.
    
    Durch die Einführung eines Standardbenennungsschemas wird die Konsistenz in einer Organisation gewährleistet, und Wartungs-und Aktualisierungsvorgänge werden vereinfacht.

  - Entscheiden Sie, ob mehrere Wählpläne für einen einzelnen Standort erforderlich sind.
    
    Wenn Ihre Organisation einen einzelnen Wählplan über mehrere Standorte hinweg verwaltet, müssen Sie möglicherweise dennoch einen separaten Wählplan für Enterprise-VoIP-Benutzer erstellen, die von einer Nebenstellenanlage migrieren und die vorhandenen Erweiterungen beibehalten müssen.

  - Entscheiden Sie, ob benutzerspezifische Wählpläne erforderlich sind. Wenn Sie beispielsweise über Benutzer an einem Zweigstellenstandort verfügen, die beim zentralen Standort registriert sind oder wenn Sie über Benutzer verfügen, die in einem Survivable Branch Appliance registriert sind, können Sie spezielle Wähl Szenarien für solche Benutzer verwenden, die benutzerspezifische Wählpläne und Normalisierungsregeln verwenden. Ausführliche Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Bestimmen des Wähl planbereichs (wie zuvor in diesem Thema beschrieben).

Zum Erstellen eines Wählplans geben Sie bei Bedarf Werte in den folgenden Feldern an, indem Sie lync Server-Systemsteuerung oder lync Server-Verwaltungsshell verwenden.

<div>

## <a name="name-and-simple-name"></a>Name und einfacher Name

Für Benutzer Wähl Pläne sollten Sie einen beschreibenden Namen angeben, der die Benutzer, Gruppen oder Kontaktobjekte identifiziert, denen der Wählplan zugewiesen wird. Für Standortwählpläne wird das Feld Name mit dem Namen des Standorts vorausgefüllt und kann nicht geändert werden. Bei Pool Wählplänen wird das Feld Name mit dem PSTN-Gateway oder Front-End-Pool vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) aufgefüllt und kann nicht geändert werden.

Der *einfache Name* des Wählplans wird mit einer Zeichenfolge aufgefüllt, die vom Namen des Wählplans abgeleitet ist. Das Feld einfacher Name ist bearbeitbar, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne erstellen können. Der Wert des *einfachen namens* darf nicht leer sein und muss eindeutig sein. Eine bewährte Methode besteht darin, eine Benennungskonvention für Ihre gesamte Organisation zu entwickeln und diese Konvention dann einheitlich für alle Websites und Benutzer zu verwenden.

</div>

<div>

## <a name="description"></a>Beschreibung

Es wird empfohlen, den allgemeinen, erkennbaren Namen des geografischen Standorts einzugeben, auf den die entsprechenden Wähleinstellungen angewendet werden. Wenn der Name des Wählplans beispielsweise London.contoso.com lautet, lautet die empfohlene Beschreibung London.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Region für Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie eine Einwahlkonferenz Region angeben, um Zugriffsnummern für Einwahlkonferenzen mit Wähleinstellungen zuzuordnen.

</div>

<div>

## <a name="external-access-prefix"></a>Präfix für externen Zugriff

Sie können ein externes Zugriffs Präfix mit bis zu vier Zeichen ( \# , \* und 0-9) angeben, wenn Benutzer eine oder mehrere zusätzliche führende Ziffern (beispielsweise 9) zum Abrufen einer externen Leitung wählen müssen.

<div>


> [!NOTE]  
> Wenn Sie ein externes Zugriffs Präfix angeben, müssen Sie keine zusätzliche Normalisierungsregel erstellen, um das Präfix anzupassen.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren, wie Telefonnummern, die in verschiedenen Formaten ausgedrückt werden, für den benannten Standort weitergeleitet werden sollen. Die gleiche Nummernzeichenfolge kann je nach Gebietsschema, aus dem Sie gewählt wird, unterschiedlich interpretiert und übersetzt werden. Normalisierungsregeln sind für das Anrufrouting erforderlich, da Benutzer unterschiedliche Formate bei der Eingabe von Telefonnummern in ihren Kontaktlisten verwenden können.

Durch die Normalisierung der von Benutzern bereitgestellten Telefonnummern wird ein konsistentes Format bereitgestellt, das die folgenden Aufgaben unterstützt:

  - Entspricht einer gewählten Nummer dem SIP-URI des beabsichtigten Empfängers.

  - Wenden Sie Wähl Autorisierungsregeln auf den anrufenden Teilnehmer an.

Die folgenden Zahlenfelder gehören zu denen, die ihre Normalisierungsregeln möglicherweise berücksichtigen müssen:

  - Wählplan

  - Landeskennzahl

  - Vorwahl

  - Länge der Erweiterung

  - Standortpräfix

<div>

## <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um numerische Übereinstimmungsmuster anzugeben, die der Server verwendet, um Wählzeichenfolgen in das E. 164-Format zu übersetzen, um eine umgekehrte Nummernsuche durchführen zu können. Normalisierungsregeln werden im lync Server-Systemsteuerung entweder durch manuelles Eingeben der Ausdrücke oder durch Eingeben der Start Ziffern und der Länge der zu entgegen gebenden Wählzeichenfolgen und dem lync Server-Systemsteuerung generieren des entsprechenden regulären Ausdrucks für Sie erstellt. In beiden Fällen können Sie, wenn Sie fertig sind, eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.

Ausführliche Informationen zur Verwendung .NET Framework reguläre Ausdrücke finden Sie unter ".NET Framework reguläre Ausdrücke" unter [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als .NET Framework reguläre Ausdrücke geschrieben werden. Die Beispiele sind nur Beispiele und sollen keine normative Referenz für die Erstellung eigener Normalisierungsregeln sein.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>Tabelle 1. Normalisierungsregeln, die .NET Framework reguläre Ausdrücke verwenden

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Regelname</th>
<th>Beschreibung</th>
<th>Nummernmuster</th>
<th>Übersetzung</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>Übersetzt vierstellige Durchwahlnummern</p></td>
<td><p>^(\d{4})$</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>0100 wird in + 14255550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Übersetzt fünfstellige Durchwahlnummern</p></td>
<td><p>^ 5 (\d {4} ) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>50100 wird in + 14255550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Übersetzt 7-stellige Nummern in lokale Redmond-Nummern.</p></td>
<td><p>^(\d{7})$</p></td>
<td><p>+ 1425 $1</p></td>
<td><p>5550100 wird in + 14255550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Übersetzt siebenstellige Nummern in lokale Dallas-Nummern</p></td>
<td><p>^(\d{7})$</p></td>
<td><p>+ 1972 $1</p></td>
<td><p>5550100 wird in + 19725550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Übersetzt 10-stellige Zahlen in den USA</p></td>
<td><p>^(\d{10})$</p></td>
<td><p>+1$1</p></td>
<td><p>2065550100 wird in + 12065550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Übersetzt Nummern mit Präfixen für Ferngespräche in den Vereinigten Staaten</p></td>
<td><p>^ 1 (\d {10} ) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100 wird in + 2145550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Übersetzt Nummern mit internationalen Präfixen in den Vereinigten Staaten</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100 wird in + 91445550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Übersetzt 0 nach Redmond-Operator</p></td>
<td><p>↑ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0 wird in + 14255550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Übersetzt Nummern mit on-net prefix (6) und Redmond Site Code (222)</p></td>
<td><p>^ 6222 (\d {4} ) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>62220100 wird in + 14255550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Übersetzt Nummern mit on-net prefix (6) und NY Site Code (333)</p></td>
<td><p>^ 6333 (\d {4} ) $</p></td>
<td><p>+ 1202555 $1</p></td>
<td><p>63330100 wird in + 12025550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Übersetzt Nummern mit on-net prefix (6) und Dallas Site Code (444)</p></td>
<td><p>^ 6444 (\d {4} ) $</p></td>
<td><p>+ 1972555 $1</p></td>
<td><p>64440100 wird in + 19725550100 übersetzt</p></td>
</tr>
</tbody>
</table>


Die folgende Tabelle zeigt einen beispielhaften Wählplan für Redmond, Washington, USA, basierend auf den Normalisierungsregeln in der vorherigen Tabelle.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>Tabelle 2. Auf der Grundlage von Normalisierungsregeln in Tabelle 1 angezeigte Redmond-Wähleinstellungen

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond. FQDN festgelegt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Die Namen der Normalisierungsregeln, die in der obigen Tabelle angezeigt werden, enthalten keine Leerzeichen, dies ist jedoch eine Frage der Wahl. Der erste Name in der Tabelle könnte beispielsweise als "5-stellige Durchwahl" oder "5-stellige Durchwahlnummer" geschrieben worden sein und trotzdem gültig sein.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

