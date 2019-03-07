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
ms.openlocfilehash: e52c757b3e2456561d664b07667a5f08fd1c1617
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458932"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="aef1b-103">Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aef1b-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="aef1b-p101">Normalerweise ist die Konfiguration von Exchange Online-Funktionen zur Verwendung mit Microsoft Teams nicht erforderlich. Für hybride Exchange-Szenarios müssen bestimmte Schritte ausgeführt werden, um die Synchronisierung von Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online zu gewährleisten. Neben verschiedenen Initialisierungsskripts beinhaltet dies die Gruppenrückschreiben-Funktionen in Azure AD Connect: [Konfigurieren von Office 365-Gruppen für lokale Exchange-Hybridbereitstellungen](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="aef1b-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
