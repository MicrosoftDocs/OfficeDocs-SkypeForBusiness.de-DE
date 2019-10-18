---
title: Was sind Wählpläne?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.dialplans.overview
ms.custom:
- Calling Plans
description: 'Erfahren Sie, welche Arten von Wähl Anrufplänen (PSTN-Wählpläne) in Office 365 zur Verfügung stehen, und wie Sie eine für Ihre Organisation auswählen.  '
ms.openlocfilehash: 7a7f736ab701f2e87e29ee2a33b4cfbebccd7c21
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568564"
---
# <a name="what-are-dial-plans"></a>Was sind Wählpläne?

Ein Wählplan ist ein Norminalisierungsregelsatz, der die von einem einzelnen Benutzer gewählten Telefonnummern zur Anrufautorisierung und Anrufweiterleitung in ein anderes Format (normalerweise E.164) übersetzt.

Ein Wählplan besteht aus einer oder mehreren Normalisierungsregeln, die definieren, wie Telefonnummern, die in verschiedenen Formaten ausgedrückt werden, in ein alternatives Format übersetzt werden. Die gleiche Wählzeichenfolge kann in verschiedenen Wählplänen anders interpretiert und übersetzt werden, je nachdem, welcher Wählplan einem bestimmten Benutzer zugewiesen ist, kann dieselbe gewählte Nummer unterschiedlich übersetzt und weitergeleitet werden.

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) zum Erstellen und Verwalten von Mandanten Wählplänen.

## <a name="tenant-dial-plan-scope"></a>Mandantenwählplanbereich

Der Bereich eines Wählplans bestimmt die hierarchische Ebene, auf der die Wähleinstellungen angewendet werden können. Die Bereiche unterscheiden sich von der lokalen Bereitstellung von Skype for Business Server. Clients erhalten den entsprechenden Wählplan über Bereitstellungseinstellungen, die automatisch bereitgestellt werden, wenn sich Benutzer bei Teams oder Skype for Business Online anmelden. Als Administrator können Sie Bereichsebenen für Wähleinstellungen mithilfe von Remote-PowerShell verwalten und zuweisen.

In Microsoft Teams und Skype for Business Online gibt es zwei Arten von Wählplänen: Dienstbereich und Mandant (für Ihre Organisation), für die ein Bereich vorgesehen ist. Ein Wählplan für Dienstbereich ist für jedes Land oder jede Region definiert, in dem das Office 365-Telefon System verfügbar ist. Jedem Benutzer wird automatisch der Dienst Land-Wählplan zugewiesen, der dem Benutzer zugewiesenen Office 365-Verwendungsstandort entspricht. Sie können den Wählplan für das Service Land nicht ändern, aber Sie können mandantenspezifische Wählpläne erstellen, die den Wählplan für das Service Land ergänzen. Wenn Clients bereitgestellt werden, erhalten Sie einen "effektiven Wählplan", der eine Kombination aus dem Wählplan des Service-Landes und dem entsprechend für den Mandanten verwendeten Wählplan ist. Daher ist es nicht erforderlich, alle Normalisierungsregeln in Mandanten Wählplänen zu definieren, wie Sie möglicherweise bereits im Wählplan für das Service Land vorhanden sind.

Mandantenwählpläne können weiter in zwei Bereiche unterteilt werden: Mandantenbereich oder Benutzerbereich. Wenn ein Mandant einen Wählplan mit Bereichszuweisung eines Benutzers definiert und zuweist, erhält dieser Benutzer einen gültigen Wählplan des Wählplans eines landesspezifischen Diensts und den zugewiesenen Benutzerwählplan. Wenn ein Mandant einen Wählplan mit Bereichszuweisung eines Mandanten definiert, ohne einen Wählplan mit Bereichszuweisung eines Benutzers zuzuweisen, erhält dieser Benutzer einen gültigen Wählplan des Wählplans eines landesspezifischen Diensts und den Mandantenwählplan.

Im folgenden wird das Vererbungsmodell für Wählpläne in Teams und Skype for Business Online.

![Vererbung von Wählplänen in Teams und Skype for Business Online](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

Mögliche gültige Wählpläne:

 **Dienstleistungs Land** Wenn kein Mandanten bezogener Wählplan definiert ist und dem bereitgestellten Benutzer keine Wähleinstellungen für Mandanten mit Gültigkeitsbereich zugewiesen sind, erhält der Benutzer einen effektiven Wählplan, der dem Dienst Land zugeordnet ist, das seinem Office 365-Verwendungsstandort zugeordnet ist.

 **Mandant Global-Service Land** Wenn ein Mandanten-Wählplan definiert, aber keinem Benutzer zugewiesen ist, erhält der bereitgestellte Benutzer einen effektiven Wählplan, der aus einem zusammengeführten Mandanten Wählplan und dem für den Office 365-Verwendungsstandort zugeordneten Service Land-Wählplan besteht.

 **Mandanten Benutzer – Dienst Land** Wenn ein Mandanten-Wählplan definiert und einem Benutzer zugewiesen wird, erhält der bereitgestellte Benutzer einen effektiven Wählplan, der aus dem zusammengeführten Mandanten Benutzer-Wählplan und dem für den Office 365-Verwendungsstandort zugeordneten Service Country-Wählplan besteht.

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) zum Erstellen Ihrer Mandanten Wählpläne.

## <a name="planning-for-tenant-dial-plans"></a>Planen von Mandantenwählplänen

Führen Sie die folgenden Schritte aus, um benutzerdefinierte Wählpläne zu planen:

- **Schritt 1** Entscheiden Sie, ob ein benutzerdefinierter Wählplan erforderlich ist, um die Benutzer Wählfunktion zu verbessern. In der Regel ist es notwendig, eine nicht-E. 164-Wählfunktion zu unterstützen, beispielsweise Durchwahlnummern oder abgekürzt nationale Wähleinstellungen.

- **Schritt 2** Ermitteln Sie, ob Mandanten-Global-oder mandantenspezifische Wählpläne benötigt werden oder beides. Wählpläne mit Bereichszuweisung eines Benutzers sind erforderlich, wenn Benutzer über unterschiedliche Anforderungen an lokale Wählvorgänge verfügen.

- **Schritt 3**: Identifizieren Sie gültige Nummernmuster für jeden erforderlichen Wählplan. Es sind nur die Nummernmuster erforderlich, die nicht in den Wählplänen auf der Ebene von landesspezifischen Diensten definiert sind.

- **Schritt 4**: Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen. Die Übernahme eines Standardbenennungsschemas stellt die Konsistenz innerhalb einer Organisation sicher und vereinfacht Wartungsaufgaben und Updates.

Das Kurzprojekt bietet zusätzliche Ressourcen und Partner [, die Ihnen](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) bei der Implementierung von Mandanten Wählplänen behilflich sein können.

## <a name="creating-your-new-tenant-dial-plan"></a>Erstellen Ihres neuen Mandantenwählplans

Wenn Sie einen neuen Wählplan erstellen, müssen Sie die erforderlichen Informationen angeben.

### <a name="name-and-simple-name"></a>Name und einfacher Name

Für Benutzer Wählpläne sollten Sie einen aussagekräftigen Namen angeben, der für die Benutzer identifiziert wird, denen der Wählplan zugewiesen wird. Der einfache Name des Wählplans ist mit einer Zeichenfolge gefüllt, die vom Namen des Wählplans abgeleitet wird. Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. Der Wert Einfacher Name darf nicht leer und muss eindeutig sein. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.

### <a name="description"></a>Beschreibung

Wir empfehlen Ihnen, einen allgemeinen, schnell erkennbaren Namen des geografischen Standorts oder der Benutzergruppe zu verwenden, auf den der jeweilige Wählplan angewendet wird.

### <a name="external-access-prefix"></a>Präfix für externen Zugriff

Sie können ein Präfix für externen Zugriff von bis zu vier Zeichen (#, * und 0-9) angeben, wenn Benutzer für eine externe Verbindung mindestens eine zusätzliche führende Ziffer (zum Beispiel 9) wählen müssen.

> [!NOTE]
> Wenn Sie ein Präfix für externen Zugriff angeben, müssen Sie keine zusätzliche Normalisierungsregel erstellen, um das Präfix aufzunehmen. 

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) zum Erstellen Ihrer Mandanten Wählpläne.

## <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren, wie die in verschiedenen Formaten ausgedrückten Telefonnummern übersetzt werden. Je nach dem lokalen Standort, von dem aus eine Nummernzeichenfolge gewählt wird, kann diese unterschiedlich interpretiert und übersetzt werden. Normalisierungsregeln sind unter Umständen notwendig, wenn Benutzer interne oder externe Kurzwahlnummern wählen müssen.

Dem Wählplan müssen mindestens eine Normalisierungsregel zugewiesen sein. Normalisierungsregeln werden von oben nach unten abgeglichen, sodass die Reihenfolge, in der Sie in einem Mandanten Wählplan angezeigt werden, wichtig ist. Wenn beispielsweise ein Mandanten Wählplan 10 Normalisierungsregeln enthält, wird die für die gewählte Nummer passende Logik ab der ersten Normalisierungsregel ausprobiert, wenn keine Übereinstimmung und dann die zweite und so weiter besteht. Wenn eine Übereinstimmung vorliegt, wird diese Regel verwendet, und es gibt keine Anstrengung, andere definierte Regeln zu erfüllen. Es können maximal 25 Normalisierungsregeln in einem bestimmten Mandanten Wähl Plan vorhanden sein.

### <a name="determining-the-required-normalization-rules"></a>Festlegen der erforderlichen Normalisierungsregeln

Da jeder Mandantenwählplan effektiv mit einem Wählplan eines landesspezifischen Diensts eines vorhandenen Benutzers zusammengeführt wird, müssen wahrscheinlich die Normalisierungsregeln des Wählplans eines landesspezifischen Diensts ausgewertet werden, um festzulegen, welche Normalisierungsregeln des Mandantenwählplans erforderlich sind. Zu diesem Zweck kann das **Get-CsEffectiveTenantDialPlan** -Cmdlet verwendet werden. Das Cmdlet verwendet eine Benutzeridentität als Eingabeparameter und gibt alle auf den Benutzer anwendbaren Normalisierungsregeln zurück.

### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre Ausdrücke von .NET Framework, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. Sie können Normalisierungsregeln erstellen, indem Sie den regulären Ausdruck für den Abgleich angeben sowie die Übersetzung, die für gefundene Übereinstimmungen durchgeführt werden soll. Abschließend können Sie eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.

Ausführliche Informationen zur Verwendung von .NET Framework-regulären Ausdrücken finden Sie unter [.NET Framework-reguläre Ausdrücke](https://go.microsoft.com/fwlink/p/?linkId=140927).

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) zum Erstellen und Verwalten von Normalisierungsregeln für Ihre Mandanten Wählpläne.

### <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre Ausdrücke von .NET Framework formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer eigenen Normalisierungsregeln dar.

 **Normalisierungsregeln mit regulären Ausdrücken in .NET Framework**

||||||
|:-----|:-----|:-----|:-----|:-----|
|**Regelname** <br/> |**Beschreibung** <br/> |**Nummernmuster** <br/> |**Übersetzung** <br/> |**Beispiel** <br/> |
|4digitExtension  <br/> |Übersetzt vierstellige Durchwahlnummern.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt.  <br/> |
|5digitExtension  <br/> |Übersetzt fünfstellige Durchwahlnummern.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt.  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt.  <br/>|
|RedmondOperator  <br/> |Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt.  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt.  <br/> |
|5digitRange  <br/> |Übersetzt fünfstellige Durchwahlnummern beginnend mit dem Ziffernbereich von 3 bis einschließlich 7.  <br/> |^([3-7]\\d{4})$  <br/> |+ 142555 $1 <br/> |54567 wird in +14255554567 übersetzt.  <br/> |
|PrefixAdded  <br/> |Fügt ein Länderpräfix vor einer neunstelligen Nummer mit Einschränkungen für die erste und dritte Ziffer hinzu.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 wird in 14255554567 übersetzt.  <br/> |
|NoTranslation  <br/> |Gleicht 5 Ziffern ab, ohne eine Übersetzung durchzuführen.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 wird in 34567 übersetzt.  <br/> |

 **Wählplan für Redmond, basierend auf den oben gezeigten Normalisierungsregeln**


| Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert. |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Wählplan für Redmond** <br/>                                                                                                                              |
| 5digitExtension <br/>                                                                                                                                    |
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

[Disclaimer-Label für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
