---
title: Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Hier erfahren Sie, wie Sie eine hybride Exchange-Organisation zur Verwendung in Microsoft Teams konfigurieren.
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 95b891394584d457f16a25b86d24614883443f9f
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2017
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="29a84-103">Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29a84-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="29a84-p101">Normalerweise ist die Konfiguration von Exchange Online-Funktionen zur Verwendung mit Microsoft Teams nicht erforderlich. Für hybride Exchange-Szenarios müssen bestimmte Schritte ausgeführt werden, um die Synchronisierung von Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online zu gewährleisten. Neben verschiedenen Initialisierungsskripts beinhaltet dies die Gruppenrückschreiben-Funktionen in Azure AD Connect: [Konfigurieren von Office 365-Gruppen für lokale Exchange-Hybridbereitstellungen](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="29a84-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
