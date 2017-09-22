---
title: Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: Hier erfahren Sie, wie Sie eine hybride Exchange-Organisation zur Verwendung in Microsoft Teams konfigurieren.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1491eee943de42646df6a403a576d48bcbbe5cb8
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2017
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="2cb02-103">Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2cb02-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="2cb02-p101">Normalerweise ist die Konfiguration von Exchange Online-Funktionen zur Verwendung mit Microsoft Teams nicht erforderlich. Für hybride Exchange-Szenarios müssen bestimmte Schritte ausgeführt werden, um die Synchronisierung von Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online zu gewährleisten. Neben verschiedenen Initialisierungsskripts beinhaltet dies die Gruppenrückschreiben-Funktionen in Azure AD Connect: [Konfigurieren von Office 365-Gruppen für lokale Exchange-Hybridbereitstellungen](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="2cb02-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
