---
title: 'Lync Server 2013: Wählpläne und Normalisierungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Wählpläne und Normalisierungsregeln in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Ein Wählplan ist ein benannter Satz von Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, für einzelne Benutzer oder für Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.

Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für benannte Standorte, Benutzer oder Kontaktobjekte. Ein und dieselbe Wählzeichenfolge kann je nach dem Standort, an dem sie gewählt wurde, und je nach der anrufenden Person bzw. dem anrufenden Kontaktobjekt unterschiedlich interpretiert und übersetzt werden.

<div>

## <a name="dial-plan-scope"></a>Wählplanbereich

Der *Bereich* eines Wählplans bestimmt die Hierarchieebene, auf der der Wählplan angewendet wird. In lync Server kann einem Benutzer ein bestimmter benutzerspezifischer Wählplan zugewiesen werden. Wenn kein Benutzer Wählplan zugewiesen ist, wird der Wählplan für den Registrar-Pool angewendet. Wenn kein Wählplan für den Registrar-Pool vorhanden ist, wird der Standort Wähl Plan angewendet. Wenn für den Benutzer keine bestimmten Wählpläne gelten, wird der globale Wählplan angewendet.

Clients erhalten Wähl Plan-Bereichsebenen über in-Band-Bereitstellungseinstellungen, die bereitgestellt werden, wenn sich Benutzer bei lync Server anmelden. Als Administrator können Sie die Bereichsebenen für Wähleinstellungen mithilfe der lync Server-Systemsteuerung verwalten und zuweisen.

<div>


> [!NOTE]  
> Der PSTN-Gateway-Wählplan auf Dienstebene wird auf eingehende Anrufe von einem bestimmten Gateway angewendet.



</div>

Bereichsebenen für Wählpläne werden wie folgt definiert:

  - **Benutzerwähleinstellungen:** Kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Sprachanwendungen können einen Wählplan pro Benutzer suchen und verwenden, wenn für „phone-context“ der Wert „user-default“ empfangen wird. Damit ein Wählplan zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.

  - **Pool-Wählplan:** Kann auf Dienstebene für alle PSTN-Gateways oder Registrierungsstellen in Ihrer Topologie erstellt werden. Zum Definieren eines Poolwählplans müssen Sie den Dienst (PSTN-Gateway oder Registrierungsstellenpool) angeben, auf den der Wählplan angewendet werden soll.

  - **Website Wähl Plan:** Kann für eine gesamte Website erstellt werden, mit Ausnahme von Benutzern, Gruppen oder Kontaktobjekten, denen ein Pool-Wählplan oder Benutzer Wähl Plan zugewiesen ist. Zum Definieren eines Standortwählplans müssen Sie den Standort angeben, auf den der Wählplan angewendet werden soll.

  - **Globaler Wählplan:** Der Standard-Wählplan, der mit dem Produkt installiert ist. Sie können den globalen Wählplan bearbeiten, aber nicht löschen. Diese Wähleinstellungen gelten für alle Enterprise-VoIP-Benutzer,-Gruppen und-Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen einen Wählplan mit einem spezifischeren Bereich zu.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Planen eines Wählplans

Führen Sie folgende Schritte aus, um einen Wählplan zu planen:

  - Listen Sie alle Standorte auf, an denen sich eine Niederlassung Ihrer Organisation befindet.
    
    Die Liste muss aktuell und vollständig sein. Sie muss immer wieder überprüft werden, wenn sich die Unternehmensorganisation weiterentwickelt. Bei einem großen internationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann diese Aufgabe sehr zeitaufwendig sein.

  - Identifizieren Sie gültige Rufnummernmuster für jeden Standort.
    
    Der zeitaufwendigste Teil der Planung von Wählplänen besteht darin, die gültigen Rufnummernmuster für jeden Standort zu identifizieren. In einigen Fällen können Sie möglicherweise Normalisierungsregeln, die Sie für einen Wählplan erstellt haben, in einen anderen Wählplan kopieren, insbesondere dann, wenn sich die zugehörigen Standorte auf demselben Kontinent oder sogar im selben Land bzw. in derselben Region befinden. In anderen Fällen genügt es möglicherweise, die Rufnummern in einem Wählplan geringfügig zu ändern, um sie auch in anderen Wählplänen verwenden zu können.

  - Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.
    
    Das Erstellen eines Standardbenennungsschemas stellt die Konsistenz innerhalb der gesamten Organisation sicher und vereinfacht Wartung und Updates.

  - Entscheiden Sie, ob für einen einzelnen Standort mehrere Wählpläne erforderlich sind.
    
    Wenn in Ihrer Organisation ein einzelner Wählplan an mehreren Standorten verwaltet wird, müssen Sie möglicherweise dennoch einen separaten Wählplan für Enterprise-VoIP-Benutzer erstellen, die von einer PBX-Anlage (Private Branch Exchange) migrieren und deren vorhandene Erweiterungen beibehalten werden müssen.

  - Entscheiden Sie, ob Wählpläne auf Benutzerebene erforderlich sind. Wenn Sie beispielsweise über Benutzer an einer Zweigstelle verfügen, die bei der zentralen Website registriert sind, oder wenn Sie über Benutzer verfügen, die auf einer überlebensfähigen Branch-Appliance registriert sind, können Sie spezielle Wähl Szenarien für diese Benutzer unter Verwendung von Wählplänen und Normalisierungsregeln für einzelne Benutzer in Frage stellen. . Ausführliche Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit von Zweigstellen für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Ermitteln Sie den Bereich für den Wählplan (wie weiter oben in diesem Thema beschrieben).

Zum Erstellen eines Wählplans geben Sie bei Bedarf Werte in den folgenden Feldern mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell an.

<div>

## <a name="name-and-simple-name"></a>Name und einfacher Name

Bei Benutzerwählplänen sollten Sie einen beschreibenden Namen für die Benutzer, Gruppen oder Kontaktobjekte angeben, denen der Wählplan zugewiesen wird. Bei Website Wählplänen ist das Feld Name mit dem Websitenamen gefüllt und kann nicht geändert werden. Für Pool-Wählpläne ist das Feld "Name" mit dem PSTN-Gateway oder dem Front-End-Pool vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) gefüllt und kann nicht geändert werden.

Der *einfache Name* des Wählplans ist mit einer Zeichenfolge gefüllt, die vom Namen des Wählplans abgeleitet wird. Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. Der Wert *Einfacher Name* darf nicht leer und muss eindeutig sein. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.

</div>

<div>

## <a name="description"></a>Beschreibung

Es wird empfohlen, den allgemeinen, wiedererkennbaren Namen des geografischen Standorts einzugeben, auf den der entsprechende Wählplan angewendet wird. Wenn der Name des Wählplans beispielsweise „London.Contoso.com“ lautet, wird für die Beschreibung der Eintrag „London“ empfohlen.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Region für Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie eine Region angeben, um die Zugriffsnummern für Einwahlkonferenzen dem entsprechenden Wählplan zuzuordnen.

</div>

<div>

## <a name="external-access-prefix"></a>Vorwahl für externen Zugriff

Sie können ein externes Zugriffs Präfix mit bis zu vier Zeichen (\#, \*und 0-9) angeben, wenn Benutzer eine oder mehrere zusätzliche führende Ziffern (beispielsweise 9) wählen müssen, um eine externe Leitung zu erhalten.

<div>


> [!NOTE]  
> Wenn Sie eine Vorwahl für den externen Zugriff eingeben, müssen Sie keine zusätzliche Normalisierungsregeln zur Unterstützung der Vorwahl erstellen.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort. Ein und dieselbe numerische Zeichenfolge wird möglicherweise unterschiedlich interpretiert und übersetzt, je nachdem, von welchem Standort aus sie gewählt wird. Normalisierungsregeln sind für das Anrufrouting notwendig, da Benutzer Rufnummern in unterschiedlichen Formaten in ihre Kontaktlisten eingeben.

Die Normalisierung der von Benutzern eingegebenen Rufnummern stellt ein konsistentes Format bereit, das folgende Aufgaben vereinfacht:

  - Zuordnen einer gewählten Rufnummer zum SIP-URI des gewünschten Empfängers

  - Anwenden von Wählautorisierungsregeln auf den Anrufer

In Normalisierungsregeln müssen möglicherweise die folgenden numerischen Felder berücksichtigt werden:

  - Wählplan

  - Landesvorwahl

  - Ortsvorwahl

  - Länge der Durchwahlnummer

  - Standortvorwahl

<div>

## <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. Sie können Normalisierungsregeln in der lync Server-Systemsteuerung erstellen, indem Sie die Ausdrücke manuell eingeben, oder indem Sie die Anfangsziffern und die Länge der zu entgleichenden Wählzeichenfolgen eingeben und die lync Server-Systemsteuerung die entsprechenden regulärer Ausdruck für Sie. Unabhängig davon, welche Methode Sie anwenden, können Sie anschließend eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.

Ausführliche Informationen zur Verwendung von regulären Ausdrücken in [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).NET Framework finden Sie unter ".NET Framework-reguläre Ausdrücke" unter.

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre .NET Framework-Ausdrücke formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer Normalisierungsregeln dar.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>Tabelle 1: Normalisierungsregeln mit regulären .NET Framework-Ausdrücken

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
<td><p>^ (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>0100 wird in +14255550100 übersetzt.</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Übersetzt fünfstellige Durchwahlnummern</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>50100 wird in +14255550100 übersetzt.</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1425$1</p></td>
<td><p>5550100 wird in +14255550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Dallas</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1972$1</p></td>
<td><p>5550100 wird in +19725550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Übersetzt zehnstellige Rufnummern in US-Rufnummern</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+1$1</p></td>
<td><p>2065550100 wird in +12065550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Übersetzt Rufnummern mit Vorwahlen für Ferngespräche in US-Rufnummern</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+$1</p></td>
<td><p>12145550100 wird in +2145550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Übersetzt Rufnummern mit internationalen Vorwahlen in US-Rufnummern</p></td>
<td><p>^011(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>01191445550100 wird in +91445550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond</p></td>
<td><p>^0$</p></td>
<td><p>+14255550100</p></td>
<td><p>0 wird in +14255550100 übersetzt.</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222)</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>62220100 wird in +14255550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von New York (333)</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+1202555$1</p></td>
<td><p>63330100 wird in +12025550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Dallas-Vorwahl (444)</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+1972555$1</p></td>
<td><p>64440100 wird in +19725550100 übersetzt</p></td>
</tr>
</tbody>
</table>


Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>Tabelle 2: Wählplan für Redmond, basierend auf den in Tabelle 1 gezeigten Normalisierungsregeln

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond.forestFQDN</th>
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
> Die Namen der Normalisierungsregeln in der vorstehenden Tabelle enthalten keine Leerzeichen, aber dies ist nicht obligatorisch. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er „5 digit extension" oder „5-digit Extension" lautet.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

