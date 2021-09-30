---
title: Konfigurieren einer Exchange Hybridorganisation
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Erfahren Sie, wie Sie eine Exchange-Hybridorganisation für die Verwendung mit Microsoft Teams konfigurieren, um sicherzustellen, dass Gruppenmitgliedschaften synchronisiert werden.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d1b5cb89f28a334b24aecf982dd3913dfce079ac
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014870"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams

Im Allgemeinen sollten Sie keine Exchange Online für die Verwendung mit Microsoft Teams. Für Hybridszenarien Exchange jedoch erforderliche Schritte, um sicherzustellen, dass Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online. Dies umfasst die Aktivierung der Funktionen für Gruppenrückschreiben in Azure AD Verbinden zusammen mit verschiedenen Initialisierungsskripts: Konfigurieren von [Microsoft 365-Gruppen](/exchange/hybrid-deployment/set-up-microsoft-365-groups)mit lokalem Exchange Hybrid.