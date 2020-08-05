---
title: Konfigurieren einer Exchange-Hybrid Organisation
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Hier erfahren Sie, wie Sie eine Exchange-Hybrid Organisation für die Verwendung mit Microsoft Teams konfigurieren, um sicherzustellen, dass Gruppenmitgliedschaften synchronisiert werden.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551961"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
======================================================================

Im Allgemeinen sollten Sie keine Exchange Online-Funktionen für die Verwendung mit Microsoft Teams konfigurieren müssen. Für Exchange-Hybrid Szenarien sind jedoch Schritte erforderlich, um sicherzustellen, dass Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online synchronisiert werden. Dies umfasst die Aktivierung der Gruppen Rückschreibe Funktion in Azure AD Connect zusammen mit verschiedenen Initialisierungsskripts: [Konfigurieren von Microsoft 365-Gruppen mit lokalem Exchange-Hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups).
