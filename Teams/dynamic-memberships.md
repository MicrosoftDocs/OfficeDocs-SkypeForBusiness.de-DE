---
title: Übersicht über die dynamische Mitgliedschaft für Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Microsoft Teams mithilfe der dynamischen Mitgliedschaft die Teams unterstützt, die Microsoft 365-Gruppen zugeordnet sind.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3a18e2cbe1a34fe78f5e84b4df4ae9a95c46fd9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613634"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Übersicht über die dynamische Mitgliedschaft für Teams

Microsoft Teams unterstützt Teams, die Microsoft 365-Gruppen zugeordnet sind, mithilfe der *dynamischen Mitgliedschaft*. Mithilfe der dynamischen Mitgliedschaft in Microsoft Teams kann die Mitgliedschaft in einem Teams durch eine oder mehrere Regeln definiert werden, die bestimmte Benutzerattribute in Azure Active Directory (Azure AD) überprüfen. Benutzer werden automatisch zu den richtigen Teams hinzugefügt bzw. daraus entfernt, wenn sich Benutzerattribute ändern oder Benutzer dem Mandanten beitreten und diesen verlassen.

Mit einer dynamischen Mitgliedschaft können Sie Teams für bestimmte Benutzergruppen in Ihrer Organisation einrichten. Mögliche Szenarien umfassen:
- Ein Krankenhaus kann verschiedene Teams für Krankenschwestern, Ärzte und Chirurgen bilden, um Mitteilungen zu übermitteln. Dies ist besonders wichtig, wenn das Krankenhaus auf temporäre Mitarbeiter angewiesen ist.
- Eine Universität kann ein Team für alle Dozenten innerhalb eines bestimmten Colleges einrichten, auch für zusätzliche, häufig wechselnde Dozenten.
- Eine Fluggesellschaft möchte für jeden Flug (z. B. Dienstagnachmittag Nonstop-Flug von Chicago nach Atlanta) ein Team erstellen und eine häufig wechselnde Flugbesatzung bei Bedarf automatisch zuweisen oder entfernen.

Mit dieser Funktion werden die Mitglieder eines bestimmten Teams automatisch anhand bestimmter Kriterien aktualisiert, anstatt die Mitgliedschaft manuell zu verwalten. Dazu sind Azure AD Premium P1-Lizenzen erforderlich und die Team-Mitgliedschaft kann den Azure AD-Eigenschaften eines beliebigen Benutzers [durch einen Mandanten-Administrator zugewiesen werden](/azure/active-directory/users-groups-roles/groups-dynamic-membership), sofern Sie über einen Mandanten und ein Administrator-Konto verfügen.

Microsoft Teams kann einige Minuten bis zu zwei Stunden benötigen, um dynamische Mitgliedschaftsänderungen zu widerspiegeln, sobald sie in der Microsoft 365-Gruppe für ein Team wirksam wurden.

Wenn Sie Teams mit dynamischen Gruppen verwenden:

- Regeln können definieren, wer ein Teammitglied ist, aber nicht, wer der Teambesitzer ist.
- Besitzer können keine Benutzer als Teammitglieder hinzufügen oder entfernen, da Mitglieder über dynamische Gruppenregeln definiert werden.
- Teams Kunden erlauben keine Mitgliederverwaltung für das Team. Die Optionen, um Mitglieder hinzuzufügen, Mitgliederrollen zu bearbeiten, Beitrittsanfragen zu senden und zu genehmigen und das Team zu verlassen, sind alle ausgeblendet.

Um ein Team zu erstellen, [](/azure/active-directory/users-groups-roles/groups-create-rule) für das die dynamische Mitgliedschaft verwendet wird, erstellen Sie zunächst eine dynamische Microsoft 365 gruppe, und erstellen Sie dann ein [Team aus dieser Gruppe.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

Sie können ein vorhandenes Team in eine dynamische Mitgliedschaft ändern. Weitere Informationen finden Sie unter Ändern [der statischen Gruppenmitgliedschaft in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) dynamischen Gruppen.

## <a name="related-topics"></a>Verwandte Themen

[Limits und Spezifikationen für Microsoft Teams](limits-specifications-teams.md)

[Dynamische Mitgliedschaftsregeln für Gruppen in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
