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
ms.openlocfilehash: 32a334f4866c1874f60e85e3b74908f161d45a33
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691551"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Behandeln von Problemen mit Gastzugriff in Microsoft Teams
======================================================

- Wenn Sie wissen möchten, ob Ihr Problem bekannt ist, lesen Sie [Support Teams in Ihrer Organisation](Known-issues.md).
- Wenn Sie nach Support für aktuelle Probleme mit dem Gastzugriff in Teams suchen möchten, wechseln Sie zu [Problembehandlung für Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Gäste sind Benutzer außerhalb Ihrer Organisation. Wenn sich eine Person in Ihrer Organisation befindet (beispielsweise ihre Mitarbeiter, Auftragnehmer oder Agenten vor Ort), können Sie nicht als Gäste hinzugefügt werden. Das gleiche gilt für Ihre Partner.
- Informationen zu geplanten neuen oder aktualisierten Funktionen für den Gastzugriff finden Sie in der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap).
- Teilen Sie uns auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website Ihre Wünsche mit.

## <a name="if-your-guests-are-seeing-license-errors"></a>Wenn Ihre Gäste Lizenzfehler sehen

Für den Gastzugriff in Microsoft Teams wird Azure Active Directory (Azure AD) Business-to-Business (B2B) und dessen Lizenzierungsmodell genutzt. Der Gastzugang ist in allen Abonnements von Microsoft 365 Business Standard, Office 365 Enterprise und Office 365 Education enthalten. Eine zusätzliche Microsoft 365- oder Office 365-Lizenz ist nicht erforderlich.

> [!NOTE]
> Teams müssen für den Home-Mandanten eines Gasts aktiviert sein, damit Gäste sich anmelden und Teams als Gast für einen anderen (Ressourcen-) Mandanten verwenden können.

Wenn Lizenzierungsfehler angezeigt werden, lesen Sie die [Azure Active Directory B2B-Lizenzierungs Anleitung](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , um die Lizenzierungsanforderungen zu ermitteln, die Ihren Anforderungen für den Gastzugriff in Ihrer Organisation entsprechen.


- Gastlizenzen werden für die einladende Organisation gezählt. Denken Sie daran, wenn Sie die Anzahl der benötigten Lizenzen berechnen.
- Lizenzen werden für Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste aus einer anderen Microsoft 365-oder Office 365-Organisation stammen oder Ihre persönlichen e-Mail-Adressen verwenden.

## <a name="support-for-b2b-user-types"></a>Unterstützung von B2B-Benutzertypen
Derzeit unterstützt Teams nur die Gastbenutzer vom Typ "Zustand 1" und "Zustand 2" [gemäß der Definition durch Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Verwandte Themen

[Gastzugriff in Teams](guest-access.md)


