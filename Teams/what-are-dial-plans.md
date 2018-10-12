---
title: Was sind Wählpläne?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Hier erfahren Sie, welche Art von Dial Plans (Aufrufen von PSTN-Wählpläne) aufrufen mit Office 365 verfügbar sind und wie Sie eine für Ihre Organisation wählen.  '
ms.openlocfilehash: 28e0b3d282cba17061f0573b5bd9efe7e27de786
ms.sourcegitcommit: 8a4ed16adc60497510a528784e139075fbae9e55
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "25502358"
---
# <a name="what-are-dial-plans"></a>Was sind Wählpläne?

Ein Wählplan ist ein Norminalisierungsregelsatz, der die von einem einzelnen Benutzer gewählten Telefonnummern zur Anrufautorisierung und Anrufweiterleitung in ein anderes Format (normalerweise E.164) übersetzt.

Ein Wählplan umfasst eine oder mehrere Normalisierungsregeln, die definieren, wie Rufnummern in unterschiedlichen Formaten in ein anderes Format übersetzt werden. Die gleichen Dial-Zeichenfolge kann sein und unterschiedlich übersetzt in verschiedene Wählpläne, damit je nach einem bestimmten Benutzer der Wählplan zugewiesen ist, dieselbe gewählte Nummer übersetzt und weitergeleitet werden anders.

Finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) zum Erstellen und Verwalten von Mandanten-Wählpläne.

## <a name="tenant-dial-plan-scope"></a>Mandantenwählplanbereich

Ein Wählplan Bereich bestimmt die Hierarchieebene, an der die Wähleinstellungen angewendet werden kann. Die Bereiche werden anders als in einer Skype für Business Server 2015: Bereitstellung lokal. Clients erhalten die entsprechenden Wähleinstellungen über die Bereitstellung von Einstellungen, die automatisch bereitgestellt werden, wenn Benutzer Skype für Business Online anmelden. Sie können als Administrator verwalten und Bereichsebenen mithilfe von Remote-PowerShell zuweisen.

In Skype für Business Online gibt es zwei Arten von Wählplänen - bezogenen Service und Mandant (bei dem es sich um für Ihre Organisation handelt) beschränkt. Ein Wählplan bezogenen Service ist für jedes Land/Region definiert, in dem das Telefonsystem für Office 365 verfügbar ist. Jeder Benutzer wird automatisch den Dienst Land Wählplan zugewiesen, der die Office 365 Usage Standort zugewiesen, die dem Benutzer entspricht. Den Dienst Land Wählplan kann nicht geändert werden, aber Sie können Mandanten bezogenen-Wählpläne, die den Dienst Land Wählplan ergänzen erstellen. Wie Clients bereitgestellt werden, ein "effektiven Wählplan," ist eine Kombination aus dem Dienst Land Wählplan und die Wähleinstellungen entsprechend bereichsbezogenen Mandanten abgerufen. Aus diesem Grund ist es nicht erforderlich, alle Normalisierungsregeln in Wählpläne Mandanten definieren, wie sie in den Dienst Land Wähleinstellungen noch vorhanden sind möglicherweise.

Mandantenwählpläne können weiter in zwei Bereiche unterteilt werden: Mandantenbereich oder Benutzerbereich. Wenn ein Mandant einen Wählplan mit Bereichszuweisung eines Benutzers definiert und zuweist, erhält dieser Benutzer einen gültigen Wählplan des Wählplans eines landesspezifischen Diensts und den zugewiesenen Benutzerwählplan. Wenn ein Mandant einen Wählplan mit Bereichszuweisung eines Mandanten definiert, ohne einen Wählplan mit Bereichszuweisung eines Benutzers zuzuweisen, erhält dieser Benutzer einen gültigen Wählplan des Wählplans eines landesspezifischen Diensts und den Mandantenwählplan.

So sieht das Vererbungsmodell für Wahlpläne in Skype for Business Online aus:

![How dial plans are inherited in Skype for Business Online.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Mögliche gültige Wählpläne:

 **Dienst Land** Wenn kein Wählplan Mandanten bezogenen definiert ist und keine Mandanten bezogenen benutzerwähleinstellungen der bereitgestellten Benutzer zugewiesen ist, erhält der Benutzer eine effektive Wählplan zugeordnet sind, in das Service Land ihre Office 365 Usage Standort zugeordnet.

 **Globale - Mandanten Service Land** Wenn ein Mandant benutzerwähleinstellungen wird definiert, aber nicht zu einem Benutzer zugewiesen, erhält der bereitgestellte Benutzer eine effektive Wählplan bestehend aus einem Wählplan zusammengeführten Mandanten und den Dienst Land Wählplan ihre Office 365 Usage Standort zugeordnet.

 **Mandanten-Benutzer - Dienst Land** Wenn ein Mandant benutzerwähleinstellungen definiert und einem Benutzer zugewiesen ist, erhält der bereitgestellte Benutzer eine effektive Wählplan bestehend aus der zusammengeführten Mandanten benutzerwählplan und den Dienst Land Wählplan ihre Office 365 Usage Standort zugeordnet.

Finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) Ihres Mandanten Wählpläne erstellen.

## <a name="planning-for-tenant-dial-plans"></a>Planen von Mandantenwählplänen

Führen Sie die folgenden Schritte aus, um benutzerdefinierte Wählpläne zu planen:

- **Schritt 1** Entscheiden Sie, ob eine benutzerdefinierte einwählen Plan so benötigt werden, um der Benutzer wählt Erfahrung zu verbessern. In der Regel die Notwendigkeit für eine zur Unterstützung von nicht e. 164-Nummer, wie Erweiterungen wäre oder abgekürzt national wählen.

- **Schritt 2** Bestimmen Sie, ob globale Mandanten oder Mandanten Benutzer bezogenen Wählpläne erforderlich sind, oder beides. Wählpläne mit Bereichszuweisung eines Benutzers sind erforderlich, wenn Benutzer über unterschiedliche Anforderungen an lokale Wählvorgänge verfügen.

- **Schritt 3**: Identifizieren Sie gültige Nummernmuster für jeden erforderlichen Wählplan. Es sind nur die Nummernmuster erforderlich, die nicht in den Wählplänen auf der Ebene von landesspezifischen Diensten definiert sind.

- **Schritt 4**: Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen. Die Übernahme eines Standardbenennungsschemas stellt die Konsistenz innerhalb einer Organisation sicher und vereinfacht Wartungsaufgaben und Updates.

Die [schnelle](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) verfügt über zusätzliche Ressourcen und Partnerunternehmen aufgeführt, die mit der Durchführung der Mandanten-Wählpläne helfen können.

## <a name="creating-your-new-tenant-dial-plan"></a>Erstellen Ihres neuen Mandantenwählplans

Wenn Sie einen neuen Wählplan erstellen, müssen Sie die erforderlichen Informationen angeben.

### <a name="name-and-simple-name"></a>Name und einfacher Name

Für Benutzer-Wählpläne sollten Sie angeben, dass ein beschreibender Namen, der den Benutzern den Wählplan identifiziert zugewiesen wird. Der Wählplan einfacher Name ist vorab aufgefüllten durch eine Zeichenfolge, die von der Wählplanname abgeleitet ist. Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. Der Wert Einfacher Name darf nicht leer und muss eindeutig sein. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.

### <a name="description"></a>Beschreibung

Wir empfehlen Ihnen, einen allgemeinen, schnell erkennbaren Namen des geografischen Standorts oder der Benutzergruppe zu verwenden, auf den der jeweilige Wählplan angewendet wird.

### <a name="external-access-prefix"></a>Präfix für externen Zugriff

> [!CAUTION]
> Der Präfix für externen Zugriff wird derzeit nicht unterstützt. 

Sie können ein Präfix für externen Zugriff von bis zu vier Zeichen (#, * und 0-9) angeben, wenn Benutzer für eine externe Verbindung mindestens eine zusätzliche führende Ziffer (zum Beispiel 9) wählen müssen.

> [!NOTE]
> Wenn Sie ein Präfix für externen Zugriff angeben, müssen Sie keine zusätzliche Normalisierungsregel erstellen, um das Präfix aufzunehmen. 

Finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) Ihres Mandanten Wählpläne erstellen.

## <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren, wie die in verschiedenen Formaten ausgedrückten Telefonnummern übersetzt werden. Je nach dem lokalen Standort, von dem aus eine Nummernzeichenfolge gewählt wird, kann diese unterschiedlich interpretiert und übersetzt werden. Normalisierungsregeln sind unter Umständen notwendig, wenn Benutzer interne oder externe Kurzwahlnummern wählen müssen.

Eine oder mehrere Normalisierungsregeln müssen mit dem Wählplan zugewiesen werden. Normalisierungsregeln werden von oben nach unten, abgeglichen werden, damit die Reihenfolge, in der sie in einem Wählplan Mandanten angezeigt werden, wichtig ist. Beispielsweise weist ein Mandanten Wählplan 10 Normalisierungsregeln, die gewählte Nummer übereinstimmende Logik versucht, beginnend mit die erste Normalisierungsregel, wenn es keine Übereinstimmung klicken Sie dann auf die zweite usw.. Wenn eine Übereinstimmung vorliegt, diese Regel wird verwendet, und es wird kein Aufwand für alle anderen Regeln entspricht, die definiert sind. In einem bestimmten Mandanten Wählplan können maximal 25 Normalisierungsregeln vorhanden sein.

### <a name="determining-the-required-normalization-rules"></a>Festlegen der erforderlichen Normalisierungsregeln

Da jeder Mandantenwählplan effektiv mit einem Wählplan eines landesspezifischen Diensts eines vorhandenen Benutzers zusammengeführt wird, müssen wahrscheinlich die Normalisierungsregeln des Wählplans eines landesspezifischen Diensts ausgewertet werden, um festzulegen, welche Normalisierungsregeln des Mandantenwählplans erforderlich sind. Zu diesem Zweck kann das **Get-CsEffectiveTenantDialPlan** -Cmdlet verwendet werden. Das Cmdlet verwendet eine Benutzeridentität als Eingabeparameter und gibt alle auf den Benutzer anwendbaren Normalisierungsregeln zurück.

### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre Ausdrücke von .NET Framework, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. Sie können Normalisierungsregeln erstellen, indem Sie den regulären Ausdruck für den Abgleich angeben sowie die Übersetzung, die für gefundene Übereinstimmungen durchgeführt werden soll. Abschließend können Sie eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.

Weitere Informationen zur Verwendung von regulärer .NET Framework-Ausdrücken finden Sie unter [Reguläre Ausdrücke von .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).

Finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) zum Erstellen und Verwalten von Normalisierungsregeln Regeln für Ihre Mandanten-Wählpläne.

### <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre Ausdrücke von .NET Framework formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer eigenen Normalisierungsregeln dar.

 **Normalisierungsregeln werden mithilfe von regulären Ausdrücken in .NET Framework**

||||||
|:-----|:-----|:-----|:-----|:-----|
|**Regelname** <br/> |**Beschreibung** <br/> |**Nummernmuster** <br/> |**Übersetzung** <br/> |**Beispiel** <br/> |
|4digitExtension  <br/> |Übersetzt vierstellige Durchwahlnummern.  <br/> |^ (\\d{4}) $  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt.  <br/> |
|5stellendurchwahl).  <br/> |Übersetzt fünfstellige Durchwahlnummern.  <br/> |^ 5 (\\d{4}) $  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt.  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond.  <br/> |^ (\\d{7}) $  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt.  <br/>|
|RedmondOperator  <br/> |Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt.  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222).  <br/> |^ 6222 (\\d{4}) $  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt.  <br/> |
|5digitRange  <br/> |Übersetzt fünfstellige Durchwahlnummern beginnend mit dem Ziffernbereich von 3 bis einschließlich 7.  <br/> |^ ([3 bis 7]\\d{4}) $  <br/> |+ 142555$ 1 <br/> |54567 wird in +14255554567 übersetzt.  <br/> |
|PrefixAdded  <br/> |Fügt ein Länderpräfix vor einer neunstelligen Nummer mit Einschränkungen für die erste und dritte Ziffer hinzu.  <br/> |^ ([2-9]\\d\\d [2-9]\\d{6}) $  <br/> |1$1  <br/> |4255554567 wird in 14255554567 übersetzt.  <br/> |
|Keine Übersetzung  <br/> |Gleicht 5 Ziffern ab, ohne eine Übersetzung durchzuführen.  <br/> |^ (\\d{5}) $  <br/> |$1  <br/> |34567 wird in 34567 übersetzt.  <br/> |

 **Wählplan für Redmond, basierend auf den oben gezeigten Normalisierungsregeln**


| Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert. |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Wählplan für Redmond** <br/>                                                                                                                              |
| 5stellendurchwahl). <br/>                                                                                                                                    |
| 7digitcallingRedmond <br/>                                                                                                                               |
| RedmondSitePrefix <br/>                                                                                                                                  |
| RedmondOperator <br/>                                                                                                                                    |

> [!NOTE]
> Die Namen der Normalisierungsregeln in der vorstehenden Tabelle enthalten keine Leerzeichen, aber dies ist nicht obligatorisch. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er „5 digit extension" oder „5-digit Extension" lautet. 


## <a name="related-topics"></a>Verwandte Themen

[Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

[Allgemeine Fragen zum Übertragen von Telefonnummern](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)