---
title: Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Hier erfahren Sie, wie Sie eine hybride Exchange-Organisation zur Verwendung in Microsoft Teams konfigurieren.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68b2fee13668db8ba3986302d58bc16b0fa89080
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235203"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
======================================================================

Im Allgemeinen sollten Sie keine Exchange Online-Funktionen für die Verwendung mit Microsoft Teams konfigurieren müssen. Für Exchange-Hybrid Szenarien sind jedoch Schritte erforderlich, um sicherzustellen, dass Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online synchronisiert werden. Dies umfasst die Aktivierung der Gruppen Rückschreibe Funktion in Azure AD Connect zusammen mit verschiedenen Initialisierungsskripts: [Konfigurieren von Office 365-Gruppen mit lokalem Exchange-Hybrid](https://go.microsoft.com/fwlink/?linkid=854389).
