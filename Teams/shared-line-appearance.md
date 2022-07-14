---
title: Teamschaltung in Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Ihren Benutzern eine E-Mail mit ihren Audiokonferenzinformationen in Microsoft Teams senden.
ms.openlocfilehash: 3646cf27e22f5224dc825c758f757cc04d5804fc
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794323"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Teamschaltung in Microsoft Teams

Die Gemeinsame Liniendarstellung ist Teil des Delegierungsfeatures, mit dem ein Benutzer eine Stellvertretung auswählen kann, um Anrufe in ihrem Namen zu beantworten oder zu verarbeiten. Dieses Feature ist hilfreich, wenn ein Benutzer über einen Administrator-Assistenten verfügt, der die Anrufe des Benutzers regelmäßig verarbeitet. Im Zusammenhang mit der gemeinsamen Leitungsdarstellung ist ein Vorgesetzter jemand, der eine Stellvertretung autorisiert, Anrufe in ihrem Namen zu tätigen oder zu empfangen, und eine Stellvertretung kann Anrufe im Namen einer anderen Person tätigen und empfangen.

> [!IMPORTANT]
> Dieses Feature ist nur im Bereitstellungsmodus "Nur Teams" verfügbar. Weitere Informationen zu Teams-Bereitstellungsmodi finden [Sie unter Grundlegendes zu Microsoft Teams und Skype for Business Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Lizenz erforderlich

Ein Benutzer muss über ein Telefonsystem mit PSTN-Konnektivität verfügen (entweder eine Anrufplanlizenz oder Direct Routing OnlineVoiceRoutingPolicy), um eine Stellvertretung zu sein oder delegieren zu können und anderen personen das Tätigen oder Empfangen von Anrufen in ihrem Namen zu ermöglichen.

Sowohl Manager als auch Stellvertretungen benötigen ein Telefonsystem mit PSTN-Konnektivität (entweder eine Anrufplanlizenz oder Direct Routing OnlineVoiceRoutingPolicy). Die gemeinsame Leitungserfahrung ist Teil der Delegierung und im Telefonsystem enthalten. Weitere Informationen zum Lizenzierungsmodell finden Sie in der [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Konfigurieren der Delegierung und der Gemeinsamen Liniendarstellung

Delegierung und gemeinsame Liniendarstellung sind benutzergesteuerte Features: Es sind keine Administratoreinstellungen zu konfigurieren. Informationen zur Verwendung des Features finden [Sie unter Freigeben einer Telefonleitung für einen Stellvertreter](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

Der Mandantenadministrator kann die Delegierung über die **Einstellung "TeamsCallingPolicy AllowDelegation**" oder über Teams Admin Portal aktivieren, damit dieses Feature funktioniert. 

Der Mandantenadministrator kann auch Delegationsbeziehungen für einen Benutzer im Teams Admin Center konfigurieren. Darüber hinaus kann der Endbenutzer seine Delegierungsbeziehungen auch direkt in Teams konfigurieren. Der Mandantenadministrator oder der Benutzer kann die Konfiguration nicht gegenseitig blockieren, aber im Teams Admin Center und im Teams-Client sollte diese Beziehung an beiden Stellen genau angezeigt werden. 

> [!IMPORTANT]
> Wenn der Mandantenadministrator die Delegierung für einen Benutzer deaktiviert (nachdem er aktiviert wurde), muss er auch die Delegierungsbeziehungen für diesen Benutzer im Teams Admin Center bereinigen, um ein falsches Anrufrouting zu vermeiden.

## <a name="shared-line-appearance-feature-availability"></a>Verfügbarkeit der Funktion "Gemeinsame Liniendarstellung"

Die Gemeinsame Liniendarstellung wird derzeit von den folgenden Apps und Geräten unterstützt.

| Funktion | Teams-Desktop | Teams Mac App | Teams Web App (Edge) |Mobile iOS/Android-App für Teams | Teams-IP-Telefon |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Einrichten der Delegierung | Ja | Ja | Ja | Nein | Ja |
| Anrufe im Auftrag eines anderen entgegennehmen | Ja | Ja | Ja | Ja | Ja |
| Anrufen einer Telefonnummer im Auftrag einer anderen | Ja | Ja | Ja | Ja | Ja |
| Anrufen eines Teams-Benutzers im Namen eines anderen Benutzers | Ja | Ja | Ja | Ja | Ja |
| Anzeigen der Stellvertretungsansicht freigegebener Zeilen | Ja | Ja | Ja | Nein | Ja |
| Anzeigen der Stellvertretungsansicht der Anrufaktivitäten des Vorgesetzten | Ja | Ja | Ja | Nein | Ja |
| Anzeigen der Manageransicht von Stellvertretungen | Ja | Ja | Ja | Nein | Ja |
| Stellvertretung oder Manager kann halten oder fortsetzen | Ja | Ja | Ja | Nein | Ja |

## <a name="limitations"></a>Einschränkungen

Manager können bis zu 25 Stellvertretungen hinzufügen, und Stellvertretungen können bis zu 25 Manager haben. Es gibt keine Beschränkung für die Anzahl der Delegierungsbeziehungen, die in einem Mandanten erstellt werden können. 
 
Wenn sich der Delegator und die Stellvertretung nicht am gleichen geografischen Standort befinden, ist es Sache des PSTN-Anbieters, die Anrufer-ID von einem anderen geografischen Ort aus für einen delegierten (im Auftrag von) Anruf anzuzeigen. 

Die Konfiguration der Zirkeldelegierung ist nicht zulässig. Wenn die delegierten Benutzer auch Delegationen zwischen ihnen haben, können sie nur ihre Delegierung und nicht die anfängliche Delegierung sehen.
 
## <a name="more-information"></a>Weitere Informationen

[Freigeben einer Telefonleitung für einen Stellvertreter](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
