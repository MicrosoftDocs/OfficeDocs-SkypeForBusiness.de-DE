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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Die Darstellung der freigegebenen Zeile ermöglicht es einem Benutzer, eine Stellvertretung zu wählen, um Anrufe in deren Auftrag zu beantworten oder zu behandeln.
ms.openlocfilehash: 619e011e1af5a765bc86ca6bd68134dc5ab1e9fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298655"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Teamschaltung in Microsoft Teams

Die Darstellung der freigegebenen Zeile ist Teil des Delegierungsfeatures, mit dem Benutzer eine Stellvertretung auswählen können, um Anrufe in Ihrem Auftrag zu beantworten oder zu behandeln. Dieses Feature ist hilfreich, wenn ein Benutzer über einen administrativen Assistenten verfügt, der regelmäßig die Anrufe des Benutzers abwickelt. Im Zusammenhang mit der Darstellung der freigegebenen Zeile ist ein Manager jemand, der eine Stellvertretung autorisiert, in seinem Namen Anrufe zu tätigen oder zu empfangen, und eine Stellvertretung kann Anrufe im Namen einer anderen Person tätigen und empfangen.

> [!IMPORTANT]
> Dieses Feature steht nur im Bereitstellungsmodus für Teams zur Verfügung. Weitere Informationen zu den Bereitstellungsmodi für Teams finden Sie Untergrund Legendes zu [Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) .

## <a name="license-required"></a>Lizenz erforderlich

Ein Benutzer muss ein Enterprise-VoIP-Benutzer sein, um Stellvertretung zu sein oder eine Delegierung einzurichten und anderen Personen das tätigen oder empfangen von Anrufen in deren Auftrag zu ermöglichen.

Für Manager und Stellvertretungen muss Enterprise-VoIP aktiviert sein. Die Erfahrung der freigegebenen Leitung ist Teil der Delegierung und erfordert keine zusätzliche Lizenz. Weitere Informationen zum Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft Teams](office-365-licensing.md).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Konfigurieren der Darstellung von Delegierungs-und freigegebenen Leitungen

Die Darstellung der Delegierung und der freigegebenen Zeile sind benutzergesteuerte Features: Es sind keine Administratoreinstellungen zum Konfigurieren vorhanden. Informationen zum Verwenden des Features finden Sie unter [Freigeben einer Telefonleitung mit einer Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

Der mandantenadministrator sollte die Delegierung über die **TeamsCallingPolicy-AllowDelegation** -Einstellung aktivieren, damit dieses Feature funktioniert.

## <a name="shared-line-appearance-feature-availability"></a>Verfügbarkeit von freigegebenen Leitungs Darstellungs Features

Die Darstellung der freigegebenen Zeile wird derzeit von den folgenden apps und Geräten unterstützt.

| Funktion | Teams-Desktop | Mac-app für Teams | Teams Web App (Edge) |Teams Mobile IOS/Android-App | IP-Telefon für Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Einrichten der Delegierung | Ja  | Ja  | Ja | Nein | Nein |
| Empfangen von Anrufen im Namen einer anderen Person | Ja  | Ja  | Ja  | Ja  | Ja |
| Anrufen einer Telefonnummer im Namen einer anderen Person | Ja  | Ja  | Ja  | Ja  | Ja |
| Anrufen eines Teams-Benutzers im Namen einer anderen Person | Ja  | Ja  | Ja  | Ja  | Ja |
| Anzeigen der Administrator Ansicht für freigegebene Zeilen | Ja  | Ja  | Ja | Nein | Nein |
| Anzeigen der Administrator Ansicht der Anrufaktivitäten des Managers | Ja  | Ja  | Ja | Nein | Nein |
| Anzeigen der Manageransicht von Stellvertretungen | Ja  | Ja  | Ja | Nein | Nein |
| Administrator oder Manager kann halten oder fortsetzen | Ja  | Ja  | Ja | Nein | Nein |

## <a name="limitations"></a>Einschränkungen

Manager können bis zu 25 Stellvertretungen hinzufügen, und Stellvertretungen können bis zu 25 Manager aufweisen. Die Anzahl der Delegierungs Beziehungen, die in einem Mandanten erstellt werden können, ist unbegrenzt. 
 
Wenn sich der delegator und der Delegat nicht am gleichen geografischen Standort befinden, ist es Sache des PSTN-Anbieters, die Rufnummernanzeige von einem anderen geografischen Standort aus für einen Delegierten (im Auftrag von) Anruf zu ermöglichen. 
 
## <a name="more-information"></a>Weitere Informationen

[Freigeben einer Telefonleitung mit einer Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
