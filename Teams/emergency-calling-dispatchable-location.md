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
ms.openlocfilehash: d80854fc36e6914ba48e8993d298c75b136bd06f
ms.sourcegitcommit: 4af3638637456f21bc97f510ed9d2f7ff2da07e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2022
ms.locfileid: "63660710"
---
# <a name="emergency-addresses-for-remote-locations"></a>Notfalladressen für Remotestandorte

In diesem Artikel wird der Support von Microsoft für Informationen zum Standort für Notrufe in den USA beschrieben. Durch diese Unterstützung wird sichergestellt, dass die präzisesten Standortinformationen für die Benutzer bereitgestellt werden, Teams Notrufe abrufen. Unabhängig vom Standort des Anrufers (vor Ort oder von zu Hause aus) müssen die Standortinformationen eines Anrufers, die an den Public Safety Answering Point (PSAP) gesendet werden, genau sein.

Dieser Artikel enthält Informationen zur Compliance von Microsoft mit RAY BAUM's Act for Multi Line Telephone Systems (MLTS). Mit RAY BAUM'S Act werden die Law-Anforderungen von Kari erweitert, die Anfang 2021 in Kraft gelaufen sind. Weitere Informationen zu RAY BAUM's Act und Karis Law finden Sie unter [Dispatchable Location for 911](https://www.fcc.gov/911-dispatchable-location) Calls and [Multi-line Telephone Systems – Kari's Law and RAY BAUM S Act 911 Direct Dialing, Notification and Dispatchable Location Requirements](https://www.fcc.gov/mlts-911-requirements). 

Benutzer, die zu Hause arbeiten, können jetzt ihre eigenen Notfalladressen festlegen (falls zutreffend). In diesem Artikel wird beschrieben, wie Sie Benutzerrichtlinien so konfigurieren können, dass Ihre Endbenutzer ihre Notfalladressen festlegen können.

Diese Informationen gelten zwar für Notrufe in den USA, aber von Benutzern eingegebene Standorte werden auch an das Prüfungscenter in Kanada übermittelt.

Dieser Artikel enthält die folgenden Abschnitte:

- [Unterstützung für Standortinformationen für Notrufe](#support-for-emergency-calling-location-information)
- [Rangfolge des Standorts](#location-precedence)
- [Klassifizierung und Weiterleitung von Notfalladressen](#emergency-address-classification-and-routing)
- [Ermöglichen der Konfiguration der Notfalladresse für Endbenutzer](#enable-end-users-to-configure-their-emergency-address)
- [Hinweise und Einschränkungen](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Unterstützung für Standortinformationen für Notrufe

Zur Unterstützung dieser Anforderungen verwendet Teams die Standortdienste, die vom jeweiligen Betriebssystem bereitgestellt werden, um eine Adresse vorschlagen – sofern vom Administrator oder Benutzer die entsprechende Berechtigung gewährt wurde. Der Endbenutzer kann den Standort einer vorgeschlagenen Adresse bestätigen, bearbeiten oder manuell eine neue Adresse eingeben. Eine bestätigt, bearbeitete oder manuell eingegebene Adresse wird dann auf dem Teams-Client gespeichert, sodass die vom Benutzer bestätigten Adresse automatisch verwendet wird, wenn der Client mit diesem Netzwerk verbunden ist. Die vom Benutzer gespeicherten Adressen werden automatisch gelöscht, wenn Teams-Client abge-


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

Um dieses Feature für Ihre Endbenutzer zu aktivieren, verwenden Sie das New-CsTeamsEmergencyCallingPolicy PowerShell-Cmdlet, und legen Sie den Parameter ExternalLocationLookupMode auf Aktiviert. Sehen Sie sich das folgende Beispiel an: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Nachdem diese Funktion für die Endbenutzer aktiviert wurde, kann der Benutzer auf der Registerkarte Anrufe eine Notfalladresse hinzufügen, bearbeiten oder bestätigen und die Adresse anzeigen, nachdem sie festgelegt wurde. Weitere Informationen dazu, wie Endbenutzer Standortdienste festlegen können, finden Sie unter Arbeit über den Notfall zu Hause [911: Aktivieren von Standortdiensten](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

Auf Windows können Sie den Windows-Standortdienst verwalten und bestimmen, ob Anwendungen auf den Speicherort zugreifen können, indem Sie eine Gruppenrichtlinie oder [MDM (Mobile Device Management](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation), Verwaltung mobiler Geräte) verwenden.

Weitere Informationen zu Windows Positionsdienst finden Sie unter Windows [positionsdienst und Datenschutz](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Hinweise und Einschränkungen

Berücksichtigen Sie dabei Folgendes:

- Die beschriebene Arbeitserfahrung von zu Hause aus gilt für Teams auf Windows und Mac.

- Teams-Telefone unterstützen die Arbeit von zu Hause aus nicht.

- Teams Mobile unterstützt die automatische Standorterkennung, jedoch nicht die beschriebene Benutzerfreundlichkeit.

- Datenschutzeinstellungen können mit der automatischen Standorterkennung im Konflikt stehen – Die Verwaltung mobiler Geräte kann verwendet werden.


## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)

- [Arbeit von Home Emergency 911: Standortdienste aktivieren](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

