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
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120767"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Übersicht über die dynamische Mitgliedschaft für Teams

Microsoft Teams unterstützt Teams, die Microsoft 365-Gruppen zugeordnet sind, mithilfe der *dynamischen Mitgliedschaft*. Mithilfe der dynamischen Mitgliedschaft in Microsoft Teams kann die Mitgliedschaft in einem Teams durch eine oder mehrere Regeln definiert werden, die bestimmte Benutzerattribute in Azure Active Directory (Azure AD) überprüfen. Benutzer werden automatisch zu den richtigen Teams hinzugefügt bzw. daraus entfernt, wenn sich Benutzerattribute ändern oder Benutzer dem Mandanten beitreten und diesen verlassen.

Mit einer dynamischen Mitgliedschaft können Sie Teams für bestimmte Benutzergruppen in Ihrer Organisation einrichten. Mögliche Szenarien umfassen:
- Ein Krankenhaus kann verschiedene Teams für Krankenschwestern, Ärzte und Chirurgen bilden, um Mitteilungen zu übermitteln. Dies ist besonders wichtig, wenn das Krankenhaus auf temporäre Mitarbeiter angewiesen ist.
- Eine Universität kann ein Team für alle Dozenten innerhalb eines bestimmten Colleges einrichten, auch für zusätzliche, häufig wechselnde Dozenten.
- Eine Fluggesellschaft möchte für jeden Flug (z. B. Dienstagnachmittag Nonstop-Flug von Chicago nach Atlanta) ein Team erstellen und eine häufig wechselnde Flugbesatzung bei Bedarf automatisch zuweisen oder entfernen.

Mit dieser Funktion werden die Mitglieder eines bestimmten Teams automatisch anhand bestimmter Kriterien aktualisiert, anstatt die Mitgliedschaft manuell zu verwalten. Dazu sind Azure AD Premium P1-Lizenzen erforderlich und die Team-Mitgliedschaft kann den Azure AD-Eigenschaften eines beliebigen Benutzers [durch einen Mandanten-Administrator zugewiesen werden](/azure/active-directory/users-groups-roles/groups-dynamic-membership), sofern Sie über einen Mandanten und ein Administrator-Konto verfügen.

Microsoft Teams kann einige Minuten bis zu zwei Stunden benötigen, um dynamische Mitgliedschaftsänderungen zu widerspiegeln, sobald sie in der Microsoft 365-Gruppe für ein Team wirksam wurden.

> [!NOTE]
> - Regeln können definieren, wer ein Teammitglied ist, aber nicht, wer der Teambesitzer ist.
> - Aktuelle Grenzwerte für Team- und Kanalgrößen finden Sie unter [Grenzwerte und Spezifikationen für Microsoft Teams](limits-specifications-teams.md).
> - Besitzer können keine Benutzer als Teammitglieder hinzufügen oder entfernen, da Mitglieder über dynamische Gruppenregeln definiert werden.
> -    Mitglieder können keine Teams verlassen, die von dynamischen Gruppen unterstützt werden.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>Erstellen und Verwalten von Microsoft 365-Gruppen mit dynamischer Mitgliedschaft

Wenn Sie als Mandanten-Administrator angemeldet sind, folgen Sie den Anweisungen in [Erstellen einer dynamischen Gruppe und Prüfen des Status](/azure/active-directory/users-groups-roles/groups-create-rule). Bei Bedarf finden Sie weitere Informationen unter [Regeln für eine dynamische Mitgliedschaft für Gruppen in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Erstellen eines neuen Teams mit Ihrer Microsoft 365-Gruppe

Warten Sie nun, bis die Mitgliedschaftsänderungen wirksam werden, und erstellen Sie ein neues Team, wie unter [Erstellen eines Teams aus einer vorhandenen Gruppe](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865) beschrieben.

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Dynamische Mitgliedschaft auf ein bestehendes Team anwenden

Sie können auch ein vorhandenes Team in ein Team mit dynamischer Mitgliedschaft ändern, wie unter [Die statische Gruppenmitgliedschaft im Azure Active Directory nach dynamisch ändern](/azure/active-directory/users-groups-roles/groups-change-type) beschrieben.

## <a name="changes-in-client-behavior"></a>Änderungen im Client-Verhalten

Sobald die dynamische Mitgliedschaft für ein Team aktiviert ist, wird der Teams-Client die Mitgliederverwaltung für das Team nicht mehr zulassen. Die Optionen, um Mitglieder hinzuzufügen, Mitgliederrollen zu bearbeiten, Beitrittsanfragen zu senden und zu genehmigen und das Team zu verlassen, sind alle ausgeblendet.