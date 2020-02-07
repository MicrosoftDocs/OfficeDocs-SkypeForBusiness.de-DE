---
title: Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Erhalten Sie Hilfe bei der Problembehandlung und Beheben von Problemen mit dem Gastzugriff in Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837635"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams
======================================================

> [!IMPORTANT]
> Möglicherweise müssen Sie bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden. 


- Wenn Sie nach aktuellen Supportproblemen mit Gastzugriff in Teams suchen möchten, wechseln Sie zur [Problembehandlung für Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Wenn Sie wissen möchten, ob Ihr Problem bekannt ist, lesen Sie [bekannte Probleme für Microsoft Teams](Known-issues.md).
- Gäste sind Benutzer außerhalb Ihrer Organisation. Wenn sich eine Person in Ihrer Organisation befindet (einschließlich ihrer Mitarbeiter, vor-Ort-Auftragnehmer oder vor-Ort-Agents), können Sie nicht als Gäste hinzugefügt werden. Das gleiche gilt für Ihre Partner.
- Informieren Sie sich über die bevorstehenden neuen oder aktualisierten Features für den Gastzugriff in der [Roadmap für Teams](https://aka.ms/teamsroadmap).
- Teilen Sie uns mit, was Sie in [Teams UserVoice](https://aka.ms/TeamsUserVoice)möchten.

## <a name="if-your-guests-are-seeing-license-errors"></a>Wenn Ihre Gäste Lizenzfehler sehen

Der Gastzugriff in Teams verwendet Azure Active Directory (Azure AD) Business to Business (B2B) und sein Lizenzierungsmodell. Gastzugriff ist in allen Office 365 Business Premium-, Office 365 Enterprise- und Office 365 Education-Abonnements enthalten. Eine zusätzliche Office 365-Lizenz ist nicht erforderlich.

Wenn Lizenzierungsfehler angezeigt werden, lesen Sie die [Azure Active Directory B2B-Lizenzierungs Anleitung](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , um die Lizenzierungsanforderungen zu ermitteln, die Ihren Anforderungen für den Gastzugriff in Ihrer Organisation entsprechen.


- Gastlizenzen werden für die einladende Organisation gezählt. Denken Sie daran, wenn Sie die Anzahl der benötigten Lizenzen berechnen.
- Lizenzen werden gegen Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste von einem anderen Office 365-Mandanten stammen oder Ihre persönlichen e-Mail-Adressen verwenden.

## <a name="support-for-b2b-user-types"></a>Unterstützung für B2B-Benutzertypen
Zurzeit unterstützt Teams nur die Typen von Gastbenutzern des Status 1 und des Status 2 [, wie Sie von Azure B2B definiert werden](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Verwandte Themen

[Gastzugriff in Teams](guest-access.md)


