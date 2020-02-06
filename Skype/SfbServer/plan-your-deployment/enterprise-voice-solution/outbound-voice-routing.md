---
title: Planen des ausgehenden VoIP-Routings in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Erfahren Sie mehr über ausgehendes VoIP-Routing in Skype for Business Server Enterprise-VoIP, einschließlich Anrufweiterleitungseinstellungen, Wählpläne, Normalisierungsregeln, VoIP-Richtlinien, PSTN-Nutzungsdaten Sätzen und VoIP-Routen.
ms.openlocfilehash: 26bea8452db00657ae87b5acbdd3f986c637d6fe
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802575"
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server"></a>Planen des ausgehenden VoIP-Routings in Skype for Business Server
 
Erfahren Sie mehr über ausgehendes VoIP-Routing in Skype for Business Server Enterprise-VoIP, einschließlich Anrufweiterleitungseinstellungen, Wählpläne, Normalisierungsregeln, VoIP-Richtlinien, PSTN-Nutzungsdaten Sätzen und VoIP-Routen.
  
Das Routing für ausgehende Anrufe bezieht sich auf Enterprise-VoIP-Anrufe, die für ein öffentliches Switched Telephone Network (PSTN)-Gateway, trunk oder Private Branch Exchange (PBX) bestimmt sind. Wenn ein Skype for Business-Benutzer einen Anruf ablegt, normalisiert der Server die Telefonnummer bei Bedarf in das E. 164-Format und versucht, Sie mit einem SIP-URI zu vergleichen. Ermittelt der Server keine Übereinstimmung, wird die Routinglogik für ausgehende Anrufe basierend auf der bereitgestellten Wählzeichenfolge angewendet. Sie können diese Logik durch Konfigurieren der Servereinstellungen definieren, die in der folgenden Tabelle beschrieben sind.
  
**Skype for Business Server-Routing Einstellungen für ausgehende Anrufe**

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

Der Bereich eines Wählplans bestimmt die hierarchische Ebene, auf der die Wähleinstellungen angewendet werden können. In Skype for Business Server kann einem Benutzer ein bestimmter benutzerspezifischer Wählplan zugewiesen werden. Wenn kein Benutzer Wählplan zugewiesen ist, wird der Wählplan des Front-End-Pools angewendet. Wenn es keinen Wählplan für den Front-End-Pool gibt, wird der Standort Wähl Plan angewendet. Wenn für den Benutzer keine bestimmten Wählpläne gelten, wird der globale Wählplan angewendet.
  
Clients erhalten Wähl Plan-Bereichsebenen über in-Band-Bereitstellungseinstellungen, die bereitgestellt werden, wenn sich Benutzer bei Skype for Business anmelden. Als Administrator können Sie die Bereichsebenen für Wähleinstellungen mithilfe der Skype for Business Server-Systemsteuerung verwalten und zuweisen.
  
> [!NOTE]
> Der PSTN-Gateway-Wählplan auf Dienstebene wird auf eingehende Anrufe von einem bestimmten Gateway angewendet. 
  
Bereichsebenen für Wählpläne werden wie folgt definiert:
  
- **Benutzerwählplan**: Dieser Wählplan kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Sprachanwendungen können einen Wählplan pro Benutzer suchen und verwenden, wenn für „phone-context“ der Wert „user-default“ empfangen wird. Damit ein Wählplan zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
- **Poolwählplan**: Dieser Wählplan kann auf Dienstebene von jedem PSTN-Gateway oder jeder Registrierung in Ihrer Topologie erstellt werden. Zum Definieren eines Poolwählplans müssen Sie den Dienst (PSTN-Gateway oder Registrierungsstellenpool) angeben, auf den der Wählplan angewendet werden soll. 
    
- **Standortwählplan**: Dieser Wählplan kann für einen gesamten Standort erstellt werden – mit Ausnahme aller Benutzer, Gruppe oder Kontaktobjekte, denen ein Pool- oder Benutzerwählplan zugewiesen wurde. Zum Definieren eines Standortwählplans müssen Sie den Standort angeben, auf den der Wählplan angewendet werden soll.
    
- **Globaler Wählplan**: Dies ist der mit dem Produkt installierte Standardwählplan. Sie können den globalen Wählplan bearbeiten, aber nicht löschen. Diese Wähleinstellungen gelten für alle Enterprise-VoIP-Benutzer,-Gruppen und-Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen einen Wählplan mit einem spezifischeren Bereich zu.
    
### <a name="planning-for-dial-plans"></a>Planen eines Wählplans

Führen Sie folgende Schritte aus, um einen Wählplan zu planen:
  
- Listen Sie alle Standorte auf, an denen sich eine Niederlassung Ihrer Organisation befindet.
    
    Die Liste muss aktuell und vollständig sein. Sie muss immer wieder überprüft werden, wenn sich die Unternehmensorganisation weiterentwickelt. Bei einem großen internationalen Unternehmen mit zahlreichen kleinen Zweigstellen kann diese Aufgabe sehr zeitaufwendig sein.
    
- Identifizieren Sie gültige Rufnummernmuster für jeden Standort.
    
    Der zeitaufwendigste Teil der Planung von Wählplänen besteht darin, die gültigen Rufnummernmuster für jeden Standort zu identifizieren. In einigen Fällen können Sie möglicherweise Normalisierungsregeln, die Sie für einen Wählplan erstellt haben, in einen anderen Wählplan kopieren, insbesondere dann, wenn sich die zugehörigen Standorte auf demselben Kontinent oder sogar im selben Land bzw. in derselben Region befinden. In anderen Fällen genügt es möglicherweise, die Rufnummern in einem Wählplan geringfügig zu ändern, um sie auch in anderen Wählplänen verwenden zu können.
    
- Entwickeln Sie ein organisationsweites Schema für die Benennung von Wählplänen.
    
    Das Erstellen eines Standardbenennungsschemas stellt die Konsistenz innerhalb der gesamten Organisation sicher und vereinfacht Wartung und Updates.
    
- Entscheiden Sie, ob für einen einzelnen Standort mehrere Wählpläne erforderlich sind. 
    
    Wenn in Ihrer Organisation ein einzelner Wählplan an mehreren Standorten verwaltet wird, müssen Sie möglicherweise dennoch einen separaten Wählplan für Enterprise-VoIP-Benutzer erstellen, die von einer PBX-Anlage (Private Branch Exchange) migrieren und deren vorhandene Erweiterungen beibehalten werden müssen.
    
- Entscheiden Sie, ob Wählpläne auf Benutzerebene erforderlich sind. Wenn Sie beispielsweise über Benutzer an einer Zweigstelle verfügen, die bei der zentralen Website registriert sind, oder wenn Sie über Benutzer verfügen, die auf einer überlebensfähigen Branch-Appliance registriert sind, können Sie spezielle Wähl Szenarien für diese Benutzer unter Verwendung von Wählplänen und Normalisierungsregeln für einzelne Benutzer in Frage stellen. . Ausführliche Informationen finden Sie unter [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
    
- Ermitteln Sie den Bereich für den Wählplan (wie weiter oben in diesem Thema beschrieben).
    
Zum Erstellen eines Wählplans geben Sie bei Bedarf in den folgenden Feldern Werte an, indem Sie die Skype for Business Server-Systemsteuerung oder die Skype for Business Server-Verwaltungsshell verwenden.
  
#### <a name="name-and-simple-name"></a>Name und einfacher Name

Bei Benutzerwählplänen sollten Sie einen beschreibenden Namen für die Benutzer, Gruppen oder Kontaktobjekte angeben, denen der Wählplan zugewiesen wird. Für Standortwählpläne ist das Feld „Name“ bereits mit dem Namen des Standorts ausgefüllt und kann nicht geändert werden. Für Pool-Wählpläne ist das Feld "Name" bereits mit dem PSTN-Gateway oder dem Front-End-Pool (Fully Qualified Domain Name, FQDN) gefüllt und kann nicht geändert werden.
  
Der Wählplan Einfacher Name ist bereits mit einer vom Namen des Wählplans abgeleiteten Zeichenfolge aufgefüllt. Das Feld „Einfacher Name“ kann bearbeitet werden, sodass Sie eine aussagekräftigere Benennungskonvention für Ihre Wählpläne festlegen können. Der TheSimple-Name-Wert darf nicht leer sein und muss eindeutig sein. Es empfiehlt sich, ein Benennungsschema für Ihre gesamte Organisation zu entwickeln und dieses Schema konsequent für alle Standorte und Benutzer zu verwenden.
  
#### <a name="description"></a>Beschreibung

Es wird empfohlen, den allgemeinen, wiedererkennbaren Namen des geografischen Standorts einzugeben, auf den der entsprechende Wählplan angewendet wird. Wenn der Name des Wählplans beispielsweise „London.Contoso.com“ lautet, wird für die Beschreibung der Eintrag „London“ empfohlen. 
  
#### <a name="dial-in-conferencing-region"></a>Region für Einwahlkonferenzen

Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie eine Region angeben, um die Zugriffsnummern für Einwahlkonferenzen dem entsprechenden Wählplan zuzuordnen. 
  
#### <a name="external-access-prefix"></a>Vorwahl für externen Zugriff

Sie können ein externes Zugriffs Präfix mit bis zu vier Zeichen (#, \*und 0-9) angeben, wenn Benutzer eine oder mehrere zusätzliche führende Ziffern (beispielsweise 9) wählen müssen, um eine externe Leitung zu erhalten.
  
> [!NOTE]
> Wenn Sie eine Vorwahl für den externen Zugriff eingeben, müssen Sie keine zusätzliche Normalisierungsregeln zur Unterstützung der Vorwahl erstellen. 
  
### <a name="normalization-rules"></a>Normalisierungsregeln

Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort. Ein und dieselbe numerische Zeichenfolge wird möglicherweise unterschiedlich interpretiert und übersetzt, je nachdem, von welchem Standort aus sie gewählt wird. Normalisierungsregeln sind für das Anrufrouting notwendig, da Benutzer Rufnummern in unterschiedlichen Formaten in ihre Kontaktlisten eingeben.
  
Die Normalisierung der von Benutzern eingegebenen Rufnummern stellt ein konsistentes Format bereit, das folgende Aufgaben vereinfacht:
  
- Eine gewählte Nummer an den SIP-URI des beabsichtigten Empfängers anpassen.
    
- Anwenden von Wählautorisierungsregeln auf den Anrufer
    
In Normalisierungsregeln müssen möglicherweise die folgenden numerischen Felder berücksichtigt werden:
  
- Wählplan
    
- Landesvorwahl
    
- Ortsvorwahl
    
- Länge der Durchwahlnummer
    
- Standortvorwahl
    
#### <a name="creating-normalization-rules"></a>Erstellen von Normalisierungsregeln

Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um numerische Vergleichsmuster anzugeben, mit denen der Server zum Zweck der umgekehrten Nummernsuche Wählzeichenfolgen in das E.164-Format übersetzen kann. Sie können Normalisierungsregeln im Skype for Business Server Control Panel erstellen, indem Sie entweder die Ausdrücke manuell eingeben, oder indem Sie die Anfangsziffern und die Länge der zu enthaltenden Wählzeichenfolgen eingeben und die Skype for Business Server-Systemsteuerung Generieren Sie den entsprechenden regulären Ausdruck für Sie. Unabhängig davon, welche Methode Sie anwenden, können Sie anschließend eine Testnummer eingeben, um zu überprüfen, ob die Normalisierungsregel wie erwartet funktioniert.
  
Ausführliche Informationen zur Verwendung von .NET Framework-regulären Ausdrücken finden Sie unter ["reguläre .NET Framework-Ausdrücke"](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
#### <a name="sample-normalization-rules"></a>Beispiele für Normalisierungsregeln
<a name="BKMK_SampleNormalizationRules"> </a>

Die folgende Tabelle enthält Beispiele für Normalisierungsregeln, die als reguläre Ausdrücke von .NET Framework formuliert sind. Diese Regeln sind nur Beispiele und stellen keine verbindliche Referenz für die Erstellung Ihrer eigenen Normalisierungsregeln dar.
  
**Tabelle 1: Normalisierungsregeln mit regulären .NET Framework-Ausdrücken**

|**Regelname**|**Beschreibung**|**Nummernmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Übersetzt vierstellige Durchwahlnummern  <br/> |^ (\d{4}) $  <br/> |+1425555$1  <br/> |0100 wird in +14255550100 übersetzt.  <br/> |
|5digitExtension  <br/> |Übersetzt fünfstellige Durchwahlnummern  <br/> |^ 5 (\d{4}) $  <br/> |+1425555$1  <br/> |50100 wird in +14255550100 übersetzt.  <br/> |
|7digitcallingRedmond  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Redmond  <br/> |^ (\d{7}) $  <br/> |+1425$1  <br/> |5550100 wird in +14255550100 übersetzt  <br/> |
|7digitcallingDallas  <br/> |Übersetzt siebenstellige Rufnummern in Rufnummern des Ortsnetzes von Dallas  <br/> |^ (\d{7}) $  <br/> |+1972$1  <br/> |5550100 wird in +19725550100 übersetzt  <br/> |
|10digitcallingUS  <br/> |Übersetzt zehnstellige Rufnummern in US-Rufnummern  <br/> |^ (\d{10}) $  <br/> |+1$1  <br/> |2065550100 wird in +12065550100 übersetzt  <br/> |
|LDCallingUS  <br/> |Übersetzt Rufnummern mit Vorwahlen für Ferngespräche in US-Rufnummern  <br/> |^ 1 (\d{10}) $  <br/> |+$1  <br/> |12145550100 wird in +2145550100 übersetzt  <br/> |
|IntlCallingUS  <br/> |Übersetzt Rufnummern mit internationalen Vorwahlen in US-Rufnummern  <br/> |^ 011 (\d\*) $  <br/> |+$1  <br/> |01191445550100 wird in +91445550100 übersetzt  <br/> |
|RedmondOperator  <br/> |Übersetzt 0 in die Vorwahl des Netzbetreibers von Redmond  <br/> |^0$  <br/> |+14255550100  <br/> |0 wird in +14255550100 übersetzt.  <br/> |
|RedmondSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von Redmond (222)  <br/> |^ 6222 (\d{4}) $  <br/> |+1425555$1  <br/> |62220100 wird in +14255550100 übersetzt  <br/> |
|NYSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Vorwahl von New York (333)  <br/> |^ 6333 (\d{4}) $  <br/> |+1202555$1  <br/> |63330100 wird in +12025550100 übersetzt  <br/> |
|DallasSitePrefix  <br/> |Übersetzt Rufnummern mit netzinterner Vorwahl (6) und Dallas-Vorwahl (444)  <br/> |^ 6444 (\d{4}) $  <br/> |+1972555$1  <br/> |64440100 wird in +19725550100 übersetzt  <br/> |
   
Die folgende Tabelle veranschaulicht einen beispielhaften Wählplan für Redmond, Washington (USA), der auf den in der vorherigen Tabelle gezeigten Normalisierungsregeln basiert.
  
**Tabelle 2: Wählplan für Redmond, basierend auf den in Tabelle 1 gezeigten Normalisierungsregeln**

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

Skype for Business Server-VoIP-Richtlinien definieren für jeden Benutzer, jede Website oder jede Organisation, der die Richtlinie zugewiesen ist, die folgenden Punkte:
  
- Eine Reihe von Anruffeatures, die aktiviert oder deaktiviert werden können, um die für Benutzer verfügbare Enterprise-VoIP-Funktionalität zu ermitteln.
    
- Einer Gruppe von Telefonfestnetz-Verwendungseinträgen, die festlegen, welche Arten von Anrufen erlaubt sind. 
    
Mit den folgenden Schritten können Sie die VoIP-Richtlinien planen, die Sie für Ihre Enterprise-VoIP-Bereitstellung benötigen:
  
- Legen Sie fest, wie die globale VoIP-Richtlinie (die Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird) konfiguriert werden soll. Diese Richtlinie gilt für alle Enterprise-VoIP-Benutzer, denen nicht explizit eine Richtlinie auf Website-oder Benutzerebene zugewiesen ist.
    
- Bestimmen der ggf. erforderlichen VoIP-Richtlinien auf Standortebene.
    
- Bestimmen der ggf. erforderlichen benutzerbezogenen VoIP-Richtlinien.
    
- Entscheiden, welche Anruffunktionen für jede VoIP-Richtlinie aktiviert werden sollen.
    
- Bestimmen, welche PSTN-Verwendungseinträge für jede VoIP-Richtlinie konfiguriert werden sollen.
    
### <a name="voice-policy-scope"></a>Gültigkeitsbereich von VoIP-Richtlinien

Der Gültigkeitsbereich von VoIP-Richtlinien bestimmt die Hierarchieebene, auf der die Richtlinie gelten soll. In Skype for Business Server können Sie VoIP-Richtlinien mit den folgenden Bereichsebenen konfigurieren (von den spezifischsten zu den allgemeinsten aufgeführt).
  
- Die **VoIP-Benutzerrichtlinie** kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Dies ist die niedrigste Richtlinienebene. VoIP-Benutzerrichtlinien können bereitgestellt werden, um Funktionen nur für bestimmte Benutzer oder Gruppen an einem Standort zu aktivieren. Sie können damit z. B. bei bestimmten Mitarbeitern Ferngespräche deaktivieren. Damit eine VoIP-Richtlinie zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
    > [!NOTE]
    > Wir empfehlen, dass Sie eine Benutzer VoIP-Richtlinie für Branch Site Enterprise-VoIP-Benutzer bereitstellen, die bei der zentralen Website Bereitstellung registriert sind, oder für Benutzer, die auf einer Survivable Branch-Appliance registriert sind. 
  
- Eine **VoIP-Standortrichtlinie** gilt für einen gesamten Standort. Ausgenommen sind Benutzer, Gruppen oder Kontaktobjekte, denen eine Benutzerrichtlinie zugeordnet wurde. Zum Definieren einer VoIP-Standortrichtlinie müssen Sie den Standort angeben, für den die Richtlinie gelten soll. Wenn keine VoIP-Benutzerrichtlinie zugewiesen ist, wird die VoIP-Standortrichtlinie verwendet.
    
- Bei der **globalen VoIP-Richtlinie** handelt es sich um die Standard VoIP-Richtlinie, die mit dem Produkt installiert wird. Sie können die globale VoIP-Richtlinie bearbeiten, um die spezifischen Anforderungen Ihrer Organisation zu erfüllen, Sie können Sie jedoch nicht umbenennen oder löschen. Diese VoIP-Richtlinie gilt für alle Enterprise-VoIP-Benutzer, Gruppen und Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen eine VoIP-Richtlinie mit einem spezifischeren Bereich zu. Wenn Sie diese Richtlinie vollständig deaktivieren möchten, stellen Sie sicher, dass allen Websites und Benutzern benutzerdefinierte Richtlinien zugewiesen sind.
    
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
    
- Durch eine **böswillige Anrufprotokollierung** können Benutzer böswillige Anrufe über den Skype for Business-Client melden und diese dann in den Anruf Detaildatensätzen kennzeichnen. Diese ist standardmäßig deaktiviert.
    
- Mit der **Voicemail-Escape** -Funktion wird verhindert, dass Anrufe sofort an das Voicemailsystem des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert ist und das Telefon ausgeschaltet, außerhalb der Batterie oder außerhalb des gültigen Bereichs liegt und auf einem Timer-Wert basiert. Mit dieser Einstellung wird der Timer aktiviert und deaktiviert sowie der Wert des Timers eingestellt. Die Konfiguration kann nur über die Skype for Business Server-Verwaltungsshell erfolgen. Diese ist standardmäßig deaktiviert.
    
- **Anrufweiterleitung und gleichzeitiges anrufen PSTN-Nutzungen** ermöglicht es Administratoren, dieselbe PSTN-Nutzung wie die VoIP-Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln festzulegen, die Anrufweiterleitung und das gleichzeitige Klingeln auf interne Skype for Business-Benutzer zu beschränken oder eine benutzerdefinierte PSTN-Nutzung festzulegen, die sich von der PSTN-Nutzung der VoIP-Richtlinie Standardmäßig wird für Anrufweiterleitung und gleichzeitiges Klingeln die gleiche PSTN-Verwendung verwendet wie bei der VoIP-Richtlinie.
    
### <a name="pstn-usage-records"></a>PSTN-Verwendungseinträge

Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungseintrag zugeordnet sein. PSTN-Verwendungen können nur zum Zweck von Anrufweiterleitung und gleichzeitigem Klingeln einer VoIP-Richtlinie zugeordnet sein. 
  
> [!NOTE]
> Die Reihenfolge der PSTN-Verwendungseinträge ist wichtig, da die Ausgangsroutingfunktion beim Zuordnen von Benutzern zu Routen die PSTN-Verwendungseinträge von oben nach unten vergleicht. Wenn der erste Eintrag mit der Anrufroute übereinstimmt, wird diese Route verwendet. Falls nicht, unterstützt die Ausgangsroutingfunktion den nächsten PSTN-Verwendungseintrag in der Liste und fährt damit fort, bis eine Übereinstimmung gefunden wird. Die nachfolgenden PSTN-Verwendungseinträge dienen zur zusätzlichen Absicherung, wenn der erste Datensatz in der Liste nicht verfügbar ist. 
  
## <a name="pstn-usage-records"></a>PSTN-Verwendungseinträge

Die Planung von PSTN-Nutzungsdaten Sätzen besteht hauptsächlich darin, alle Anrufberechtigungen aufzulisten, die derzeit in Ihrer Organisation gelten, vom CEO bis hin zu Leiharbeitern, Beratern und Kontingenten Mitarbeitern. Dieser Prozess bietet auch die Möglichkeit, vorhandene Anrufberechtigungen erneut zu überprüfen und zu überarbeiten. Sie können PSTN-Verwendungsdaten Sätze nur für diese Anrufberechtigungen erstellen, die für Ihre erwarteten Enterprise-VoIP-Benutzer gelten, doch eine bessere Lösung für den langfristigen Bereich kann darin liegen, PSTN-Verwendungsdaten Sätze für alle Anrufberechtigungen zu erstellen, und zwar unabhängig davon, ob einige möglicherweise derzeit nicht wenden Sie sich an die Gruppe von Benutzern, die für Enterprise-VoIP aktiviert werden soll. Wenn sich die Anrufberechtigungen ändern oder neue Benutzer mit unterschiedlichen Anrufberechtigungen hinzugefügt werden, haben Sie bereits die erforderlichen PSTN-Nutzungsdatensätze erstellt.
  
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

Anrufrouten geben an, wie Skype for Business Server ausgehende Anrufe von Enterprise-VoIP-Benutzern abwickelt. Wenn ein Benutzer eine Nummer wählt, normalisiert der Front-End-Server die Wählzeichenfolge bei Bedarf in das E. 164-Format und versucht, Sie mit einem SIP-URI zu vergleichen. Wenn keine Zuordnung möglich ist, wendet der Server eine auf der Nummer basierende Routinglogik für ausgehende Anrufe an. Der letzte Schritt zum Definieren der Logik besteht darin, eine separate benannte Anrufroute für jeden Satz von Zielrufnummern zu erstellen, die in den einzelnen Wählplänen aufgeführt sind.
  
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
    
In der Skype for Business Server-Systemsteuerung können Sie Anrufrouten angeben. Diese Anrufrouten füllen die Server Routingtabelle aus, die von Skype for Business Server für die Weiterleitung von Anrufen verwendet wird, die für das PSTN bestimmt sind.
  
### <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Skype for Business Server bietet Flexibilität bei der Weiterleitung von Anrufen an das PSTN. Eine VoIP-Route gibt eine Reihe von Trunks für das PSTN an, die für einen bestimmten Sprachanruf verwendet werden können. Ein trunk ordnet einen Vermittlungs Server und eine Portnummer einem PSTN-Gateway und einer Abhör Portnummer zu. Diese logische Zuordnung ermöglicht es einem Vermittlungs Server, mehreren Gateways zugeordnet zu werden und über mehrere Verbindungen mit dem gleichen Gateway zu verfügen. Wenn Sie eine Anrufroute definieren, geben Sie die Trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver der Route zugeordnet sind. Wenn Sie Trunks erstellen möchten, indem Sie die Beziehungen zwischen Vermittlungsservern und PSTN-Gateways, IP-PBX-Anlagen und Session Border Controllers (SBCS) definieren, verwenden Sie den Topologie-Generator.
  
### <a name="least-cost-routing"></a>Kostenoptimierter Verbindungsaufbau

Durch das Festlegen von Trunks, an die verschiedene Rufnummern weitergeleitet werden, können Sie die Routen bestimmen, die die geringsten Kosten verursachen, und sie entsprechend implementieren. Normalerweise wählen Sie Trunks aus, indem Sie den Trunk mit dem nächstgelegenen Gateway zum Standort der Zielrufnummer auswählen, um die Gebühren für Ferngespräche möglichst gering zu halten. Wenn Sie sich z. B. in New York befinden und eine Rufnummer in Rom wählen, leiten Sie den Anruf über das IP-Netzwerk an den Trunk mit dem Gateway in Ihrer Niederlassung in Rom weiter, sodass nur Gebühren für ein Ortsgespräch anfallen.
  
Das folgende Beispiel zeigt eine Verwendungsmöglichkeit des kostenoptimierten Verbindungsaufbaus: Fabrikam beschließt, dass deutsche Benutzer Rufnummern in den USA über den US-Trunk wählen sollen. Fabrikam möchte das System auch so konfigurieren, dass alle Anrufe von US-Skype for Business Server-Benutzern nach Deutschland und benachbarte Länder/Regionen auf dem Stamm mit dem Gateway in Deutschland beendet werden. Durch dieses Routing wird Geld gespart, da ein Anruf von Deutschland nach Österreich beispielsweise weniger kostspielig ist als ein Anruf aus den USA nach Österreich.
  
### <a name="translating-outbound-dial-strings"></a>Übersetzen ausgehender Wählzeichenfolgen

Für Skype for Business Server müssen alle Wählzeichenfolgen im E. 164-Format normalisiert werden, um eine Reverse-Number-Lookup-Funktion (RNL) durchführen zu können. Für Trunks mit Gateways oder Private Branch Exchanges (PBX), die Zahlen erfordern, die in lokale Wähl Formate übersetzt werden, können Sie mit Skype for Business Server eine oder mehrere Regeln erstellen, die beim Manipulieren der angerufenen Nummer (also des Request-URIs) vor dem Routing helfen. in den Kofferraum. Sie können beispielsweise eine Regel schreiben, mit der die Vorwahl +44 aus einer Wählzeichenfolge entfernt und durch 0144 ersetzt wird.
  
Mit Skype for Business Server können Sie eine oder mehrere Regeln erstellen, die Ihnen helfen, die Rufnummer zu manipulieren, bevor Sie Sie an den trunk weiterleiten.
  
Bei der Planung Ihrer Trunks, die Gateway: Port-Paare mit Mediation Server verbinden: Port-Paare, kann es hilfreich sein, Trunks mit ähnlichen lokalen wählanforderungen zu gruppieren, und daher die Anzahl der erforderlichen Übersetzungsregeln und die Zeitdauer für den Schreibvorgang zu verringern.
  
### <a name="configuring-caller-id"></a>Konfigurieren der Anrufer-ID

Skype for Business Server bietet eine Möglichkeit, die Rufnummernanzeige für ausgehende Anrufe zu manipulieren. Wenn eine Organisation beispielsweise die Durchwahlnummern der Mitarbeiter maskieren und durch die generische Firmen-oder Abteilungsnummer ersetzen möchte, kann ein Administrator dies über die Skype for Business Server-Systemsteuerung tun, um die Rufnummernanzeige zu unterdrücken und zu ersetzen. mit einer angegebenen alternativen Rufnummernanzeige. Bei der Planung Ihrer Routinglogik sollten Sie Bedenken, für welche Einzelpersonen, Gruppen und Websites Sie diese Option benötigen – vielleicht sogar für alle Mitarbeiter.
  
> [!NOTE]
> Für Anrufe, die über das Telefonfestnetz (PSTN) umgeleitet werden, wird die allgemeine Anrufer-ID anstelle der ursprünglichen Anrufer-ID angezeigt. Dies kann dazu führen, dass „Nicht stören“- oder Privatsphäreneinstellungen umgangen werden, die der angerufene Teilnehmer möglicherweise konfiguriert hat. 
  
### <a name="additional-routing-logic"></a>Zusätzliche Routinglogik

Beachten Sie bei der Erstellung von Routen für ausgehende Anrufe die folgenden Faktoren, die sich auf die Routinglogik auswirken können:
  
- Wenn ein Anruf über eine Verbundgrenze hinweg eingerichtet wird, wird der Anruf mithilfe der Domäne im URI an das Unternehmen weitergeleitet, das für die Anwendung der Ausgangsroutinglogik verantwortlich ist.
    
- Wenn die im Anforderungs-URI angegebene Domäne nicht für das Unternehmen unterstützt wird, verarbeitet die Ausgangsroutingkomponente auf dem Server den Anruf nicht.
    
- Wenn ein Benutzer nicht für Enterprise-VoIP aktiviert ist, wendet der Server gegebenenfalls eine andere Routinglogik an.
    
- Wenn der Anruf an ein vollständig besetztes Gateway (bei dem alle Trunkleitungen belegt sind) geroutet wird, weist das Gateway den Anruf zurück und die Ausgangsroutingkomponente leitet ihn an die Route mit den zweitgeringsten Kosten um. Bedenken Sie dies sorgfältig, da ein Gateway, dessen Größe auf ein kleines Büro in Europa (im Beispiel: Zürich) ausgerichtet ist, möglicherweise einen umfangreichen nicht lokalen Datenverkehr für Auslandsgespräche mit der Schweiz übertragen muss. Wenn das Gateway nicht die richtige Größe für diesen zusätzlichen Datenverkehr aufweist, werden Anrufe aus den USA in die Schweiz möglicherweise über ein Gateway in Deutschland weitergeleitet, was höhere Telefongebühren bedeutet.
    

