---
title: Planen und Verwalten von Notrufen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Erfahren Sie mehr über Notrufe, einschließlich Informationen zu Notfalladressen, Notrufweiterleitung und dynamischen Notrufen.
ms.openlocfilehash: 2118bfd3f380ac5e5e2773f1f4ccdc703332893a
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606564"
---
# <a name="manage-emergency-calling"></a>Verwalten von Notrufen

In diesem Artikel werden Konzepte beschrieben, die Sie kennen müssen, um Notrufe&mdash;zu verwalten, einschließlich Informationen zu Notfalladressen, dynamischen Notfalladressen und Notrufweiterleitung. In diesem Artikel wird die folgende Terminologie verwendet:

- **Notfalladresse** – Eine Anschrift&mdash;, die physische oder Straßenadresse eines Geschäftsorts für Ihre Organisation.

  Beispielsweise wird die Adresse *12345 North Main Street, Redmond, WA 98052 verwendet,* um Notrufe an die zuständigen Versandbehörden weiterzuleiten und bei der Suche nach dem Notrufer zu unterstützen.

- **Ort** – In der Regel eine Boden-, Gebäude-, Flügel- oder Büronummer. Ort ist einer Notfalladresse zugeordnet, um einen genaueren Standort innerhalb eines Gebäudes anzugeben. Sie können eine unbegrenzte Anzahl von Orten haben, die einer Notfalladresse zugeordnet sind. Wenn Ihre Organisation z. B. über mehrere Gebäude verfügt, möchten Sie möglicherweise Platzinformationen für jedes Gebäude und jede Etage in jedem Gebäude einschließen.

- **Notfallstandort** – Ein Standort ist eine Adresse&mdash;mit optionalem Ort. Wenn Ihr Unternehmen über mehrere physische Standorte verfügt, benötigen Sie wahrscheinlich mehrere Notfallstandorte.

  Wenn Sie eine Notfalladresse erstellen, wird automatisch eine eindeutige Standort-ID für diese Adresse erstellt. Wenn Sie z. B. einer Notfalladresse&mdash;einen Ort hinzufügen, wird beim Hinzufügen eines Stockwerks zu einer Gebäudeadresse&mdash;eine Standort-ID für die Kombination aus Notfalladresse und Ort erstellt.  In diesem Beispiel gibt es zwei Standort-IDs: eine für die Anschrift; eine für die beigetretene Adresse und den zugehörigen Ort.

  Wenn Sie einem Benutzer oder Standort einen Notfallstandort zuweisen, ist dies diese eindeutige Standort-ID, die dem Benutzer oder standort zugeordnet ist.

- **Registrierte Adresse** – Eine Notfalladresse, die jedem Benutzer zugewiesen ist. Eine registrierte Adresse wird manchmal als statische Notfalladresse oder Datensatzadresse bezeichnet. (Registrierte Adressen werden für Direct Routing derzeit nicht unterstützt. Schauen Sie bald wieder nach Updates.)

>[!Note]
>Es gibt einige Unterschiede bei der Verwaltung von Notrufen, je nachdem, ob Sie Microsoft Calling Plans, Operator Connect, Telefonieanbieter mit Mobil (Public Preview Release) oder Direct Routing für Ihre [PSTN-Konnektivität](pstn-connectivity.md) verwenden. Diese Überlegungen werden in diesem Artikel beschrieben.

## <a name="emergency-address-validation"></a>Validierung von Notfalladressen

Um einem Benutzer oder einer Netzwerk-ID eine Notfalladresse zuzuweisen, müssen Sie sicherstellen, dass die Notfalladresse als "überprüft" gekennzeichnet ist. Die Adressüberprüfung stellt sicher, dass die Adresse legitim ist und nicht geändert werden kann, nachdem sie zugewiesen wurde.

Wenn Sie eine Notfalladresse mithilfe des Features für die Adresszuordnungssuche im Teams Admin Center definieren, wird die Adresse automatisch als überprüft markiert. Da Sie eine überprüfte Notfalladresse&mdash;nicht ändern können, wenn sich das Format oder die Darstellung der Adresse ändert, müssen Sie eine neue Adresse mit dem aktualisierten Format erstellen.

## <a name="emergency-address-geo-codes"></a>Geocodes für Notfalladressen

Jeder Notfalladresse kann ein Geocode (Breiten- und Längengrad) zugeordnet sein. Diese Geocodes werden in einigen Ländern verwendet, um die Weiterleitung von Notrufen mit dynamischen Standorten zu unterstützen.

Wenn Sie eine Notfalladresse mithilfe der Adresskarten-Suchfunktion im Teams Admin Center definieren, wird der Geocode automatisch einer Notfalladresse zugeordnet. Sie können einer Adresse auch Geocodes zuordnen, wenn Sie die Adresse mithilfe von PowerShell definieren.

Microsoft empfiehlt, Notfalladressen mithilfe des Kartensuchfeatures im Teams Admin Center zu erstellen, um sicherzustellen, dass die Adressen formatiert, überprüft und über die entsprechenden Geocodes verfügen.

>[!Important]
>Um einen Notfallstandort einem Netzwerkbezeichner für dynamische Notrufe zuzuweisen, muss die Notfalladresse einen entsprechenden Geocode enthalten.

## <a name="considerations-for-calling-plans"></a>Überlegungen zu Anrufplänen

In den folgenden Abschnitten wird beschrieben, wie Sie Notrufe für Benutzer von Microsoft-Anrufplänen verwalten. Informationen dazu, ob Microsoft-Anrufpläne die richtige Lösung für Ihr Unternehmen sind, finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-calling-plans"></a>Notrufaktivierung für Anrufpläne

Jeder Anrufplanbenutzer wird automatisch für Notrufe aktiviert und muss über eine registrierte Notfalladresse verfügen, die der zugewiesenen Telefonnummer zugeordnet ist.

Wann der Standort der Telefonnummer zugeordnet ist, hängt vom Land/der Region ab:

- In den Estados Unidos und Kanada ist beispielsweise ein Notfallstandort erforderlich, wenn einem Benutzer eine Nummer zugewiesen wird.

- Für andere Länder&mdash;wie Europa, den Nahen Osten und Afrika (EMEA)&mdash; ist ein Notfallstandort erforderlich, wenn Sie die Telefonnummer von Microsoft 365 erhalten oder von einem anderen Dienstanbieter oder Netzbetreiber übertragen werden.

### <a name="dynamic-emergency-calling-for-calling-plans"></a>Dynamische Notrufe für Anrufpläne

Dynamische Notrufe für Anrufpläne bieten die Möglichkeit, Notrufe basierend auf dem aktuellen Standort des Teams-Clients zu konfigurieren und weiterzuleiten. Die Möglichkeit, automatisches Routing an den entsprechenden Public Safety Answering Point (PSAP) durchzuführen oder Das Personal des Security Desk zu benachrichtigen, hängt vom Nutzungsland des Teams-Benutzers ab.

Der dynamische Standort für das Weiterleiten von Notrufen wird in der Estados Unidos wie folgt unterstützt.

- Wenn ein Teams-Client für einen benutzer mit Estados Unidos Anrufplan dynamisch eine Notfalladresse innerhalb der Estados Unidos erwirbt, wird diese Adresse für das Notfallrouting anstelle der registrierten Adresse verwendet, und der Anruf wird automatisch an die PSP im Bereitstellungsbereich der Adresse weitergeleitet.

- Wenn ein Teams-Client für einen Estados Unidos Anrufplanbenutzer innerhalb der Estados Unidos nicht dynamisch eine Notfalladresse abruft, wird die registrierte Notfalladresse verwendet, um den Anruf zu suchen und weiterzuleiten. Der Anruf wird jedoch überprüft, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

Der dynamische Standort für die Weiterleitung von Notrufen wird in Kanada genauso unterstützt wie im Estados Unidos mit der folgenden Ausnahme: Alle Notrufe werden national überprüft, bevor sie an das PSAP weitergeleitet werden.

Weitere Informationen finden Sie unter ["Planen und Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md)".

### <a name="emergency-call-routing-for-calling-plans"></a>Notrufweiterleitung für Anrufpläne

Wenn ein Benutzer eines Teams-Anrufplans eine Notrufnummer wählt, hängt die Weiterleitung des Anrufs an das Telefondiensttelefon von Folgenden ab:

- Gibt an, ob die Notfalladresse vom Teams-Client dynamisch bestimmt wird.

- Gibt an, ob die Notfalladresse die registrierte Adresse ist, die der Telefonnummer des Benutzers zugeordnet ist.

- Das Notrufnetzwerk dieses Landes.

Zum Beispiel: 

**Im Estados Unidos:**

- Wenn sich ein Teams-Client an einem mandantendefinierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client automatisch an den PSAP weitergeleitet, der diesen geografischen Standort bedient.

- Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client von einem nationalen Callcenter überprüft, um den Standort des Anrufers zu ermitteln, bevor der Anruf an den PSAP weitergeleitet wird, der diesen geografischen Standort bedient.

- Wenn ein Notrufer seinen Notfallstandort nicht in das Screening-Center aktualisieren kann, wird der Anruf an die PSAP weitergeleitet, die die registrierte Adresse des Anrufers bedient.

**In Kanada, Irland und dem Vereinigten Königreich** werden Notrufe zuerst überprüft, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf mit dem entsprechenden Versandzentrum verbunden wird.

**In Frankreich, Deutschland und Spanien** werden Notrufe unabhängig vom Standort des Anrufers direkt an die Notrufadresse weitergeleitet, die der Nummer zugeordnet ist.

**In den Niederlanden** werden Notrufe für die Ortsvorwahl der Nummer unabhängig vom Standort des Anrufers direkt an das PSAP weitergeleitet.

**In Australien** werden Notfalladressen vom Netzbetreiber konfiguriert und weitergeleitet.

**In Japan** werden Notrufe nicht unterstützt.

Weitere Informationen finden Sie unter:

- [Anrufpläne](calling-plan-landing-page.md)
- [Einrichten von Anrufplänen](set-up-calling-plans.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>Überlegungen zu Operator Connect

In den folgenden Abschnitten wird beschrieben, wie Sie Notrufe für Operator Connect-Benutzer verwalten. Informationen dazu, ob Operator Connect die richtige Lösung für Ihr Unternehmen ist, finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-operator-connect"></a>Notrufaktivierung für Operator Connect

Jeder Operator Connect-Benutzer wird automatisch für Notrufe aktiviert. Notrufe werden automatisch für eine bestimmte Nummer an den Netzbetreiber weitergeleitet.

Die Möglichkeit für einen Mandantenadministrator, die registrierte Adresse für einen Operator Connect-Benutzer festzulegen, hängt von den Funktionen ab, die der Nummer zugewiesen sind, wenn der Netzbetreiber sie in einen Kundenbestand hochlädt. Basierend auf dieser Einstellung ist der Mandantenadministrator möglicherweise erforderlich oder nicht in&mdash;der Lage&mdash;, den Notfallstandort eines Benutzers festzulegen, zu ändern oder zu löschen.

### <a name="dynamic-emergency-calling-for-operator-connect"></a>Dynamische Notrufe für Operator Connect

Dynamische Notrufe für Operator Connect bieten die Möglichkeit, Notrufe basierend auf dem aktuellen Standort des Teams-Clients zu konfigurieren und weiterzuleiten. Die Möglichkeit, automatisches Routing an den entsprechenden Public Safety Answering Point (PSAP) durchzuführen oder Das Personal des Security Desk zu benachrichtigen, hängt vom Nutzungsland des Teams-Benutzers ab.

Der dynamische Standort für das Weiterleiten von Notrufen wird in der Estados Unidos wie folgt unterstützt.

- Wenn ein Teams-Client für einen Estados Unidos Benutzer dynamisch eine Notfalladresse innerhalb der Estados Unidos erwirbt, wird diese Adresse für das Notfallrouting anstelle der registrierten Adresse verwendet, und der Anruf wird automatisch an das PSP im Dienstbereich der Adresse weitergeleitet.

- Wenn ein Teams-Client für einen Estados Unidos Benutzer innerhalb der Estados Unidos nicht dynamisch eine Notfalladresse abruft, wird die registrierte Notfalladresse verwendet, um den Anruf zu suchen und weiterzuleiten. Der Anruf wird jedoch überprüft, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

Der dynamische Standort für die Weiterleitung von Notrufen wird in Kanada genauso unterstützt wie im Estados Unidos mit den folgenden Ausnahmen: Alle Notrufe werden national überprüft, bevor sie an das PSAP weitergeleitet werden.

Weitere Informationen finden Sie unter ["Planen und Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md)".

### <a name="emergency-call-routing-for-operator-connect"></a>Notrufweiterleitung für Telefonieanbieter

Wenn ein Benutzer von Teams Operator Connect eine Notrufnummer wählt, hängt es davon ab, wie der Anruf an das PsAP weitergeleitet wird:

- Gibt an, ob die Notfalladresse vom Teams-Client dynamisch bestimmt wird.

- Gibt an, ob die Notfalladresse die registrierte Adresse ist, die der Telefonnummer des Benutzers zugeordnet ist.

- Das Notrufnetzwerk dieses Landes.

- In den Estados Unidos und Kanada ist dynamisches Routing Teil des Dienstes des Netzbetreibers. Sie müssen diesen Dienst nicht von einem anderen Dienstanbieter beziehen.

- Wenn sich ein Teams-Client an einem mandantendefinierten dynamischen Notfallstandort befindet:
  - In der Estados Unidos werden Notrufe von diesem Client automatisch an den PSAP weitergeleitet, der diesen geografischen Standort bedient.
  - In Kanada werden alle Notrufe von einem nationalen Callcenter überprüft, bevor der Anruf an die PSAP weitergeleitet wird, die diesen geografischen Standort bedient.

- Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client von einem nationalen Callcenter überprüft, um den Standort des Anrufers zu ermitteln, bevor der Anruf an den PSAP weitergeleitet wird, der diesen geografischen Standort bedient.

- Wenn ein Notrufer seinen Notfallstandort nicht in das Screening-Center aktualisieren kann, wird der Anruf an die PSAP weitergeleitet, die die registrierte Adresse des Anrufers bedient.

## <a name="considerations-for-operator-connect-mobile"></a>Überlegungen zur Telefonieanbieter mit Mobil

In den folgenden Abschnitten wird beschrieben, wie Sie Notrufe für Telefonieanbieter mit Mobil Benutzer verwalten. Informationen dazu, ob Telefonieanbieter mit Mobil die richtige Lösung für Ihr Unternehmen ist, finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md).

**Telefonieanbieter mit Mobil ist eine öffentliche Vorschauversion.**

### <a name="emergency-call-enablement-for-operator-connect-mobile"></a>Notrufaktivierung für Telefonieanbieter mit Mobil

Jeder Telefonieanbieter mit Mobil Benutzer wird automatisch für Notrufe aktiviert. Notrufe werden automatisch an den Telefonieanbieter mit Mobil Netzbetreiber für eine bestimmte Nummer weitergeleitet.

Die Möglichkeit für einen Mandantenadministrator, die registrierte Adresse für einen Telefonieanbieter mit Mobil Benutzer festzulegen, hängt von den Funktionen ab, die der Nummer zugewiesen sind, wenn der Netzbetreiber sie in einen Kundenbestand hochlädt. Basierend auf dieser Einstellung kann oder kann der Mandantenadministrator den Notfallstandort eines Benutzers festlegen, ändern oder löschen.

Wenn Anrufe über die systemeigene Wählhilfe des SIM-fähigen Smartphones getätigt werden, kann Ihr Betreiber die geografischen Koordinaten oder den Zellturm für die Behandlung des Anrufs verwenden, um den Notfallstandort näherungsweise zu unterstützen.

### <a name="dynamic-emergency-calling-for-operator-connect-mobile"></a>Dynamische Notrufe für Telefonieanbieter mit Mobil

Dynamische Notrufe für Operator Connect bieten die Möglichkeit, Notrufe basierend auf dem aktuellen Standort des Teams-Clients zu konfigurieren und weiterzuleiten. Die Möglichkeit, automatisches Routing an den entsprechenden Public Safety Answering Point (PSAP) durchzuführen oder Das Personal des Security Desk zu benachrichtigen, hängt vom Nutzungsland des Teams-Benutzers ab.

Der dynamische Standort für das Weiterleiten von Notrufen wird in der Estados Unidos wie folgt unterstützt.

- Wenn ein Teams-Client für einen Estados Unidos Benutzer dynamisch eine Notfalladresse innerhalb der Estados Unidos erwirbt, wird diese Adresse für das Notfallrouting anstelle der registrierten Adresse verwendet, und der Anruf wird automatisch an das PSP im Dienstbereich der Adresse weitergeleitet.

- Wenn ein Teams-Client für einen Estados Unidos Benutzer innerhalb der Estados Unidos nicht dynamisch eine Notfalladresse abruft, wird die registrierte Notfalladresse verwendet, um den Anruf zu suchen und weiterzuleiten. Der Anruf wird jedoch überprüft, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

Der dynamische Standort für die Weiterleitung von Notrufen wird in Kanada genauso unterstützt wie im Estados Unidos mit den folgenden Ausnahmen: Alle Notrufe werden national überprüft, bevor sie an das PSAP weitergeleitet werden.

Weitere Informationen finden Sie unter ["Planen und Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md)".

### <a name="emergency-call-routing-for-operator-connect-mobile"></a>Notrufweiterleitung für Telefonieanbieter mit Mobil

Wenn ein Teams-Telefonieanbieter mit Mobil Benutzer mithilfe eines Microsoft Teams-Clients eine Notrufnummer wählt, hängt die Weiterleitung des Anrufs an das PSAP von Folgenden ab:

- Gibt an, ob die Notfalladresse vom Teams-Client dynamisch bestimmt wird.

- Gibt an, ob die Notfalladresse die registrierte Adresse ist, die der Telefonnummer des Benutzers zugeordnet ist.

- Das Notrufnetzwerk dieses Landes.

- In den Estados Unidos und Kanada ist dynamisches Routing Teil des Dienstes des Netzbetreibers. Sie müssen diesen Dienst nicht von einem anderen Dienstanbieter beziehen.

- Wenn sich ein Teams-Client an einem mandantendefinierten dynamischen Notfallstandort befindet:
  - In der Estados Unidos werden Notrufe von diesem Client automatisch an den PSAP weitergeleitet, der diesen geografischen Standort bedient.
  - In Kanada werden alle Notrufe von einem nationalen Callcenter überprüft, bevor der Anruf an die PSAP weitergeleitet wird, die diesen geografischen Standort bedient.

- Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client von einem nationalen Callcenter überprüft, um den Standort des Anrufers zu ermitteln, bevor der Anruf an den PSAP weitergeleitet wird, der diesen geografischen Standort bedient.

- Wenn ein Notrufer seinen Notfallstandort nicht in das Screening-Center aktualisieren kann, wird der Anruf an die PSAP weitergeleitet, die die registrierte Adresse des Anrufers bedient.

Ihr Mobilfunkanbieter verwaltet alle Notrufe, die über die systemeigene Dialer Ihres SIM-Enabled Smartphones getätigt werden, und kann mehrere Technologien verwenden, um den Notfallstandort näherungsweise anzurufen, um Unterstützung zu erhalten, z. B. geografische Koordinaten oder welche Zelltürme den Anruf entgegennehmen usw. Bitte wenden Sie sich an Ihren Betreiber, um weitere Informationen zu erfahren.


## <a name="considerations-for-direct-routing"></a>Überlegungen zum Direct Routing

In den folgenden Abschnitten wird beschrieben, wie Sie Notrufe für Direct Routing-Benutzer verwalten. Informationen dazu, ob Direct Routing die richtige Lösung für Ihr Unternehmen ist, finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-direct-routing"></a>Notrufaktivierung für Direct Routing

Für Direct Routing müssen Sie Notrufrichtlinien für Benutzer definieren, indem Sie eine [Teams-Richtlinie für die Notrufweiterleitung](manage-emergency-call-routing-policies.md) verwenden, um Notrufnummern und deren zugeordnetes Routingziel zu definieren. (Registrierte Notfallstandorte werden derzeit für Direct Routing-Benutzer nicht unterstützt.)

Sie können eine Richtlinie für die Notrufweiterleitung einem Direct Routing-Benutzerkonto, einem Netzwerkstandort oder beiden zuweisen. Wenn ein Teams-Client eine Netzwerkverbindung startet oder ändert, führt Teams eine Suche nach dem Netzwerkstandort durch, an dem sich der Client befindet:

- Wenn dem Standort eine Richtlinie für die Notrufweiterleitung zugeordnet ist, wird die Standortrichtlinie zum Konfigurieren von Notrufen verwendet.

- Wenn dem Standort keine Richtlinie für die Notrufweiterleitung zugeordnet ist, wenn der Client an einem nicht definierten Standort verbunden ist oder wenn die gewählte Nummer keiner der Notrufnummern entspricht, die in der Richtlinie für die Notrufweiterleitung definiert sind, die dem Standort zugeordnet ist, wird die dem Benutzerkonto zugeordnete Notrufweiterleitungsrichtlinie zum Konfigurieren von Notrufen verwendet.

- Wenn der Teams-Client keine Richtlinie für die Notrufweiterleitung abrufen kann, ist der Benutzer nicht für Notrufe aktiviert.

### <a name="dynamic-emergency-calling-for-direct-routing"></a>Dynamische Notrufe für Direct Routing

Dynamische Notrufe für Direct Routing bieten die Möglichkeit, Notrufe basierend auf dem aktuellen Standort des Teams-Clients zu konfigurieren und weiterzuleiten. Die Möglichkeit, automatisches Routing an den entsprechenden Public Safety Answering Point (PSAP) durchzuführen oder Das Personal des Security Desk zu benachrichtigen, hängt vom Nutzungsland des Teams-Benutzers ab.

Für Direct Routing-Benutzer wird der dynamische Standort für das Weiterleiten von Notrufen nur in der Estados Unidos wie folgt unterstützt:

- Wenn ein Teams-Client für einen Estados Unidos Direct Routing-Benutzer dynamisch eine Notfalladresse innerhalb der Estados Unidos erwirbt, wird diese Adresse für das Notfallrouting verwendet, und der Anruf wird automatisch an das PSP im Dienstbereich der Adresse weitergeleitet.

- Wenn ein Teams-Client für einen Estados Unidos Direct Routing-Benutzer innerhalb der Estados Unidos nicht dynamisch eine Notfalladresse abruft, wird der Anruf überprüft, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

Der dynamische Standort für die Weiterleitung von Notrufen wird in Kanada genauso unterstützt wie im Estados Unidos mit der folgenden Ausnahme: Alle Notrufe werden national überprüft, bevor sie an das PSAP weitergeleitet werden.

Weitere Informationen finden [Sie unter Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-direct-routing"></a>Notrufweiterleitung für Direct Routing

Die Richtlinie für die Notrufweiterleitung für Direct Routing verweist auf eine Online-PSTN-Nutzung, die über die entsprechende Direct Routing-Konfiguration verfügen muss, um die Notrufe ordnungsgemäß an die entsprechenden PSTN-Gateways weiterzuleiten. Insbesondere müssen Sie sicherstellen, dass eine OnlineVoiceRoute für die Notrufzeichenfolge vorhanden ist. Weitere Informationen finden [Sie unter Konfigurieren von Direct Routing](direct-routing-configure.md).

> [!NOTE]
> Teams-Clients haben das "+"-Zeichen nicht mehr vor Notrufnummern vorangestellt. d. h. +911. Folglich senden Teams-Notrufe kein "+" mehr vor der Nummer 911. Stellen Sie sicher, dass Ihre VoIP-Routenmuster diese Änderung widerspiegeln.

Die Möglichkeit, Notrufe für Direct Routing-Benutzer dynamisch weiterzuleiten, hängt vom Notrufnetzwerk in einem bestimmten Land ab. Es stehen zwei Lösungen zur Verfügung:

- [Notfallroutingdienstanbieter (nur USA)](#emergency-routing-service-providers)
- [Anwendungen für Notfallstandort-Identifikationsnummern](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>Anbieter von Notfallroutingdiensten

In der Estados Unidos gibt es zahlreiche zertifizierte Emergency Routing Service Providers (ERSPs), die Notrufe basierend auf dem Standort des Anrufers automatisch weiterleiten können.

- Wenn ein Notfallroutingdienstanbieter in eine Direct Routing-Bereitstellung integriert ist, werden Notrufe mit einem dynamisch erworbenen Standort automatisch an den Public Safety Answering Point (PSAP) weitergeleitet, der diesen Standort bedient.

- Notrufe ohne dynamisch erworbenen Standort werden zuerst überprüft, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf basierend auf dem aktualisierten Standort mit dem entsprechenden Versandzentrum verbunden wird.

Weitere Informationen finden Sie unter [Session Border Controller, die für Direct Routing zertifiziert sind](direct-routing-border-controllers.md).

#### <a name="emergency-location-identification-number-applications"></a>Anwendungen für Notfallstandort-Identifikationsnummern

Session Border Controller (SBCs) können ELIN-Anwendungen (Emergency Location Identification Number) enthalten. Wenn eine SBC ELIN-Anwendung in eine Direct Routing-Bereitstellung integriert ist, müssen Sie die Notfalladressen und zugehörigen Telefonnummern in der ELIN-Anwendung konfigurieren und dann die ELIN-Einträge in die Notrufdatenbank im jeweiligen PSTN hochladen. Teams-Notfallstandorte mit einem ELIN-Bezeichner müssen mit denen in der ELIN-Anwendung übereinstimmen.

Wenn ein Notruf mit einem dynamisch erworbenen Standort an den entsprechenden SBC weitergeleitet wird, wird die ELIN-Anwendung:

- Analysiert den Notfallstandort des Anrufers.
- Entspricht dem Speicherort einem ELIN-Eintrag.
- Ersetzt die Nummer des Notrufers durch die ELIN-Telefonnummer.
- Leitet den Anruf an das PSAP weiter, das diesen Standort bedient, und dann rufen die Disponenten den Standort aus dem hochgeladenen ELIN-Eintrag ab.

Bei einem Rückruf an die Notrufnummer führt die ELIN-Anwendung die umgekehrte Nummernersetzung durch die des ursprünglichen Notrufers durch.

Weitere Informationen finden Sie unter [Session Border Controller, die für Direct Routing zertifiziert sind](direct-routing-border-controllers.md).

## <a name="security-desk-notification"></a>Security Desk-Benachrichtigung

Security Desk-Benachrichtigungen sind sowohl mit Microsoft-Anrufplänen, Telefonieanbieter und Direct Routing verfügbar.

Sie verwenden eine Teams-Notrufrichtlinie (TeamsEmergencyCallingPolicy), um zu konfigurieren, wer während eines Notrufs benachrichtigt werden soll und wie diese benachrichtigt werden: Nur Chat, Konferenzen in und stummgeschaltet oder konferenzen und stummgeschaltet, aber mit der Möglichkeit, die Stummschaltung aufzuheben. Sie können auch eine externe PSTN-Nummer eines Benutzers oder einer Gruppe angeben, um den Notruf anzurufen und daran teilzunehmen. Beachten Sie, dass die PSTN-Partei die Stummschaltung nicht aufheben darf.

Eine Richtlinie für Notrufe kann einem Teams-Benutzerkonto, einem Netzwerkstandort oder beidem zugewiesen werden.  Wenn ein Teams-Client eine Netzwerkverbindung startet oder ändert, führt Teams eine Suche nach dem Netzwerkstandort durch, an dem sich der Client befindet:

- Wenn eine Richtlinie für Notrufe einem Netzwerkstandort zugeordnet ist, wird die Standortrichtlinie verwendet, um die Benachrichtigung des Security Desk zu konfigurieren.

- Wenn dem Standort keine Richtlinie für Notrufe zugeordnet ist oder wenn der Client an einem nicht definierten Standort verbunden ist, wird die dem Benutzerkonto zugeordnete Notrufrichtlinie verwendet, um die Benachrichtigung des Security Desk zu konfigurieren.

- Wenn der Teams-Client keine Richtlinie für Notrufe abrufen kann, ist der Benutzer nicht für Benachrichtigungen am Sicherheitsdesk aktiviert.

Während eines Notrufs wird ein Sicherheitsdesk in den Anruf konferenziert, und die Erfahrung des Security Desk-Benutzers wird basierend auf der Teams-Notrufrichtlinie gesteuert. Ein Gruppenchat wird mit jedem Mitglied des Sicherheitsdesks gestartet, und der Standort des Notrufers wird über eine wichtige Nachrichtenbenachrichtigung freigegeben.  Wenn eine Konferenzoption als Teil der Richtlinie konfiguriert ist, wird jeder Security Desk-Benutzer zusätzlich als Teil der Konferenz aufgerufen.

### <a name="custom-emergency-disclaimer"></a>Benutzerdefinierter Haftungsausschluss für Notfälle

Administratoren haben die Möglichkeit, ein benutzerdefiniertes Banner im Mandanten für ihre Benutzer hinzuzufügen, um E911 zu aktivieren. Benutzer können das Banner schließen, wenn sie ihre Adresse bestätigen, und das Banner wird wieder angezeigt, wenn Teams neu gestartet wird. Um dieses Feature zu aktivieren, legen Sie den **Haftungsausschluss für den Notfalldienst** unter der Microsoft Teams-Richtlinie für Notrufe fest und geben eine Zeichenfolgenmeldung ein, die Benutzern angezeigt werden soll. Dieses Feld ist optional beim Einrichten einer benutzerdefinierten Richtlinie, und das Zeichenfolgenfeld ist auf 250 Zeichen beschränkt.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Richtlinien für die Notrufweiterleitung ](manage-emergency-call-routing-policies.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für Den Benutzer](assign-change-emergency-location-user.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
