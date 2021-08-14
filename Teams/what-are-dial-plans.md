---
title: Was sind Wählpläne?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Hier erfahren Sie, welche Wählpläne (PSTN-Anrufpläne) für Ihre Teams verfügbar sind und wie Sie einen Wählplan für Ihre Organisation auswählen.  '
ms.openlocfilehash: cfe90a65fb7e1bbc0aae30cd5d0a0dc052f86cb4
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234410"
---
# <a name="what-are-dial-plans"></a>Was sind Wählpläne?

Bei einem Wählplan handelt es sich um einen benannten Satz von Normalisierungsregeln, mit dem die von einzelnen Benutzern gewählten Telefonnummern zum Zweck der Anrufautorisierung und Sprachrouting in ein alternatives Format (normalerweise E.164) übersetzt werden.

Ein Wählplan besteht aus einer oder mehreren Normalisierungsregeln, die definieren, wie in verschiedenen Formaten ausgedrückte Telefonnummern in ein alternatives Format übersetzt werden. Da dieselbe Wählzeichenfolge in unterschiedlichen Wählplänen unterschiedlich interpretiert und übersetzt werden kann, wird je nach dem einem Benutzer zugewiesenen Wählplan möglicherweise dieselbe gewählte Nummer anders übersetzt und geroutet. Es kann maximal 1.000 Mandantenwählpläne gibt.

Siehe [Erstellen und Verwalten von Wählplänen zum](create-and-manage-dial-plans.md) Erstellen und Verwalten von Mandantenwählplänen.

## <a name="tenant-dial-plan-scope"></a>Mandantenwählplanbereich

Der Bereich eines Wählplans bestimmt die Hierarchieebene, auf der der Wählplan angewendet werden kann. Clients erhalten den entsprechenden Wählplan über Bereitstellungseinstellungen, die automatisch bereitgestellt werden, wenn sich Benutzer bei Ihrem Teams. Als Administrator können Sie Wählplanbereichsebenen verwalten und zuweisen, indem Sie Microsoft Teams Admin Center oder Remote PowerShell verwenden.

In Teams gibt es zwei Arten von Wählplänen: Wählpläne mit Dienstbereich und Mandantenbereich (für Ihre Organisation). Ein Wählplan mit Leistungsumfang wird für jedes Land oder jede Region definiert, in Telefonsystem verfügbar ist. Jedem Benutzer wird automatisch der Wählplan eines Landes zugeordnet, der dem dem Benutzer zugewiesenen Nutzungsstandort entspricht. Sie können den Wählplan für einen Landesdienst nicht ändern, aber Sie können Wählpläne mit Mandantenbereich erstellen, wodurch der Wählplan für das Land des Landes erweitert wird. Bei der Bereitstellung erhalten die Kunden einen "effektiven Wählplan", bei dem es sich um eine Kombination aus dem Wählplan für einen Landesdienst und dem Entsprechend begrenzten Mandantenwählplan handelt. Daher ist es nicht erforderlich, alle Normalisierungsregeln in Mandantenwählplänen zu definieren, da sie möglicherweise bereits im Wählplan für das Land des Diensts vorhanden sind.

Mandantenwählpläne können weiter in zwei Bereiche aufgeschlüsselt werden: Mandantenbereich oder Benutzerbereich. Wenn ein Mandant einen Wählplan mit Benutzerbereich definiert und zu weist, wird diesem Benutzer ein effektiver Wählplan des Wählplans eines Landesdiensts des Benutzers und des zugewiesenen Benutzerwählplans bereitgestellt. Wenn ein Mandant einen Wählplan mit Mandantenbereich definiert, aber keinen Wählplan mit Benutzerbereich zu weist, wird diesem Benutzer ein effektiver Wählplan des Wählplans eines Landesdiensts des Benutzers und des Mandantenwählplans bereitgestellt.

Im Folgenden wird das Vererbungsmodell von Wählplänen in Teams.

![Vererbung von Wählplänen in Teams](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Mögliche gültige Wählpläne:

 **Service Country (Land des Diensts)** Wenn kein Wählplan mit Bereichsumfang des Mandanten definiert ist und dem bereitgestellten Benutzer kein Wählplan mit Bereichsbereich eines Mandantenbenutzers zugewiesen ist, erhält der Benutzer einen effektiven Wählplan, der dem mit dem Verwendungsstandort verknüpften Dienstland zugeordnet ist.

 **Tenant Global – Service Country** Wenn ein Mandanten-Benutzerwählplan definiert, aber keinem Benutzer zugewiesen ist, erhält der bereitgestellte Benutzer einen effektiven Wählplan, der aus einem zusammengeführten Mandantenwählplan und dem mit dem Verwendungsstandort verknüpften Wählplan eines Landesdiensts besteht.

 **Mandantenbenutzer – Land des Diensts** Wenn ein Mandanten-Benutzerwählplan definiert und einem Benutzer zugewiesen ist, erhält der bereitgestellte Benutzer einen effektiven Wählplan, der aus dem zusammengeführten Mandanten-Benutzerwählplan und dem mit dem Verwendungsstandort verknüpften Wählplan eines Landesdiensts besteht.

Informationen [zum Erstellen Ihrer Mandantenwählpläne finden](create-and-manage-dial-plans.md) Sie unter Erstellen und Verwalten von Wählplänen.

> [!NOTE]
> In dem Szenario, in dem keine Wählplannormalisierungsregeln für eine gewählte Nummer gelten, wird die gewählte Zeichenfolge weiterhin normalisiert und "+CC" vorausgeöffnet, wobei CC die Landesvorwahl des Nutzungsstandorts des Wählbenutzers ist. Dies gilt für Anrufpläne, direktes Routing und DFÜ-Szenarien für PSTN-Konferenz. Wenn eine Normalisierungsregel für einen Mandantenwählplan zu einer Nummer führt, die nicht mit "+" beginnt, versucht der Anrufdienst außerdem, die vom Teams-Client empfangene Nummer basierend auf dem Mandantenwählplan zu normalisieren und, wenn dies nicht übereinstimmen, auf dem Wählplan für die Region zu normalisieren. Um eine doppelte Normalisierung zu vermeiden, empfiehlt es sich, dass Kunden des Direct-Routings Zahlen normalisieren, um ein + zu erhalten, und dann das Pluszeichen (+) mithilfe von Regeln für die Trunkübersetzung entfernen. 

## <a name="planning-for-tenant-dial-plans"></a>Planen von Mandantenwählplänen

Führen Sie die folgenden Schritte aus, um benutzerdefinierte Wählpläne zu planen:

- **Schritt 1** Entscheiden Sie, ob ein benutzerdefinierter Wählplan erforderlich ist, um die Wählerfahrung der Benutzer zu verbessern. In der Regel ist es nötig, Nicht-E.164-Wählhilfen zu unterstützen, z. B. Erweiterungen oder kurzkürzte Nationale Wählwahlen.

- **Schritt 2** Bestimmen Sie, ob globale oder Mandantenbenutzer-Wählpläne mit Bereichsbereich des Mandanten oder beides erforderlich sind. Wählpläne mit Bereichszuweisung eines Benutzers sind erforderlich, wenn Benutzer über unterschiedliche Anforderungen an lokale Wählvorgänge verfügen.

- **Schritt 3**: Identifizieren Sie gültige Nummernmuster für jeden erforderlichen Wählplan. Es sind nur die Nummernmuster erforderlich, die nicht in den Wählplänen auf der Ebene von landesspezifischen Diensten definiert sind.

- **Schritt 4**: Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen. Die Übernahme eines Standardbenennungsschemas stellt die Konsistenz innerhalb einer Organisation sicher und vereinfacht Wartungsaufgaben und Updates.


## <a name="creating-your-new-dial-plan"></a>Erstellen Ihres neuen Wählplans

Wenn Sie einen neuen Wählplan erstellen, müssen Sie die erforderlichen Informationen angeben.

### <a name="name-and-simple-name"></a>Name und einfacher Name

Für Benutzerwählpläne sollten Sie einen beschreibenden Namen angeben, der die Benutzer identifiziert, denen der Wählplan zugewiesen wird. Der Wählplan Einfacher Name ist bereits mit einer vom Namen des Wählplans abgeleiteten Zeichenfolge aufgefüllt. Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. Der Wert Einfacher Name darf nicht leer und muss eindeutig sein. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.

### <a name="description"></a>Beschreibung

Wir empfehlen Ihnen, einen allgemeinen, schnell erkennbaren Namen des geografischen Standorts oder der Benutzergruppe zu verwenden, auf den der jeweilige Wählplan angewendet wird.

### <a name="external-access-prefix"></a>Präfix für externen Zugriff
<a name="bkexternalprefix"> </a>

Sie können ein Präfix für externen Zugriff von bis zu vier Zeichen (#, * und 0-9) angeben, wenn Benutzer für eine externe Verbindung mindestens eine zusätzliche führende Ziffer (zum Beispiel 9) wählen müssen.

> [!NOTE]
> Wenn Sie ein Präfix für externen Zugriff angeben, müssen Sie keine zusätzliche Normalisierungsregel erstellen, um das Präfix aufzunehmen.

Informationen [zum Erstellen Ihrer Mandantenwählpläne finden](create-and-manage-dial-plans.md) Sie unter Erstellen und Verwalten von Wählplänen.

## <a name="normalization-rules"></a>Normalisierungsregeln
<a name="bknormalizationrule"> </a>

Normalisierungsregeln definieren, wie die in verschiedenen Formaten ausgedrückten Telefonnummern übersetzt werden. Je nach dem lokalen Standort, von dem aus eine Nummernzeichenfolge gewählt wird, kann diese unterschiedlich interpretiert und übersetzt werden. Normalisierungsregeln sind unter Umständen notwendig, wenn Benutzer interne oder externe Kurzwahlnummern wählen müssen.

Dem Wählplan müssen mindestens eine Normalisierungsregeln zugewiesen werden. Normalisierungsregeln werden von oben nach unten abgestimmt, daher ist die Reihenfolge, in der sie in einem Mandantenwählplan angezeigt werden, wichtig. Wenn ein Mandantenwählplan beispielsweise 10 Normalisierungsregeln enthält, wird die Abgleichlogik für gewählte Nummern ab der ersten Normalisierungsregel ausprobiert, wenn keine Übereinstimmung vor liegt, dann die zweite usw. Wenn eine Übereinstimmung vorgenommen wird, wird diese Regel verwendet, und es ist nicht mehr aufwand, andere definierte Regeln zu beachten. In einem bestimmten Mandantenwählplan können maximal 50 Normalisierungsregeln gelten.

### <a name="determining-the-required-normalization-rules"></a>Festlegen der erforderlichen Normalisierungsregeln

Da jeder Mandantenwählplan effektiv mit dem Wählplan eines landesüblichen Diensts eines bestimmten Benutzers zusammengeführt wird, müssen wahrscheinlich die Normalisierungsregeln des Wählplans eines Landes ausgewertet werden, um zu bestimmen, welche Normalisierungsregeln für den Mandantenwählplan erforderlich sind. Zu diesem Zweck kann das **Get-CsEffectiveTenantDialPlan** -Cmdlet verwendet werden. Das Cmdlet verwendet eine Benutzeridentität als Eingabeparameter und gibt alle auf den Benutzer anwendbaren Normalisierungsregeln zurück.

### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln
<a name="createrule"> </a>

Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um numerische Vergleichsmuster anzugeben, die vom Server zum Übersetzen von Wählzeichenfolgen in das E.164-Format verwendet werden. Sie können Normalisierungsregeln erstellen, indem Sie den regulären Ausdruck für den Abgleich angeben sowie die Übersetzung, die für gefundene Übereinstimmungen durchgeführt werden soll. Abschließend können Sie eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.

Details zur Verwendung von regulären .NET Framework finden Sie unter verwenden [.NET Framework reguläre Ausdrücke.](/dotnet/standard/base-types/regular-expressions)

Informationen [zum Erstellen und Verwalten von](create-and-manage-dial-plans.md) Normalisierungsregeln für Ihre Mandantenwählpläne finden Sie unter Erstellen und Verwalten von Wählplänen.

> [!NOTE]
> Normalisierungsregeln mit dem ersten Token als optional werden derzeit auf 3pip-Geräten (z. B. Polycom VVX 601-Modell) nicht unterstützt. Wenn Sie Normalisierungsregeln mit optionaler Optionalität auf 3pip-Geräten anwenden möchten, sollten Sie zwei Normalisierungsregeln anstelle von einer erstellen. Beispiel: Die Regel ^0? (999)$ sollte durch die folgenden beiden Regeln ersetzt werden: (999)$ (Übersetzung:$1) und ^0(999)$ (Übersetzung:$1).


### <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre Ausdrücke von .NET Framework formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer eigenen Normalisierungsregeln dar.

<a name="regularexpression"> </a> 
 **Normalisierungsregeln mit .NET Framework regulären Ausdrücken**

| Regelname<br/> | Beschreibung<br/> | Nummernmuster<br/> | Übersetzung<br/> | Beispiel<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Übersetzt vierstellige Durchwahlnummern.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt.  <br/> |
|5digitExtension  <br/> |Übersetzt fünfstellige Durchwahlnummern.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt.  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt.  <br/>|
|RedmondOperator  <br/> |Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt.  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt.  <br/> |
|5digitRange  <br/> |Übersetzt fünfstellige Durchwahlnummern beginnend mit dem Ziffernbereich von 3 bis einschließlich 7.  <br/> |^([3-7]\\d{4})$  <br/> |+142555$1 <br/> |54567 wird in +14255554567 übersetzt.  <br/> |
|PrefixAdded  <br/> |Fügt ein Länderpräfix vor einer neunstelligen Nummer mit Einschränkungen für die erste und dritte Ziffer hinzu.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 wird in 14255554567 übersetzt.  <br/> |
|NoTranslation  <br/> |Gleicht 5 Ziffern ab, ohne eine Übersetzung durchzuführen.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 wird in 34567 übersetzt.  <br/> |

 **Wählplan für Redmond, basierend auf den oben gezeigten Normalisierungsregeln**

 Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert.

| Wählplan für Redmond<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> Die Namen der Normalisierungsregeln in der obigen Tabelle enthalten keine Leerzeichen, aber dies ist eine Frage der Wahl. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er „5 digit extension" oder „5-digit Extension" lautet.

## <a name="related-topics"></a>Verwandte Themen

[Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
