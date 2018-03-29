---
title: Plan für ausgehendes VoIP-Routing in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Learn about outbound voice routing in Skype for Business Server Enterprise Voice, including call routing settings, dial plans, normalization rules, voice policies, PSTN usage records, and voice routes.
ms.openlocfilehash: 9a26f734faaa7bb070c826a427b47f805ad7438f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server-2015"></a>Plan für ausgehendes VoIP-Routing in Skype for Business Server 2015
 
Learn about outbound voice routing in Skype for Business Server Enterprise Voice, including call routing settings, dial plans, normalization rules, voice policies, PSTN usage records, and voice routes.
  
Outbound call routing applies to Enterprise Voice calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a Skype for Business user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. Ermittelt der Server keine Übereinstimmung, wird die Routinglogik für ausgehende Anrufe basierend auf der bereitgestellten Wählzeichenfolge angewendet. Sie können diese Logik durch Konfigurieren der Servereinstellungen definieren, die in der folgenden Tabelle beschrieben sind.
  
**Skype for Business Server Outbound Call Routing Settings**

|**Object**|**Beschreibung**|
|:-----|:-----|
|Wählplan  <br/> |Ein Wählplan ist ein benannter Satz von Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, für einzelne Benutzer oder für Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.  <br/> |
|Normalisierungsregel  <br/> |Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für benannte Standorte, Benutzer oder Kontaktobjekte. Ein und dieselbe Wählzeichenfolge kann je nach dem Standort, an dem sie gewählt wurde, und je nach der anrufenden Person bzw. dem anrufenden Kontaktobjekt unterschiedlich interpretiert und übersetzt werden. Eine Gruppe von Normalisierungsregeln, die einem bestimmten Standort zugeordnet sind, bildet einen Wählplan.  <br/> |
|VoIP-Richtlinie  <br/> |Eine VoIP-Richtlinie ordnet einem Benutzer oder einer Benutzergruppe mindestens einen PSTN-Verwendungseintrag zu. Außerdem enthält eine VoIP-Richtlinie immer eine Liste der Anruffunktionen, die Sie aktivieren oder deaktivieren können.  <br/> |
|PSTN-Verwendungseintrag  <br/> |Ein PSTN-Verwendungseintrag gibt eine Klasse von Anrufen an (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche), die von bestimmten Benutzern oder Benutzergruppen in einer Organisation getätigt werden dürfen.  <br/> |
|Anrufroute  <br/> |Eine Anrufroute ordnet Zielrufnummern bestimmte Trunks und PSTN-Verwendungseinträge zu. Ein PSTN-Gateway wird als Trunk angesehen.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Wählpläne und Normalisierungsregeln

Ein Wählplan ist ein benannter Satz von Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, für einzelne Benutzer oder für Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden. 
  
Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für benannte Standorte, Benutzer oder Kontaktobjekte. Ein und dieselbe Wählzeichenfolge kann je nach dem Standort, an dem sie gewählt wurde, und je nach der anrufenden Person bzw. dem anrufenden Kontaktobjekt unterschiedlich interpretiert und übersetzt werden.
  
### <a name="dial-plan-scope"></a>Wählplanbereich

A dial plan's scope determines the hierarchical level at which the dial plan can be applied. In Skype for Business Server, a user can be assigned a specific per-user dial plan. If a user dial plan is not assigned, the Front End pool dial plan is applied. If there is no Front End pool pool dial plan, the site dial plan is applied. Wenn für den Benutzer keine bestimmten Wählpläne gelten, wird der globale Wählplan angewendet.
  
Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Skype for Business. As the administrator, you can manage and assign dial plan scope levels by using Skype for Business Server Control Panel.
  
> [!NOTE]
> Der PSTN-Gateway-Wählplan auf Dienstebene wird auf eingehende Anrufe von einem bestimmten Gateway angewendet. 
  
Bereichsebenen für Wählpläne werden wie folgt definiert:
  
- **Benutzerwählplan**: Dieser Wählplan kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Sprachanwendungen können einen Wählplan pro Benutzer suchen und verwenden, wenn für „phone-context“ der Wert „user-default“ empfangen wird. Damit ein Wählplan zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
- **Poolwählplan**: Dieser Wählplan kann auf Dienstebene von jedem PSTN-Gateway oder jeder Registrierung in Ihrer Topologie erstellt werden. Zum Definieren eines Poolwählplans müssen Sie den Dienst (PSTN-Gateway oder Registrierungsstellenpool) angeben, auf den der Wählplan angewendet werden soll. 
    
- **Standortwählplan**: Dieser Wählplan kann für einen gesamten Standort erstellt werden – mit Ausnahme aller Benutzer, Gruppe oder Kontaktobjekte, denen ein Pool- oder Benutzerwählplan zugewiesen wurde. Zum Definieren eines Standortwählplans müssen Sie den Standort angeben, auf den der Wählplan angewendet werden soll.
    
- **Globaler Wählplan**: Dies ist der mit dem Produkt installierte Standardwählplan. Sie können den globalen Wählplan bearbeiten, aber nicht löschen. This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.
    
### <a name="planning-for-dial-plans"></a>Planen eines Wählplans

Führen Sie folgende Schritte aus, um einen Wählplan zu planen:
  
- Listen Sie alle Standorte auf, an denen sich eine Niederlassung Ihrer Organisation befindet.
    
    Die Liste muss aktuell und vollständig sein. Sie muss immer wieder überprüft werden, wenn sich die Unternehmensorganisation weiterentwickelt. Bei einem großen internationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann diese Aufgabe sehr zeitaufwendig sein.
    
- Identifizieren Sie gültige Rufnummernmuster für jeden Standort.
    
    Der zeitaufwendigste Teil der Planung von Wählplänen besteht darin, die gültigen Rufnummernmuster für jeden Standort zu identifizieren. In einigen Fällen können Sie möglicherweise Normalisierungsregeln, die Sie für einen Wählplan erstellt haben, in einen anderen Wählplan kopieren, insbesondere dann, wenn sich die zugehörigen Standorte auf demselben Kontinent oder sogar im selben Land bzw. in derselben Region befinden. In anderen Fällen genügt es möglicherweise, die Rufnummern in einem Wählplan geringfügig zu ändern, um sie auch in anderen Wählplänen verwenden zu können.
    
- Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.
    
    Das Erstellen eines Standardbenennungsschemas stellt die Konsistenz innerhalb der gesamten Organisation sicher und vereinfacht Wartung und Updates.
    
- Entscheiden Sie, ob für einen einzelnen Standort mehrere Wählpläne erforderlich sind. 
    
    If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.
    
- Entscheiden Sie, ob Wählpläne auf Benutzerebene erforderlich sind. For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules. For details, see [Plan for Enterprise Voice resiliency in Skype for Business Server 2015](enterprise-voice-resiliency.md).
    
- Ermitteln Sie den Bereich für den Wählplan (wie weiter oben in diesem Thema beschrieben).
    
To create a dial plan, you specify values in the following fields, as required, by using Skype for Business Server Control Panel or Skype for Business Server Management Shell.
  
#### <a name="name-and-simple-name"></a>Name und einfacher Name

Bei Benutzerwählplänen sollten Sie einen beschreibenden Namen für die Benutzer, Gruppen oder Kontaktobjekte angeben, denen der Wählplan zugewiesen wird. Für Standortwählpläne ist das Feld „Name“ bereits mit dem Namen des Standorts ausgefüllt und kann nicht geändert werden. For pool dial plans, the Name field is pre-populated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.
  
The dial plan Simple Name is pre-populated with a string that is derived from the dial plan name. Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. TheSimple Name value cannot be empty and must be unique. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.
  
#### <a name="description"></a>Beschreibung

Es wird empfohlen, den allgemeinen, wiedererkennbaren Namen des geografischen Standorts einzugeben, auf den der entsprechende Wählplan angewendet wird. Wenn der Name des Wählplans beispielsweise „London.Contoso.com“ lautet, wird für die Beschreibung der Eintrag „London“ empfohlen. 
  
#### <a name="dial-in-conferencing-region"></a>Region für Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie eine Region angeben, um die Zugriffsnummern für Einwahlkonferenzen dem entsprechenden Wählplan zuzuordnen. 
  
#### <a name="external-access-prefix"></a>Vorwahl für externen Zugriff

You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.
  
> [!NOTE]
> Wenn Sie eine Vorwahl für den externen Zugriff eingeben, müssen Sie keine zusätzliche Normalisierungsregeln zur Unterstützung der Vorwahl erstellen. 
  
### <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort. Ein und dieselbe numerische Zeichenfolge wird möglicherweise unterschiedlich interpretiert und übersetzt, je nachdem, von welchem Standort aus sie gewählt wird. Normalisierungsregeln sind für das Anrufrouting notwendig, da Benutzer Rufnummern in unterschiedlichen Formaten in ihre Kontaktlisten eingeben.
  
Die Normalisierung der von Benutzern eingegebenen Rufnummern stellt ein konsistentes Format bereit, das folgende Aufgaben vereinfacht:
  
- Match a dialed number to the intended recipient's SIP-URI.
    
- Anwenden von Wählautorisierungsregeln auf den Anrufer
    
In Normalisierungsregeln müssen möglicherweise die folgenden numerischen Felder berücksichtigt werden:
  
- Wählplan
    
- Landesvorwahl
    
- Ortsvorwahl
    
- Länge der Durchwahlnummer
    
- Standortvorwahl
    
#### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. You create normalization rules in the Skype for Business Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Skype for Business Server Control Panel generate the corresponding regular expression for you. Unabhängig davon, welche Methode Sie anwenden, können Sie anschließend eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.
  
For details about using .NET Framework regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
#### <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln
<a name="BKMK_SampleNormalizationRules"> </a>

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre Ausdrücke von .NET Framework formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer eigenen Normalisierungsregeln dar.
  
**Table 1.Normalization Rules Using .NET Framework Regular Expressions**

|**Regelname**|**Beschreibung**|**Nummernmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Übersetzt vierstellige Durchwahlnummern  <br/> |^(\d{4})$  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt.  <br/> |
|5digitExtension  <br/> |Übersetzt fünfstellige Durchwahlnummern  <br/> |^5(\d{4})$  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt.  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond  <br/> |^(\d{7})$  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt  <br/> |
|7digitcallingDallas  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Dallas  <br/> |^(\d{7})$  <br/> |+1972$1  <br/> |5550100 wird in +19725550100 übersetzt  <br/> |
|10digitcallingUS  <br/> |Übersetzt zehnstellige Rufnummern in US-Rufnummern  <br/> |^(\d{10})$  <br/> |+1$1  <br/> |2065550100 wird in +12065550100 übersetzt  <br/> |
|LDCallingUS  <br/> |Übersetzt Rufnummern mit Vorwahlen für Ferngespräche in US-Rufnummern  <br/> |^1(\d{10})$  <br/> |+$1  <br/> |12145550100 wird in +2145550100 übersetzt  <br/> |
|IntlCallingUS  <br/> |Übersetzt Rufnummern mit internationalen Vorwahlen in US-Rufnummern  <br/> |^011(\d\*)$  <br/> |+$1  <br/> |01191445550100 wird in +91445550100 übersetzt  <br/> |
|RedmondOperator  <br/> |Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt.  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222)  <br/> |^6222(\d{4})$  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt  <br/> |
|NYSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von New York (333)  <br/> |^6333(\d{4})$  <br/> |+1202555$1  <br/> |63330100 wird in +12025550100 übersetzt  <br/> |
|DallasSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Dallas-Vorwahl (444)  <br/> |^6444(\d{4})$  <br/> |+1972555$1  <br/> |64440100 wird in +19725550100 übersetzt  <br/> |
   
Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert.
  
**Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1**

|**Redmond.forestFQDN**|
|:-----|
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|10digitcallingUS  <br/> |
|IntlCallingUS  <br/> |
|RedmondSitePrefix  <br/> |
|NYSitePrefix  <br/> |
|DallasSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> Die Namen der Normalisierungsregeln in der vorstehenden Tabelle enthalten keine Leerzeichen, aber dies ist nicht obligatorisch. Beispielsweise ist der erste Name in der Tabelle auch gültig, wenn er „5 digit extension“ oder „5-digit Extension“ lautet. 
  
## <a name="voice-policies"></a>VoIP-Richtlinien

Skype for Business Server voice policies define the following for each user, site, or organization that is assigned the policy:
  
- A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.
    
- Einer Gruppe von Telefonfestnetz-Verwendungseinträgen, die festlegen, welche Arten von Anrufen erlaubt sind. 
    
The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:
  
- Legen Sie fest, wie die globale VoIP-Richtlinie (die Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird) konfiguriert werden soll. This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.
    
- Bestimmen der ggf. erforderlichen VoIP-Richtlinien auf Standortebene.
    
- Bestimmen der ggf. erforderlichen benutzerbezogenen VoIP-Richtlinien.
    
- Entscheiden, welche Anruffunktionen für jede VoIP-Richtlinie aktiviert werden sollen.
    
- Bestimmen, welche PSTN-Verwendungseinträge für jede VoIP-Richtlinie konfiguriert werden sollen.
    
### <a name="voice-policy-scope"></a>Gültigkeitsbereich von VoIP-Richtlinien

Voice policy scope determines the hierarchical level at which the policy can be applied. In Skype for Business Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).
  
- Die **VoIP-Benutzerrichtlinie** kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Dies ist die niedrigste Richtlinienebene. VoIP-Benutzerrichtlinien können bereitgestellt werden, um Funktionen nur für bestimmte Benutzer oder Gruppen an einem Standort zu aktivieren. Sie können damit z. B. bei bestimmten Mitarbeitern Ferngespräche deaktivieren. Damit eine VoIP-Richtlinie zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
    > [!NOTE]
    > We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance. 
  
- Eine **VoIP-Standortrichtlinie** gilt für einen gesamten Standort. Ausgenommen sind Benutzer, Gruppen oder Kontaktobjekte, denen eine Benutzerrichtlinie zugeordnet wurde. Zum Definieren einer VoIP-Standortrichtlinie müssen Sie den Standort angeben, für den die Richtlinie gelten soll. Wenn keine VoIP-Benutzerrichtlinie zugewiesen ist, wird die VoIP-Standortrichtlinie verwendet.
    
- **Global voice policy** is the default voice policy that is installed with the product. You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it. This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope. If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.
    
### <a name="call-features"></a>Anruffunktionen

Für jede Richtlinie können Sie die folgenden Anruffunktionen aktivieren oder deaktivieren:
  
- **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Diese Option ist standardmäßig aktiviert.
    
- **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. Diese Option ist standardmäßig aktiviert.
    
- **Anrufdurchstellung** ermöglicht Benutzern, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.
    
- **Anruf parken** ermöglicht Benutzern, Anrufe in der Warteschleife zu parken und mit einem anderen Telefon oder Clientgerät wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.
    
- **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Läuten auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Diese Option ist standardmäßig aktiviert.
    
- **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.
    
- **PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.
    
- **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.
    
- **Malicious call tracing** enables users to report malicious calls by using the Skype for Business client, and then flags such calls in the call detail records. Diese Option ist standardmäßig deaktiviert.
    
- **Voicemail escape** prevents calls from being immediately routed to the user's mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value. Mit dieser Einstellung wird der Timer aktiviert und deaktiviert sowie der Wert des Timers eingestellt. It can be configured only by using the Skype for Business Server Management Shell. Diese Option ist standardmäßig deaktiviert.
    
- **Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Skype for Business users only, or specify a custom PSTN usage that is different from the voice policy's PSTN usage. Standardmäßig wird für Anrufweiterleitung und gleichzeitiges Klingeln die gleiche PSTN-Verwendung verwendet wie bei der VoIP-Richtlinie.
    
### <a name="pstn-usage-records"></a>PSTN-Verwendungseinträge

Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungseintrag zugeordnet sein. PSTN-Verwendungen können nur zum Zweck von Anrufweiterleitung und gleichzeitigem Klingeln einer VoIP-Richtlinie zugeordnet sein. 
  
> [!NOTE]
> Die Reihenfolge der PSTN-Verwendungseinträge ist wichtig, da die Ausgangsroutingfunktion beim Zuordnen von Benutzern zu Routen die PSTN-Verwendungseinträge von oben nach unten vergleicht. Wenn der erste Eintrag mit der Anrufroute übereinstimmt, wird diese Route verwendet. Falls nicht, unterstützt die Ausgangsroutingfunktion den nächsten PSTN-Verwendungseintrag in der Liste und fährt damit fort, bis eine Übereinstimmung gefunden wird. Die nachfolgenden PSTN-Verwendungseinträge dienen zur zusätzlichen Absicherung, wenn der erste Datensatz in der Liste nicht verfügbar ist. 
  
## <a name="pstn-usage-records"></a>PSTN-Verwendungseinträge

Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.
  
Im Folgenden sehen Sie eine typische PSTN-Verwendungstabelle.
  
**PSTN Usage Records**

|**Phone attribute**|**Beschreibung**|
|:-----|:-----|
|Local  <br/> |Ortsgespräche  <br/> |
|Long-Distance  <br/> |Ferngespräche  <br/> |
|International  <br/> |Auslandsgespräche  <br/> |
|Delhi  <br/> |Vollzeitmitarbeiter in Delhi  <br/> |
|Redmond  <br/> |Vollzeitmitarbeiter in Redmond  <br/> |
|RedmondTemps  <br/> |Zeitarbeiter in Redmond  <br/> |
|Zurich  <br/> |Vollzeitmitarbeiter in Zürich  <br/> |
   
PSTN-Verwendungseinträge alleine führen keine Aktionen aus. Um sie verwenden zu können, müssen Sie sie mit Folgendem verknüpfen:
  
- VoIP-Richtlinien, die Benutzern zugewiesen sind
    
- Routen, die Rufnummern zugewiesen sind
    
## <a name="voice-routes"></a>VoIP-Routen

Call routes specify how Skype for Business Server handles outbound calls placed by Enterprise Voice users. When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI. Wenn keine Zuordnung möglich ist, wendet der Server eine auf der Nummer basierende Routinglogik für ausgehende Anrufe an. Der letzte Schritt zum Definieren der Logik besteht darin, eine separate benannte Anrufroute für jeden Satz von Zielrufnummern zu erstellen, die in den einzelnen Wählplänen aufgeführt sind.
  
Vor dem Definieren von Routen für ausgehende Anrufe sollten Sie die folgenden Schritte abschließen:
  
- Stellen Sie einen oder mehrere Trunks bereit.
    
- Erstellen Sie nach Bedarf Wählpläne für Standorte, Einzelpersonen und Kontaktobjekte.
    
- Erstellen Sie PSTN-Verwendungseinträge (Public Switched Telephone Network, Telefonfestnetz)
    
Sie müssen außerdem eine oder mehrere VoIP-Richtlinien erstellen und zuweisen, um das Routing ausgehender Anrufe zu aktivieren. Diese Aktion kann entweder vor oder nach der Definition ausgehender Anrufrouten durchgeführt werden.
  
Für jede Route müssen Sie Folgendes angeben:
  
- Einen Namen, mit dem die Route leicht identifiziert werden kann
    
- Eine optionale Beschreibung in Fällen, in denen der Name allein möglicherweise nicht als Beschreibung der Route ausreicht
    
- Den regulären Ausdruck für das Vergleichsmuster, das die Zielrufnummern identifiziert, auf die die Route angewendet wird, sowie Ausnahmen, auf die das Vergleichsmuster nicht angewendet wird
    
- Einen oder mehrere Trunks, den Sie der Route zuweisen möchten
    
- Die PSTN-Verwendungseinträge, über die Benutzer verfügen müssen, um Rufnummern anzurufen, die dem regulären Ausdruck für die Zielrufnummer entsprechen
    
You can specify call routes in the Skype for Business Server Control Panel. These call routes populate the server routing table, which Skype for Business Server uses to route calls that are destined for the PSTN.
  
### <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Skype for Business Server provides flexibility in how calls are routed to the PSTN. A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call. A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number. This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway. When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route. To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.
  
### <a name="least-cost-routing"></a>Kostenoptimierter Verbindungsaufbau

Durch das Festlegen von Trunks, an die verschiedene Rufnummern weitergeleitet werden, können Sie die Routen bestimmen, die die geringsten Kosten verursachen, und sie entsprechend implementieren. Normalerweise wählen Sie Trunks aus, indem Sie den Trunk mit dem nächstgelegenen Gateway zum Standort der Zielrufnummer auswählen, um die Gebühren für Ferngespräche möglichst gering zu halten. Wenn Sie sich z. B. in New York befinden und eine Rufnummer in Rom wählen, leiten Sie den Anruf über das IP-Netzwerk an den Trunk mit dem Gateway in Ihrer Niederlassung in Rom weiter, sodass nur Gebühren für ein Ortsgespräch anfallen.
  
Das folgende Beispiel zeigt eine Verwendungsmöglichkeit des kostenoptimierten Verbindungsaufbaus: Fabrikam beschließt, dass deutsche Benutzer Rufnummern in den USA über den US-Trunk wählen sollen. Fabrikam also wants to configure the system so that all calls from U.S. Skype for Business Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany. Durch dieses Routing wird Geld gespart, da ein Anruf von Deutschland nach Österreich beispielsweise weniger kostspielig ist als ein Anruf aus den USA nach Österreich.
  
### <a name="translating-outbound-dial-strings"></a>Übersetzen ausgehender Wählzeichenfolgen

Skype for Business Server requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL). For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Skype for Business Server enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk. Sie können beispielsweise eine Regel schreiben, mit der die Vorwahl +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.
  
With Skype for Business Server, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.
  
In planning your trunks that associate gateway:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.
  
### <a name="configuring-caller-id"></a>Konfigurieren der Anrufer-ID

Skype for Business Server provides a way to manipulate the caller ID for outbound calls. For example, if an organization wants to mask employees' direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Skype for Business Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID. In planning your routing logic, consider which individuals, groups, sites you'll want this option for—perhaps, even, for all employees.
  
> [!NOTE]
> Für Anrufe, die über das Telefonfestnetz (PSTN) umgeleitet werden, wird die allgemeine Anrufer-ID anstelle der ursprünglichen Anrufer-ID angezeigt. Dies kann dazu führen, dass „Nicht stören“- oder Privatsphäreneinstellungen umgangen werden, die der angerufene Teilnehmer möglicherweise konfiguriert hat. 
  
### <a name="additional-routing-logic"></a>Zusätzliche Routinglogik

Beachten Sie bei der Erstellung von Routen für ausgehende Anrufe die folgenden Faktoren, die sich auf die Routinglogik auswirken können:
  
- Wenn ein Anruf über eine Verbundgrenze hinweg eingerichtet wird, wird der Anruf mithilfe der Domäne im URI an das Unternehmen weitergeleitet, das für die Anwendung der Ausgangsroutinglogik verantwortlich ist.
    
- Wenn die im Anforderungs-URI angegebene Domäne nicht für das Unternehmen unterstützt wird, verarbeitet die Ausgangsroutingkomponente auf dem Server den Anruf nicht.
    
- If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.
    
- Wenn der Anruf an ein vollständig besetztes Gateway (bei dem alle Trunkleitungen belegt sind) geroutet wird, weist das Gateway den Anruf zurück und die Ausgangsroutingkomponente leitet ihn an die Route mit den zweitgeringsten Kosten um. Bedenken Sie dies sorgfältig, da ein Gateway, dessen Größe auf ein kleines Büro in Europa (im Beispiel: Zürich) ausgerichtet ist, möglicherweise einen umfangreichen nicht lokalen Datenverkehr für Auslandsgespräche mit der Schweiz übertragen muss. Wenn das Gateway nicht die richtige Größe für diesen zusätzlichen Datenverkehr aufweist, werden Anrufe aus den USA in die Schweiz möglicherweise über ein Gateway in Deutschland weitergeleitet, was höhere Telefongebühren bedeutet.
    

