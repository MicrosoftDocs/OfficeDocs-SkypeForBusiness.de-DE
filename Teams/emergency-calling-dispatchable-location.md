---
title: Notfalladressen für Remotestandorte
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Microsoft verteilbare Standortinformationen zur Unterstützung von Notrufen unterstützt.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7d241cee858d3ac19747be56b5a53e157b563f64
ms.sourcegitcommit: 05e7c8ac9d6d6f712742d08820d43118c8949bbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2021
ms.locfileid: "61323000"
---
# <a name="emergency-addresses-for-remote-locations"></a>Notfalladressen für Remotestandorte

In diesem Artikel wird der Support von Microsoft für Informationen zum Standort für Notrufe in den USA beschrieben. Durch diese Unterstützung wird sichergestellt, dass die präzisesten Standortinformationen für die Benutzer bereitgestellt werden, Teams Notrufe abrufen. Unabhängig vom Standort des Anrufers (vor Ort oder von zu Hause aus) müssen die Standortinformationen eines Anrufers, die an den Public Safety Answering Point (PSAP) gesendet werden, genau sein.

Dieser Artikel enthält Informationen zur Compliance von Microsoft mit RAY BAUM's Act for Multi Line Telephone Systems (MLTS). Mit RAY BAUM'S Act werden die Law-Anforderungen von Kari erweitert, die Anfang 2021 in Kraft gelaufen sind. Weitere Informationen zu RAY BAUM's Act und Karis Law finden Sie unter Verteilerfähige Position für [911-Anrufe](https://www.fcc.gov/911-dispatchable-location) und mehrstufige Telefonsysteme [– Kari's Law und Ray BAUM S Act 911 Direct Dialing, Notification und Dispatchable Location Requirements](https://www.fcc.gov/mlts-911-requirements). 

Benutzer, die zu Hause arbeiten, können jetzt ihre eigenen Notfalladressen festlegen (falls zutreffend). In diesem Artikel wird beschrieben, wie Sie Benutzerrichtlinien so konfigurieren können, dass Ihre Endbenutzer ihre Notfalladressen festlegen können.

Diese Informationen gelten zwar für Notrufe in den USA, aber von Benutzern eingegebene Standorte werden auch an das Prüfungscenter in Kanada übermittelt.

Dieser Artikel enthält die folgenden Abschnitte:

- [Unterstützung für Standortinformationen für Notrufe](#support-for-emergency-calling-location-information)
- [Rangfolge des Standorts](#location-precedence)
- [Klassifizierung und Weiterleitung von Notfalladressen](#emergency-address-classification-and-routing)
- [Ermöglichen der Konfiguration der Notfalladresse für Endbenutzer](#enable-end-users-to-configure-their-emergency-address)
- [Hinweise und Einschränkungen](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Unterstützung für Standortinformationen für Notrufe

Zur Unterstützung dieser Anforderungen verwendet Teams die Standortdienste, die vom jeweiligen Betriebssystem bereitgestellt werden, um eine Adresse vorschlagen – sofern vom Administrator oder Benutzer die entsprechende Berechtigung gewährt wurde. Der Endbenutzer kann den Standort einer vorgeschlagenen Adresse bestätigen, bearbeiten oder manuell eine neue Adresse eingeben. Eine bestätigt, bearbeitete oder manuell eingegebene Adresse wird dann auf dem Teams-Client gespeichert, sodass die vom Benutzer bestätigten Adressen automatisch verwendet werden, wenn der Client mit dem Netzwerk verbunden ist. Die vom Benutzer gespeicherten Adressen werden automatisch gelöscht, wenn Teams-Client angemeldet ist.


## <a name="location-precedence"></a>Rangfolge des Standorts

Notfalladressen für Teams können nach unterschiedlichen Typen kategorisiert werden. Die folgende Liste zeigt die Standortrangfolge, die beim Wählen einer Notfallnummer verwendet wird:

1. Eine dynamisch erworbene Adresse, die vom Mandanten verwaltet wird, die im Location Information Service verwaltet wird.

2. Eine Adresse, die der Endbenutzer bestätigt, bearbeitet oder manuell eingegeben hat und die dem lokalen Netzwerk zugeordnet ist, mit Teams der der Client verbunden ist.

3. Eine vom Betriebssystem automatisch vorgeschlagene Adresse.

4. Eine Adresse, die der Administrator dem Benutzer statisch zu weist.


## <a name="emergency-address-classification-and-routing"></a>Klassifizierung und Weiterleitung von Notfalladressen

Die folgende Tabelle enthält die Typen von Notfalladressen und zugeordneten Routingmethoden für jeden Typ: Ob der Anruf automatisch an das zugehörige PSAP geroutet oder auf Genauigkeit vor der Übertragung an das zugehörige PSAP angezeigt wird. Dieses Routingverhalten wird in den USA für alle Anrufplanbenutzer, Netzbetreiber Verbinden Partner und Anbieter zertifizierter Direct Routing-Notrufe unterstützt.


| Typ der Notfalladresse | Notfallroutingmethode |
| :------------| :-------|
| Dynamisch erworbene Notfalladresse, die vom Administrator definiert wurde. | Direkt zu PSAP. |
| Notfalladresse aus dem Betriebssystem ohne **Bestätigung der Genauigkeit durch** den Benutzer. | Bildschirm und Übertragen in PSAP. |
| Notfalladresse aus dem Betriebssystem mit **Bestätigung der Genauigkeit durch** den Benutzer.| Direkt zu PSAP. |
| Eine vom Betriebssystem erhaltene und vom Benutzer bearbeitete und bestätigte Notfalladresse. | Bildschirm und Übertragen in PSAP. |
| Vom Benutzer eingegebene und bestätigte Notfalladresse. | Bildschirm und Übertragen in PSAP. |
| Notfalladresse, die dem Benutzer/der Nummer statisch zugewiesen ist. | Bildschirm und Übertragen in PSAP. |
| Null | Bildschirm und Übertragen in PSAP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Ermöglichen der Konfiguration der Notfalladresse für Endbenutzer

Um dieses Feature für ihre Endbenutzer zu aktivieren, verwenden Sie das New-CsTeamsEmergencyCallingPolicy PowerShell-Cmdlet, und legen Sie den Parameter ExternalLocationLookupMode auf Aktiviert. Sehen Sie sich das folgende Beispiel an: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Nachdem diese Funktion für die Endbenutzer aktiviert wurde, kann der Benutzer auf der Registerkarte Anrufe eine Notfalladresse hinzufügen, bearbeiten oder bestätigen und die Adresse anzeigen, nachdem sie festgelegt wurde. 

Auf Windows können Sie den Windows-Positionsdienst verwalten und bestimmen, ob Anwendungen auf den Speicherort zugreifen können, indem Sie eine Gruppenrichtlinie oder [MDM (Mobile Device Management) verwenden.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)

Weitere Informationen zu Windows Positionsdienst finden Sie unter Windows [positionsdienst und Datenschutz](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Hinweise und Einschränkungen

Berücksichtigen Sie dabei Folgendes:

- Die beschriebene Arbeitserfahrung von zu Hause aus gilt für Teams auf Windows und Mac.

- Teams-Telefone unterstützen die Arbeit von zu Hause aus nicht.

- Teams mobile Geräte unterstützt die automatische Standorterkennung, jedoch nicht die beschriebene Benutzerfreundlichkeit.

- Datenschutzeinstellungen können mit der automatischen Standorterkennung im Konflikt stehen – Die Verwaltung mobiler Geräte kann verwendet werden.


## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)

