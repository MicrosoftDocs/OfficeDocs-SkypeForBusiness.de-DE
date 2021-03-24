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
description: 'Erfahren Sie, welche Arten von Wählplänen (PSTN-Anrufpläne) in Teams verfügbar sind und wie Sie einen für Ihre Organisation auswählen.  '
ms.openlocfilehash: 86ec311a7abec9b9268555884db3ff8de7ee256b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100981"
---
# <a name="what-are-dial-plans"></a>Was sind Wählpläne?

Ein Wählplan ist ein Norminalisierungsregelsatz, der die von einem einzelnen Benutzer gewählten Telefonnummern zur Anrufautorisierung und Anrufweiterleitung in ein anderes Format (normalerweise E.164) übersetzt.

Ein Wählplan besteht aus einer oder mehreren Normalisierungsregeln, die definieren, wie In verschiedenen Formaten ausgedrückte Telefonnummern in ein alternatives Format übersetzt werden. Die gleiche Wählzeichenfolge kann in verschiedenen Wählplänen unterschiedlich interpretiert und übersetzt werden. Je nachdem, welcher Wählplan einem bestimmten Benutzer zugewiesen ist, kann dieselbe Wählnummer anders übersetzt und geroutet werden. Es können maximal 1.000 Wählpläne für Mandanten verwendet werden.

Weitere Informationen finden Sie unter Erstellen [und Verwalten von Wählplänen](create-and-manage-dial-plans.md) zum Erstellen und Verwalten von Mandantenwählplänen.

## <a name="tenant-dial-plan-scope"></a>Mandantenwählplanbereich

Der Bereich eines Wählplans bestimmt die hierarchische Ebene, auf der der Wählplan angewendet werden kann. Clients erhalten den entsprechenden Wählplan über Bereitstellungseinstellungen, die automatisch bereitgestellt werden, wenn sich Benutzer bei Teams anmelden. Als Administrator können Sie Wählplanbereichsebenen verwalten und zuweisen, indem Sie das Microsoft Teams Admin Center oder Remote PowerShell verwenden.

In Teams gibt es zwei Arten von Wählplänen: Dienstbereich und Mandantenbereich (für Ihre Organisation). Für jedes Land oder jede Region, in dem Telefonsystem verfügbar ist, wird ein Wählplan für den Dienstbereich definiert. Jedem Benutzer wird automatisch der Wählplan für das Serviceland zugewiesen, der dem dem Benutzer zugewiesenen Nutzungsstandort entspricht. Sie können den Wählplan für Das Land des Diensts nicht ändern, aber Sie können Wählpläne mit Mandantenbereich erstellen, die den Wählplan für Serviceland erweitern. Wenn Kunden bereitgestellt werden, erhalten sie einen "effektiven Wählplan", bei dem es sich um eine Kombination aus dem Wählplan für das Serviceland und dem entsprechend begrenzten Mandantenwählplan handelt. Daher müssen nicht alle Normalisierungsregeln in Mandantenwählplänen definiert werden, da sie möglicherweise bereits im Wählplan für Serviceland vorhanden sind.

Mandantenwählpläne können weiter in zwei Bereiche aufschlüsselt werden: Mandantenbereich oder Benutzerbereich. Wenn ein Mandant einen Wählplan mit Benutzerbereich definiert und zugewiesen hat, wird diesem Benutzer ein effektiver Wählplan des Wählplans für das Land des Diensts und des zugewiesenen Benutzerwählplans bereitgestellt. Wenn ein Mandant einen Wählplan mit Mandantenbereich definiert, aber keinen Wählplan mit Benutzerbereich zuzuordnen hat, wird dieser Benutzer mit einem effektiven Wählplan des Wählplans für das Serviceland des Benutzers und des Mandantenwählplans bereitgestellt.

Im Folgenden finden Sie das Vererbungsmodell von Wählplänen in Teams.

![So werden Wählpläne in Teams geerbt](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Mögliche gültige Wählpläne:

 **Dienstland** Wenn kein Wählplan mit Mandantenbereich definiert ist und dem bereitgestellten Benutzer kein Wählplan mit Mandantenbereich zugewiesen ist, erhält der Benutzer einen effektiven Wählplan, der dem Dienstland zugeordnet ist, das seinem Nutzungsstandort zugeordnet ist.

 **Mandanten global – Dienstland** Wenn ein Mandantenbenutzerwählplan definiert, aber nicht einem Benutzer zugewiesen ist, erhält der bereitgestellte Benutzer einen effektiven Wählplan, der aus einem zusammengeführten Mandantenwählplan und dem Wählplan für das Land des Diensts besteht, der seinem Nutzungsstandort zugeordnet ist.

 **Mandantenbenutzer – Dienstland** Wenn ein Wählplan eines Mandantenbenutzers definiert und einem Benutzer zugewiesen ist, erhält der bereitgestellte Benutzer einen effektiven Wählplan, der aus dem zusammengeführten Benutzerwählplan des Mandanten und dem Wählplan für das Land des Diensts besteht, der seinem Nutzungsstandort zugeordnet ist.

Weitere Informationen finden Sie unter Erstellen und Verwalten von [Wählplänen](create-and-manage-dial-plans.md) zum Erstellen Ihrer Mandantenwählpläne.

> [!NOTE]
> In dem Szenario, in dem keine Normalisierungsregeln für einen Wählplan für eine gewählte Nummer gelten, wird die gewählte Zeichenfolge weiterhin auf "+CC" normalisiert, wobei CC die Landesvorwahl des Verwendungsorts des Wählbenutzers ist. Dies gilt für Anrufpläne, Direct Routing- und PSTN-Konferenz-Einwahlszenarien.

## <a name="planning-for-tenant-dial-plans"></a>Planen von Mandantenwählplänen

Führen Sie die folgenden Schritte aus, um benutzerdefinierte Wählpläne zu planen:

- **Schritt 1** Entscheiden Sie, ob ein benutzerdefinierter Wählplan erforderlich ist, um die Benutzerwählerfahrung zu verbessern. In der Regel muss eine nicht E.164-Wählhilfe unterstützt werden, z. B. Erweiterungen oder abgekürzte nationale Wählhilfen.

- **Schritt 2** Bestimmen Sie, ob globale Wählpläne für Mandanten oder Mandanten mit Benutzerbereich oder beides erforderlich sind. Wählpläne mit Bereichszuweisung eines Benutzers sind erforderlich, wenn Benutzer über unterschiedliche Anforderungen an lokale Wählvorgänge verfügen.

- **Schritt 3**: Identifizieren Sie gültige Nummernmuster für jeden erforderlichen Wählplan. Es sind nur die Nummernmuster erforderlich, die nicht in den Wählplänen auf der Ebene von landesspezifischen Diensten definiert sind.

- **Schritt 4**: Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen. Die Übernahme eines Standardbenennungsschemas stellt die Konsistenz innerhalb einer Organisation sicher und vereinfacht Wartungsaufgaben und Updates.


## <a name="creating-your-new-dial-plan"></a>Erstellen ihres neuen Wählplans

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

Weitere Informationen finden Sie unter Erstellen und Verwalten von [Wählplänen](create-and-manage-dial-plans.md) zum Erstellen Ihrer Mandantenwählpläne.

## <a name="normalization-rules"></a>Normalisierungsregeln
<a name="bknormalizationrule"> </a>

Normalisierungsregeln definieren, wie die in verschiedenen Formaten ausgedrückten Telefonnummern übersetzt werden. Je nach dem lokalen Standort, von dem aus eine Nummernzeichenfolge gewählt wird, kann diese unterschiedlich interpretiert und übersetzt werden. Normalisierungsregeln sind unter Umständen notwendig, wenn Benutzer interne oder externe Kurzwahlnummern wählen müssen.

Dem Wählplan muss mindestens eine Normalisierungsregeln zugewiesen werden. Normalisierungsregeln werden von oben nach unten übereinstimmen, daher ist die Reihenfolge, in der sie in einem Mandantenwählplan angezeigt werden, wichtig. Wenn z. B. ein Mandantenwählplan 10 Normalisierungsregeln enthält, wird die Logik für den Abgleich der gewählten Nummer ab der ersten Normalisierungsregel ausprobiert, wenn es keine Übereinstimmung gibt, dann die zweite usw. Wenn eine Übereinstimmung hergestellt wird, wird diese Regel verwendet, und es gibt keinen Versuch, andere definierte Regeln zu entsprechen. In einem bestimmten Mandantenwählplan können maximal 50 Normalisierungsregeln gelten.

### <a name="determining-the-required-normalization-rules"></a>Festlegen der erforderlichen Normalisierungsregeln

Da ein beliebiger Mandantenwählplan effektiv mit dem Wählplan eines bestimmten Benutzers zusammengeführt wird, ist es wahrscheinlich, dass die Normalisierungsregeln des Wählplans für das Land des Diensts ausgewertet werden müssen, um festzustellen, welche Normalisierungsregeln für den Mandantenwählplan erforderlich sind. Zu diesem Zweck kann das **Get-CsEffectiveTenantDialPlan** -Cmdlet verwendet werden. Das Cmdlet verwendet eine Benutzeridentität als Eingabeparameter und gibt alle auf den Benutzer anwendbaren Normalisierungsregeln zurück.

### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln
<a name="createrule"> </a>

Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um numerische Übereinstimmungsmuster anzugeben, die vom Server zum Übersetzen von Wählzeichenfolgen in das E.164-Format verwendet werden. Sie können Normalisierungsregeln erstellen, indem Sie den regulären Ausdruck für den Abgleich angeben sowie die Übersetzung, die für gefundene Übereinstimmungen durchgeführt werden soll. Abschließend können Sie eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.

Details zur Verwendung .NET Framework regulären Ausdrücken finden Sie [unter .NET Framework Reguläre Ausdrücke](/dotnet/standard/base-types/regular-expressions).

Weitere Informationen finden Sie unter Erstellen und Verwalten von [Wählplänen](create-and-manage-dial-plans.md) zum Erstellen und Verwalten von Normalisierungsregeln für Ihre Mandantenwählpläne.

> [!NOTE]
> Normalisierungsregeln mit dem ersten Token als optional werden derzeit auf 3pip-Geräten (z. B. Polycom VVX 601-Modell) nicht unterstützt. Wenn Sie Normalisierungsregeln mit Optionalität auf 3pip-Geräten anwenden möchten, sollten Sie zwei Normalisierungsregeln anstelle einer erstellen. Beispiel: Die Regel ^0? (999)$ sollte durch die folgenden beiden Regeln ersetzt werden: (999)$ (Übersetzung:$1) und ^0(999)$ (Übersetzung:$1).


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
> Die Namen der Normalisierungsregeln, die in der vorherigen Tabelle angezeigt werden, enthalten keine Leerzeichen, aber dies ist eine Frage der Wahl. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er „5 digit extension" oder „5-digit Extension" lautet.

## <a name="related-topics"></a>Verwandte Themen

[Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)