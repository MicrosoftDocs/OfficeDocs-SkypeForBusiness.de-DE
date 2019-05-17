---
title: Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dstrome
description: Hier erfahren Sie, wie Sie eine hybride Exchange-Organisation zur Verwendung in Microsoft Teams konfigurieren.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3b41f0ae30fb0c21baab1f7e01b86e79300008e
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108636"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="edf5c-103">Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="edf5c-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="edf5c-p101">Im Allgemeinen sollten Sie keine Exchange Online-Funktionalität für die Verwendung mit Microsoft-Teams, zu konfigurieren. Für Exchange Hybrid-Szenarien gibt es jedoch Schritte erforderlich sind, um sicherzustellen, dass Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online synchronisiert werden. Dies beinhaltet die Aktivierung der Gruppe Rückschreiben-Funktionalität in Azure AD-Connect zusammen mit verschiedenen Initialisierungsskripts: [Konfigurieren von Office 365-Gruppen mit der lokale Exchange Hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="edf5c-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
