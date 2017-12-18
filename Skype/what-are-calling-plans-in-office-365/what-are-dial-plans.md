---
title: "Was sind Wählpläne?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
description: "Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your company.  "
---

# Was sind Wählpläne?

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b.md#MT_Footer).  
  
Ein Wählplan ist ein Norminalisierungsregelsatz, der die von einem einzelnen Benutzer gewählten Telefonnummern zur Anrufautorisierung und Anrufweiterleitung in ein anderes Format (normalerweise E.164) übersetzt.
  
Besteht aus einem Wählplan mindestens Normalisierungsregeln, die definieren, wie die Telefonnummern in verschiedenen Formaten ausgedrückt in ein anderes Format übersetzt werden. Dieselbe Einwahlnummern Zeichenfolge interpretiert und anders in anderen Wählpläne übersetzt werden möglicherweise, damit je nachdem, welche Wählplan zu einem bestimmten Benutzer zugeordnet ist, der sich per Telefon Zahl übersetzt und weitergeleitet werden anders.
  
Finden Sie unter [Erstellen und Verwalten von Wählpläne](create-and-manage-dial-plans.md) erstellen und Verwalten von Mandanten Wählpläne.
  
## Mandantenwählplanbereich

Ein Wählplan Bereich bestimmt die hierarchische Ebene, der Wählplan angewendet werden kann. Die Bereiche unterscheiden sich als in einem Skype für Business Server 2015 Bereitstellung lokalen. Clients abrufen den entsprechenden Wählplan mittels Bereitstellung Einstellungen, die automatisch bereitgestellt werden, wenn Benutzer Skype für Business Online anmelden. Als Administrator können Sie verwalten und Einwahlnummern Plan Umfang Ebenen mithilfe des Remote PowerShell zuweisen.
  
In Skype für Business Online gibt es zwei Arten von Wählpläne - Dienst ausgelegte und Mandanten (also für Ihre Organisation) ausgelegte. Ein Wählplans ausgelegte Service ist für jedes Land/Region definiert, in dem die Office 365-Telefonsystem verfügbar ist. Jedem Benutzer wird automatisch den Dienst Land Wählplan zugewiesen, der den Office 365-Verwendungsstandort dem Benutzer zugewiesenen entspricht. Den Dienst Land Wählplan kann nicht geändert werden, aber Sie können Mandanten ausgelegte Wählpläne, die den Dienst Land Wählplan ergänzen erstellen. Wie Clients bereitgestellt werden, erhalten sie ein "effektiven Wählplan," also eine Kombination aus dem Dienst Land Wählplan und dem Wählplan ordnungsgemäß Suchbegriffs Mandanten. Daher ist es nicht erforderlich, alle Normalisierungsregeln in Wählpläne Mandanten definieren, wie sie in dem Dienst Land Wählplan bereits vorhanden sind möglicherweise.
  
Mandantenwählpläne können weiter in zwei Bereiche unterteilt werden: Mandantenbereich oder Benutzerbereich. Wenn ein Mandant einen Wählplan mit Bereichszuweisung eines Benutzers definiert und zuweist, erhält dieser Benutzer einen gültigen Wählplan des Wählplans eines landesspezifischen Diensts und den zugewiesenen Benutzerwählplan. Wenn ein Mandant einen Wählplan mit Bereichszuweisung eines Mandanten definiert, ohne einen Wählplan mit Bereichszuweisung eines Benutzers zuzuweisen, erhält dieser Benutzer einen gültigen Wählplan des Wählplans eines landesspezifischen Diensts und den Mandantenwählplan.
  
So sieht das Vererbungsmodell für Wahlpläne in Skype for Business Online aus:
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Mögliche gültige Wählpläne:
  
 **Dienst Land** Wenn kein Wählplan Mandanten ausgelegte definiert ist, und der bereitgestellte Benutzer keine Mandanten Benutzer ausgelegte Wählplan zugeordnet ist, erhält der Benutzer eine effektive Wählplan zugeordneten Dienst Land ihrer Office 365-Verwendungsstandort zugeordnet.
  
 **Globale - Mandanten Dienst Land** Wenn einem Mandanten Benutzer Wählplan definiert, aber keinem Benutzer zugewiesenen erhält der bereitgestellte Benutzer eine effektive Wählplan aus einem verbundenen Mandanten Wählplan und dem Dienst Land Wählplan zugeordnet sind die Office 365 Verwendung Standortinformationen besteht.
  
 **Mandanten Benutzer - Dienst Land** Wenn einem Mandanten Benutzer Wählplan definiert und ein Benutzer zugewiesen wird, erhält der bereitgestellte Benutzer eine effektive Wählplan aus dem verbundenen Mandanten Benutzer Wählplan und dem Dienst Land Wählplan zugeordnet sind die Office 365 Verwendung Standortinformationen besteht.
  
Finden Sie unter [Erstellen und Verwalten von Wählpläne](create-and-manage-dial-plans.md) in Ihrem Mandanten Wählpläne erstellen.
  
## Planen von Mandantenwählplänen

Führen Sie die folgenden Schritte aus, um benutzerdefinierte Wählpläne zu planen:
  
- **Schritt 1** Entscheiden Sie, ob ein benutzerdefiniertes einwählen Plan so erforderlich ist, den Benutzer einwählen Erfahrung zu verbessern. In der Regel, die Notwendigkeit der eine zur Unterstützung von nicht-e. 164 wählen, wie z. B. Erweiterungen wäre oder Abkürzung nationalen sich einwählen.
    
- **Schritt 2** Bestimmen Sie, ob Mandanten globaler oder Mandanten Benutzer ausgelegte Wählpläne erforderlich sind, oder beides. Benutzer ausgelegte Wählpläne, die erforderlich sind, wenn Benutzer mit unterschiedlichen lokalen sich einwählen Anforderungen haben.
    
- **Schritt 3**: Identifizieren Sie gültige Nummernmuster für jeden erforderlichen Wählplan. Es sind nur die Nummernmuster erforderlich, die nicht in den Wählplänen auf der Ebene von landesspezifischen Diensten definiert sind.
    
- **Schritt 4**: Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen. Die Übernahme eines Standardbenennungsschemas stellt die Konsistenz innerhalb einer Organisation sicher und vereinfacht Wartungsaufgaben und Updates.
    
Das [schnelle](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) weist zusätzliche Ressourcen und Wählpläne für Partner zur Verfügung, die mit der Durchführung der Mandanten helfen können.
  
## Erstellen Ihres neuen Mandantenwählplans

Wenn Sie einen neuen Wählplan erstellen, müssen Sie die erforderlichen Informationen angeben.
  
### Name und einfacher Name

Für Benutzer Wählpläne sollten Sie angeben, dass ein beschreibender Namen, der an die Benutzer den Wählplan identifiziert zugewiesen wird. Der Wählplan einfachen Namen ist bereits ausgefüllt, durch eine Zeichenfolge, die den Namen der DFÜ-Plan abgeleitet wird. Das einfache Namensfeld ist bearbeitet werden kann, wodurch ermöglicht Ihnen, erstellen eine aussagekräftige Benennungskonvention für Ihre Wählpläne. Der einfachen Wert darf nicht leer und muss eindeutig sein. Bewährte Methode ist eine Benennungskonvention für die gesamte Organisation zu entwickeln und verwenden Sie diese Messe konsistent für alle Websites und Benutzern.
  
### Beschreibung

Wir empfehlen Ihnen, einen allgemeinen, schnell erkennbaren Namen des geografischen Standorts oder der Benutzergruppe zu verwenden, auf den der jeweilige Wählplan angewendet wird.
  
### Präfix für externen Zugriff

> [!CAUTION]
> Der Präfix für externen Zugriff wird derzeit nicht unterstützt. 
  
Sie können ein Präfix für externen Zugriff von bis zu vier Zeichen (#, * und 0-9) angeben, wenn Benutzer für eine externe Verbindung mindestens eine zusätzliche führende Ziffer (zum Beispiel 9) wählen müssen.
  
> [!NOTE]
> Wenn Sie ein Präfix für externen Zugriff angeben, müssen Sie keine zusätzliche Normalisierungsregel erstellen, um das Präfix aufzunehmen. 
  
Finden Sie unter [Erstellen und Verwalten von Wählpläne](create-and-manage-dial-plans.md) in Ihrem Mandanten Wählpläne erstellen.
  
## Normalisierungsregeln

Normalisierungsregeln definieren, wie die in verschiedenen Formaten ausgedrückten Telefonnummern übersetzt werden. Je nach dem lokalen Standort, von dem aus eine Nummernzeichenfolge gewählt wird, kann diese unterschiedlich interpretiert und übersetzt werden. Normalisierungsregeln sind unter Umständen notwendig, wenn Benutzer interne oder externe Kurzwahlnummern wählen müssen.
  
Eine oder mehrere Normalisierungsregeln müssen mit dem Wählplan zugewiesen werden. Damit die Reihenfolge, in einem Mandanten Wählplan angezeigt, wichtig ist, werden von oben nach unten, Normalisierungsregeln verglichen. Beispielsweise weist einen Mandanten Wählplan 10 Normalisierungsregeln, die gewählte Zahl übereinstimmende Logik versucht, beginnend mit der ersten Normalisierung Regel, wenn es keine Übereinstimmung klicken Sie dann das zweite, usw. Wird eine Übereinstimmung gefunden wird, wird diese Regel verwendet, und es ist keine leistungsgesteuert zu einem beliebigen anderen Regeln entsprechen, die definiert werden. In einem bestimmten Mandanten Wählplan kann maximal 25 Normalisierungsregeln sein.
  
### Festlegen der erforderlichen Normalisierungsregeln

Da jeder Mandantenwählplan effektiv mit einem Wählplan eines landesspezifischen Diensts eines vorhandenen Benutzers zusammengeführt wird, müssen wahrscheinlich die Normalisierungsregeln des Wählplans eines landesspezifischen Diensts ausgewertet werden, um festzulegen, welche Normalisierungsregeln des Mandantenwählplans erforderlich sind. Zu diesem Zweck kann das **Get-CsEffectiveTenantDialPlan** -Cmdlet verwendet werden. Das Cmdlet verwendet eine Benutzeridentität als Eingabeparameter und gibt alle auf den Benutzer anwendbaren Normalisierungsregeln zurück.
  
### Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre Ausdrücke von .NET Framework, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. Sie können Normalisierungsregeln erstellen, indem Sie den regulären Ausdruck für den Abgleich angeben sowie die Übersetzung, die für gefundene Übereinstimmungen durchgeführt werden soll. Abschließend können Sie eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.
  
Weitere Informationen zur Verwendung von regulärer Ausdrücken in .NET Framework finden Sie unter [Reguläre Ausdrücke in .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
Finden Sie unter [Erstellen und Verwalten von Wählpläne](create-and-manage-dial-plans.md) erstellen und Verwalten von Normalisierung Regeln für Ihren Mandanten Wählpläne.
  
### Beispiele für Normalisierungsregeln

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre Ausdrücke von .NET Framework formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer eigenen Normalisierungsregeln dar.
  
 **Verwenden von regulären Ausdrücken in .NET Framework Normalisierungsregeln**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Regelname** <br/> |**Beschreibung** <br/> |**Nummernmuster** <br/> |**Übersetzung** <br/> |**Beispiel** <br/> |
|4digitExtension  <br/> |Übersetzt vierstellige Durchwahlnummern.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt.  <br/> |
|5digitExtension  <br/> |Übersetzt fünfstellige Durchwahlnummern.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt.  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt.  <br/> |
|RedmondOperator  <br/> |Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt.  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt.  <br/> |
|5digitRange  <br/> |Übersetzt fünfstellige Durchwahlnummern beginnend mit dem Ziffernbereich von 3 bis einschließlich 7.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 wird in +14255554567 übersetzt.  <br/> |
|PrefixAdded  <br/> |Fügt ein Länderpräfix vor einer neunstelligen Nummer mit Einschränkungen für die erste und dritte Ziffer hinzu.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 wird in 14255554567 übersetzt.  <br/> |
|NoTranslation  <br/> |Gleicht 5 Ziffern ab, ohne eine Übersetzung durchzuführen.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 wird in 34567 übersetzt.  <br/> |
   
 **Wählplan für Redmond, basierend auf den oben gezeigten Normalisierungsregeln**
  
Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert.
  
||
|:-----|
|**Wählplan für Redmond** <br/> |
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|RedmondSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> Die Namen der Normalisierungsregeln in der vorstehenden Tabelle enthalten keine Leerzeichen, aber dies ist nicht obligatorisch. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er „5 digit extension" oder „5-digit Extension" lautet. 
  
## Verwandte Themen

[Erstellen und Verwalten von Wählpläne](create-and-manage-dial-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

