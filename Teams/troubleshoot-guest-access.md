---
title: Behandeln von Problemen mit Gastzugriff in Microsoft Teams
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
description: Hier erhalten Sie Hilfe bei der Problembehandlung und dem Lösen von Problemen mit dem Gastzugriff in Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837635"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Behandeln von Problemen mit Gastzugriff in Microsoft Teams
======================================================

> [!IMPORTANT]
> Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden. 


- Wenn Sie nach Support für aktuelle Probleme mit dem Gastzugriff in Teams suchen möchten, wechseln Sie zu [Problembehandlung für Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Wenn Sie wissen möchten, ob Ihr Problem bereits bekannt ist, lesen Sie [Bekannte Probleme bei Microsoft Teams](Known-issues.md).
- Gäste sind Benutzer außerhalb Ihrer Organisation. Wenn sich eine Person in Ihrer Organisation befindet (beispielsweise ihre Mitarbeiter, Auftragnehmer oder Agenten vor Ort), können Sie nicht als Gäste hinzugefügt werden. Das gleiche gilt für Ihre Partner.
- Informationen zu geplanten neuen oder aktualisierten Funktionen für den Gastzugriff finden Sie in der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap).
- Teilen Sie uns auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website Ihre Wünsche mit.

## <a name="if-your-guests-are-seeing-license-errors"></a>Wenn Ihre Gäste Lizenzfehler sehen

Für den Gastzugriff in Microsoft Teams wird Azure Active Directory (Azure AD) Business-to-Business (B2B) und dessen Lizenzierungsmodell genutzt. Gastzugriff ist in allen Office 365 Business Premium-, Office 365 Enterprise- und Office 365 Education-Abonnements enthalten. Eine zusätzliche Office 365-Lizenz ist nicht erforderlich.

Wenn Sie Lizenzierungsprobleme haben, finden Sie im [Leitfaden zur Lizenzierung von Azure Active Directory B2B-Kollaboration](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) die Lizenzierungsanforderungen, die für den Gastzugriff in Ihrer Organisation erfüllt sein müssen.


- Gastlizenzen werden für die einladende Organisation gezählt. Denken Sie daran, wenn Sie die Anzahl der benötigten Lizenzen berechnen.
- Lizenzen werden gegen Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste von einem anderen Office 365-Mandanten stammen oder Ihre persönlichen e-Mail-Adressen verwenden.

## <a name="support-for-b2b-user-types"></a>Unterstützung von B2B-Benutzertypen
Derzeit unterstützt Teams nur die Gastbenutzer vom Typ "Zustand 1" und "Zustand 2" [gemäß der Definition durch Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Verwandte Themen

[Gastzugriff in Teams](guest-access.md)


