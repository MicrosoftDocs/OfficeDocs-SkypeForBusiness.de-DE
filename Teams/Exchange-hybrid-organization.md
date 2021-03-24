---
title: Konfigurieren einer Exchange-Hybridorganisation
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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094607"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
======================================================================

Im Allgemeinen sollten Sie keine Exchange Online-Funktionen für die Verwendung mit Microsoft Teams konfigurieren müssen. Für Exchange Hybrid-Szenarien sind jedoch Schritte erforderlich, um sicherzustellen, dass Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online synchronisiert werden. Dazu gehört die Aktivierung der Gruppenrückschreiben-Funktionalität in Azure AD Connect zusammen mit verschiedenen Initialisierungsskripts: Konfigurieren von [Microsoft 365-Gruppen](/exchange/hybrid-deployment/set-up-microsoft-365-groups)mit einer lokalen Exchange-Hybrid- .