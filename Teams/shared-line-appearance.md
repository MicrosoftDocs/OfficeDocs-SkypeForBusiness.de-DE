---
title: Teamschaltung in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Darstellung einer freigegebenen Linie ermöglicht dem Benutzer die Stellvertreter zum entgegennehmen oder in ihrem Auftrag Anrufe auswählen.
ms.openlocfilehash: d16fe4b3241e814609999d8068ee47743bfca516
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204491"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Teamschaltung in Microsoft Teams

Darstellung einer freigegebenen Linie ist Bestandteil der Delegierung-Feature, mit dem einen Benutzer wählen Sie ein Stellvertreter zum entgegennehmen oder in ihrem Auftrag Anrufe. Dieses Feature ist hilfreich, wenn ein Benutzer ein Verwaltungsmitarbeiter verfügt, die die Anrufe des Benutzers regelmäßig behandelt. Im Kontext von freigegebenen Zeile Darstellung, ist ein Manager einer Person, die eine Stellvertretung tätigen und Entgegennehmen von Anrufen in ihrem Auftrag autorisiert und Stellvertreter kann tätigen und Entgegennehmen von Anrufen im Auftrag einer anderen Person.

> [!IMPORTANT]
> Dieses Feature ist nur im Modus nur Teams Bereitstellung zur Verfügung. Weitere Informationen zu Bereitstellungsmethoden Teams finden Sie unter [Grundlegendes zu Microsoft-Teams und Skype für Interoperabilität und Koexistenz Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Lizenz erforderlich

Ein Benutzer muss ein Enterprise Voice-Benutzer werden eine Stellvertretung oder Delegierung einrichten und aktivieren für andere Benutzer Anrufe in ihrem Auftrag tätigen oder Entgegennehmen können.

Sowohl Vorgesetzte als auch Stellvertreter müssen Enterprise-VoIP aktiviert sein. Die Erfahrung freigegebenen Zeile ist Teil der Delegierung und ist keine zusätzliche Lizenz erforderlich. Weitere Details zur am Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft-Teams](office-365-licensing.md).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Konfigurieren der Delegierung und Darstellung einer freigegebenen Linie

Delegierung und Darstellung einer freigegebenen Linie sind benutzergesteuerten Features: Es sind keine Admin Einstellungen konfiguriert. Informationen zur Verwendung des Features finden Sie unter [Freigeben einer Telefonleitung mit einem Delegaten](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

Administrator des Mandanten sollten Delegierung über die **TeamsCallingPolicy AllowDelegation** Einstellung für dieses Feature zu aktivieren.

## <a name="shared-line-appearance-feature-availability"></a>Verfügbarkeit von Zeile Darstellung Shared

Darstellung einer freigegebenen Linie wird derzeit von den folgenden apps und -Geräte unterstützt.

| Funktion | Teams Desktop | Teams Mac-App | Teams Web App (Edge) |Mobile-iOS/Android-App-Teams | Teams IP-Telefon |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Einrichten von Delegierung | Ja  | Ja  | Ja | Nein | Nein |
| Ausgehende Anrufe im Auftrag eines anderen | Ja  | Ja  | Ja  | Ja  | Ja |
| Eine Rufnummer im Auftrag eines anderen | Ja  | Ja  | Ja  | Ja  | Ja |
| Rufen Sie einen Benutzer Teams im Auftrag eines anderen | Ja  | Ja  | Ja  | Ja  | Ja |
| Finden Sie unter der Admin-Ansicht des freigegebenen Zeilen | Ja  | Ja  | Ja | Nein | Nein |
| Finden Sie unter der Admin-Ansicht des Managers Anrufsaktivitäten | Ja  | Ja  | Ja | Nein | Nein |
| Finden Sie unter der Manager – Übersicht über Delegaten | Ja  | Ja  | Ja | Nein | Nein |
| Admin oder Manager halten oder Wiederaufnehmen | Ja  | Ja  | Ja | Nein | Nein |

## <a name="limitations"></a>Einschränkungen

Manager können bis zu 25 Stellvertretungen hinzufügen, und bis zu 25 Manager eine Stellvertretung werden können. Es gibt keine Begrenzung der Anzahl der Delegierung Beziehungen, die in einem Mandanten erstellt werden können. 
 
Wenn die Person als auch der Stellvertreter nicht in den gleichen geografischen Standort befinden, ist es bis zu dem PSTN-Dienstanbieter zu Anrufer-ID an einem anderen geografischen Standort für einen Anruf delegierte (im Auftrag von) angezeigt wird. 
 
## <a name="more-information"></a>Weitere Informationen

[Freigeben einer Telefonleitung für eine Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
