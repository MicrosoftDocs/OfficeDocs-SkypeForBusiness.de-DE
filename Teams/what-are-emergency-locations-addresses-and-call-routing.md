---
title: Planen und Verwalten von Notrufen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Erfahren Sie mehr über Notrufe, einschließlich Informationen zu Notfalladressen, Notrufen und dynamischen Notrufen.
ms.openlocfilehash: ef3f9bcf3a8eab2edc4cff4d99c31a1eb4028cb26a32f40adf4e0eaaa68deeee
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849080"
---
# <a name="manage-emergency-calling"></a>Verwalten von Notrufen

In diesem Artikel werden die Konzepte beschrieben, die Sie kennen müssen, um Notrufe zu verwalten, einschließlich Informationen zu Notfalladressen, dynamischen Notfalladressen und &mdash; Notrufrouting. In diesem Artikel wird die folgende Terminologie verwendet:

- **Notfalladresse** – Eine Anschrift, die physische oder Anschrift eines Orts Ihres &mdash; Unternehmens.

  Beispielsweise wird die Adresse  *12345 North Main Street, Redmond, WA 98052, WA 98052* verwendet, um Notrufe an die entsprechenden Einsatzkräfte weiter zu senden und den Standort des Notrufers zu suchen.

- **Ort** – In der Regel ein Stockwerk, gebäude, wing oder office number. Der Ort ist einer Notfalladresse zugeordnet, um einen exakten Standort innerhalb eines Gebäudes zu erhalten. Sie können eine unbegrenzte Anzahl von Orten mit einer Notfalladresse verknüpft haben. Wenn Ihre Organisation z. B. über mehrere Gebäude verfügt, können Sie Für jedes Gebäude und jedes Stockwerk in jedem Gebäude Ortsinformationen erstellen.  

- **Notfallstandort** – Ein Standort ist eine Adresse mit &mdash; optionalem Ort. Wenn Ihr Unternehmen über mehrere physische Standorte verfügt, benötigen Sie wahrscheinlich mehrere Notfallstandorte. 

  Wenn Sie eine Notfalladresse erstellen, wird automatisch eine eindeutige Standort-ID für diese Adresse erstellt.  Wenn Sie beispielsweise einer Notfalladresse einen Ort hinzufügen, wenn Sie einer Gebäudeadresse einen Boden hinzufügen, wird eine Standort-ID für die Kombination aus Notfalladresse und &mdash; &mdash; -ort erstellt.  In diesem Beispiel gibt es zwei Standort-IDs: eine für die Adresse; eine Adresse für die beigetretene Adresse und den zugehörigen Ort.

  Wenn Sie einem Benutzer oder einer Website einen Notfallstandort zuweisen, wird diese eindeutige Standort-ID dem Benutzer oder der Website zugeordnet.

- **Registrierte Adresse** – Eine Notfalladresse, die jedem Anrufplanbenutzer zugewiesen wird; wird gelegentlich auch als statische Notfalladresse oder Datensatzadresse bezeichnet.  (Registrierte Adressen gelten nicht für Direct Routing-Benutzer.)

Sie erstellen Notfalladressen für Anrufplanbenutzer über das Teams Admin Center.  

>[!Note]
>Es gibt einige Unterschiede bei der Verwaltung von Notrufen, je nachdem, ob Sie Telefonsystem Anrufpläne verwenden oder Telefonsystem Direct Routing für Ihre PSTN-Verbindung verwenden. Diese Überlegungen werden in diesem Artikel beschrieben.

## <a name="emergency-address-validation"></a>Überprüfung von Notfalladressen

Um einem Benutzer oder einer Netzwerk-ID eine Notfalladresse zuzuordnen, müssen Sie sicherstellen, dass die Notfalladresse als "überprüft" gekennzeichnet ist.  Mit der Adressvalidierung wird sichergestellt, dass die Adresse legitim ist und nach derEntierung nicht mehr geändert werden kann. 

Wenn Sie eine Notfalladresse mithilfe der Funktion für die Suche nach Adresskarten im Teams Admin Center definieren, wird die Adresse automatisch als überprüft markiert. Sie können eine überprüfte Notfalladresse nicht ändern. Wenn sich das Format oder die Darstellung der Adresse ändert, müssen Sie daher eine neue Adresse mit dem aktualisierten Format erstellen.


## <a name="emergency-address-geo-codes"></a>Notfalladressen-Geocodes

Jeder Notfalladresse kann ein Geocode (Breiten- und Längengrad) zugeordnet sein. Diese Geocodes werden in einigen Ländern verwendet, um das Routing von Notrufen mit dynamischen Standorten zu unterstützen. 

Wenn Sie eine Notfalladresse mithilfe der Funktion für die Suche nach Adresskarten im Teams Admin Center definieren, wird der Geocode automatisch einer Notfalladresse zugeordnet. Sie können einer Adresse auch Geocodes zuordnen, wenn Sie die Adresse mithilfe von PowerShell definieren. Microsoft empfiehlt jedoch, dass Sie Notfalladressen für Anrufplan erstellen, indem Sie die Kartensuche im Teams Admin Center verwenden, um sicherzustellen, dass die Adressen formatiert, überprüft und über die entsprechenden Geocodes verfügen.  

>[!Important]
>Um einer Netzwerk-ID einen Notfallstandort für dynamische Notrufe zuzuordnen, muss die Notfalladresse einen geeigneten Geocode enthalten.


## <a name="considerations-for-calling-plans"></a>Überlegungen für Anrufpläne

Um herauszufinden, ob Anrufpläne in Ihrer Region verfügbar sind, lesen Sie Verfügbarkeit von Ländern und [Regionen für Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).


### <a name="emergency-call-enablement"></a>Aktivierung eines Notrufs

Jeder Anrufplanbenutzer wird automatisch für Notrufe aktiviert und muss über eine registrierte Notfalladresse verfügen, die der zugewiesenen Telefonnummer zugeordnet ist. 

Wann der Standort der Telefonnummer zugeordnet werden muss, hängt vom Land/der Region ab:

- In den USA und Kanada beispielsweise ist ein Notfallstandort erforderlich, wenn einem Benutzer eine Nummer zugewiesen wird.

- Für andere Länder – wie etwa in Europa, dem Nahen Osten und Afrika (EMEA) – ist ein Notfallstandort erforderlich, wenn Sie die Telefonnummer von Microsoft 365 oder Office 365 erhalten oder von einem anderen Dienstanbieter oder Netzbetreiber übertragen werden.

### <a name="dynamic-emergency-calling"></a>Dynamische Notruffunktion

Dynamische Notrufe für Microsoft-Anrufpläne bieten die Möglichkeit, Notrufe basierend auf der aktuellen Position des Teams zu konfigurieren und zu routen. Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden Public Safety Answering Point (PSAP) oder zum Benachrichtigen von Mitarbeitern des Sicherheitsdesks hängt vom Land ab, in dem der Benutzer Teams wird.  

Bei Anrufplanbenutzern wird der dynamische Standort für das Routing von Notrufen nur wie folgt in den USA unterstützt. (Informationen zu dynamischen Notrufen und Direct Routing finden Sie unter [Überlegungen für Direct-Routing.](#considerations-for-direct-routing)

- Wenn ein Teams-Client für einen Benutzer eines Anrufplans für die USA dynamisch eine Notfalladresse in den USA abruft, wird diese Adresse anstelle der registrierten Adresse für das Notfallrouting verwendet, und der Anruf wird automatisch an das PSAP im Dienstbereich der Adresse umleitig.

- Wenn ein Teams-Client für einen Anrufplanbenutzer in den USA nicht dynamisch eine Notfalladresse abruft, wird die registrierte Notfalladresse verwendet, um den Anruf zu bildschirm- und routen zu unterstützen. Der Anruf wird jedoch angezeigt, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

In den USA müssen Sie die Adresse, die Zu den Notfallstandorten gehört, die Netzwerk-IDs zugewiesen sind, konfigurieren und &mdash; die zugehörigen Geocodes enthalten. Weitere Informationen finden Sie unter [Planen und Konfigurieren von dynamischen Notrufen.](configure-dynamic-emergency-calling.md)


### <a name="emergency-call-routing"></a>Routing von Notrufen

Wenn ein Teams Anrufplan-Benutzer eine Notfallnummer wählt, hängt die Art und Weise, wie der Anruf an das PSAP-System umgerufen wird, von Folgendem ab:

- Die Notfalladresse wird vom Client dynamisch Teams bestimmt.

- Die Notfalladresse soll die registrierte Adresse sein, die der Telefonnummer des Benutzers zugeordnet ist.

- Das Notrufnetzwerk dieses Landes.

  **In den USA:**

  - Wenn sich Teams-Client an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client automatisch an das PSAP geroutet, das den geografischen Standort verwendet. 

  - Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfallstandort befindet, werden Notrufe von diesem Client von einem nationalen Anrufcenter angezeigt, um den Standort des Anrufers zu ermitteln, bevor der Anruf an den PSAP-Dienst mit diesem geografischen Standort übertragen wird.

  - Wenn ein Notrufer seinen Notfallstandort nicht auf das Prüfungscenter aktualisieren kann, wird der Anruf an das PSAP übermittelt, das die registrierte Adresse des Anrufers verwendet.

  **In Kanada, Irland** und dem Vereinigten Königreich werden Notrufe zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf mit dem entsprechenden Verteilercenter verbunden wird. 

  **In Frankreich, Deutschland und Spanien** werden Notrufe unabhängig vom Standort des Anrufers direkt an das PSAP um die der Nummer zugeordnete Notfalladresse gesendet.

  **In den Niederlanden** werden Notrufe unabhängig vom Standort des Anrufers direkt an das PSAP für die lokale Ortswahl der Rufnummer gesendet.

  **In Australien** werden Notfalladressen vom Netzbetreiberpartner konfiguriert und geroutet.

  **In Japan** werden Notrufe nicht unterstützt.


Weitere Informationen finden Sie unter:

- [Anrufpläne](calling-plan-landing-page.md)

- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Überlegungen zum direkten Routing

Wenn Anrufpläne in Ihrer Region nicht verfügbar sind oder Sie Ihren vorhandenen Netzbetreiber behalten möchten, ziehen Sie [Direct Routing in Betracht.](direct-routing-landing-page.md) Weitere Informationen finden Sie unter [Konfigurieren von Direktes Routing und](direct-routing-configure.md) Verwalten von Richtlinien für das Routing von [Notrufen.](manage-emergency-call-routing-policies.md)

### <a name="emergency-call-enablement-and-configuration"></a>Aktivieren und Konfigurieren von Notrufen

Sie müssen Richtlinien für Notrufe für Direct Routing-Benutzer definieren, indem Sie eine Richtlinie für das Routing von Teams-Notrufen (TeamsEmergencyCallRoutingPolicy) verwenden, um Notrufnummern und das zugeordnete Routingziel zu definieren. (Beachten Sie, dass registrierte Notfallstandorte für Direct Routing-Benutzer nicht unterstützt werden.)

Sie können eine Richtlinie für die Weiterleitung von Notrufen einem Teams Direct Routing-Benutzerkonto, einem Netzwerkstandort oder beiden zuweisen. Wenn ein Teams gestartet oder eine Netzwerkverbindung ändert, führt Teams eine Suche der Netzwerkwebsite durch, auf der sich der Client befindet:

- Wenn der Website eine Richtlinie für die Weiterleitung von Notrufen zugeordnet ist, wird die Websiterichtlinie zum Konfigurieren von Notrufen verwendet.

- Wenn der Website keine Richtlinie für die Weiterleitung von Notrufen zugeordnet ist, wenn der Client an einem nicht definierten Standort verbunden ist oder die gewählte Nummer keiner der Notrufnummern in der Der Website zugeordneten Routingrichtlinie für Notrufe zu entsprechen, wird die Richtlinie für die Weiterleitung von Notrufen verwendet, die dem Benutzerkonto zugeordnet ist, um Notrufe zu konfigurieren. 

- Wenn der Teams die Routingrichtlinie für Notrufe nicht abrufen kann, ist der Benutzer nicht für Notrufe aktiviert.

### <a name="dynamic-emergency-calling"></a>Dynamische Notruffunktion

Teams-Clients für Direct Routing-Benutzer können eine dynamische Notfalladresse erwerben, mit der Anrufe basierend auf der Position des Anrufers dynamisch weiterleiten werden können. Weitere Informationen finden Sie unter [Konfigurieren dynamischer Notrufe.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing"></a>Routing von Notrufen

Die Richtlinie für das Routing von Notrufen verweist auf eine Online-PSTN-Nutzung, die über die geeignete Direct Routing-Konfiguration verfügen muss, um die Notrufe ordnungsgemäß an die entsprechenden PSTN-Gateways weiterleiten zu können. Insbesondere müssen Sie sicherstellen, dass onlineVoiceRoute für die Notrufzeichenfolge verfügbar ist. Weitere Informationen finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md) 

(Hinweis: Teams-Clients haben die +-Anmeldung vor Notfallnummern auf ähnliche Weise wie der Client Skype for Business, d. h. +911. Dieses Verhalten wird in den kommenden Monaten geändert, sodass Teams Notrufe nicht mehr ein "+" vor der Nummer senden. das heißt, 911.)

Die Möglichkeit zum dynamischen Weiterleiten von Notrufen für Direct Routing-Benutzer hängt vom Notrufnetzwerk in einem bestimmten Land ab. Es stehen zwei Lösungen zur Verfügung:

- Anbieter für Notfallroutingdienste (nur USA) 
- Gatewayanwendungen mit Notfall-Standortidentifikationsnummer (Emergency Location Identification Number, ELIN)

#### <a name="emergency-routing-service-providers"></a>Anbieter für Notfallroutingdienste

In den USA gibt es zahlreiche zertifizierte Anbieter für Notfall-Routingdienste (Emergency Routing Service Providers, ERSPs), die Notrufe automatisch basierend auf der Position des Anrufers weiterleiten können.

- Wenn ein Anbieter für Notfallroutingdienste in eine Direct Routing-Bereitstellung integriert ist, werden Notrufe mit dynamisch angeschafften Standort automatisch an den öffentlichen Sicherheits-Antwortpunkt (Public Safety Answering Point, PSAP) geroutet, der diese Position einnimmt.

-  Notrufe ohne dynamisch erfassten Standort werden zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf anhand des aktualisierten Standorts mit der entsprechenden Rettungszentrale verbunden wird.

Weitere Informationen finden Sie unter Für Direct Routing zertifizierte [Session Border Controller.](direct-routing-border-controllers.md)


#### <a name="emergency-location-identification-number-elin-applications"></a>ELIN-Anwendungen (Emergency Location Identification Number)

Session Border Controller (SBCs) können ELIN-Anwendungen (Emergency Location Identification Number) enthalten. Wenn eine SBC ELIN-Anwendung in eine Direct Routing-Bereitstellung integriert ist, müssen Sie die Notfalladressen und zugehörigen Telefonnummern in der ELIN-Anwendung konfigurieren und dann die ELIN-Einträge in die Datenbank für Notrufe im jeweiligen PSTN hochladen.  Teams Notfallstandorte mit einem ELIN-Bezeichner müssen mit denen innerhalb der ELIN-Anwendung übereinstimmen.

Wenn ein Notruf mit dynamisch erfassten Standort an die entsprechende SBC-Anwendung geroutet wird, gilt die ELIN-Anwendung:

- Analysiert den Notfallstandort des Anrufers.
- Passt die Position an einen ELIN-Datensatz an.
- Ersetzt die Rufnummer des Notrufs durch die ELIN-Telefonnummer.
- Leitet den Aufruf an das PSAP weiter, in dem dieser Standort verwendet wird, und dann rufen die Verteiler den Standort aus dem hochgeladenen ELIN-Eintrag ab.

Nach einem Rückruf bei der Notrufnummer wird die ELIN-Anwendung die als Nummernersetzung bezeichnete Umkehrung auf die des ursprünglichen Notrufdiensts umdrehen. 

Weitere Informationen finden Sie unter Für Direct Routing zertifizierte [Session Border Controller.](direct-routing-border-controllers.md)


## <a name="security-desk-notification"></a>Benachrichtigung des Security Desk

Die Benachrichtigung des Sicherheitsdesks ist sowohl bei Microsoft-Anrufplänen als Telefonsystem Direct Routing verfügbar.

Sie verwenden eine Teams-Richtlinie für Notrufe (TeamsEmergencyCallingPolicy), um zu konfigurieren, wer während eines Notrufs benachrichtigt werden soll und wie sie benachrichtigt werden sollen: nur chatten, ein- und stummgeschaltete Telefonkonferenzen oder Telefonkonferenzen mit der Möglichkeit, die Stummschaltung auf stumm zu setzen.  Sie können auch eine externe PSTN-Nummer eines Benutzers oder einer Gruppe angeben, der angerufen und an dem Notruf teilnehmen soll. 

Eine Richtlinie für Notrufe kann einem Benutzerkonto Teams, einem Netzwerkstandort zugewiesen oder beiden zugewiesen werden.  Wenn ein Teams startet oder eine Netzwerkverbindung ändert, führt Teams eine Suche der Netzwerkwebsite aus, auf der sich der Client befindet:

- Wenn einer Netzwerkwebsite eine Richtlinie für Notrufe zugeordnet ist, wird die Websiterichtlinie zum Konfigurieren der Benachrichtigung des Sicherheitsdesks verwendet.

- Wenn der Website keine Richtlinie für Notrufe zugeordnet ist oder der Client an einem nicht definierten Standort verbunden ist, wird die Dem Benutzerkonto zugeordnete Richtlinie für Notrufe verwendet, um die Benachrichtigung des Security Desk zu konfigurieren.  

- Wenn der Teams keine Richtlinie für Notrufe erhalten kann, ist der Benutzer nicht für Benachrichtigungen des Sicherheitsdesks aktiviert.

Während eines Notrufs wird ein Sicherheits desk zu dem Anruf konferenziert, und die Benutzererfahrung des Sicherheitsdesk-Benutzers wird anhand der Richtlinie für Teams Notrufe gesteuert. Mit jedem Mitglied der Sicherheitsstelle wird ein Gruppenchat gestartet, und der Standort des Notrufers wird über eine wichtige Benachrichtigung freigegeben.  Wenn eine Konferenzoption als Teil der Richtlinie konfiguriert ist, wird jeder Benutzer des Sicherheitsdesks zusätzlich als Teil der Konferenz aufgerufen.

    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Richtlinien für das Routing von Notrufen ](manage-emergency-call-routing-policies.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Notfallstandorts für den Benutzer](assign-change-emergency-location-user.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
