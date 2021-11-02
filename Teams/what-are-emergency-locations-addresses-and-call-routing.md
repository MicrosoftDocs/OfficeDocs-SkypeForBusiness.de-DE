---
title: Planen und Verwalten von Notrufen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz, jastark
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
description: Erfahren Sie mehr über Notrufe, einschließlich Informationen zu Notfalladressen, Notrufen und dynamischen Notrufen.
ms.openlocfilehash: f6c1dd766ae14d855b9f2ffcf21c41ed8a5a1550
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634864"
---
# <a name="manage-emergency-calling"></a>Verwalten von Notrufen

In diesem Artikel werden die Konzepte beschrieben, die Sie kennen müssen, um Notrufe zu verwalten, einschließlich Informationen zu Notfalladressen, dynamischen Notfalladressen und &mdash; Notrufrouting. In diesem Artikel wird die folgende Terminologie verwendet:

- **Notfalladresse** – Eine Anschrift, die physische oder Anschrift eines Orts Ihres &mdash; Unternehmens.

  Beispielsweise wird die Adresse *12345 North Main Street, Redmond, WA 98052, WA 98052* verwendet, um Notrufe an die entsprechenden Einsatzkräfte weiter zu senden und den Standort des Notrufers zu suchen.

- **Ort** – In der Regel ein Stockwerk, gebäude, wing oder office number. Der Ort ist einer Notfalladresse zugeordnet, um einen exakten Standort innerhalb eines Gebäudes zu erhalten. Sie können eine unbegrenzte Anzahl von Orten mit einer Notfalladresse verknüpft haben. Wenn Ihre Organisation z. B. über mehrere Gebäude verfügt, können Sie Ortsinformationen für jedes Gebäude und jedes Stockwerk in jedem Gebäude bei sich haben.  

- **Notfallstandort** – Ein Standort ist eine Adresse mit &mdash; optionalem Ort. Wenn Ihr Unternehmen über mehrere physische Standorte verfügt, benötigen Sie wahrscheinlich mehrere Notfallstandorte. 

  Wenn Sie eine Notfalladresse erstellen, wird automatisch eine eindeutige Standort-ID für diese Adresse erstellt. Wenn Sie beispielsweise einer Notfalladresse einen Ort hinzufügen, wenn Sie einer Gebäudeadresse einen Boden hinzufügen, wird eine Standort-ID für die Kombination aus Notfalladresse und &mdash; &mdash; -ort erstellt.  In diesem Beispiel gibt es zwei Standort-IDs: eine für die Adresse; eine Adresse für die beigetretene Adresse und den zugehörigen Ort.

  Wenn Sie einem Benutzer oder einer Website einen Notfallstandort zuweisen, wird diese eindeutige Standort-ID dem Benutzer oder der Website zugeordnet.

- **Registrierte Adresse** – Eine Notfalladresse, die jedem Benutzer zugewiesen wird. Eine registrierte Adresse wird manchmal als statische Notfalladresse oder Datensatzadresse bezeichnet. (Derzeit werden registrierte Adressen für Direct-Routing nicht unterstützt. Schauen Sie bald wieder nach Updates.)

>[!Note]
>Je nachdem, ob Sie Microsoft-Anrufpläne, operator Verbinden oder Direct Routing für Ihre [PSTN-Verbindung](pstn-connectivity.md)verwenden, gibt es einige Unterschiede bei der Verwaltung von Notrufen. Diese Überlegungen werden in diesem Artikel beschrieben.

## <a name="emergency-address-validation"></a>Überprüfung von Notfalladressen

Um einem Benutzer oder einer Netzwerk-ID eine Notfalladresse zuzuordnen, müssen Sie sicherstellen, dass die Notfalladresse als "überprüft" gekennzeichnet ist. Mit der Adressvalidierung wird sichergestellt, dass die Adresse legitim ist und nach derEntierung nicht mehr geändert werden kann. 

Wenn Sie eine Notfalladresse mithilfe der Funktion für die Suche nach Adresskarten im Teams Admin Center definieren, wird die Adresse automatisch als überprüft markiert. Da Sie eine überprüfte Notfalladresse nicht ändern können, wenn sich das Format oder die Darstellung der Adresse ändert, müssen Sie eine neue Adresse mit dem &mdash; aktualisierten Format erstellen.


## <a name="emergency-address-geo-codes"></a>Notfalladressen-Geocodes

Jeder Notfalladresse kann ein Geocode (Breiten- und Längengrad) zugeordnet sein. Diese Geocodes werden in einigen Ländern verwendet, um das Routing von Notrufen mit dynamischen Standorten zu unterstützen. 

Wenn Sie eine Notfalladresse mithilfe der Funktion für die Suche nach Adresskarten im Teams Admin Center definieren, wird der Geocode automatisch einer Notfalladresse zugeordnet. Sie können einer Adresse auch Geocodes zuordnen, wenn Sie die Adresse mithilfe von PowerShell definieren. 

Microsoft empfiehlt, dass Sie Notfalladressen mithilfe der Funktion für die Kartensuche im Teams Admin Center erstellen, mit der sichergestellt wird, dass die Adressen formatiert und validiert sind und über die entsprechenden Geocodes verfügen. 

>[!Important]
>Um einer Netzwerk-ID einen Notfallstandort für dynamische Notrufe zuzuordnen, muss die Notfalladresse einen geeigneten Geocode enthalten.


## <a name="considerations-for-calling-plans"></a>Überlegungen für Anrufpläne

In den folgenden Abschnitten wird beschrieben, wie Notrufe für Benutzer des Microsoft-Anrufplans verwaltet werden. Wenn Sie herausfinden möchten, ob Microsoft-Anrufpläne die richtige Lösung für Ihr Unternehmen sind, lesen Sie [PSTN-Konnektivitätsoptionen.](pstn-connectivity.md)


### <a name="emergency-call-enablement-for-calling-plans"></a>Aktivierung von Notrufen für Anrufpläne

Jeder Anrufplanbenutzer wird automatisch für Notrufe aktiviert und muss über eine registrierte Notfalladresse verfügen, die der zugewiesenen Telefonnummer zugeordnet ist. 

Wann der Standort mit der Telefonnummer verknüpft ist, hängt vom Land/der Region ab:

- In den USA und Kanada beispielsweise ist ein Notfallstandort erforderlich, wenn einem Benutzer eine Nummer zugewiesen wird.

- Bei anderen Ländern wie Europa, dem Nahen Osten und Afrika (EMEA) ist ein Notfallstandort erforderlich, wenn Sie die Telefonnummer von Microsoft 365 erhalten oder wenn sie von einem anderen Dienstanbieter oder Netzbetreiber übertragen &mdash; &mdash; wird.


### <a name="dynamic-emergency-calling-for-calling-plans"></a>Dynamische Notrufe für Anrufpläne

Dynamische Notrufe für Anrufpläne bieten die Möglichkeit, Notrufe basierend auf der aktuellen Position des anrufbasierten Clients zu konfigurieren Teams weiter. Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden Public Safety Answering Point (PSAP) oder zum Benachrichtigen der Mitarbeiter des Sicherheitsdesks hängt vom Land ab, in dem der Benutzer Teams wird.  

Die dynamische Position für Notrufe wird in den USA wie folgt unterstützt. 

- Wenn ein Teams-Client für einen Benutzer eines Anrufplans in den USA dynamisch eine Notfalladresse abruft, wird diese Adresse anstelle der registrierten Adresse für das Notfallrouting verwendet, und der Anruf wird automatisch an das PSAP im Dienstbereich der Adresse geroutet.

- Wenn ein Teams-Client für einen Anrufplanbenutzer in den USA nicht dynamisch eine Notfalladresse abruft, wird die registrierte Notfalladresse verwendet, um den Anruf zu bildschirm- und routen zu unterstützen. Der Anruf wird jedoch angezeigt, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

Die dynamische Position für Notrufe wird in Kanada genauso wie in den USA unterstützt. Ausnahme: Alle Notrufe werden national vor der Übertragung an das PSAP angezeigt.

Weitere Informationen finden Sie unter [Planen und Konfigurieren von dynamischen Notrufen.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing-for-calling-plans"></a>Routing von Notrufen für Anrufpläne

Wenn ein Teams Anrufplan-Benutzer eine Notfallnummer wählt, hängt die Art und Weise, wie der Anruf an das PSAP-System umgerufen wird, von Folgendem ab:

- Die Notfalladresse wird vom Client dynamisch Teams bestimmt.

- Die Notfalladresse soll die registrierte Adresse sein, die der Telefonnummer des Benutzers zugeordnet ist.

- Das Notrufnetzwerk dieses Landes.

Zum Beispiel: 

**In den USA:**

- Wenn sich Teams-Client an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client automatisch an das PSAP umgerufen, das den geografischen Standort bedient.

- Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client von einem nationalen Anrufcenter zur Ermittlung des Standorts des Anrufers vor der Übertragung des Anrufs an den psAP-Dienst für den geografischen Standort angezeigt.

- Wenn ein Notrufer seinen Notfallstandort nicht auf das Prüfungscenter aktualisieren kann, wird der Anruf an das PSAP übermittelt, das die registrierte Adresse des Anrufers verwendet.

**In Kanada, Irland** und dem Vereinigten Königreich werden Notrufe zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf mit dem entsprechenden Verteilercenter verbunden wird.

**In Frankreich, Deutschland und Spanien** werden Notrufe unabhängig vom Standort des Anrufers direkt an das PSAP um die der Nummer zugeordnete Notfalladresse gesendet.

**In den Niederlanden** werden Notrufe unabhängig vom Standort des Anrufers direkt an das PSAP für die lokale Ortswahl der Rufnummer gesendet.

**In Australien** werden Notfalladressen vom Netzbetreiberpartner konfiguriert und geroutet.

**In Japan** werden Notrufe nicht unterstützt.


Weitere Informationen finden Sie unter:

- [Anrufpläne](calling-plan-landing-page.md)
- [Einrichten von Anrufplänen](set-up-calling-plans.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>Überlegungen zur operatoren Verbinden

In den folgenden Abschnitten wird beschrieben, wie Notrufe für Netzbetreiber und Verbinden verwaltet werden. Um herauszufinden, ob Verbinden die richtige Lösung für Ihr Unternehmen ist, lesen Sie [PSTN-Konnektivitätsoptionen.](pstn-connectivity.md)

### <a name="emergency-call-enablement-for-operator-connect"></a>Aktivierung eines Notrufs für die Verbinden

Jeder Netzbetreiber Verbinden Benutzer wird automatisch für Notrufe aktiviert. Notrufe werden automatisch an den Netzbetreiber Verbinden einer bestimmten Nummer umgerufen.

Die Möglichkeit eines Mandantenadministrators, die registrierte Adresse für einen Operator Verbinden-Benutzer festlegen zu können, hängt von den Funktionen ab, die der Nummer zugewiesen sind, wenn der Netzbetreiber sie in einen Kundeninventar hochlädt. Basierend auf dieser Einstellung ist der Mandantenadministrator möglicherweise erforderlich oder in der Lage, den Notfallstandort eines Benutzers zu festlegen, zu ändern &mdash; &mdash; oder zu löschen. 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>Dynamische Notrufe für die Verbinden

Dynamische Notrufe für die Operator-Verbinden ermöglicht das Konfigurieren und Routen von Notrufen basierend auf der aktuellen Position des Teams Clients. Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden Public Safety Answering Point (PSAP) oder zum Benachrichtigen der Mitarbeiter des Sicherheitsdesks hängt vom Land ab, in dem der Benutzer Teams wird. 

Die dynamische Position für Notrufe wird in den USA wie folgt unterstützt. 

- Wenn ein Teams-Client für einen US-Benutzer dynamisch eine Notfalladresse in den USA erwirbt, wird diese Adresse für das Notfallrouting anstelle der registrierten Adresse verwendet, und der Anruf wird automatisch an das PSAP im Dienstbereich der Adresse geroutet.

- Wenn ein Teams-Client für einen US-Benutzer nicht dynamisch eine Notfalladresse in den USA erwirbt, wird die registrierte Notfalladresse verwendet, um den Anruf zu bildschirm- und routen zu unterstützen. Der Anruf wird jedoch angezeigt, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

Der dynamische Standort für Die Weiterleitung von Notrufen wird in Kanada genauso wie in den VEREINIGTEn Staaten unterstützt. Ausnahmen: Alle Notrufe werden national vor der Übertragung an das PSAP angezeigt.

Weitere Informationen finden Sie unter [Planen und Konfigurieren von dynamischen Notrufen.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing-for-operator-connect"></a>Routing von Notrufen für Verbinden

Wenn ein Teams-Operator Verbinden Benutzer eine Notrufnummer wählt, hängt die Art der Route des Anrufs an das PSAP von folgendem Thema ab:

- Die Notfalladresse wird vom Client dynamisch Teams bestimmt.

- Die Notfalladresse soll die registrierte Adresse sein, die der Telefonnummer des Benutzers zugeordnet ist.

- Das Notrufnetzwerk dieses Landes.

- In den USA und Kanada ist dynamisches Routing Teil des Diensts des Netzbetreibers. Sie müssen diesen Dienst nicht bei einem anderen Dienstanbieter beziehen.

In den USA und Kanada:

- Wenn sich Teams-Client an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client automatisch an das PSAP umgerufen, das den geografischen Standort bedient.

- Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client von einem nationalen Anrufcenter zur Ermittlung des Standorts des Anrufers vor der Übertragung des Anrufs an den psAP-Dienst für den geografischen Standort angezeigt.

- Wenn ein Notrufer seinen Notfallstandort nicht auf das Prüfungscenter aktualisieren kann, wird der Anruf an das PSAP übermittelt, das die registrierte Adresse des Anrufers verwendet.


## <a name="considerations-for-direct-routing"></a>Überlegungen zum direkten Routing

In den folgenden Abschnitten wird beschrieben, wie Notrufe für Direct Routing-Benutzer verwaltet werden. Wenn Sie herausfinden müssen, ob Direct Routing die richtige Lösung für Ihr Unternehmen ist, lesen Sie [PSTN-Konnektivitätsoptionen.](pstn-connectivity.md)

### <a name="emergency-call-enablement-for-direct-routing"></a>Aktivierung von Notrufen für direktes Routing

Für Direct Routing müssen Sie Richtlinien für Notrufe für Benutzer definieren, indem Sie eine Richtlinie für Teams-Notruf-Routing verwenden, um Notrufnummern und ihr zugeordnetes Routingziel zu definieren. [](manage-emergency-call-routing-policies.md) (Derzeit werden registrierte Notfallstandorte für Direct Routing-Benutzer nicht unterstützt.)

Sie können eine Richtlinie für das Routing von Notrufen einem Direct Routing-Benutzerkonto, einem Netzwerkstandort oder beiden Konten zuweisen. Wenn ein Teams-Client startet oder eine Netzwerkverbindung ändert, führt Teams eine Suche der Netzwerkwebsite durch, auf der sich der Client befindet:

- Wenn der Website eine Richtlinie für die Weiterleitung von Notrufen zugeordnet ist, wird die Websiterichtlinie zum Konfigurieren von Notrufen verwendet.

- Wenn der Website keine Richtlinie für die Weiterleitung von Notrufen zugeordnet ist, wenn der Client an einem nicht definierten Standort verbunden ist oder die gewählte Nummer keiner der Notrufnummern in der Der Website zugeordneten Routingrichtlinie für Notrufe zu entsprechen, wird die Richtlinie für die Weiterleitung von Notrufen verwendet, die dem Benutzerkonto zugeordnet ist, um Notrufe zu konfigurieren. 

- Wenn der Teams richtlinie für das Routing von Notrufen nicht abrufen kann, ist der Benutzer nicht für Notrufe aktiviert.


### <a name="dynamic-emergency-calling-for-direct-routing"></a>Dynamische Notrufe für Direct Routing

Dynamische Notrufe für Direct Routing bieten die Möglichkeit zum Konfigurieren und Weiterleiten von Notrufen basierend auf der aktuellen Position des Teams Clients. Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden Public Safety Answering Point (PSAP) oder zum Benachrichtigen der Mitarbeiter des Sicherheitsdesks hängt vom Land ab, in dem der Benutzer Teams wird.

Bei Direct Routing-Benutzern wird die dynamische Position für Notrufe über das Routing nur wie folgt in den USA unterstützt:

-   Wenn ein Teams-Client für einen US-Direct Routing-Benutzer dynamisch eine Notfalladresse in den USA abruft, wird diese Adresse für das Notfallrouting verwendet, und der Anruf wird automatisch an das PSAP im Dienstbereich der Adresse geroutet.

-   Wenn ein Teams-Client für einen Us-amerikanischen Direct Routing-Benutzer nicht dynamisch eine Notfalladresse in den USA abruft, wird der Anruf angezeigt, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

Die dynamische Position für Notrufe wird in Kanada genauso wie in den USA unterstützt. Ausnahme: Alle Notrufe werden national vor der Übertragung an das PSAP angezeigt.

Weitere Informationen finden Sie unter [Konfigurieren dynamischer Notrufe.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing-for-direct-routing"></a>Routing von Notrufen für direktes Routing

Die Richtlinie für das Routing von Notrufen für Direct Routing verweist auf eine Online-PSTN-Verwendung, die über die geeignete Direct Routing-Konfiguration verfügen muss, damit Notrufe ordnungsgemäß an die entsprechenden PSTN-Gateways weiterleiten werden. Insbesondere müssen Sie sicherstellen, dass onlineVoiceRoute für die Notrufzeichenfolge verfügbar ist. Weitere Informationen finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md) 

> [!NOTE]
> Teams Kunden die "+"-Anmeldung nicht mehr vor den Notrufnummern erhalten; d. h., +911. Daher wird Teams"+" vor der Nummer 911 nicht mehr an Notrufe senden. Stellen Sie sicher, dass ihre Sprachroutenmuster diese Änderung widerspiegeln.

Die Möglichkeit zum dynamischen Weiterleiten von Notrufen für Direct Routing-Benutzer hängt vom Notrufnetzwerk in einem bestimmten Land ab. Es stehen zwei Lösungen zur Verfügung:

- [Anbieter für Notfallroutingdienste (nur USA)](#emergency-routing-service-providers)
- [Notfall-Standortidentifikationsnummer-Anwendungen](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>Anbieter für Notfallroutingdienste

In den USA gibt es zahlreiche zertifizierte Anbieter für Notfall-Routingdienste (Emergency Routing Service Providers, ERSPs), die Notrufe automatisch basierend auf der Position des Anrufers weiterleiten können.

- Wenn ein Anbieter für Notfallroutingdienste in eine Direct Routing-Bereitstellung integriert ist, werden Notrufe mit dynamisch angeschafften Standort automatisch an den öffentlichen Sicherheits-Antwortpunkt (Public Safety Answering Point, PSAP) geroutet, der diese Position einnimmt.

-  Notrufe ohne dynamisch erfassten Standort werden zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf anhand des aktualisierten Standorts mit der entsprechenden Rettungszentrale verbunden wird.

Weitere Informationen finden Sie unter Für Direct Routing zertifizierte [Session Border Controller.](direct-routing-border-controllers.md)


#### <a name="emergency-location-identification-number-applications"></a>Notfall-Standortidentifikationsnummer-Anwendungen

Session Border Controller (SBCs) können ELIN-Anwendungen (Emergency Location Identification Number) enthalten. Wenn eine SBC ELIN-Anwendung in eine Direct Routing-Bereitstellung integriert ist, müssen Sie die Notfalladressen und zugehörigen Telefonnummern in der ELIN-Anwendung konfigurieren und dann die ELIN-Einträge in die Datenbank für Notrufe im jeweiligen PSTN hochladen. Teams Notfallstandorte mit einem ELIN-Bezeichner müssen mit denen innerhalb der ELIN-Anwendung übereinstimmen.

Wenn ein Notruf mit dynamisch erfassten Standort an die entsprechende SBC-Anwendung geroutet wird, gilt die ELIN-Anwendung:

- Analysiert den Notfallstandort des Anrufers.
- Passt die Position an einen ELIN-Datensatz an.
- Ersetzt die Rufnummer des Notrufs durch die ELIN-Telefonnummer.
- Leitet den Aufruf an das PSAP weiter, in dem dieser Standort verwendet wird, und dann rufen die Verteiler den Standort aus dem hochgeladenen ELIN-Eintrag ab.

Nach einem Rückruf bei der Notrufnummer wird die ELIN-Anwendung die als Nummernersetzung bezeichnete Umkehrung auf die des ursprünglichen Notrufdiensts umdrehen. 

Weitere Informationen finden Sie unter Für Direct Routing zertifizierte [Session Border Controller.](direct-routing-border-controllers.md)


## <a name="security-desk-notification"></a>Benachrichtigung des Security Desk

Die Benachrichtigung des Sicherheitsdesks ist sowohl bei Microsoft-Anrufplänen als Verbinden als auch bei Direct-Routing verfügbar.

Sie verwenden eine Teams-Richtlinie für Notrufe (TeamsEmergencyCallingPolicy), um zu konfigurieren, wer während eines Notrufs benachrichtigt werden soll und wie sie benachrichtigt werden sollen: nur chatten, ein- und stummgeschaltete Telefonkonferenzen oder Ein- und Stummschaltungen, jedoch mit der Möglichkeit der Stummschaltung. Sie können auch eine externe PSTN-Nummer eines Benutzers oder einer Gruppe angeben, der angerufen und an dem Notruf teilnehmen soll. Beachten Sie, dass die PstN-Partei die Stummschaltung nicht wieder aufschaltungen darf.

Eine Richtlinie für Notrufe kann einem Benutzerkonto Teams, einem Netzwerkstandort zugewiesen oder beiden zugewiesen werden.  Wenn ein Teams startet oder eine Netzwerkverbindung ändert, führt Teams eine Suche der Netzwerkwebsite aus, an der sich der Client befindet:

- Wenn einer Netzwerkwebsite eine Richtlinie für Notrufe zugeordnet ist, wird die Websiterichtlinie zum Konfigurieren der Benachrichtigung des Sicherheitsdesks verwendet.

- Wenn der Website keine Richtlinie für Notrufe zugeordnet ist oder der Client an einem nicht definierten Standort verbunden ist, wird die Dem Benutzerkonto zugeordnete Richtlinie für Notrufe verwendet, um die Benachrichtigung des Security Desk zu konfigurieren.  

- Wenn der Teams eine Richtlinie für Notrufe nicht abrufen kann, ist der Benutzer nicht für Benachrichtigungen des Sicherheitsdesks aktiviert.

Während eines Notrufs wird ein Sicherheits desk zu dem Anruf konferenziert, und die Benutzererfahrung des Sicherheitsdesks wird anhand der Richtlinie für Teams Notrufe gesteuert. Mit jedem Mitglied der Sicherheitsstelle wird ein Gruppenchat gestartet, und der Standort des Notrufers wird über eine wichtige Benachrichtigung freigegeben.  Wenn eine Konferenzoption als Teil der Richtlinie konfiguriert ist, wird jeder Benutzer des Sicherheitsdesks zusätzlich als Teil der Konferenz aufgerufen.

    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Richtlinien für das Routing von Notrufen ](manage-emergency-call-routing-policies.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für den Benutzer](assign-change-emergency-location-user.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
