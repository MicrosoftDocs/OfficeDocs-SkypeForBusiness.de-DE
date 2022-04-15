---
title: Verwalten der Teilnahmeerfahrung für Teams virtueller Termine in Browsern
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
description: Erfahren Sie mehr über die Teilnahmeerfahrung für Teams virtuellen Termine in Browsern.
ms.openlocfilehash: 418186734befa66f145ca56f883605715d83aa30
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853306"
---
# <a name="manage-the-join-experience-for-teams-virtual-appointments-on-browsers"></a>Verwalten der Teilnahmeerfahrung für Teams virtueller Termine in Browsern

Microsoft Teams erleichtert es Personen, an virtuellen Terminen teilzunehmen, ohne Teams herunterladen zu müssen. Für eine nahtlosere Erfahrung können Die Teilnehmer an Terminen wie Gesundheitsbesuchen und Finanzberatungen über einen Desktop- oder mobilen Browser teilnehmen. Teilnehmer müssen die Teams-App nicht auf ihrem Gerät installieren.

Wenn ein Teilnehmer an einem Termin teilnimmt, wird er beim Browserbeitritt nicht aufgefordert, Teams herunterzuladen. Stattdessen wird Teams in einem Browser geöffnet, in dem der Teilnehmer **"Jetzt** beitreten" auswählen kann, um teilzunehmen. Bedenken Sie bei diesem Feature, dass Teams in einem Browser und nicht in der App geöffnet wird, wenn Teams bereits auf dem Gerät installiert ist.

Derzeit ist der Browserbeitritt für Termine verfügbar, die über Folgendes geplant werden:

- [Die Bookings-App](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams EHR-Connector (Electronic Health Record)

  - Integration mit [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Integration in [Epic EHR](healthcare/ehr-admin.md)

## <a name="set-up-browser-join"></a>Einrichten des Browserbeitritts

### <a name="appointments-scheduled-through-the-bookings-app"></a>Termine, die über die Bookings-App geplant werden

Planer in Ihrer Organisation können dieses Feature für bestimmte Termintypen und für einzelne Termine in der Bookings-App aktivieren.

Nachdem diese Funktion aktiviert wurde, enthält die Bestätigungs-E-Mail oder der SMS-Text, der an die Teilnehmer gesendet wird, einen Besprechungsbeitrittslink, der Teams in einem Desktop- oder mobilen Browser öffnet. Eine Liste der unterstützten Browser finden Sie unter ["Unterstützte Browser"](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>Browserbeitritt für einen Termintyp aktivieren

Wechseln Sie in Bookings zu **Einstellungen** >  **Appointment-Typen**, wählen Sie einen [Termintyp](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) aus, und aktivieren Sie dann "**Teilnehmern die Teilnahme über einen Browser erlauben**". Auf diese Weise wird die Browserbeitritt für alle Termine dieses Typs aktiviert.

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="Screenshot der Einstellung &quot;Teilnehmern die Teilnahme über eine Browsereinstellung für Termintypen in der Bookings-App erlauben&quot;":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>Aktivieren des Browserbeitritts für einen einzelnen Termin

Wählen Sie in Bookings **"Neue Buchung**" aus, und aktivieren Sie dann "**Teilnehmern die Teilnahme über einen Browser erlauben"**.

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="Screenshot der Einstellung &quot;Teilnehmern die Teilnahme über eine Browsereinstellung im neuen Buchungsformular in der Bookings-App erlauben&quot;":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Termine, die über den Teams EHR-Connector geplant werden

Sie oder Ihre Mitarbeiter brauchen keine Einrichtung!

**Integration mit Cerner EHR**: Der Teams EHR Connector unterstützt Patienten bei der Teilnahme an virtuellen Terminen über einen Link in der SMS-Sms. Zum Zeitpunkt des Termins können Patienten teilnehmen, indem sie auf den Link in der SMS-Sms tippen, und Teams wird in einem Browser geöffnet.

**Integration mit Epic EHR**: Der Teams EHR Connector unterstützt Patienten, die über MyChart Web und Mobile an virtuellen Terminen teilnehmen. Zum Zeitpunkt des Termins können Patienten den Termin über MyChart über die Schaltfläche **"Virtuellen Besuch beginnen**" starten und Teams in einem Browser öffnen.

## <a name="supported-browsers"></a>Unterstützte Browser

Hier sind die Browser, die derzeit unterstützt werden. Wir unterstützen die neueste Version plus zwei vorherige Versionen, sofern nicht anders angegeben.

|Plattform  |Chrome |Safari |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; Ausgehende Bildschirmfreigaben werden unter iOS oder Android nicht unterstützt.

&sup2; iOS-Apps in Safari können keine Mikrofon- und Lautsprechergeräte auswählen. Beispielsweise Bluetooth Geräte. Dies ist eine Einschränkung des Betriebssystems, das die Standardgeräteauswahl steuert.

## <a name="things-to-consider"></a>Dinge, die Sie berücksichtigen sollten

Die Mitarbeiter, die den Termin durchführen, können ihren Bildschirm über ihren Teams Desktop-, Mobil- oder Webclient für einen Teilnehmer freigeben, der über einen Desktop- oder mobilen Browser beitritt. Teilnehmer können ihren Bildschirm jedoch nicht über einen Desktop- oder mobilen Browser freigeben.

## <a name="related-articles"></a>Verwandte Artikel

- [Virtuelle Termine mit Teams und der Bookings-App](bookings-virtual-visits.md)
- [Erstellen eines Bookings Termintyps](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Teilnehmen an einem Bookings Termin als Teilnehmer](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Virtuelle Termine mit Teams - Integration in Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Virtuelle Termine mit Teams - Integration in Epic EHR](healthcare/ehr-admin.md)
