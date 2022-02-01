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
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: Erfahren Sie mehr über die Teilnahmeerfahrung für Teams Besuche in mobilen Browsern.
ms.openlocfilehash: 5c4b0f7ac9011d12d12e3076f900880292e72eb1
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288563"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>Verwalten der Teilnahmeerfahrung für Teams Besuche in mobilen Browsern

Microsoft Teams erleichtert Personen die Teilnahme an Terminen auf ihren mobilen Geräten, ohne sie herunterladen Teams. Für eine nahtlose Erfahrung können die Teilnehmer über einen mobilen Browser an Terminen teilnehmen, z. B. Arztbesuche, Finanzberatungen, Dozentenbürozeiten und so weiter. Teilnehmer müssen die mobile Teams-App nicht auf ihren mobilen Android- oder iOS-Geräten installieren.

Bei der Teilnahme über einen mobilen Browser wird ein Teilnehmer, der einem Termin über ein Mobilgerät beitritt, nicht zum Herunterladen Teams. Stattdessen wird Teams in einem mobilen Browser geöffnet, in dem der **Teilnehmer Jetzt teilnehmen** auswählen kann, um bei der Besprechung teilnehmen. Beachten Sie bei diesem Feature, dass Teams in einem mobilen Browser und nicht in der App geöffnet wird, wenn Teams Teams bereits auf dem mobilen Gerät eines Teilnehmers installiert ist.

Derzeit ist die Teilnahme über einen mobilen Browser für Termine verfügbar, die wie folgt geplant werden:

- [Die Bookings-App](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- Microsoft Teams EHR-Connector (Electronic Health Records)

  - Integration in [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Integration mit [epischer EHR](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>Einrichten der Teilnahme über einen mobilen Browser

### <a name="appointments-scheduled-through-the-bookings-app"></a>Termine, die über die Bookings-App geplant wurden

Planer in Ihrer Organisation können dieses Feature für bestimmte Termintypen und für einzelne Termine in der Bookings-App aktivieren.

Nachdem dieses Feature aktiviert wurde, enthält die an die Teilnehmer gesendete Bestätigungs-E-Mail oder der SMS-Text einen Teilnahmelink für eine Besprechung, der Teams in einem mobilen Browser geöffnet wird. Auf mobilen Android-Geräten Teams in Chrome geöffnet. Auf mobilen iOS-Geräten Teams in Safari geöffnet.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>Aktivieren der Teilnahme per mobilem Browser für einen Termintyp

Wechseln Sie in Bookings zu **Einstellungen** >  **Appointment-Typen**, wählen Sie einen Termintyp [aus, und](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) aktivieren Sie dann Teilnehmer die Teilnahme über einen **mobilen Browser erlauben**. Auf diese Weise kann der mobile Browser für alle Termine dieses Typs teilnehmen.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Screenshot der Einstellung "Teilnehmern die Teilnahme über einen mobilen Browser erlauben" für Termintypen in der Bookings-App":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>Aktivieren der Teilnahme per mobilem Browser für einen einzelnen Termin

Wählen Sie in Bookings **Neue Buchung** aus, und aktivieren Sie dann Teilnehmern die Teilnahme über einen **mobilen Browser erlauben**.

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Screenshot der Einstellung "Teilnehmern die Teilnahme über einen mobilen Browser erlauben" auf dem neuen Buchungsformular in der Bookings-App":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Termine, die über den Teams EHR-Connector geplant sind

Sie oder Ihre Mitarbeiter müssen nichts einrichten!

**Integration in Cerner EHR**: Der EHR Teams EHR-Connector unterstützt Patienten bei virtuellen Visiten über Mobilgeräte. Zum Zeitpunkt des Termins können Patienten an einem virtuellen Besuch teilnehmen, indem sie auf den Link in der SMS tippen. Der Patient wählt den Browser aus, den er möchte, und Teams dann in diesem Browser geöffnet.

**Integration in Epische EHR**: Der EHR Teams Connector unterstützt Patienten bei virtuellen Visiten über MyChart-Web und Mobile. Zum Zeitpunkt des Termins können Patienten einen virtuellen Besuch über MyChart starten, indem sie die Schaltfläche virtuellen **Visit beginnen** verwenden. Der Patient wählt den Browser aus, den er möchte, und Teams dann in diesem Browser geöffnet.

## <a name="supported-mobile-browsers"></a>Unterstützte mobile Browser

Dies sind die mobilen Browser, die derzeit unterstützt werden. Sofern nicht anders angegeben, wird die neueste Version plus zwei frühere Versionen unterstützt.

|Plattform  |Chrome |Safari |Edge (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &Sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&Sup1; iOS-Apps in Safari können keine Mikrofon- und Lautsprechergeräte auswählen. Verwenden Sie beispielsweise Bluetooth Geräte. Dies ist eine Einschränkung des Betriebssystems, das die standardmäßige Geräteauswahl steuert.

&sup2; Für die Unterstützung ausgehender Videos wird Safari 14+ und macOS 11+ benötigt.

## <a name="things-to-consider"></a>Zu berücksichtigende Dinge

Die Mitarbeiter, die den virtuellen Besuch durchführen, können ihren Bildschirm auf ihrem Teams-Desktop, auf einem mobilen Gerät oder in einem Webclient mit einem Teilnehmer teilen, der über einen mobilen Browser teilt. Teilnehmer können ihren Bildschirm jedoch nicht über einen mobilen Browser freigeben.

> [!NOTE]
> In zukünftigen Versionen von Teams werden weitere Funktionen für die Teilnahme an Besprechungen hinzugefügt, daher sollten Sie sich hier über die neuesten Informationen informieren. Weitere Informationen zu bevorstehenden Features von Microsoft Teams finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="related-articles"></a>Verwandte Artikel

- [Virtuelle Besuche mit Teams und der Bookings-App](bookings-virtual-visits.md)
- [Erstellen eines Bookings-Termintyps](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Teilnehmen an einem Bookings-Termin als Teilnehmer](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Virtuelle Besuche mit Teams - Integration in Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Virtuelle Besuche mit Teams - Integration in die Epische EHR](healthcare/ehr-admin.md)
