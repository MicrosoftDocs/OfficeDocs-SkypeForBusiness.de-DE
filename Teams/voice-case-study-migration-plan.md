---
title: Teams Voice Contoso– Upgradeplan für Fallstudien
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
description: 'Teams Voice Case Study für multinationale Unternehmen: Upgradeplanung.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39cfd66f0ff34fb0f8792871ddfdcceebb2b9961
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822984"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso-Fallstudie: Teams Upgradeplan

Bei der Entscheidung für die Migration von Skype for Business zu Teams wollte Contoso Endbenutzern eine einfache Übergangserfahrung bieten. Anstatt alle gleichzeitig auf Teams umzustellen, entschied man sich für die Einrichtung einer Hybridkonnektivität und die Verwendung der Methode für überlappende Funktionen, um Benutzer in Teams zu verschieben. Dadurch konnten Benutzer in Teams und Skype for Business lokal Anwesenheitsinformationen freigeben und kommunizieren. Als Benutzer das Pilotprojekt für Telefonsystem eingegeben haben, wurden sie in den Modus "Nur Teams" verschoben.

Um grundlegende Konzepte zu Upgrade, Methoden und Modi zu verstehen, lesen Contoso die folgenden Artikel:

- [Erste Schritte beim Upgrade auf Microsoft Teams](upgrade-start-here.md)
- [Upgradestrategien für IT-Administratoren](upgrade-to-teams-on-prem-implement.md) 
- [Migrations- und Interoperabilitätsleitfaden](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso nahm auch an der Ignite 2019 Session [Designing your path from Skype for Business to Teams](https://myignite.microsoft.com/archives/IG20-OD251) teil. Contoso hat Folgendes gelernt:

- Grundlegende Konzepte wie Interoperabilität, Verbund und Upgradeverhalten 

- Koexistenzmodi und Verwaltung basierend auf TeamsUpgradePolicy 

- Endbenutzererfahrung für: 

  - Chat und Anrufe 

  - Besprechungsplanung 

  - Verfügbarkeit von Zusammenarbeitsfunktionen in Teams Clients 

Um die Hybridkonnektivität zu planen und zu konfigurieren, ist der erste Schritt beim Verschieben ihrer lokalen Umgebung in die Cloud, Contoso lesen [Sie "Planen der Hybridkonnektivität](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) " und ["Konfigurieren der Hybridkonnektivität](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) ", um zu verstehen, wie Folgendes zu verstehen ist: 

  - Konfigurieren Sie den lokalen Umgebungsdienst für den Verbund mit Office 365. 

  - Konfigurieren Sie die lokale Umgebung so, dass Office 365 vertraut wird, und aktivieren Sie gemeinsam genutzten SIP-Adressraum mit Office 365 

  - Aktivieren Sie den freigegebenen SIP-Adressraum in ihrem Office 365 Mandanten.

  - Verwenden Sie den Inselmodus während des technischen Pilotprojekts.

  - Schalten Sie Benutzer in den TeamsOnly-Modus, sobald der Benutzer für Telefonsystem aktiviert ist. Der TeamsOnly-Modus ist für Anrufplan und Direct Routing erforderlich.
