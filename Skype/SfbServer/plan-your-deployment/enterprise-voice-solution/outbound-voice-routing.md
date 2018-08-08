---
title: Planen der ausgehende VoIP-routing in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Erfahren Sie mehr über ausgehende VoIP-routing in Skype für Business Server Enterprise-VoIP, einschließlich Aufruf für Routen, Wählpläne, Normalisierungsregeln, VoIP-Richtlinien, PSTN-verwendungsdatensätzen, und VoIP-Routen.
ms.openlocfilehash: 1f399ff44eafdc1fc61fb5bab41b0d8949127e62
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21029189"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planen der ausgehende VoIP-routing in Skype für Business Server
 
Erfahren Sie mehr über ausgehende VoIP-routing in Skype für Business Server Enterprise-VoIP, einschließlich Aufruf für Routen, Wählpläne, Normalisierungsregeln, VoIP-Richtlinien, PSTN-verwendungsdatensätzen, und VoIP-Routen.
  
Routing ausgehender Anrufe gilt für Enterprise-VoIP-Anrufe, die für ein Gateway public switched Telephone Network (Telefonfestnetz PSTN), Trunk oder private Branch Exchange, (Nebenstellenanlage PBX) bestimmt sind. Wenn eine Skype für Business Benutzer einen Anruf tätigt, wird der Server normalisiert die Telefonnummer in das e. 164-Format, falls erforderlich und versucht, es zu einem SIP-URI zuzuordnen. Ermittelt der Server keine Übereinstimmung, wird die Routinglogik für ausgehende Anrufe basierend auf der bereitgestellten Wählzeichenfolge angewendet. Sie können diese Logik durch Konfigurieren der Servereinstellungen definieren, die in der folgenden Tabelle beschrieben sind.
  
**Skype für Business Server ausgehenden Anrufen Routingeinstellungen**

|**Objekt**|**Beschreibung**|
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

Ein Wählplan Bereich bestimmt die Hierarchieebene, an der die Wähleinstellungen angewendet werden kann. In Skype für Business Server kann ein Benutzer einen bestimmten benutzerspezifischen Wählplan zugewiesen werden. Wenn ein benutzerwählplan nicht zugewiesen ist, wird der Front-End-Pool-Wählplan angewendet. Ist kein Front-End-Pool-Pool-Wählplan, wird die Website Wähleinstellungen angewendet. Wenn für den Benutzer keine bestimmten Wählpläne gelten, wird der globale Wählplan angewendet.
  
Clients erhalten Bereichsebenen über in-Band-bereitstellungseinstellungen, die bereitgestellt werden, wenn Benutzer Skype für Unternehmen anmelden. Als Administrator können Sie verwalten und Zuweisen von Bereichsebenen mithilfe von Skype Business Server-Systemsteuerung.
  
> [!NOTE]
> Der PSTN-Gateway-Wählplan auf Dienstebene wird auf eingehende Anrufe von einem bestimmten Gateway angewendet. 
  
Bereichsebenen für Wählpläne werden wie folgt definiert:
  
- **Benutzerwählplan**: Dieser Wählplan kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Sprachanwendungen können einen Wählplan pro Benutzer suchen und verwenden, wenn für „phone-context“ der Wert „user-default“ empfangen wird. Damit ein Wählplan zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
- **Poolwählplan**: Dieser Wählplan kann auf Dienstebene von jedem PSTN-Gateway oder jeder Registrierung in Ihrer Topologie erstellt werden. Zum Definieren eines Poolwählplans müssen Sie den Dienst (PSTN-Gateway oder Registrierungsstellenpool) angeben, auf den der Wählplan angewendet werden soll. 
    
- **Standortwählplan**: Dieser Wählplan kann für einen gesamten Standort erstellt werden – mit Ausnahme aller Benutzer, Gruppe oder Kontaktobjekte, denen ein Pool- oder Benutzerwählplan zugewiesen wurde. Zum Definieren eines Standortwählplans müssen Sie den Standort angeben, auf den der Wählplan angewendet werden soll.
    
- **Globaler Wählplan**: Dies ist der mit dem Produkt installierte Standardwählplan. Sie können den globalen Wählplan bearbeiten, aber nicht löschen. Dieser Wählplan gilt für alle Enterprise-VoIP-Benutzer, Gruppen und Contact-Objekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und ein Wählplans mit einem spezifischen Bereich zuweisen.
    
### <a name="planning-for-dial-plans"></a>Planen eines Wählplans

Führen Sie folgende Schritte aus, um einen Wählplan zu planen:
  
- Listen Sie alle Standorte auf, an denen sich eine Niederlassung Ihrer Organisation befindet.
    
    Die Liste muss aktuell und vollständig sein. Sie muss immer wieder überprüft werden, wenn sich die Unternehmensorganisation weiterentwickelt. Bei einem großen internationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann diese Aufgabe sehr zeitaufwendig sein.
    
- Identifizieren Sie gültige Rufnummernmuster für jeden Standort.
    
    Der zeitaufwendigste Teil der Planung von Wählplänen besteht darin, die gültigen Rufnummernmuster für jeden Standort zu identifizieren. In einigen Fällen können Sie möglicherweise Normalisierungsregeln, die Sie für einen Wählplan erstellt haben, in einen anderen Wählplan kopieren, insbesondere dann, wenn sich die zugehörigen Standorte auf demselben Kontinent oder sogar im selben Land bzw. in derselben Region befinden. In anderen Fällen genügt es möglicherweise, die Rufnummern in einem Wählplan geringfügig zu ändern, um sie auch in anderen Wählplänen verwenden zu können.
    
- Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.
    
    Das Erstellen eines Standardbenennungsschemas stellt die Konsistenz innerhalb der gesamten Organisation sicher und vereinfacht Wartung und Updates.
    
- Entscheiden Sie, ob für einen einzelnen Standort mehrere Wählpläne erforderlich sind. 
    
    Wenn Ihre Organisation einen einzigen Wählplan für mehrere Standorte verwaltet werden, müssen Sie zum Erstellen von separaten Wähleinstellungen für Enterprise-VoIP-Benutzer migrieren, die aus einer private Branch Exchange, (Nebenstellenanlage PBX) und ihren vorhandenen Erweiterungen beibehalten vorhanden sein muss.
    
- Entscheiden Sie, ob Wählpläne auf Benutzerebene erforderlich sind. Beispielsweise gewählt, wenn Sie Benutzer an einem Zweigstellenstandort, die mit einem zentralen Standort registriert sind oder wenn Sie Benutzer, die auf einer Survivable Branch Appliance registriert sind, können Sie spezielle berücksichtigen Wählvorgang Szenarien für solche Benutzer pro Benutzer mit Pläne und Normalisierungsregeln . Weitere Informationen hierzu finden Sie unter [Planen für Enterprise Voice Resiliency in Skype für Business Server](enterprise-voice-resiliency.md).
    
- Ermitteln Sie den Bereich für den Wählplan (wie weiter oben in diesem Thema beschrieben).
    
Um einen Wählplan zu erstellen, geben Sie Werte in den folgenden Feldern, je nach Bedarf mithilfe von Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell.
  
#### <a name="name-and-simple-name"></a>Name und einfacher Name

Bei Benutzerwählplänen sollten Sie einen beschreibenden Namen für die Benutzer, Gruppen oder Kontaktobjekte angeben, denen der Wählplan zugewiesen wird. Für Standortwählpläne ist das Feld „Name“ bereits mit dem Namen des Standorts ausgefüllt und kann nicht geändert werden. Pool-Wählpläne, im Feld Name wird automatisch gefüllt, mit dem PSTN-Gateway oder Front-End-Pool vollständig qualifizierten Domänennamen (FQDN) und kann nicht geändert werden.
  
Der Wählplan Einfacher Name ist bereits mit einer vom Namen des Wählplans abgeleiteten Zeichenfolge aufgefüllt. Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. TheSimple Name-Wert darf nicht leer und muss eindeutig sein. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.
  
#### <a name="description"></a>Beschreibung

Es wird empfohlen, den allgemeinen, wiedererkennbaren Namen des geografischen Standorts einzugeben, auf den der entsprechende Wählplan angewendet wird. Wenn der Name des Wählplans beispielsweise „London.Contoso.com“ lautet, wird für die Beschreibung der Eintrag „London“ empfohlen. 
  
#### <a name="dial-in-conferencing-region"></a>Region für Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie eine Region angeben, um die Zugriffsnummern für Einwahlkonferenzen dem entsprechenden Wählplan zuzuordnen. 
  
#### <a name="external-access-prefix"></a>Vorwahl für externen Zugriff

Sie können angeben, dass eine externe zugriffsvorwahl von bis zu vier Zeichen (#, \*, und 0-9) Wenn Benutzer auf einen oder mehrere zusätzliche führende Ziffern (z. B. 9), um eine externe Zeile können einwählen müssen.
  
> [!NOTE]
> Wenn Sie eine Vorwahl für den externen Zugriff eingeben, müssen Sie keine zusätzliche Normalisierungsregeln zur Unterstützung der Vorwahl erstellen. 
  
### <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort. Ein und dieselbe numerische Zeichenfolge wird möglicherweise unterschiedlich interpretiert und übersetzt, je nachdem, von welchem Standort aus sie gewählt wird. Normalisierungsregeln sind für das Anrufrouting notwendig, da Benutzer Rufnummern in unterschiedlichen Formaten in ihre Kontaktlisten eingeben.
  
Die Normalisierung der von Benutzern eingegebenen Rufnummern stellt ein konsistentes Format bereit, das folgende Aufgaben vereinfacht:
  
- Zuordnen einer gewählten Rufnummer zum SIP-URI des gewünschten Empfängers an.
    
- Anwenden von Wählautorisierungsregeln auf den Anrufer
    
In Normalisierungsregeln müssen möglicherweise die folgenden numerischen Felder berücksichtigt werden:
  
- Wählplan
    
- Landesvorwahl
    
- Ortsvorwahl
    
- Länge der Durchwahlnummer
    
- Standortvorwahl
    
#### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. Sie erstellen Normalisierungsregeln im der Skype Business Server-Systemsteuerung, indem Sie die Ausdrücke manuell eingeben oder durch Eingabe von Ziffern und der Eingabelänge Wählzeichenfolgen zu vergleichende starten und Navigate die Skype Business Server-Systemsteuerung den entsprechenden regulären Ausdruck für Sie zu generieren. Unabhängig davon, welche Methode Sie anwenden, können Sie anschließend eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.
  
Weitere Informationen zur Verwendung von regulärer .NET Framework-Ausdrücken finden Sie unter ["reguläre Ausdrücke von .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
#### <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln
<a name="BKMK_SampleNormalizationRules"> </a>

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre Ausdrücke von .NET Framework formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer eigenen Normalisierungsregeln dar.
  
**Tabelle 1: Normalisierungsregeln mit regulären .NET Framework-Ausdrücken**

|**Regelname**|**Beschreibung**|**Nummernmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Übersetzt vierstellige Durchwahlnummern  <br/> |^(\d{4})$  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt.  <br/> |
|5stellendurchwahl).  <br/> |Übersetzt fünfstellige Durchwahlnummern  <br/> |^ 5(\d{4})$  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt.  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond  <br/> |^(\d{7})$  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt  <br/> |
|7digitcallingDallas  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Dallas  <br/> |^(\d{7})$  <br/> |+1972$1  <br/> |5550100 wird in +19725550100 übersetzt  <br/> |
|10digitcallingUS  <br/> |Übersetzt zehnstellige Rufnummern in US-Rufnummern  <br/> |^(\d{10})$  <br/> |+1$1  <br/> |2065550100 wird in +12065550100 übersetzt  <br/> |
|LDCallingUS  <br/> |Übersetzt Rufnummern mit Vorwahlen für Ferngespräche in US-Rufnummern  <br/> |^ 1(\d{10})$  <br/> |+$1  <br/> |12145550100 wird in +2145550100 übersetzt  <br/> |
|IntlCallingUS  <br/> |Übersetzt Rufnummern mit internationalen Vorwahlen in US-Rufnummern  <br/> |^ 011(\d\*)$  <br/> |+$1  <br/> |01191445550100 wird in +91445550100 übersetzt  <br/> |
|RedmondOperator  <br/> |Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt.  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222)  <br/> |^ 6222(\d{4})$  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt  <br/> |
|NYSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von New York (333)  <br/> |^ 6333(\d{4})$  <br/> |+1202555$1  <br/> |63330100 wird in +12025550100 übersetzt  <br/> |
|DallasSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Dallas-Vorwahl (444)  <br/> |^ 6444(\d{4})$  <br/> |+1972555$1  <br/> |64440100 wird in +19725550100 übersetzt  <br/> |
   
Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert.
  
**Tabelle 2: Wählplan für Redmond, basierend auf den in Tabelle 1 gezeigten Normalisierungsregeln**

|**Redmond.forestFQDN**|
|:-----|
|5stellendurchwahl).  <br/> |
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

Skype für Business Server VoIP-Richtlinien definieren die folgenden für jeden Benutzer, eine Website oder eine Organisation, die die Richtlinie zugewiesen wird:
  
- Eine Gruppe von Anruffunktionen, die aktiviert oder deaktiviert, um die Enterprise-VoIP-Funktionen für Benutzer verfügbar bestimmen werden können.
    
- Einer Gruppe von Telefonfestnetz-Verwendungseinträgen, die festlegen, welche Arten von Anrufen erlaubt sind. 
    
Die folgenden Schritte helfen Ihnen beim Planen der VoIP-Richtlinien, die Sie für Ihre Bereitstellung von Enterprise-VoIP müssen:
  
- Legen Sie fest, wie die globale VoIP-Richtlinie (die Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird) konfiguriert werden soll. Diese Richtlinie gilt für alle Enterprise-VoIP-Benutzer, die nicht explizit eine Richtlinie auf Standort- oder Benutzerebene zugewiesen sind.
    
- Bestimmen der ggf. erforderlichen VoIP-Richtlinien auf Standortebene.
    
- Bestimmen der ggf. erforderlichen benutzerbezogenen VoIP-Richtlinien.
    
- Entscheiden, welche Anruffunktionen für jede VoIP-Richtlinie aktiviert werden sollen.
    
- Bestimmen, welche PSTN-Verwendungseinträge für jede VoIP-Richtlinie konfiguriert werden sollen.
    
### <a name="voice-policy-scope"></a>Gültigkeitsbereich von VoIP-Richtlinien

Der Gültigkeitsbereich von VoIP-Richtlinien bestimmt die Hierarchieebene, auf der die Richtlinie gelten soll. In Skype für Business Server, konfigurieren Sie VoIP-Richtlinien mit den folgenden Ebenen für den Bereich (aufgeführt, die von der genauesten bis hin zu den allgemeinen).
  
- Die **VoIP-Benutzerrichtlinie** kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Dies ist die niedrigste Richtlinienebene. VoIP-Benutzerrichtlinien können bereitgestellt werden, um Funktionen nur für bestimmte Benutzer oder Gruppen an einem Standort zu aktivieren. Sie können damit z. B. bei bestimmten Mitarbeitern Ferngespräche deaktivieren. Damit eine VoIP-Richtlinie zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
    > [!NOTE]
    > Es wird empfohlen, dass Sie bereitstellen eine VoIP-Benutzerrichtlinie für Enterprise-VoIP Zweigstellenbenutzer, die mit der Bereitstellung der zentralen Standort registriert sind, oder Benutzer, die auf einer Survivable Branch Appliance registriert sind. 
  
- Eine **VoIP-Standortrichtlinie** gilt für einen gesamten Standort. Ausgenommen sind Benutzer, Gruppen oder Kontaktobjekte, denen eine Benutzerrichtlinie zugeordnet wurde. Zum Definieren einer VoIP-Standortrichtlinie müssen Sie den Standort angeben, für den die Richtlinie gelten soll. Wenn keine VoIP-Benutzerrichtlinie zugewiesen ist, wird die VoIP-Standortrichtlinie verwendet.
    
- **Global VoIP-Richtlinie** ist der Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird. Sie können die globale VoIP-Richtlinie, um den spezifischen Bedürfnissen des Unternehmens gerecht bearbeiten, aber Sie können nicht umbenennen oder löschen Sie ihn. Diese VoIP-Richtlinie gilt für alle Enterprise-VoIP-Benutzer, Gruppen und Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und eine VoIP-Richtlinie mit spezifischeren Bereich zuweisen. Wenn Sie diese Richtlinie vollständig deaktivieren möchten, müssen Sie unbedingt, dass alle Standorte und Benutzer benutzerdefinierte Richtlinien zugewiesen haben.
    
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
    
- **Böswilligen aufrufen Tracing** ermöglicht es Benutzern, Melden von missbräuchlichen anrufen mithilfe der Skype für Business-Client, und klicken Sie dann Kennzeichen solcher Anrufe in die kommunikationsdatensätze. Diese Option ist standardmäßig deaktiviert.
    
- **Voicemail Escape** verhindert, dass Anrufe von wird unmittelbar auf dem System des Benutzers Mobiltelefon Voicemail weitergeleitet, wenn Gleichzeitiges Klingeln konfiguriert ist und das Telefon ist deaktiviert, nicht genügend Batterie oder außerhalb des gültigen Bereichs aktiviert, und basiert auf einen Wert Timer. Mit dieser Einstellung wird der Timer aktiviert und deaktiviert sowie der Wert des Timers eingestellt. Es kann nur mithilfe der Skype für Business Server-Verwaltungsshell konfiguriert werden. Diese Option ist standardmäßig deaktiviert.
    
- **Rufen Sie die anrufweiterleitung und gleichzeitige Klingeln PSTN-Verwendungen** können Administratoren die gleiche PSTN-Verwendung angeben, wie die VoIP-Richtlinie für die anrufweiterleitung und Gleichzeitiges Klingeln zu beschränken, die anrufweiterleitung und Gleichzeitiges Klingeln zu internen Skype für Geschäftsbenutzer nur, oder geben Sie eine benutzerdefinierte PSTN-Verwendung, die vom PSTN-Verwendung für die VoIP-Richtlinie unterscheidet. Standardmäßig wird für Anrufweiterleitung und gleichzeitiges Klingeln die gleiche PSTN-Verwendung verwendet wie bei der VoIP-Richtlinie.
    
### <a name="pstn-usage-records"></a>PSTN-Verwendungseinträge

Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungseintrag zugeordnet sein. PSTN-Verwendungen können nur zum Zweck von Anrufweiterleitung und gleichzeitigem Klingeln einer VoIP-Richtlinie zugeordnet sein. 
  
> [!NOTE]
> Die Reihenfolge der PSTN-Verwendungseinträge ist wichtig, da die Ausgangsroutingfunktion beim Zuordnen von Benutzern zu Routen die PSTN-Verwendungseinträge von oben nach unten vergleicht. Wenn der erste Eintrag mit der Anrufroute übereinstimmt, wird diese Route verwendet. Falls nicht, unterstützt die Ausgangsroutingfunktion den nächsten PSTN-Verwendungseintrag in der Liste und fährt damit fort, bis eine Übereinstimmung gefunden wird. Die nachfolgenden PSTN-Verwendungseinträge dienen zur zusätzlichen Absicherung, wenn der erste Datensatz in der Liste nicht verfügbar ist. 
  
## <a name="pstn-usage-records"></a>PSTN-Verwendungseinträge

Planen der PSTN-verwendungsdatensätzen besteht aus hauptsächlich die Anrufberechtigungen, die derzeit in Ihrer Organisation, die CEO temporäre Mitarbeiter, Berater und Zeitarbeiter geltenden sind aufgelistet. Dieses Verfahren bietet außerdem die Gelegenheit, vorhandene Anrufberechtigungen Gelegenheit und überarbeiten. Sie können PSTN-Verwendungseinträge für die Anrufberechtigungen, die für die erwarteten Enterprise-VoIP-Benutzer gelten nur erstellen, aber möglicherweise eine bessere langfristige Lösung zum Erstellen von PSTN-Verwendungseinträge für alle Anrufberechtigungen, unabhängig davon, ob einige derzeit nicht kann gelten Sie für die Gruppe von Benutzern für Enterprise Voice aktiviert werden soll. Wenn der Aufruf die Berechtigungen ändern oder neue Benutzer mit unterschiedlichen Anrufberechtigungen werden hinzugefügt, Sie haben bereits erstellt die erforderlichen PSTN-verwendungsdatensätzen.
  
Im Folgenden sehen Sie eine typische PSTN-Verwendungstabelle.
  
**PSTN-Verwendungseinträge**

|**Telefonattribut**|**Beschreibung**|
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

Anrufrouten wird angegeben, wie von Enterprise-VoIP-Benutzern getätigte ausgehende Anrufe von Skype für Business Server behandelt. Wenn ein Benutzer eine Rufnummer wählt, der Front-End-Server normalisiert die DFÜ-Zeichenfolge in das e. 164-Format bei Bedarf und versucht, einen SIP-URI zugeordnet. Wenn keine Zuordnung möglich ist, wendet der Server eine auf der Nummer basierende Routinglogik für ausgehende Anrufe an. Der letzte Schritt zum Definieren der Logik besteht darin, eine separate benannte Anrufroute für jeden Satz von Zielrufnummern zu erstellen, die in den einzelnen Wählplänen aufgeführt sind.
  
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
    
Sie können anrufrouten in die Skype Business Server-Systemsteuerung angeben. Diese Anruf Routen aufgefüllt, die Server Routingtabelle Skype für Business Server für das Anrufrouting verwendet, die für das PSTN gerichtet sind.
  
### <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Skype für Business Server bietet Flexibilität in wie Anrufe an das Telefonfestnetz weitergeleitet werden. Eine VoIP-Route gibt eine Reihe von Trunks an das Telefonfestnetz, die für einen bestimmten Anruf verwendet werden kann. Ein Trunk ordnet einen Vermittlungsserver und eine Portnummer ein PSTN-Gateway und listening Portnummer ein. Diese logische Zuordnung ermöglicht einen Vermittlungsserver haben mehrere Verbindungen mit dem gleichen Gateway und mehrere Gateways zugeordnet werden. Beim Definieren einer Route für Anrufe, geben Sie den Trunks dieser Route zugeordnet, aber keine angeben die Vermittlungsserver der Route zugeordnet sind. Verwenden Sie den Topologie-Generator, um Trunks definieren die Beziehungen zwischen Vermittlungsserver und PSTN-Gateways, IP-PBXs und Session Border Controller (SBCs) erstellen.
  
### <a name="least-cost-routing"></a>Kostenoptimierter Verbindungsaufbau

Durch das Festlegen von Trunks, an die verschiedene Rufnummern weitergeleitet werden, können Sie die Routen bestimmen, die die geringsten Kosten verursachen, und sie entsprechend implementieren. Normalerweise wählen Sie Trunks aus, indem Sie den Trunk mit dem nächstgelegenen Gateway zum Standort der Zielrufnummer auswählen, um die Gebühren für Ferngespräche möglichst gering zu halten. Wenn Sie sich z. B. in New York befinden und eine Rufnummer in Rom wählen, leiten Sie den Anruf über das IP-Netzwerk an den Trunk mit dem Gateway in Ihrer Niederlassung in Rom weiter, sodass nur Gebühren für ein Ortsgespräch anfallen.
  
Das folgende Beispiel zeigt eine Verwendungsmöglichkeit des kostenoptimierten Verbindungsaufbaus: Fabrikam beschließt, dass deutsche Benutzer Rufnummern in den USA über den US-Trunk wählen sollen. Fabrikam möchte auch das System so konfigurieren, dass alle Anrufe von US Skype für Business Server-Benutzer an Deutschland und angrenzenden Ländern/Regionen auf den Trunk mit dem Gateway in Deutschland beenden. Durch dieses Routing wird Geld gespart, da ein Anruf von Deutschland nach Österreich beispielsweise weniger kostspielig ist als ein Anruf aus den USA nach Österreich.
  
### <a name="translating-outbound-dial-strings"></a>Übersetzen ausgehender Wählzeichenfolgen

Skype für Business Server erfordert, dass alle Wählzeichenfolgen in das e. 164-Format für die inverssuche (RNL) normalisiert werden. Für Trunks mit Gateways oder private Nebenstellenanlagen (PBX), die Zahlen in den lokalen Wählvorgang übersetzt werden müssen, kann Skype für Business Server Sie erstellen eine oder mehrere Regeln, mit denen die gewählte Nummer (d. h. Anforderungs-URI) Änderung vor der Weiterleitung um den Trunk. Sie können beispielsweise eine Regel schreiben, mit der die Vorwahl +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.
  
Mit Skype für Business Server ist es möglich, eine oder mehrere Regeln, mit denen in der Änderung der Rufnummer vor der Weiterleitung an den Trunk zu erstellen.
  
Bei der Planung Ihrer Trunks, den Gateway: Port-Paare Mediation Server: Port-Paare zuzuordnen, es kann hilfreich sein, Gruppe Trunks mit ähnlichen lokalen Anforderungen einwählen und daher reduzieren Sie die Anzahl der erforderlichen Übersetzungsregeln und die Zeit, die benötigt wird, um sie zu schreiben.
  
### <a name="configuring-caller-id"></a>Konfigurieren der Anrufer-ID

Skype für Business Server bietet die Möglichkeit zum Bearbeiten von Anrufer-ID für ausgehende Anrufe. Angenommen, wenn eine Organisation möchte maskieren Mitarbeiter Wählen bei Bedarf-Erweiterungen, und Ersetzen Sie sie mit der generischen im Unternehmen oder die Abteilung Nummer, Möglichkeiten ein Administrator, die mithilfe von Skype Business Server-Systemsteuerung zum Unterdrücken der Anrufer-ID, und Ersetzen Sie ihn mit einer angegebenen alternative Anrufer-ID Berücksichtigen Sie bei der Planung Ihrer Routinglogik an, welche Personen, Gruppen, Sie diese Option für sollten, Websites – vielleicht, sogar, für alle Mitarbeiter.
  
> [!NOTE]
> Für Anrufe, die über das Telefonfestnetz (PSTN) umgeleitet werden, wird die allgemeine Anrufer-ID anstelle der ursprünglichen Anrufer-ID angezeigt. Dies kann dazu führen, dass „Nicht stören“- oder Privatsphäreneinstellungen umgangen werden, die der angerufene Teilnehmer möglicherweise konfiguriert hat. 
  
### <a name="additional-routing-logic"></a>Zusätzliche Routinglogik

Beachten Sie bei der Erstellung von Routen für ausgehende Anrufe die folgenden Faktoren, die sich auf die Routinglogik auswirken können:
  
- Wenn ein Anruf über eine Verbundgrenze hinweg eingerichtet wird, wird der Anruf mithilfe der Domäne im URI an das Unternehmen weitergeleitet, das für die Anwendung der Ausgangsroutinglogik verantwortlich ist.
    
- Wenn die im Anforderungs-URI angegebene Domäne nicht für das Unternehmen unterstützt wird, verarbeitet die Ausgangsroutingkomponente auf dem Server den Anruf nicht.
    
- Wenn ein Benutzer für Enterprise-VoIP nicht aktiviert ist, wendet der Server eine andere, geeignete Routinglogik an.
    
- Wenn der Anruf an ein vollständig besetztes Gateway (bei dem alle Trunkleitungen belegt sind) geroutet wird, weist das Gateway den Anruf zurück und die Ausgangsroutingkomponente leitet ihn an die Route mit den zweitgeringsten Kosten um. Bedenken Sie dies sorgfältig, da ein Gateway, dessen Größe auf ein kleines Büro in Europa (im Beispiel: Zürich) ausgerichtet ist, möglicherweise einen umfangreichen nicht lokalen Datenverkehr für Auslandsgespräche mit der Schweiz übertragen muss. Wenn das Gateway nicht die richtige Größe für diesen zusätzlichen Datenverkehr aufweist, werden Anrufe aus den USA in die Schweiz möglicherweise über ein Gateway in Deutschland weitergeleitet, was höhere Telefongebühren bedeutet.
    

