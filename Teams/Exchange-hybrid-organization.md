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
description: Erfahren Sie, wie Sie Exchange Hybridorganisation für die Verwendung mit Microsoft Teams konfigurieren, um sicherzustellen, dass Gruppenmitgliedschaften synchronisiert werden.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4a0480ff8a795addb9ae322478fddb69e9aeceeed14ebca83f27cac34b01bfbb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284475"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Konfigurieren einer hybriden Exchange-Organisation zur Verwendung in Microsoft Teams
======================================================================

Im Allgemeinen sollte es nicht erforderlich sein, eine Exchange Online für die Verwendung mit Microsoft Teams. Für hybride Exchange sind jedoch Schritte erforderlich, um sicherzustellen, dass Gruppenmitgliedschaften zwischen Exchange Server (lokal) und Exchange Online. Dies umfasst die Aktivierung der Funktionen für Gruppenrückschreiben in Azure AD Verbinden zusammen mit verschiedenen Initialisierungsskripts: Konfigurieren von Microsoft 365-Gruppen mit einer lokalen [Exchange Hybridbereitstellung.](/exchange/hybrid-deployment/set-up-microsoft-365-groups)