---
title: Verwalten der Teilnahmeerfahrung für Teams Besuche in mobilen Browsern
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: Erfahren Sie mehr über die Teilnahmeerfahrung für Teams virtuellen Besuche in mobilen Browsern.
ms.openlocfilehash: 6183fccce1c455ac46f4eb7c166530535d5dbbe8
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432687"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>Verwalten der Teilnahmeerfahrung für Teams Besuche in mobilen Browsern

Microsoft Teams erleichtert Personen die Teilnahme an Terminen auf ihren mobilen Geräten, ohne sie herunterladen Teams. Für eine nahtlose Erfahrung können die Teilnehmer über einen mobilen Browser an Terminen teilnehmen, z. B. Arztbesuche, Finanzberatungen, Dozentenbürozeiten und so weiter. Teilnehmer müssen die mobile Teams auf ihren mobilen Android- oder iOS-Geräten nicht installieren.

Bei der Teilnahme über einen mobilen Browser wird ein Teilnehmer, der einem Termin über ein mobiles Gerät beitritt, nicht zum Herunterladen Teams. Stattdessen wird Teams in einem mobilen Browser geöffnet, in dem der Teilnehmer **Jetzt** teilnehmen auswählen kann, um bei der Besprechung teilnehmen. Beachten Sie bei diesem Feature, dass Teams in einem mobilen Browser und nicht in der App geöffnet wird, wenn Teams bereits auf dem mobilen Gerät eines Teilnehmers installiert ist.

Derzeit ist die Teilnahme über einen mobilen Browser für Termine verfügbar, die wie folgt geplant werden:

- [Die Bookings-App](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- [Microsoft Teams EHR-Connector (Electronic Health Records)](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>Einrichten der Teilnahme über einen mobilen Browser

### <a name="appointments-scheduled-through-the-bookings-app"></a>Termine, die über die Bookings-App geplant wurden

Planer in Ihrer Organisation können dieses Feature für bestimmte Termintypen und für einzelne Termine in der Bookings-App aktivieren.

Nachdem dieses Feature aktiviert wurde, enthält die an die Teilnehmer gesendete Bestätigungs-E-Mail oder der SMS-Text einen Teilnahmelink für eine Besprechung, der Teams in einem mobilen Browser geöffnet wird. Auf mobilen Android-Geräten Teams in Chrome geöffnet. Auf mobilen iOS-Geräten Teams in Safari geöffnet.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>Aktivieren der Teilnahme per mobilem Browser für einen Termintyp

Wechseln Sie in Bookings zu **Einstellungen** Termintypen , wählen Sie einen Termintyp aus, und aktivieren Sie dann Teilnehmer die Teilnahme über einen  >   **mobilen Browser erlauben**. [](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) Auf diese Weise kann der mobile Browser für alle Termine dieses Typs teilnehmen.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Screenshot der Einstellung Teilnehmern die Teilnahme über einen mobilen Browser erlauben für Termintypen in der Bookings-App":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>Aktivieren der Teilnahme per mobilem Browser für einen einzelnen Termin

Wählen Sie in Bookings **Neue Buchung** aus, und aktivieren Sie dann Teilnehmern die Teilnahme über einen **mobilen Browser erlauben.**

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Screenshot der Einstellung Teilnehmern die Teilnahme über einen mobilen Browser erlauben auf dem neuen Buchungsformular in der Bookings-App":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Termine, die über den EHR Teams geplant wurden

Sie oder Ihre Mitarbeiter müssen nichts einrichten!

Der Teams EHR-Connector unterstützt Patienten bei virtuellen Visiten über MyChart-Web und Mobile. Zum Zeitpunkt des Termins können Patienten einen virtuellen Besuch über MyChart starten, indem sie die Schaltfläche virtuellen **Visit beginnen** verwenden. Der Patient wählt den Browser aus, den er möchte, und Teams dann in diesem Browser geöffnet.

## <a name="supported-mobile-browsers"></a>Unterstützte mobile Browser

Dies sind die mobilen Browser, die derzeit unterstützt werden. Sofern nicht anders angegeben, wird die neueste Version plus zwei frühere Versionen unterstützt.

|Plattform  |Chrome |Safari |Edge (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &Sup1;       |         |
|macOS     |         |  &#x2714; &Sup2;    |         |

&Sup1; iOS-Apps in Safari können keine Mikrofon- und Lautsprechergeräte auswählen. Verwenden Sie beispielsweise Bluetooth Geräte. Dies ist eine Einschränkung des Betriebssystems, das die standardmäßige Geräteauswahl steuert.

&sup2; Für die Unterstützung ausgehender Videos wird Safari 14+ und macOS 11+ benötigt.

> [!NOTE]
> Wir fügen der Teilnahmeerfahrung für Besprechungen in zukünftigen Versionen von Teams weitere Funktionen hinzu. Überprüfen Sie daher die neuesten Informationen. Weitere Informationen zu bevorstehenden Features von Microsoft Teams finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="related-articles"></a>Verwandte Artikel

- [Virtuelle Besuche mit Teams und der Bookings-App](bookings-virtual-visits.md)
- [Erstellen eines Bookings-Termintyps](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Teilnehmen an einem Bookings-Termin als Teilnehmer](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Virtuelle Besuche mit Teams – Integration in die EGA](healthcare/ehr-admin.md)
