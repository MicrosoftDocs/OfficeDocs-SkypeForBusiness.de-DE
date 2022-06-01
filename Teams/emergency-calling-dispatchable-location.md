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
description: Erfahren Sie, wie Microsoft versandbare Standortinformationen unterstützt, um Notrufe zu unterstützen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e45b5a18d8acd09714ebedd40a722bcbd152fc3c
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823537"
---
# <a name="emergency-addresses-for-remote-locations"></a>Notfalladressen für Remotestandorte

In diesem Artikel wird die Unterstützung von Microsoft für 911-Standortinformationen für Notrufe in der USA beschrieben. Diese Unterstützung stellt sicher, dass die präzisesten versandbaren Standortinformationen für Teams Benutzer, die Notrufe tätigen, bereitgestellt werden. Unabhängig vom Standort des Anrufers – vor Ort oder bei der Arbeit von zu Hause aus – müssen die Standortinformationen eines Anrufers, die an den Public Safety Answering Point (PSAP) gesendet werden, korrekt sein.

Dieser Artikel enthält Informationen zur Einhaltung des RAY BAUM-Gesetzes für Mehrleitungstelefonsysteme (MLTS) durch Microsoft. Mit dem RAY BAUM-Gesetz werden die Gesetzlichen Anforderungen des Kari erweitert, die Anfang 2021 in Kraft gelaufen sind. Weitere Informationen zum RAY BAUM-Gesetz und zum Kari-Gesetz finden Sie unter [Dispatchable Location for 911 Calls](https://www.fcc.gov/911-dispatchable-location) and [Multi-line Telephone Systems – Kari es Law und RAY BAUM es Act 911 Direct Dialing, Notification, and Dispatchable Location Requirements](https://www.fcc.gov/mlts-911-requirements). 

Benutzer, die zu Hause arbeiten, können jetzt ggf. eigene Notfalladressen festlegen. In diesem Artikel wird beschrieben, wie Sie Benutzerrichtlinien so konfigurieren können, dass Ihre Endbenutzer ihre Notfalladressen festlegen können.

Obwohl diese Informationen für Notrufe 911 im USA gelten, werden vom Benutzer eingegebene Standorte auch an das Screening-Center in Kanada übermittelt.

Dieser Artikel enthält die folgenden Abschnitte:

- [Unterstützung für Standortinformationen für Notrufe](#support-for-emergency-calling-location-information)
- [Standortrangfolge](#location-precedence)
- [Klassifizierung und Routing von Notfalladressen](#emergency-address-classification-and-routing)
- [Endbenutzern die Konfiguration ihrer Notfalladresse ermöglichen](#enable-end-users-to-configure-their-emergency-address)
- [Hinweise und Einschränkungen](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Unterstützung für Standortinformationen für Notrufe

Um diese Anforderungen zu unterstützen, verwendet Teams die vom jeweiligen Betriebssystem bereitgestellten Standortdienste, um eine Adresse vorzuschlagen – sofern die Berechtigung vom Administrator oder Benutzer erteilt wurde. Der Endbenutzer kann den Speicherort einer vorgeschlagenen Adresse bestätigen, bearbeiten oder manuell eine neue Adresse eingeben. Eine bestätigte, bearbeitete oder manuell eingegebene Adresse wird dann auf dem Teams-Client gespeichert, sodass die vom Benutzer bestätigte Adresse automatisch verwendet wird, wenn der Client mit diesem Netzwerk verbunden ist. Die vom Benutzer gespeicherten Adressen werden automatisch gelöscht, wenn der Teams Client abgemeldet ist.


## <a name="location-precedence"></a>Standortrangfolge

Notfalladressen für Teams können nach verschiedenen Typen kategorisiert werden. Die folgende Liste zeigt die Standortrangfolge, die beim Wählen einer Notrufnummer verwendet wird:

1. Eine dynamisch erworbene Adresse, die von der Mandantenverwaltung im Standortinformationsdienst definiert wird.

2. Eine Adresse, die der Endbenutzer bestätigt, bearbeitet oder manuell eingegeben hat, die dem lokalen Netzwerk zugeordnet ist, mit dem der Teams Client verbunden ist.

3. Eine vom Betriebssystem automatisch vorgeschlagene Adresse.

4. Eine Adresse, die der Administrator dem Benutzer statisch zuweist.


## <a name="emergency-address-classification-and-routing"></a>Klassifizierung und Routing von Notfalladressen

In der folgenden Tabelle sind die Arten von Notfalladressen und zugehörigen Routingmethoden für jeden Typ aufgeführt: Ob der Anruf automatisch an das dienstende PSP weitergeleitet oder auf Genauigkeit überprüft wird, bevor er an den dienstenden PSAP weitergeleitet wird. Dieses Routingverhalten wird in der USA für alle Anrufplanbenutzer, Telefonieanbieter Partner und Direct Routing-zertifizierten Notrufdienstanbieter unterstützt.


| Typ der Notfalladresse | Notfallroutingmethode |
| :------------| :-------|
| Dynamisch erworbene Notfalladresse, die vom Administrator definiert wurde. | Direkt zu PSAP. |
| Notfalladresse, die vom Betriebssystem **ohne Bestätigung für die Genauigkeit** des Benutzers abgerufen wurde. | Abgeschirmt und an PSAP übertragen. |
| Vom Betriebssystem abgerufene Notfalladresse **mit Bestätigung für die Genauigkeit** des Benutzers.| Direkt zu PSAP. |
| Notfalladresse, die vom Betriebssystem abgerufen und vom Benutzer bearbeitet und bestätigt wird. | Abgeschirmt und an PSAP übertragen. |
| Notfalladresse eingegeben und vom Benutzer bestätigt. | Abgeschirmt und an PSAP übertragen. |
| Notfalladresse, die dem Benutzer/der Nummer statisch zugewiesen ist. | Abgeschirmt und an PSAP übertragen. |
| Null | Abgeschirmt und an PSAP übertragen. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Endbenutzern die Konfiguration ihrer Notfalladresse ermöglichen

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **VoIP-Notfallrichtlinien** > .
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen für die Notrufrichtlinie ein, z. B. "E911WFH".
4. Aktivieren Sie den **Nachschlagemodus für externe Speicherorte**.
5. Wählen Sie **"Übernehmen" aus**.

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Notrufrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>Verwendung von PowerShell

Um dieses Feature für Ihre Endbenutzer zu aktivieren, verwenden Sie das New-CsTeamsEmergencyCallingPolicy PowerShell-Cmdlet, und legen Sie den Parameter ExternalLocationLookupMode auf "Enabled" fest. Sehen Sie sich das folgende Beispiel an: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Nachdem Sie dieses Feature für Ihre Endbenutzer aktiviert haben, kann der Benutzer auf der Registerkarte "Anrufe" eine Notfalladresse hinzufügen, bearbeiten oder bestätigen und die Adresse anzeigen, nachdem sie festgelegt wurde. Weitere Informationen dazu, wie Endbenutzer Standortdienste festlegen können, finden Sie unter [Work from Home Emergency 911: Aktivieren von Standortdiensten](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

Auf Windows können Sie den Windows Standortdienst verwalten und festlegen, ob Anwendungen Zugriff auf den Standort haben, mithilfe von Gruppenrichtlinien oder mithilfe der [verwaltung mobiler Geräte (Mobile Device Management, MDM).](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)

Weitere Informationen zu Windows Standortdienst finden Sie [unter Windows Standortdienst und Datenschutz](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Hinweise und Einschränkungen

Berücksichtigen Sie dabei Folgendes:

- Die beschriebene Arbeit von zu Hause aus ist für Teams Desktop auf Windows und Mac geeignet.

- Teams Telefone unterstützen die Arbeit von zu Hause aus nicht.

- Teams Mobile unterstützt die automatische Standorterkennung, aber nicht die beschriebene Benutzererfahrung.

- Datenschutzeinstellungen können mit der automatischen Standorterkennung in Konflikt stehen – Mobile Geräteverwaltung-Systeme können verwendet werden.


## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)

- [Arbeit von Home Emergency 911: Standortdienste aktivieren](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

