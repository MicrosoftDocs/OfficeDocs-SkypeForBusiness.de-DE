---
title: Übersicht über dynamische Mitgliedschaft für Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zu dynamischen Teammitgliedschaft basierend auf AAD.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45e9da5b5bc9c1bb5800634d727bd6c9218812ab
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569830"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Übersicht über dynamische Mitgliedschaft für Teams

Microsoft-Teams unterstützt Teams dynamischen Mitgliedschaft mit Office 365-Gruppen zugeordnet. Dynamische Mitgliedschaft kann die Mitgliedschaft der ein Team durch eine oder mehrere Regeln definiert werden, die für bestimmte Benutzerattribute in Azure Active Directory (AAD) überprüfen. Benutzer werden automatisch hinzugefügt oder entfernt den richtigen Teams, wie Benutzerattribute ändern oder Benutzer teilnehmen, und lassen Sie den Mandanten.

Mit der dynamischen Mitgliedschaft können teams Setup für bestimmte Kohorten von Benutzern in Ihrer Organisation. Gibt die folgenden mögliche Szenarien:
- Ein Krankenhaus kann unterschiedliche Teams für Pflegepersonal, Ärzten und Chirurgen Communications Übertragung erstellen. Dies ist besonders wichtig, wenn das Krankenhaus temp Mitarbeiter erforderlich ist.
- Eine Universität kann erstellen Sie ein Team für alle Fakultät innerhalb einer bestimmten Universität, einschließlich einer angeschlossenen Fakultäts, die häufig ändert.
- Flugzeug möchte ein Team für jeden Flug (wie ein Tag Dienstag ununterbrochenen aus Chicago zu Atlanta) erstellen und eine oft geändertem Flug Crew automatisch zugewiesen oder bei Bedarf entfernt haben.

Verwenden dieses Feature, ein bestimmtes Team Mitglieder Update automatisch basierend auf einem bestimmten Satz von Kriterien manuell verwalten der Mitgliedschaft. Dies erfordert Azure AD Premium P1 Lizenzen und Teammitgliedschaft kann jeder Benutzer AAD Eigenschaften [von einem mandantenadministrator zugewiesen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) , vorausgesetzt, Sie haben einen Mandanten und ein Administratorkonto sein. 

Microsoft-Teams, kann an einer beliebigen Stelle von ein paar Minuten, bis zu 2 Stunden dauern dynamischen mitgliedschaftsänderungen aktualisiert, sobald sie in der Office 365-Gruppe für ein Team wirksam werden. 

> [!NOTE]
> - Regeln können definieren, die ein Teammitglied ist, jedoch nicht, die ein Team Besitzer ist.
> - Aktuelle Einschränkungen für Teams und der Kanal Größen finden Sie unter [Limits und Spezifikationen für Microsoft-Teams](limits-specifications-teams.md) .
> - Besitzer werden nicht hinzufügen oder Entfernen von Benutzern als Mitglieder des Teams, da durch Regeln für die dynamische Gruppe Mitglieder definiert sind.
> - Elemente werden nicht verlassen können Teams, die auf dynamische Gruppen.


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>Erstellen und Verwalten von einer Office 365-Gruppe mit dynamischen Mitgliedschaft
Beim Anmelden als den Mandanten Admin, befolgen Sie die Anweisungen in [einer dynamischen Gruppe erstellen und überprüfen Sie Status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule). Bei Bedarf finden Sie unter [Regeln für die dynamische Mitgliedschaft für Azure Active Directory-Gruppen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-o365-group"></a>Erstellen Sie ein neues Team mit Ihrer O365-Gruppe

Jetzt warten Sie die Änderungen wirksam werden, und erstellen Sie ein neues Team, wie in [Gruppen mit Microsoft-Teams verbessern vorhandenen Office 365](enhance-office-365-groups.md)beschrieben.

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Anwenden von dynamischen Mitgliedschaft an vorhandenen team

Sie können auch nehmen ein vorhandenes Team und ändern, um eine dynamische Mitgliedschaft, wie beschrieben in [statische Gruppenmitgliedschaft in einen dynamischen in Azure Active Directory ändern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Änderungen in Clientverhaltens

Sobald dynamischen Mitgliedschaft für ein Team aktiviert ist, können Teams Clients nicht mehr Member Management für das Team, nämlich. Optionen zum Hinzufügen von Mitgliedern, Rollen bearbeiten, senden und Genehmigen von Anfragen Join und das Team verlassen werden alle ausgeblendet.
