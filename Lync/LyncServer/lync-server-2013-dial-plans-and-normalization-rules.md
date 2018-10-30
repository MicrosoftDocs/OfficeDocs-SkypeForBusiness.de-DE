---
title: 'Lync Server 2013: Wählpläne und Normalisierungsregeln'
TOCTitle: Wählpläne und Normalisierungsregeln
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413082(v=OCS.15)
ms:contentKeyID: 49296010
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wählpläne und Normalisierungsregeln in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Ein Wählplan ist ein benannter Satz Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.

Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt. Ein und dieselbe Wählzeichenfolge kann je nach Standort, an dem sie gewählt wurde, und je nach Person oder Kontaktobjekt, die bzw. das den Anruf tätigt, unterschiedlich interpretiert und übersetzt werden.

## Bereich für Wählpläne

Der *Bereich* eines Wählplans bestimmt die Hierarchieebene, auf der der Wählplan angewendet wird. In Lync Server kann einem Benutzer ein bestimmter Wählplan auf Benutzerebene zugewiesen werden. Wenn kein Wählplan zugewiesen wurde, wird der Wählplan des Registrierungspools angewendet. Ist kein Wählplan des Registrierungspools vorhanden, wird der Wählplan des Standorts angewendet. Wenn für den Benutzer keine bestimmten Wählpläne gelten, wird der globale Wählplan angewendet.

Clients rufen die Bereichsebene für Wählpläne durch In-Band-Bereitstellungseinstellungen ab, die bereitgestellt werden, wenn Benutzer sich bei Lync Server anmelden. Als Administrator können Sie Bereichsebenen für Wählpläne über die Lync Server-Systemsteuerung verwalten und zuweisen.


> [!NOTE]
> Der PSTN-Gateway-Wählplan auf Dienstebene wird auf eingehende Anrufe von einem bestimmten Gateway angewendet.



Bereichsebenen für Wählpläne werden folgendermaßen definiert

  - **Benutzerwählplan :** Diese Einstellungen können einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Sprachanwendungen können einen Wählplan pro Benutzer suchen und verwenden, wenn für "phone-context" der Wert "user-default" empfangen wird. Damit ein Wählplan zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.

  - **Poolwählplan :** Diese Einstellungen können auf Dienstebene von jedem PSTN-Gateway oder jeder Registrierung in Ihrer Topologie erstellt werden. Zum Definieren eines Poolwählplans müssen Sie den Dienst (PSTN-Gateway oder Registrierungspool) angeben, auf den der Wählplan angewendet werden soll.

  - **Standortwählplan :** Diese Einstellungen können für einen gesamten Standort erstellt werden, mit Ausnahme von jeglichen Benutzern, Gruppen oder Kontaktobjekten, denen ein Pool- oder Benutzerwählplan zugewiesen wurde. Zum Definieren einen Standortwählplans müssen Sie den Standort angeben, für den der Wählplan angewendet werden soll.

  - **Globaler Wählplan :** Dies ist der mit dem Produkt installierte Standardwählplan. Sie können den globalen Wählplan bearbeiten, nicht jedoch löschen. Dieser Wählplan gilt für alle Enterprise-VoIP-Benutzer, -Gruppen und -Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren einen Wählplan mit einem spezifischeren Bereich und weisen diesen zu.

## Planen eines Wählplans

Führen Sie folgende Schritte aus, um einen Wählplan zu planen:

  - Listen Sie alle Standorte auf, an denen sich eine Niederlassung Ihrer Organisation befindet.
    
    Die Liste muss aktuell und vollständig sein. Sie muss immer wieder überprüft werden, wenn sich die Unternehmensorganisation weiterentwickelt. Bei einem großen internationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann diese Aufgabe sehr zeitaufwendig sein.

  - Identifizieren Sie gültige Rufnummernmuster für jeden Standort.
    
    Der zeitaufwendigste Teil der Planung von Wählplänen besteht darin, die gültigen Rufnummernmuster für jeden Standort zu identifizieren. In einigen Fällen können Sie möglicherweise Normalisierungsregeln, die Sie für einen Wählplan erstellt haben, in einen anderen Wählplan kopieren, insbesondere dann, wenn sich die zugehörigen Standorte auf demselben Kontinent oder sogar im selben Land bzw. in derselben Region befinden. In anderen Fällen genügt es möglicherweise, die Rufnummern in einem Wählplan geringfügig zu ändern, um sie auch in anderen Wählplänen verwenden zu können.

  - Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.
    
    Das Erstellen eines Standardbenennungsschemas stellt die Konsistenz innerhalb der gesamten Organisation sicher und vereinfacht Wartung und Updates.

  - Entscheiden Sie, ob für einen einzelnen Standort mehrere Wählpläne erforderlich sind.
    
    Wenn Ihre Organisation einen einzigen Wählplan für mehrere Standorte verwendet, müssen Sie möglicherweise dennoch einen separate Wählplan für Enterprise-VoIP-Benutzer erstellen, die von einer Nebenstellenanlage migriert werden und ihre vorhandenen Durchwahlnummern behalten müssen.

  - Entscheiden Sie, ob Wählpläne auf Benutzerebene erforderlich sind. Wenn beispielsweise Benutzer am zentralen Standort registriert sind, sich jedoch an einem Zweigstellenstandort befinden, oder wenn Benutzer bei einer Survivable Branch-Anwendung registriert sind, können Sie spezielle Wählszenarios für solche Benutzer mit benutzerbezogenen Wählplänen und Normalisierungsregeln unterstützen. Ausführliche Informationen finden Sie unter [Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Ermitteln Sie den Bereich für den Wählplan (wie weiter oben in diesem Thema beschrieben).

Zum Erstellen eines Wählplans geben Sie mithilfe der Lync Server-Systemsteuerung oder der Lync Server-Verwaltungsshell je nach Bedarf Werte in den folgenden Fehldern ein.

## Name und einfacher Name

Bei Benutzerwählplänen sollten Sie einen beschreibenden Namen für die Benutzer, Gruppen oder Kontaktobjekte angeben, denen der Wählplan zugewiesen wird. Für Standortwählpläne ist das Feld **Name** bereits mit dem Namen des Standorts aufgefüllt und kann nicht geändert werden. Für Poolwählpläne ist das Feld **Name** bereits mit dem Namen des PSTN-Gateways oder dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools aufgefüllt und kann nicht geändert werden.

Der Wählplan *Einfacher Name* ist bereits mit einer vom Namen des Wählplans abgeleiteten Zeichenfolge aufgefüllt. Das Feld **Einfacher Name** kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. Der Wert *Einfacher Name* darf nicht leer und muss eindeutig sein. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsistent für alle Standorte und Benutzer zu verwenden.

## Beschreibung

Es wird empfohlen, den allgemeinen, wiedererkennbaren Namen des geografischen Standorts einzugeben, auf den der entsprechende Wählplan angewendet werden. Wenn der Name des Wählplans beispielsweise "London.Contoso.com" lautet, wird für die Beschreibung der Eintrag "London" empfohlen.

## Region für Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie eine Region angeben, um die Zugriffsnummern für Einwahlkonferenzen dem entsprechenden Wählplan zuzuordnen. Ausführliche Informationen hierzu finden Sie unter Dial-In Conferencing in Communications Server 2010 in der Planungsdokumentation.

## Präfix für externen Zugriff

Sie können ein aus bis zu vier Zeichen (\#, \* und 0-9) bestehendes Präfix für den externen Zugriff angeben, wenn die Benutzer ein oder mehrere zusätzliche Ziffern (z. B. 9) wählen müssen, um eine externe Leitung zu erhalten.


> [!NOTE]
> Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine zusätzliche Normalisierungsregel zur Unterstützung des Präfixes erstellen.



## Normalisierungsregeln

Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort. Ein und dieselbe numerische Zeichenfolge wird möglicherweise unterschiedlich interpretiert und übersetzt, je nachdem, von welchem Standort aus sie gewählt wird. Normalisierungsregeln sind für das Anrufrouting notwendig, da Benutzer Rufnummern in unterschiedlichen Formaten in ihre Kontaktlisten eingeben.

Die Normalisierung der von Benutzern eingegebenen Rufnummern stellt ein konsistentes Format bereit, das folgende Aufgaben vereinfacht:

  - Zuordnen einer gewählten Rufnummer zum SIP-URI des gewünschten Empfängers

  - Anwenden von Wählautorisierungsregeln auf den Anrufer

In Normalisierungsregeln müssen möglicherweise die folgenden numerischen Felder berücksichtigt werden:

  - Wählplan

  - Landesvorwahl

  - Ortsvorwahl

  - Länge der Durchwahlnummer

  - Standortpräfix

## Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. Sie erstellen Normalisierungsregeln in der Lync Server-Systemsteuerung, indem Sie die Ausdrücke entweder manuell eingeben, oder indem Sie die Anfangsziffern und die Länge der Wählzeichenfolgen eingeben und es der Lync Server-Systemsteuerung überlassen, den entsprechenden regulären Ausdruck zu generieren. Unabhängig davon, welche Methode Sie verwendet haben, können Sie anschließend eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.

Ausführliche Informationen zur Verwendung von regulären .NET Framework-Ausdrücken finden Sie in "Reguläre Ausdrücke von .NET Framework" unter [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).

## Beispiele für Normalisierungsregeln

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre .NET Framework-Ausdrücke formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer Normalisierungsregeln dar.

### Tabelle 1: Normalisierungsregeln mit regulären .NET Framework-Ausdrücken

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
<td><p>+1425555$1</p></td>
<td><p>0100 wird in +14255550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Übersetzt fünfstellige Durchwahlnummern</p></td>
<td><p>^5(\d{4})$</p></td>
<td><p>+1425555$1</p></td>
<td><p>50100 wird in +14255550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond</p></td>
<td><p>^(\d{7})$</p></td>
<td><p>+1425$1</p></td>
<td><p>5550100 wird in +14255550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Dallas</p></td>
<td><p>^(\d{7})$</p></td>
<td><p>+1972$1</p></td>
<td><p>5550100 wird in +19725550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Übersetzt zehnstellige Rufnummern in US-Rufnummern</p></td>
<td><p>^(\d{10})$</p></td>
<td><p>+1$1</p></td>
<td><p>2065550100 wird in +12065550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Übersetzt Rufnummern mit Vorwahlen für Ferngespräche in US-Rufnummern</p></td>
<td><p>^1(\d{10})$</p></td>
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
<td><p>0 wird in +14255550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Redmond-Vorwahl (222)</p></td>
<td><p>^6222(\d{4})$</p></td>
<td><p>+1425555$1</p></td>
<td><p>62220100 wird in +14255550100 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Übersetzt Rufnummern mit netzinterner Vorwahl (6) und New York-Vorwahl (333)</p></td>
<td><p>^6333(\d{4})$</p></td>
<td><p>+1202555$1</p></td>
<td><p>63330100 wird in +12025550100 übersetzt</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Dallas-Vorwahl (444)</p></td>
<td><p>^6444(\d{4})$</p></td>
<td><p>+1972555$1</p></td>
<td><p>64440100 wird in +19725550100 übersetzt</p></td>
</tr>
</tbody>
</table>


Die folgende Tabelle veranschaulicht beispielhafte Wähleinstellungen für Redmond, Washington (USA), die auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basieren.

### Tabelle 2: Wähleinstellungen für Redmond, basierend auf den in Tabelle 1 gezeigten Normalisierungsregeln

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



> [!NOTE]
> Die Namen der Normalisierungsregeln in der vorstehenden Tabelle enthalten keine Leerzeichen. Dies ist durchaus möglich. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er "5 digit extension" oder "5-digit Extension" lautet.


