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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie Ihren Benutzern eine e-Mail mit ihren Audiokonferenzinformationen in Microsoft Teams senden.
ms.openlocfilehash: 92eda8a1818d98689e71d81f31c5355df3ef1e26
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45125978"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Teamschaltung in Microsoft Teams

Die Darstellung der freigegebenen Zeile ist Teil des Delegierungsfeatures, mit dem Benutzer eine Stellvertretung auswählen können, um Anrufe in Ihrem Auftrag zu beantworten oder zu behandeln. Dieses Feature ist hilfreich, wenn ein Benutzer über einen administrativen Assistenten verfügt, der regelmäßig die Anrufe des Benutzers abwickelt. Im Zusammenhang mit der Darstellung der freigegebenen Zeile ist ein Manager jemand, der eine Stellvertretung autorisiert, in seinem Namen Anrufe zu tätigen oder zu empfangen, und eine Stellvertretung kann Anrufe im Namen einer anderen Person tätigen und empfangen.

> [!IMPORTANT]
> Dieses Feature steht nur im Bereitstellungsmodus für Teams zur Verfügung. Weitere Informationen zu den Bereitstellungsmodi für Teams finden Sie Untergrund [Legendes zu Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) .

## <a name="license-required"></a>Lizenz erforderlich

Ein Benutzer muss über ein Telefon System mit PSTN-Konnektivität verfügen (entweder eine Anruf Plan Lizenz oder ein direktes Routing-OnlineVoiceRoutingPolicy), um eine Stellvertretung zu sein oder eine Delegierung einzurichten und anderen Personen das tätigen oder empfangen von Anrufen in Ihrem Auftrag zu ermöglichen.

Sowohl Manager als auch Stellvertretungen müssen über ein Telefon System mit PSTN-Konnektivität verfügen (entweder über eine Anruf Plan Lizenz oder über ein direktes Routing-OnlineVoiceRoutingPolicy). Die freigegebene Leitungserfahrung ist Teil der Delegierung und in der Telefonanlage enthalten. Weitere Informationen zum Lizenzierungsmodell finden Sie in der [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Konfigurieren der Darstellung von Delegierungs-und freigegebenen Leitungen

Die Darstellung der Delegierung und der freigegebenen Zeile sind benutzergesteuerte Features: Es sind keine Administratoreinstellungen zum Konfigurieren vorhanden. Informationen zum Verwenden des Features finden Sie unter [Freigeben einer Telefonleitung mit einer Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

Der mandantenadministrator kann die Delegierung über die **TeamsCallingPolicy AllowDelegation** -Einstellung oder über das Team-Administrator Portal aktivieren, damit dieses Feature funktioniert. 

Der mandantenadministrator kann auch Delegierungs Beziehungen für einen Benutzer im Team Admin Center konfigurieren. Darüber hinaus kann der Endbenutzer seine Delegierungs Beziehungen auch direkt in Teams konfigurieren. Der mandantenadministrator oder der Benutzer kann die Konfiguration nicht voneinander blockieren, aber das Team-Admin Center und der Team-Client sollten diese Beziehung an beiden Stellen genau anzeigen. 

> [!IMPORTANT]
> Wenn der mandantenadministrator die Delegierung für einen Benutzer deaktiviert (nachdem er aktiviert wurde), muss er auch Delegierungs Beziehungen für diesen Benutzer im Team Admin Center bereinigen, um eine falsche Anrufweiterleitung zu vermeiden.

## <a name="shared-line-appearance-feature-availability"></a>Verfügbarkeit von freigegebenen Leitungs Darstellungs Features

Die Darstellung der freigegebenen Zeile wird derzeit von den folgenden apps und Geräten unterstützt.

| Funktion | Teams-Desktop | Mac-app für Teams | Teams Web App (Edge) |Teams Mobile IOS/Android-App | IP-Telefon für Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Einrichten der Delegierung | Ja  | Ja  | Ja | Nein | Ja |
| Empfangen von Anrufen im Namen einer anderen Person | Ja  | Ja  | Ja  | Ja  | Ja  |
| Anrufen einer Telefonnummer im Namen einer anderen Person | Ja  | Ja  | Ja  | Ja  | Ja  |
| Anrufen eines Teams-Benutzers im Namen einer anderen Person | Ja  | Ja  | Ja  | Ja  | Ja  |
| Anzeigen der Administrator Ansicht für freigegebene Zeilen | Ja  | Ja  | Ja | Nein | Nein |
| Anzeigen der Administrator Ansicht der Anrufaktivitäten des Managers | Ja  | Ja  | Ja | Nein | Nein |
| Anzeigen der Manageransicht von Stellvertretungen | Ja  | Ja  | Ja | Nein | Nein |
| Administrator oder Manager kann halten oder fortsetzen | Ja  | Ja  | Ja | Nein | Nein |

## <a name="limitations"></a>Einschränkungen

Manager können bis zu 25 Stellvertretungen hinzufügen, und Stellvertretungen können bis zu 25 Manager aufweisen. Die Anzahl der Delegierungs Beziehungen, die in einem Mandanten erstellt werden können, ist unbegrenzt. 
 
Wenn sich der delegator und der Delegat nicht am gleichen geografischen Standort befinden, ist es Sache des PSTN-Anbieters, die Rufnummernanzeige von einem anderen geografischen Standort aus für einen Delegierten (im Auftrag von) Anruf zu ermöglichen. 
 
## <a name="more-information"></a>Weitere Informationen

[Freigeben einer Telefonleitung mit einer Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
