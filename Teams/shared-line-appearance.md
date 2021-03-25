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
description: Erfahren Sie, wie Sie Ihren Benutzern eine E-Mail mit ihren Audiokonferenzinformationen in Microsoft Teams senden.
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117043"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Teamschaltung in Microsoft Teams

Die Darstellung freigegebener Zeilen ist Teil des Delegierungsfeatures, mit dem ein Benutzer eine Stellvertretung auswählen kann, um Anrufe in seinem Auftrag zu beantworten oder zu behandeln. Dieses Feature ist hilfreich, wenn ein Benutzer über einen Verwaltungsassistenten verfügt, der die Anrufe des Benutzers regelmäßig bearbeitet. Im Kontext der Darstellung einer freigegebenen Zeile ist ein Vorgesetzter eine Person, die eine Stellvertretung autorisiert, in ihrem Auftrag Anrufe zu machen oder zu empfangen, und eine Stellvertretung kann Anrufe im Auftrag einer anderen Person an- und empfangen.

> [!IMPORTANT]
> Dieses Feature ist nur im Bereitstellungsmodus von Teams verfügbar. Weitere Informationen zu den Bereitstellungsmodi von Teams finden Sie unter [Verstehen der Koexistenz](teams-and-skypeforbusiness-coexistence-and-interoperability.md) und Interoperabilität von Microsoft Teams und Skype for Business

## <a name="license-required"></a>Lizenz erforderlich

Ein Benutzer muss über ein Telefonsystem mit PSTN-Konnektivität verfügen (entweder eine Lizenz für einen Anrufplan oder Direct Routing OnlineVoiceRoutingPolicy), um eine Stellvertretung zu sein oder eine Delegierung einrichten zu können und anderen Personen das Anrufen oder Empfangen von Anrufen in ihrem Auftrag zu ermöglichen.

Sowohl Vorgesetzte als auch Stellvertretung müssen über ein Telefonsystem mit PSTN-Konnektivität verfügen (entweder eine Lizenz für einen Anrufplan oder Direct Routing OnlineVoiceRoutingPolicy). Die freigegebene Linienerfahrung ist Teil der Delegierung und ist im Telefonsystem enthalten. Weitere Details zum Lizenzierungsmodell finden Sie unter [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Konfigurieren der Delegierung und der darstellung freigegebener Zeilen

Delegierung und freigegebene Zeilenansicht sind benutzergesteuerte Features: Es gibt keine Administratoreinstellungen, die konfiguriert werden müssen. Informationen zur Verwendung des Features finden Sie unter [Freigeben einer Telefonleitung für eine Stellvertretung.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

Der Mandantenadministrator kann die Delegierung über die **Einstellung "TeamsCallingPolicy AllowDelegation"** oder über das Teams Admin Portal aktivieren, damit dieses Feature funktioniert. 

Der Mandantenadministrator kann auch Delegierungsbeziehungen für einen Benutzer im Teams Admin Center konfigurieren. Darüber hinaus kann der Endbenutzer seine Delegierungsbeziehungen auch direkt in Teams konfigurieren. Der Mandantenadministrator oder der Benutzer können die Konfiguration nicht gegenseitig blockieren, aber das Teams Admin Center und der Teams-Client sollten diese Beziehung an beiden Stellen genau anzeigen. 

> [!IMPORTANT]
> Wenn der Mandantenadministrator die Delegierung für einen Benutzer deaktiviert (nachdem sie aktiviert wurde), muss er auch die Delegierungsbeziehungen für diesen Benutzer im Teams Admin Center bereinigen, um ein falsches Anrufrouting zu vermeiden.

## <a name="shared-line-appearance-feature-availability"></a>Verfügbarkeit von Features für freigegebene Linien

Die Darstellung freigegebener Zeilen wird derzeit von den folgenden Apps und Geräten unterstützt.

| Funktion | Teams Desktop | Teams Mac App | Teams Web App (Edge) |Mobile iOS/Android-App für Teams | Teams IP Phone |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Einrichten der Delegierung | Ja | Ja | Ja | Nein | Ja |
| Empfangen von Anrufen im Auftrag eines anderen | Ja | Ja | Ja | Ja | Ja |
| Anrufen einer Telefonnummer im Auftrag eines anderen | Ja | Ja | Ja | Ja | Ja |
| Anrufen eines Teams-Benutzers im Auftrag eines anderen Benutzers | Ja | Ja | Ja | Ja | Ja |
| Anzeigen der Administratoransicht freigegebener Zeilen | Ja | Ja | Ja | Nein | Nein |
| Anzeigen der Administratoransicht der Anrufaktivitäten des Vorgesetzten | Ja | Ja | Ja | Nein | Nein |
| Anzeigen der Manageransicht von Stellvertretung | Ja | Ja | Ja | Nein | Nein |
| Administrator oder Vorgesetzter kann halten oder fortsetzen | Ja | Ja | Ja | Nein | Nein |

## <a name="limitations"></a>Einschränkungen

Manager können bis zu 25 Stellvertretung und Stellvertretung bis zu 25 Manager hinzufügen. Die Anzahl der Delegierungsbeziehungen, die in einem Mandanten erstellt werden können, ist nicht begrenzt. 
 
Wenn sich der Delegator und die Stellvertretung nicht am gleichen geografischen Standort befinden, ist es Sache des PSTN-Anbieters, die Anrufer-ID von einem anderen geografischen Ort für einen delegierten Anruf (im Auftrag) anzeigen zu lassen. 
 
## <a name="more-information"></a>Weitere Informationen

[Freigeben einer Telefonleitung für eine Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)