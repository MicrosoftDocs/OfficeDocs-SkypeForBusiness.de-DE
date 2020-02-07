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
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb81460a5a3d388bc9634cb53ce15655933534c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834445"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="f99ea-103">Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f99ea-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="f99ea-p101">Im Allgemeinen sollten Sie keine Exchange Online-Funktionen für die Verwendung mit Microsoft Teams konfigurieren müssen. Für Exchange-Hybrid Szenarien sind jedoch Schritte erforderlich, um sicherzustellen, dass Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online synchronisiert werden. Dies umfasst die Aktivierung der Gruppen Rückschreibe Funktion in Azure AD Connect zusammen mit verschiedenen Initialisierungsskripts: [Konfigurieren von Office 365-Gruppen mit lokalem Exchange-Hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="f99ea-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
