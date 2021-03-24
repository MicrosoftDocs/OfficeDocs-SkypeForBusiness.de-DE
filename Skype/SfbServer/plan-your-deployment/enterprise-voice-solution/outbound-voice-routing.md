---
title: Planen des ausgehenden Voiceroutings in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Erfahren Sie mehr über ausgehendes Voicerouting in Skype for Business Server Enterprise-VoIP, einschließlich Anrufroutingeinstellungen, Wähleinstellungen, Normalisierungsregeln, Sprachrichtlinien, PSTN-Verwendungsdatensätzen und Sprachrouten.
ms.openlocfilehash: 70681e995068a0999324694a78806421e0f2d129
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101281"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planen des ausgehenden Voiceroutings in Skype for Business Server
 
Erfahren Sie mehr über ausgehendes Voicerouting in Skype for Business Server Enterprise-VoIP, einschließlich Anrufroutingeinstellungen, Wähleinstellungen, Normalisierungsregeln, Sprachrichtlinien, PSTN-Verwendungsdatensätzen und Sprachrouten.
  
Das Routing ausgehender Anrufe gilt für Enterprise-VoIP, die für ein Public Switched Telephone Network (PSTN)-Gateway, einen Trunk oder eine Nebenstellenanlage (Private Branch Exchange, PBX) bestimmt sind. Wenn ein Skype for Business-Benutzer einen Anruf anruft, normalisiert der Server die Telefonnummer bei Bedarf in das E.164-Format und versucht, sie mit einem SIP-URI zu verbinden. Ermittelt der Server keine Übereinstimmung, wird die Routinglogik für ausgehende Anrufe basierend auf der bereitgestellten Wählzeichenfolge angewendet. Sie können diese Logik durch Konfigurieren der Servereinstellungen definieren, die in der folgenden Tabelle beschrieben werden.
  
**Routingeinstellungen für ausgehende Anrufe in Skype for Business Server**

|**Objekt**|**Beschreibung**|
|:-----|:-----|
|Wähleinstellungen  <br/> |Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden.  <br/> |
|Normalisierungsregel  <br/> |Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt. Ein und dieselbe Wählzeichenfolge kann je nach Standort, an dem sie gewählt wurde, und je nach Person oder Kontaktobjekt, die bzw. das den Anruf tätigt, unterschiedlich interpretiert und übersetzt werden. Eine Gruppe von Normalisierungsregeln, die einem bestimmten Standort zugeordnet sind, bildet einen Satz mit Wähleinstellungen.  <br/> |
|VoIP-Richtlinie  <br/> |Eine VoIP-Richtlinie ordnet einem Benutzer oder einer Benutzergruppe mindestens einen PSTN-Verwendungsdatensatz zu. Eine VoIP-Richtlinie stellt darüber hinaus eine Liste der Anruffunktionen bereit, die Sie aktivieren oder deaktivieren können.  <br/> |
|PSTN-Verwendungsdatensatz  <br/> |Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von bestimmten Benutzern oder Benutzergruppen in einer Organisation getätigt werden dürfen.  <br/> |
|Anrufroute  <br/> |Eine Anrufroute ordnet Zielrufnummern bestimmte Trunks und PSTN-Verwendungseinträge zu. Ein PSTN-Gateway wird als Trunk angesehen.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Wählpläne und Normalisierungsregeln

Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden. 
  
Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt. Die gleiche Wählzeichenfolge kann je nach dem Ort, von dem sie gewählt wird, und der Person oder dem Kontaktobjekt, die den Anruf führt, unterschiedlich interpretiert und übersetzt werden.
  
### <a name="dial-plan-scope"></a>Bereich "Wählplan"

Der Bereich eines Wählplans bestimmt die hierarchische Ebene, auf der der Wählplan angewendet werden kann. In Skype for Business Server kann einem Benutzer ein bestimmter Wählplan pro Benutzer zugewiesen werden. Wenn kein Benutzerwählplan zugewiesen ist, wird der Front-End-Poolwählplan angewendet. Wenn kein Front-End-Poolwählplan vorhanden ist, wird der Standortwählplan angewendet. Wenn kein anderer Wählplan für den Benutzer gilt, wird schließlich der globale Wählplan angewendet.
  
Clients erhalten Wählplanbereichsebenen über In-Band-Bereitstellungseinstellungen, die bereitgestellt werden, wenn sich Benutzer bei Skype for Business anmelden. Als Administrator können Sie Wählplanbereichsebenen mithilfe der Skype for Business Server-Systemsteuerung verwalten und zuweisen.
  
> [!NOTE]
> Der Service Level Public Switched Telephone Network (PSTN)-Gatewaywählplan wird auf die eingehenden Anrufe von einem bestimmten Gateway angewendet. 
  
Wählplanbereichsebenen werden wie folgt definiert:
  
- **Benutzerwählplan**: Kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Sprachanwendungen können einen benutzerbezogenen Wählplan nachschauen, wenn ein Anruf empfangen wird, während der Telefonkontext auf Benutzereinstellungen festgelegt ist. Zum Zuweisen eines Wählplans wird ein Kontaktobjekt als einzelner Benutzer behandelt.
    
- **Poolwählplan:** Kann auf Dienstebene für alle PSTN-Gateways oder Registrierungsstellen in Ihrer Topologie erstellt werden. Zum Definieren eines Poolwählplans müssen Sie den bestimmten Dienst (PSTN-Gateway oder Registrierungsstellenpool) angeben, auf den der Wählplan angewendet wird. 
    
- **Standortwählplan**: Kann für einen gesamten Standort erstellt werden, mit Ausnahme von Benutzern, Gruppen oder Kontaktobjekten, denen ein Poolwählplan oder ein Benutzerwählplan zugewiesen ist. Zum Definieren eines Standortwählplans müssen Sie den Standort angeben, auf den der Wählplan angewendet wird.
    
- **Globaler Wählplan:** Der standardmäßige Wählplan, der mit dem Produkt installiert ist. Sie können den globalen Wählplan bearbeiten, ihn jedoch nicht löschen. Dieser Wählplan gilt für alle Enterprise-VoIP, Gruppen und Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen einen Wählplan mit einem spezielleren Bereich zu.
    
### <a name="planning-for-dial-plans"></a>Planen von Wählplänen

Führen Sie die folgenden Schritte aus, um einen Wählplan zu planen:
  
- Listet alle Locales auf, in denen Ihre Organisation über ein Büro verfügt.
    
    Die Liste muss aktuell und vollständig sein. Sie muss bei der Weiterentwicklung der Unternehmensorganisation überarbeitet werden. In einem großen, multinationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann dies eine zeitaufwändige Aufgabe sein.
    
- Identifizieren Sie gültige Nummernmuster für jede Website.
    
    Der zeitaufwändigste Teil der Planung Ihrer Wählpläne ist die Identifizierung der gültigen Nummernmuster für jeden Standort. In einigen Fällen können Sie Normalisierungsregeln, die Sie für einen Wählplan geschrieben haben, in andere Wählpläne kopieren, insbesondere, wenn sich die entsprechenden Standorte innerhalb desselben Landes/einer Region oder sogar eines Kontinents befinden. In anderen Fällen können kleine Änderungen an Nummern in einem Wählplan ausreichen, um sie in anderen Wählplänen zu verwenden.
    
- Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.
    
    Die Einführung eines Standardbenennungsschemas gewährleistet konsistenzübergreifend in einer Organisation und vereinfacht Wartung und Updates.
    
- Entscheiden Sie, ob mehrere Wählpläne für einen einzelnen Standort erforderlich sind. 
    
    Wenn Ihre Organisation einen einzigen Wählplan an mehreren Standorten verwaltet, müssen Sie möglicherweise weiterhin einen separaten Wählplan für Enterprise-VoIP-Benutzer erstellen, die von einer Nebenstellenanlage migrieren und deren vorhandene Durchwahlen beibehalten werden müssen.
    
- Entscheiden Sie, ob benutzerfreundliche Wählpläne erforderlich sind. Wenn Sie beispielsweise Benutzer an einem Zweigstellenstandort haben, die beim zentralen Standort registriert sind, oder wenn Sie Benutzer haben, die in einer Survivable Branch Appliance registriert sind, können Sie spezielle Wählszenarien für diese Benutzer mithilfe von Benutzerwählplänen und Normalisierungsregeln in Betracht ziehen. Weitere Informationen finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Bestimmen des Wählplanbereichs (wie zuvor in diesem Thema beschrieben).
    
Zum Erstellen eines Wählplans geben Sie die Werte in den folgenden Feldern nach Bedarf mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell an.
  
#### <a name="name-and-simple-name"></a>Name und einfacher Name

Für Benutzerwählpläne sollten Sie einen beschreibenden Namen angeben, der die Benutzer, Gruppen oder Kontaktobjekte identifiziert, denen der Wählplan zugewiesen wird. Bei Standortwählplänen wird das Feld Name mit dem Websitenamen vorab aufgefüllt und kann nicht geändert werden. Bei Poolwählplänen wird das Feld Name mit dem PSTN-Gateway oder dem vollqualifizierten Domänennamen (FQDN) des Front-End-Pools ausgefüllt und kann nicht geändert werden.
  
Der einfache Name des Wählplans wird mit einer Zeichenfolge vorgefüllt, die vom Namen des Wählplans abgeleitet ist. Das Feld Einfacher Name kann bearbeitet werden, wodurch Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne erstellen können. Der WertSimple Name darf nicht leer sein und muss eindeutig sein. Eine bewährte Methode ist es, eine Benennungskonvention für Ihre gesamte Organisation zu entwickeln und diese Konvention dann konsistent auf allen Websites und Benutzern zu verwenden.
  
#### <a name="description"></a>Beschreibung

Es wird empfohlen, den allgemeinen, erkennbaren Namen des geografischen Standorts ein, für den der entsprechende Wählplan gilt. Wenn der Name des Wählplans z. B. London.Contoso.com ist, wird empfohlen, London zu beschreiben. 
  
#### <a name="dial-in-conferencing-region"></a>Einwahlkonferenzregion

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie einen Einwahlkonferenzbereich angeben, um Einwahlkonferenznummern einem Wählplan zuzuordnen. 
  
#### <a name="external-access-prefix"></a>Präfix für den externen Zugriff

Sie können ein Präfix für den externen Zugriff von bis zu vier Zeichen (#, und 0-9) angeben, wenn Benutzer eine oder mehrere zusätzliche vorangestellte Ziffern (z. B. 9) wählen müssen, um eine externe Zeile zu \* erhalten.
  
> [!NOTE]
> Wenn Sie ein Präfix für den externen Zugriff angeben, müssen Sie keine zusätzliche Normalisierungsregel erstellen, um das Präfix zu verwenden. 
  
### <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren, wie Telefonnummern, die in verschiedenen Formaten ausgedrückt werden, für den benannten Speicherort geroutet werden sollen. Die gleiche Zahlenzeichenfolge kann je nach dem Ort, aus dem sie gewählt wird, unterschiedlich interpretiert und übersetzt werden. Normalisierungsregeln sind für das Anrufrouting erforderlich, da Benutzer bei der Eingabe von Telefonnummern in ihren Kontaktlisten verschiedene Formate verwenden können und können.
  
Die Normalisierung von vom Benutzer bereitgestellten Telefonnummern bietet ein konsistentes Format, das die folgenden Aufgaben erleichtert:
  
- Match a dialed number to the intended recipient's SIP-URI.
    
- Wenden Sie Wählautorisierungsregeln auf den Anrufer an.
    
Die folgenden Zahlenfelder gehören zu denen, die Ihre Normalisierungsregeln möglicherweise berücksichtigen müssen:
  
- Wählplan
    
- Landeskennzahl
    
- Vorwahl
    
- Länge der Erweiterung
    
- Websitepräfix
    
#### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden .NET Framework regulären Ausdrücke, um numerische Übereinstimmungsmuster anzugeben, die der Server zum Übersetzen von Wählzeichenfolgen in das E.164-Format zum Zwecke der Reversenummer-Suche verwendet. Sie erstellen Normalisierungsregeln in der Skype for Business Server-Systemsteuerung, indem Sie die Ausdrücke manuell eingeben oder die Anfangsziffern und die Länge der Wählzeichenfolgen eingeben, die übereinstimmen sollen, und die Skype for Business Server-Systemsteuerung den entsprechenden regulären Ausdruck für Sie generieren lässt. Wenn Sie fertig sind, können Sie eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.
  
Weitere Informationen zur Verwendung .NET Framework regulären Ausdrücken finden Sie [unter ".NET Framework Reguläre Ausdrücke"](/dotnet/standard/base-types/regular-expressions).
  
#### <a name="sample-normalization-rules"></a>Beispielnormalisierungsregeln
<a name="BKMK_SampleNormalizationRules"> </a>

In der folgenden Tabelle sind Beispielnormalisierungsregeln aufgeführt, die als reguläre Ausdrücke .NET Framework werden. Die Beispiele sind nur Beispiele und sollten kein präskriptiver Verweis zum Erstellen eigener Normalisierungsregeln sein.
  
**Tabelle 1.Normalisierungsregeln mit .NET Framework regulären Ausdrücken**

|**Regelname**|**Beschreibung**|**Nummernmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Übersetzt vierstellige Erweiterungen  <br/> |^(\d{4})$  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt  <br/> |
|5digitExtension  <br/> |Übersetzt 5-stellige Erweiterungen  <br/> |^5(\d {4} )$  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt 7-stellige Zahlen in lokale Redmond-Nummern  <br/> |^(\d{7})$  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt  <br/> |
|7digitcallingDallas  <br/> |Übersetzt 7-stellige Zahlen in lokale Zahlen in Dallas  <br/> |^(\d{7})$  <br/> |+1972$1  <br/> |5550100 wird in +19725550100 übersetzt  <br/> |
|10digitcallingUS  <br/> |Übersetzt 10-stellige Zahlen in den VEREINIGTEn Staaten  <br/> |^(\d{10})$  <br/> |+1$1  <br/> |2065550100 wird in +12065550100 übersetzt  <br/> |
|LDCallingUS  <br/> |Übersetzt Zahlen mit Fernpräfixen in den VEREINIGTEn Staaten  <br/> |^1(\d {10} )$  <br/> |+$1  <br/> |12145550100 wird in +2145550100 übersetzt  <br/> |
|IntlCallingUS  <br/> |Übersetzt Zahlen mit internationalen Präfixen in den Vereinigten Staaten  <br/> |^011(\d \* )$  <br/> |+$1  <br/> |01191445550100 wird in +91445550100 übersetzt  <br/> |
|RedmondOperator  <br/> |Übersetzt 0 in Redmond Operator  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Zahlen mit dem On-Net-Präfix (6) und dem Redmond-Standortcode (222)  <br/> |^6222(\d {4} )$  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt  <br/> |
|NYSitePrefix  <br/> |Übersetzt Zahlen mit dem On-Net-Präfix (6) und dem NY-Websitecode (333)  <br/> |^6333(\d {4} )$  <br/> |+1202555$1  <br/> |63330100 wird in +12025550100 übersetzt  <br/> |
|DallasSitePrefix  <br/> |Übersetzt Zahlen mit dem On-Net-Präfix (6) und dem Dallas-Websitecode (444)  <br/> |^6444(\d {4} )$  <br/> |+1972555$1  <br/> |64440100 wird in +19725550100 übersetzt  <br/> |
   
Die folgende Tabelle veranschaulicht einen Beispielwählplan für Redmond, Washington, USA, basierend auf den In der vorherigen Tabelle gezeigten Normalisierungsregeln.
  
**Tabelle 2. Redmond Dial Plan based on Normalization Rules shown in Table 1**

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
> Die Namen der Normalisierungsregeln, die in der vorherigen Tabelle angezeigt werden, enthalten keine Leerzeichen, aber dies ist eine Frage der Wahl. Der Vorname in der Tabelle könnte beispielsweise "5-stellige Durchwahl" oder "5-stellige Durchwahl" geschrieben worden sein und ist weiterhin gültig. 
  
## <a name="voice-policies"></a>Sprachrichtlinien

Skype for Business Server-Voicerichtlinien definieren folgendes für jeden Benutzer, jede Website oder Organisation, dem die Richtlinie zugewiesen ist:
  
- Eine Reihe von aufrufenden Features, die aktiviert oder deaktiviert werden können, um die verfügbaren Enterprise-VoIP zu bestimmen.
    
- Einer Gruppe von Telefonfestnetz-Verwendungsdatensätzen, die festlegen, welche Arten von Anrufen erlaubt sind. 
    
Die folgenden Schritte helfen Ihnen bei der Planung der Sprachrichtlinien, die Sie für Ihre bereitstellung Enterprise-VoIP benötigen:
  
- Legen Sie fest, wie die globale VoIP-Richtlinie (die Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird), konfiguriert werden soll. Diese Richtlinie gilt für alle benutzer Enterprise-VoIP, denen keine Richtlinie auf Websiteebene oder pro Benutzer explizit zugewiesen ist.
    
- Bestimmen der ggf. erforderlichen VoIP-Richtlinien auf Standortebene.
    
- Bestimmen der ggf. erforderlichen benutzerbezogenen VoIP-Richtlinien.
    
- Entscheiden, welche Anruffunktionen für jede VoIP-Richtlinie aktiviert werden sollen.
    
- Bestimmen, welche PSTN-Verwendungsdatensätze für jede VoIP-Richtlinie konfiguriert werden sollen.
    
### <a name="voice-policy-scope"></a>Gültigkeitsbereich von VoIP-Richtlinien

Der Gültigkeitsbereich von VoIP-Richtlinien bestimmt die Hierarchieebene, auf der die Richtlinie gelten soll. In Skype for Business Server können Sie Sprachrichtlinien mit den folgenden Bereichsstufen konfigurieren (von den spezifischsten bis zu den allgemeinsten).
  
- Die **VoIP-Benutzerrichtlinie** kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Dies ist die niedrigste Richtlinienebene. VoIP-Benutzerrichtlinien können bereitgestellt werden, um Funktionen nur für bestimmte Benutzer oder Gruppen an einem Standort zu aktivieren. Sie können damit z. B. bei bestimmten Mitarbeitern Ferngespräche deaktivieren. Damit eine VoIP-Richtlinie zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
    > [!NOTE]
    > Es wird empfohlen, eine Benutzerstimmenrichtlinie für Zweigstellenstandorte Enterprise-VoIP Benutzer, die bei der zentralen Standortbereitstellung registriert sind, oder Benutzer, die bei einer Survivable Branch Appliance registriert sind, bereitstellen. 
  
- Eine **VoIP-Standortrichtlinie** gilt für einen gesamten Standort. Ausgenommen sind Benutzer, Gruppen oder Kontaktobjekte, denen eine Benutzerrichtlinie zugeordnet wurde. Zum Definieren einer VoIP-Standortrichtlinie müssen Sie den Standort angeben, für den die Richtlinie gelten soll. Wenn keine VoIP-Benutzerrichtlinie zugewiesen ist, wird die VoIP-Standortrichtlinie verwendet.
    
- **Globale Sprachrichtlinie** ist die Standard-Voicerichtlinie, die mit dem Produkt installiert wird. Sie können die globale Sprachrichtlinie bearbeiten, um die spezifischen Anforderungen Ihrer Organisation zu erfüllen, aber Sie können sie nicht umbenennen oder löschen. Diese Voicerichtlinie gilt für alle Enterprise-VoIP, Gruppen und Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen eine Sprachrichtlinie mit einem spezielleren Bereich zu. Wenn Sie diese Richtlinie vollständig deaktivieren möchten, stellen Sie sicher, dass allen Websites und Benutzern benutzerdefinierte Richtlinien zugewiesen sind.
    
### <a name="call-features"></a>Anruffunktionen

Für jede Richtlinie können Sie die folgenden Anruffunktionen aktivieren oder deaktivieren:
  
- **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Diese Option ist standardmäßig aktiviert.
    
- **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. Diese Option ist standardmäßig aktiviert.
    
- **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.
    
- **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.
    
- **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Läuten auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Diese Option ist standardmäßig aktiviert.
    
- **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.
    
- **PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.
    
- **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht es Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.
    
- **Die Ablaufverfolgung bösartiger** Anrufe ermöglicht Es Benutzern, böswillige Anrufe mithilfe des Skype for Business-Clients zu melden und diese Anrufe dann in den Anrufdetailseakten zu kennzeichnet. Diese ist standardmäßig deaktiviert.
    
- **Voicemail-Escape** verhindert, dass Anrufe sofort an das Voicemailsystem des Mobiltelefons des Benutzers geroutet werden, wenn gleichzeitiges Klingeln konfiguriert ist und das Telefon ausgeschaltet ist, der Akku leer ist oder nicht mehr verfügbar ist und auf einem Zeitgeberwert basiert. Diese Einstellung aktiviert und deaktiviert den Timer und stellt den Wert des Timers ein. Sie kann nur mithilfe der Skype for Business Server-Verwaltungsshell konfiguriert werden. Diese ist standardmäßig deaktiviert.
    
- Die Anruf weiterleitung und gleichzeitiges Klingeln von **PSTN-Verwendungen** ermöglicht Es Administratoren, die gleiche PSTN-Verwendung wie die Voicerichtlinie für die Anruf weiterleitung und das gleichzeitige Klingeln anzugeben, die Anruf weiterleitung und das gleichzeitige Klingeln nur für interne Skype for Business-Benutzer einzuschränken oder eine benutzerdefinierte PSTN-Verwendung anzugeben, die sich von der PSTN-Verwendung der Sprachrichtlinie ab unterscheiden. Standardmäßig wird für Anrufweiterleitung und gleichzeitiges Klingeln die gleiche PSTN-Verwendung verwendet, wie bei der VoIP-Richtlinie.
    
### <a name="pstn-usage-records"></a>PSTN-Verwendungsdatensätze

Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungsdatensatz zugeordnet sein. PSTN-Verwendungen können nur zum Zweck von Anrufweiterleitung und gleichzeitigem Klingeln einer VoIP-Richtlinie zugeordnet sein. 
  
> [!NOTE]
> Die Reihenfolge der PSTN-Verwendungsdatensätze ist wichtig, da die Ausgangsroutingfunktion beim Zuordnen von Benutzern zu Routen die PSTN-Verwendungsdatensätze von oben nach unten vergleicht. Wenn der erste Datensatz mit der Anrufroute übereinstimmt, wird diese Route verwendet. Falls nicht, unterstützt die Ausgangsroutingfunktion den nächsten PSTN-Verwendungsdatensatz in der Liste und fährt damit fort, bis eine Übereinstimmung gefunden wird. Die nachfolgenden PSTN-Verwendungsdatensätze dienen der zusätzlichen Absicherung, wenn der erste Datensatz in der Liste nicht verfügbar ist. 
  
## <a name="pstn-usage-records"></a>PSTN-Verwendungseinträge

Die Planung von PSTN-Verwendungsdatensätzen besteht hauptsächlich darin, alle Anrufberechtigungen aufzulisten, die aktuell in Ihrer Organisation vorhanden sind, vom Firmenchef bis hin zu Personen mit befristeten Arbeitsverträgen, Beratern und Zeitarbeitern. Dieses Verfahren bietet außerdem die Gelegenheit, vorhandene Berechtigungen neu zu überprüfen und sie zu überarbeiten. Sie können PSTN-Verwendungsdatensätze ausschließlich für Berechtigungen erstellen, die sich auf Ihre vorgesehenen Enterprise-VoIP-Benutzer beziehen. Langfristig besteht eine bessere Lösung möglicherweise darin, PSTN-Verwendungsdatensätze einfach für alle Berechtigungen zu erstellen, und zwar unabhängig davon, ob einige davon derzeit nicht für die Gruppe der Benutzer gelten, für die Enterprise-VoIP aktiviert werden soll. Wenn Anrufberechtigungen geändert oder neue Benutzer mit abweichenden Abrufberechtigungen hinzugefügt werden, haben Sie die erforderlichen PSTN-Verwendungsdatensätze bereits erstellt.
  
Die folgende Tabelle stellt eine typische PSTN-Verwendungstabelle dar.
  
**PSTN-Verwendungsdatensätze**

|**Telefonattribut**|**Beschreibung**|
|:-----|:-----|
|Lokal  <br/> |Ortsgespräche  <br/> |
|Long-Distance  <br/> |Ferngespräche  <br/> |
|International  <br/> |Auslandsgespräche  <br/> |
|Delhi  <br/> |Vollzeitmitarbeiter in Delhi  <br/> |
|Redmond  <br/> |Vollzeitmitarbeiter in Redmond  <br/> |
|RedmondTemps  <br/> |Zeitarbeiter in Redmond  <br/> |
|Zürich  <br/> |Vollzeitmitarbeiter in Zürich  <br/> |
   
PSTN-Verwendungsdatensätze alleine führen keine Aktionen aus. Um sie verwenden zu können, müssen Sie sie mit Folgendem verknüpfen:
  
- VoIP-Richtlinien, die Benutzern zugewiesen sind
    
- Routen, die Rufnummern zugewiesen sind
    
## <a name="voice-routes"></a>VoIP-Routen

Anrufrouten geben an, wie Skype for Business Server ausgehende Anrufe verarbeitet, die von Enterprise-VoIP werden. Wenn ein Benutzer eine Nummer wählt, normalisiert der Front-End-Server die Wählzeichenfolge bei Bedarf in das E.164-Format und versucht, sie mit einem SIP-URI zu verbinden. Wenn keine Zuordnung möglich ist, wendet der Server eine auf der Nummer basierende Routinglogik für ausgehende Anrufe an. Der letzte Schritt zum Definieren der Logik besteht darin, eine separate benannte Anrufroute für jeden Satz von Zielrufnummern zu erstellen, die in den einzelne Wählplänen aufgeführt sind.
  
Vor dem Definieren von Routen für ausgehende Anrufe sollten Sie die folgenden Schritte abschließen:
  
- Stellen Sie einen oder mehrere Trunks bereit.
    
- Erstellen Sie nach Bedarf Wähleinstellungen für Standorte, Einzelpersonen und Kontaktobjekte.
    
- Erstellen Sie PSTN-Verwendungsdatensätze (Public Switched Telephone Network, Telefonfestnetz)
    
Sie müssen außerdem eine oder mehrere VoIP-Richtlinien erstellen und zuweisen, um das Routen ausgehender Anrufe zu aktivieren. Diese Aktion kann entweder vor oder nach der Definition ausgehender Anrufrouten durchgeführt werden.
  
Für jede Route müssen Sie Folgendes angeben:
  
- Einen Namen, mit dem die Route leicht identifiziert werden kann
    
- Eine optionale Beschreibung in Fällen, in denen der Name allein möglicherweise nicht als Beschreibung der Route ausreicht
    
- Den regulären Ausdruck für das Vergleichsmuster, das die Zielrufnummern identifiziert, auf welche die Route angewendet wird, sowie Ausnahmen, auf die das Vergleichsmuster nicht angewendet wird
    
- Einen oder mehrere Trunks, den Sie der Route zuweisen möchten
    
- Die PSTN-Verwendungsdatensätze, über die Benutzer verfügen müssen, um Rufnummern anzurufen, die dem regulären Ausdruck für die Zielrufnummer entsprechen
    
Sie können Anrufrouten in der Skype for Business Server-Systemsteuerung angeben. Diese Anrufrouten füllen die Serverroutingtabelle auf, die Skype for Business Server zum Weiterleiten von Anrufen verwendet, die für das PSTN bestimmt sind.
  
### <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Skype for Business Server bietet Flexibilität bei der Routenführung von Anrufen an das PSTN. Eine Voiceroute gibt eine Gruppe von Trunks zum PSTN an, die für einen bestimmten Sprachanruf verwendet werden können. Ein Trunk ordnet einem Vermittlungsserver und einer Portnummer ein PSTN-Gateway und eine Portnummer zu. Diese logische Zuordnung ermöglicht es einem Vermittlungsserver, mehreren Gateways zugeordnet zu werden und mehrere Verbindungen mit demselben Gateway zu haben. Beim Definieren einer Anrufroute geben Sie die trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver der Route zugeordnet sind. Verwenden Sie den Topologie-Generator, um Trunks zu erstellen, indem Sie die Beziehungen zwischen Vermittlungsservern und PSTN-Gateways, IP-Nebenstellenanlagen und SbCs (Session Border Controller) definieren.
  
### <a name="least-cost-routing"></a>Kostenoptimierter Verbindungsaufbau

Durch das Festlegen von Trunks, an die verschiedene Rufnummern weitergeleitet werden, können Sie die Routen bestimmen, die die geringsten Kosten verursachen, und sie entsprechend implementieren. Normalerweise wählen Sie Trunks aus, indem Sie den Trunk mit dem nächst gelegenen Gateway zum Standort der Zielrufnummer auswählen, um die Gebühren für Ferngespräche möglichst gering zu halten. Wenn Sie sich z. B. in New York befinden und eine Rufnummer in Rom wählen, leiten Sie den Anruf über das IP-Netzwerk an den Trunk mit dem Gateway in Ihrer Niederlassung in Rom weiter, sodass nur Gebühren für ein Ortsgespräch anfallen.
  
Das folgende Beispiel zeigt eine Verwendungsmöglichkeit des kostenoptimierten Verbindungsaufbaus: Fabrikam beschließt, dass deutsche Benutzer Rufnummern in den USA über den US-Trunk wählen sollen. Fabrikam möchte das System auch so konfigurieren, dass alle Anrufe von Skype for Business Server-Benutzern aus den USA nach Deutschland und angrenzenden Ländern/Regionen im Trunk mit dem Gateway in Deutschland beendet werden. Durch dieses Routing wird Geld gespart, da ein Anruf von Deutschland nach Österreich beispielsweise weniger kostspielig ist als ein Anruf aus den USA nach Österreich.
  
### <a name="translating-outbound-dial-strings"></a>Übersetzen ausgehender Wählzeichenfolgen

Skype for Business Server erfordert, dass alle Wählzeichenfolgen im E.164-Format normalisiert werden, um die Reverse Number Lookup (RNL) durchführen zu können. Für Trunks mit Gateways oder Nebenstellenanlagen (Private Branch Exchanges), für die Nummern in lokalen Wählformaten übersetzt werden müssen, können Sie mit Skype for Business Server eine oder mehrere Regeln erstellen, die beim Bearbeiten der angerufenen Nummer (d. h. Anforderungs-URI) vor dem Routing an den Trunk helfen. Sie können beispielsweise eine Regel schreiben, mit der das Präfix +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.
  
Mit Skype for Business Server können Sie eine oder mehrere Regeln erstellen, mit deren Hilfe die Telefonnummer vor dem Routing an den Trunk geändert werden kann.
  
Bei der Planung Ihrer Trunks, die Gateway:Port-Paaren Vermittlungsserver:Port-Paaren zuordnen, kann es hilfreich sein, Trunks mit ähnlichen lokalen Wählanforderungen zu gruppieren und daher die Anzahl der erforderlichen Übersetzungsregeln und die Zeit zu reduzieren, die zum Schreiben erforderlich ist.
  
### <a name="configuring-caller-id"></a>Konfigurieren der Anrufer-ID

Skype for Business Server bietet eine Möglichkeit, die Anrufer-ID für ausgehende Anrufe zu bearbeiten. Wenn eine Organisation beispielsweise die Direktwahlerweiterungen von Mitarbeitern maskieren und durch die generische Unternehmens- oder Abteilungsnummer ersetzen möchte, kann ein Administrator dies mithilfe der Skype for Business Server-Systemsteuerung tun, um die Anrufer-ID zu unterdrücken und durch eine angegebene alternative Anrufer-ID zu ersetzen. Berücksichtigen Sie bei der Planung Ihrer Routinglogik, für welche Personen, Gruppen und Standorte diese Option verwendet werden soll – vielleicht sogar für alle Mitarbeiter.
  
> [!NOTE]
> Für Anrufe, die über das Telefonfestnetz (PSTN) umgeleitet werden, wird die allgemeine Anrufer-ID anstelle der ursprünglichen Anrufer-ID angezeigt. Dies kann dazu führen, dass "Nicht stören"- oder Privatsphäreeinstellungen umgangen werden, die der angerufene Teilnehmer möglicherweise konfiguriert hat. 
  
### <a name="additional-routing-logic"></a>Zusätzliche Routinglogik

Beachten Sie bei der Erstellung von Routen für ausgehende Anrufe die folgenden Faktoren, die sich auf die Routinglogik auswirken können:
  
- Wenn ein Anruf über eine Verbundgrenze hinweg eingerichtet wird, wird der Anruf mithilfe der Domäne im URI an das Unternehmen weitergeleitet, das für die Anwendung der Ausgangsroutinglogik verantwortlich ist.
    
- Wenn die im Anforderungs-URI angegebene Domäne nicht für das Unternehmen unterstützt wird, verarbeitet die Ausgangsroutingkomponente auf dem Server den Anruf nicht.
    
- Wenn ein Benutzer nicht für die Enterprise-VoIP aktiviert ist, wendet der Server gegebenenfalls eine andere Routinglogik an.
    
- Wenn der Anruf an ein vollständig besetztes Gateway (bei dem alle Trunkleitungen belegt sind) geroutet wird, weist das Gateway den Anruf zurück, und die Ausgangsroutingkomponente leitet ihn an die Route mit den zweitgeringsten Kosten um. Bedenken Sie dies sorgfältig, da ein Gateway, dessen Größe auf ein kleines Büro in Europa (im Beispiel: Zürich) ausgerichtet ist, möglicherweise einen umfangreichen nicht lokalen Datenverkehr für Auslandsgespräche mit der Schweiz übertragen muss. Wenn das Gateway nicht die richtige Größe für diesen zusätzlichen Datenverkehr aufweist, werden Anrufe aus den USA in die Schweiz möglicherweise über ein Gateway in Deutschland weitergeleitet, was höhere Telefongebühren bedeutet.
