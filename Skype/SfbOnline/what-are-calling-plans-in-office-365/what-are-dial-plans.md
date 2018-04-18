---
title: What are dial plans?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
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
- Strat_SB_PSTN
description: 'Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your organization.  '
search.appverid:
- MED150
- MOE150
ms.openlocfilehash: c24727dec0a9d938b3b0e40ef6f47501944e70e1
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="what-are-dial-plans"></a>What are dial plans?

Ein Wählplan ist ein Norminalisierungsregelsatz, der die von einem einzelnen Benutzer gewählten Telefonnummern zur Anrufautorisierung und Anrufweiterleitung in ein anderes Format (normalerweise E.164) übersetzt.
  
A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format. The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.
  
## <a name="tenant-dial-plan-scope"></a>Mandantenwählplanbereich

A dial plan's scope determines the hierarchical level at which the dial plan can be applied. The scopes are different than in a Skype for Business Server 2015 on-premises deployment. Clients obtain the appropriate dial plan through provisioning settings that are automatically provided when users log on to Skype for Business Online. As an administrator, you can manage and assign dial plan scope levels by using Remote PowerShell.
  
In Skype for Business Online, there are two types of dial plans - service scoped and tenant (which is for your organization) scoped. A service scoped dial plan is defined for every country/region where the Office 365 Phone System is available. Each user is automatically assigned the service country dial plan that matches the Office 365 Usage Location assigned to the user. You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan. As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan. Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.
  
Mandantenwählpläne können weiter in zwei Bereiche unterteilt werden: Mandantenbereich oder Benutzerbereich. Wenn ein Mandant einen Wählplan mit Bereichszuweisung eines Benutzers definiert und zuweist, erhält dieser Benutzer einen gültigen Wählplan des Wählplans eines landesspezifischen Diensts und den zugewiesenen Benutzerwählplan. Wenn ein Mandant einen Wählplan mit Bereichszuweisung eines Mandanten definiert, ohne einen Wählplan mit Bereichszuweisung eines Benutzers zuzuweisen, erhält dieser Benutzer einen gültigen Wählplan des Wählplans eines landesspezifischen Diensts und den Mandantenwählplan.
  
So sieht das Vererbungsmodell für Wahlpläne in Skype for Business Online aus:
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Mögliche gültige Wählpläne:
  
 **Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their Office 365 Usage Location.
  
 **Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
 **Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="planning-for-tenant-dial-plans"></a>Planen von Mandantenwählplänen

Führen Sie die folgenden Schritte aus, um benutzerdefinierte Wählpläne zu planen:
  
- **Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.
    
- **Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. Wählpläne mit Bereichszuweisung eines Benutzers sind erforderlich, wenn Benutzer über unterschiedliche Anforderungen an lokale Wählvorgänge verfügen.
    
- **Schritt 3**: Identifizieren Sie gültige Nummernmuster für jeden erforderlichen Wählplan. Es sind nur die Nummernmuster erforderlich, die nicht in den Wählplänen auf der Ebene von landesspezifischen Diensten definiert sind.
    
- **Schritt 4**: Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen. Die Übernahme eines Standardbenennungsschemas stellt die Konsistenz innerhalb einer Organisation sicher und vereinfacht Wartungsaufgaben und Updates.
    
The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.
  
## <a name="creating-your-new-tenant-dial-plan"></a>Erstellen Ihres neuen Mandantenwählplans

Wenn Sie einen neuen Wählplan erstellen, müssen Sie die erforderlichen Informationen angeben.
  
### <a name="name-and-simple-name"></a>Name und einfacher Name

For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned. The dial plan Simple Name is prepopulated with a string that is derived from the dial plan name. Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. The Simple Name value cannot be empty and must be unique. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.
  
### <a name="description"></a>Beschreibung

Wir empfehlen Ihnen, einen allgemeinen, schnell erkennbaren Namen des geografischen Standorts oder der Benutzergruppe zu verwenden, auf den der jeweilige Wählplan angewendet wird.
  
### <a name="external-access-prefix"></a>Präfix für externen Zugriff

> [!CAUTION]
> Der Präfix für externen Zugriff wird derzeit nicht unterstützt. 
  
Sie können ein Präfix für externen Zugriff von bis zu vier Zeichen (#, * und 0-9) angeben, wenn Benutzer für eine externe Verbindung mindestens eine zusätzliche führende Ziffer (zum Beispiel 9) wählen müssen.
  
> [!NOTE]
> Wenn Sie ein Präfix für externen Zugriff angeben, müssen Sie keine zusätzliche Normalisierungsregel erstellen, um das Präfix aufzunehmen. 
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren, wie die in verschiedenen Formaten ausgedrückten Telefonnummern übersetzt werden. Je nach dem lokalen Standort, von dem aus eine Nummernzeichenfolge gewählt wird, kann diese unterschiedlich interpretiert und übersetzt werden. Normalisierungsregeln sind unter Umständen notwendig, wenn Benutzer interne oder externe Kurzwahlnummern wählen müssen.
  
One or more normalization rules must be assigned to the dial plan. Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important. For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth. If a match is made, that rule is used and there is no effort to match any other rules that are defined. There can be a maximum of 25 normalization rules in a given tenant dial plan.
  
### <a name="determining-the-required-normalization-rules"></a>Festlegen der erforderlichen Normalisierungsregeln

Da jeder Mandantenwählplan effektiv mit einem Wählplan eines landesspezifischen Diensts eines vorhandenen Benutzers zusammengeführt wird, müssen wahrscheinlich die Normalisierungsregeln des Wählplans eines landesspezifischen Diensts ausgewertet werden, um festzulegen, welche Normalisierungsregeln des Mandantenwählplans erforderlich sind. Zu diesem Zweck kann das **Get-CsEffectiveTenantDialPlan** -Cmdlet verwendet werden. Das Cmdlet verwendet eine Benutzeridentität als Eingabeparameter und gibt alle auf den Benutzer anwendbaren Normalisierungsregeln zurück.
  
### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre Ausdrücke von .NET Framework, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. Sie können Normalisierungsregeln erstellen, indem Sie den regulären Ausdruck für den Abgleich angeben sowie die Übersetzung, die für gefundene Übereinstimmungen durchgeführt werden soll. Abschließend können Sie eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.
  
For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.
  
### <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre Ausdrücke von .NET Framework formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer eigenen Normalisierungsregeln dar.
  
 **Normalization rules using .NET Framework regular expressions**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Regelname** <br/> |**Beschreibung** <br/> |**Nummernmuster** <br/> |**Übersetzung** <br/> |**Beispiel** <br/> |
|4digitExtension  <br/> |Übersetzt vierstellige Durchwahlnummern.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt.  <br/> |
|5digitExtension  <br/> |Übersetzt fünfstellige Durchwahlnummern.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt.  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt.  <br/>|
|RedmondOperator  <br/> |Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt.  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt.  <br/> |
|5digitRange  <br/> |Übersetzt fünfstellige Durchwahlnummern beginnend mit dem Ziffernbereich von 3 bis einschließlich 7.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 wird in +14255554567 übersetzt.  <br/> |
|PrefixAdded  <br/> |Fügt ein Länderpräfix vor einer neunstelligen Nummer mit Einschränkungen für die erste und dritte Ziffer hinzu.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 wird in 14255554567 übersetzt.  <br/> |
|NoTranslation  <br/> |Gleicht 5 Ziffern ab, ohne eine Übersetzung durchzuführen.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 wird in 34567 übersetzt.  <br/> |
   
 **Wählplan für Redmond, basierend auf den oben gezeigten Normalisierungsregeln**
  
Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert.
|:-----| |**Redmond dial plan** <br/> | |5digitExtension <br/> | |7digitcallingRedmond <br/> | |RedmondSitePrefix <br/> | |RedmondOperator <br/> |
   
> [!NOTE]
> Die Namen der Normalisierungsregeln in der vorstehenden Tabelle enthalten keine Leerzeichen, aber dies ist nicht obligatorisch. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er „5 digit extension" oder „5-digit Extension" lautet. 
  
## <a name="related-topics"></a>See Also
[Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

[Allgemeine Fragen zum Übertragen von Telefonnummern](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 