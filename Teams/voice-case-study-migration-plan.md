---
title: Fallstudie "Teams voice Contoso"
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Sprachfallstudie zu Teams für multinationale Unternehmen
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093725"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso-Fallstudie: Upgradeplan für Teams

Bei der Entscheidung, von Skype for Business zu Teams zu migrieren, wollte Contoso endbenutzern eine einfache Übergangserfahrung bieten. Statt alle Benutzer gleichzeitig zu Teams zu wechseln, entschieden sie sich für die Einrichtung einer Hybridkonnektivität und verwenden die überlappende Funktionsmethode, um Benutzer nach Teams zu verschieben. Dadurch konnten Benutzer in Teams und Skype for Business lokal Anwesenheits- und Kommunikationsfreigaben nutzen. Als Benutzer in den Pilotmodus für Telefonsystem eintraten, wurden sie in den Modus "Nur Teams" verschoben.

Um grundlegende Konzepte zu Upgrade, Methoden und Modi zu verstehen, lesen Sie in Contoso die folgenden Artikel:

- [Erste Schritte mit dem Upgrade von Microsoft Teams](upgrade-start-here.md)
- [Upgradestrategien für IT-Administratoren](upgrade-to-teams-on-prem-implement.md) 
- [Migrations- und Interoperabilitätsleitfäden](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso nahm auch an der Ignite 2019-Sitzung ["Entwerfen Des Pfads von Skype for Business zu Teams" teil.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso hat gelernt:

- Grundlegende Konzepte wie Interoperabilität, Verbund und Upgradeverhalten 

- Koexistenzmodi und Verwaltung basierend auf TeamsUpgradePolicy 

- Endbenutzererfahrung für: 

  - Chatten und Anrufen 

  - Besprechungsplanung 

  - Verfügbarkeit von Funktionen für die Zusammenarbeit in Teams-Clients 

Um hybride Konnektivität zu planen und zu konfigurieren, lesen Sie im ersten Schritt beim Verschieben ihrer lokalen Umgebung in die Cloud contoso die Informationen [Planen](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) der Hybridkonnektivität und [Konfigurieren](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) der Hybridkonnektivität, um zu verstehen, wie Sie: 

  - Konfigurieren Sie den lokalen Umgebungsdienst für die Zusammenarbeit mit Office 365. 

  - Konfigurieren der lokalen Umgebung, um Office 365 zu vertrauen und gemeinsam genutzten SIP-Adressraum mit Office 365 zu aktivieren 

  - Aktivieren sie gemeinsam genutzten SIP-Adressbereich in ihrem Office 365-Mandanten.

  - Verwenden Sie den Inselmodus während des technischen Pilotprojekts.

  - Wechseln von Benutzern in den TeamsOnly-Modus, sobald der Benutzer für Telefonsystem aktiviert ist. Der Modus "TeamsOnly" ist für anrufplan und direktes Routing erforderlich.