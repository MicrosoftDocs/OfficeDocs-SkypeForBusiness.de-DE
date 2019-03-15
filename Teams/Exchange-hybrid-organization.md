---
title: Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Hier erfahren Sie, wie Sie eine hybride Exchange-Organisation zur Verwendung in Microsoft Teams konfigurieren.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4dfc6b476498fef4484718a90f9c242a565cd64
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568560"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
======================================================================

Im Allgemeinen sollten Sie keine Exchange Online-Funktionalität für die Verwendung mit Microsoft-Teams, zu konfigurieren. Für Exchange Hybrid-Szenarien gibt es jedoch Schritte erforderlich sind, um sicherzustellen, dass Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online synchronisiert werden. Dies beinhaltet die Aktivierung der Gruppe Rückschreiben-Funktionalität in Azure AD-Connect zusammen mit verschiedenen Initialisierungsskripts: [Konfigurieren von Office 365-Gruppen mit der lokale Exchange Hybrid](https://go.microsoft.com/fwlink/?linkid=854389).
