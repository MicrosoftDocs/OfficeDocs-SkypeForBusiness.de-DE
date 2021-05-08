---
title: Teamschaltung in Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
description: Erfahren Sie, wie Sie Ihren Benutzern eine E-Mail mit ihren Audiokonferenzinformationen in einer Microsoft Teams.
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117043"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Teamschaltung in Microsoft Teams

Die Darstellung der freigegebenen Zeile ist Teil des Delegierungsfeatures, mit dem ein Benutzer eine Stellvertretung zum Beantworten oder Behandeln von Anrufen in seinem Auftrag auswählen kann. Dieses Feature ist hilfreich, wenn ein Benutzer über einen Verwaltungsassistenten verfügt, der die Anrufe des Benutzers regelmäßig verarbeitet. Im Zusammenhang mit der Darstellung einer freigegebenen Zeile ist ein Manager eine Person, die eine Stellvertretung autorisiert, in deren Namen Anrufe zu erstellen oder zu empfangen, und eine Stellvertretung kann Anrufe im Namen einer anderen Person anrufen und empfangen.

> [!IMPORTANT]
> Dieses Feature ist nur im Teams Bereitstellungsmodus verfügbar. Weitere Details zu Teams Bereitstellungsmodi finden Sie unter Verstehen Microsoft Teams und Skype for Business [Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Lizenz erforderlich

Ein Benutzer muss über Telefonsystem pstN-Konnektivität (entweder über eine Anrufplanlizenz oder Direct Routing OnlineVoiceRoutingPolicy) verfügen, um Stellvertretung zu sein oder eine Stellvertretung einrichten zu können und anderen Personen das Anrufen in ihrem Namen zu ermöglichen.

Sowohl Vorgesetzte als auch Stellvertretung Telefonsystem PSTN-Anbindung (entweder über eine Anrufplanlizenz oder Direct Routing OnlineVoiceRoutingPolicy) verfügen. Die Erfahrung mit freigegebenen Zeilen ist Teil der Delegierung und in der Telefonsystem. Weitere Informationen zum Lizenzierungsmodell finden Sie unter Microsoft Teams [Dienstbeschreibung.](/office365/servicedescriptions/teams-service-description)

## <a name="configuring-delegation-and-shared-line-appearance"></a>Konfigurieren der Darstellung von Delegierung und freigegebenen Zeilen

Delegierung und Darstellung freigegebener Zeilen sind benutzergesteuerte Features: Es müssen keine Administratoreinstellungen konfiguriert werden. Informationen zur Verwendung des Features finden Sie unter [Freigeben einer Telefonleitung für eine Stellvertretung.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

Der Mandantenadministrator kann die Delegierung über die **TeamsCallingPolicy AllowDelegation-Einstellung** oder über Teams Admin Portal aktivieren, damit dieses Feature funktioniert. 

Der Mandantenadministrator kann auch Delegierungsbeziehungen für einen Benutzer im Teams Admin Center konfigurieren. Darüber hinaus kann der Endbenutzer seine Delegierungsbeziehungen auch direkt in Teams. Der Mandantenadministrator oder der Benutzer kann die Konfiguration nicht voneinander blockieren, aber der Teams Admin Center und der Teams-Client sollten diese Beziehung an beiden Stellen genau anzeigen. 

> [!IMPORTANT]
> Wenn der Mandantenadministrator die Delegierung für einen Benutzer deaktiviert (nachdem sie aktiviert wurde), muss er auch die Delegierungsbeziehungen für diesen Benutzer im Teams Admin Center bereinigen, um falsche Anrufrouting zu vermeiden.

## <a name="shared-line-appearance-feature-availability"></a>Verfügbarkeit des Features "Darstellung freigegebener Zeilen"

Die Darstellung einer freigegebenen Zeile wird derzeit von den folgenden Apps und Geräten unterstützt.

| Funktion | Teams Desktop | Teams Mac-App | Teams Web App (Edge) |Teams mobile iOS-/Android-App | Teams IP-Telefon |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Einrichten von Delegierung | Ja | Ja | Ja | Nein | Ja |
| Anrufe im Auftrag einer anderen empfangen | Ja | Ja | Ja | Ja | Ja |
| Anrufen einer Telefonnummer im Auftrag einer anderen Rufnummer | Ja | Ja | Ja | Ja | Ja |
| Anrufen eines Teams Benutzers im Auftrag eines anderen Benutzers | Ja | Ja | Ja | Ja | Ja |
| Anzeigen der Administratoransicht von freigegebenen Zeilen | Ja | Ja | Ja | Nein | Nein |
| Anzeigen der Administratoransicht der Anrufaktivitäten des Vorgesetzten | Ja | Ja | Ja | Nein | Nein |
| Anzeigen der Manageransicht von Stellvertretung | Ja | Ja | Ja | Nein | Nein |
| Der Administrator oder Manager kann die Schleife halten oder fortsetzen. | Ja | Ja | Ja | Nein | Nein |

## <a name="limitations"></a>Einschränkungen

Vorgesetzte können bis zu 25 Stellvertretung hinzufügen, und Stellvertretung kann bis zu 25 Vorgesetzte haben. Die Anzahl der Delegierungsbeziehungen, die in einem Mandanten erstellt werden können, ist nicht begrenzt. 
 
Wenn sich der Delegator und die Stellvertretung nicht am gleichen geografischen Standort befinden, kann der PSTN-Anbieter die Anrufer-ID für einen delegierten Anruf (im Auftrag von) von einem anderen geografischen Standort anzeigen lassen. 
 
## <a name="more-information"></a>Weitere Informationen

[Freigeben einer Telefonleitung für eine Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)