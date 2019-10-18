---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Verwenden Sie PowerShell, um den Gastzugriff auf Teams in Microsoft Teams zuzulassen oder zu blockieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1cecceb81b967d4c6d2f4c9ca440e04d6fec9518
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563483"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
================================================

Neben der Verwendung des Microsoft 365 admin Centers und des Azure Active Directory (Azure AD)-Portals können Sie Windows PowerShell zum Steuern des Gastzugriffs verwenden. Mit PowerShell können Sie folgende Aktionen durchführen:
  
- Zulassen oder Blockieren des Gastzugriffs auf alle Teams und Office 365-Gruppen

- Zulassen, dass Gäste allen Teams und Office 365-Gruppen hinzugefügt werden

- Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe

Ausführliche Informationen finden Sie unter "Verwenden von PowerShell zum Steuern des Gastzugriffs" in [Verwalten des Gastzugriffs in Office 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).
  
Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden. Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam). Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können. Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).
  
Wenn Sie die Gäste in Teams blockieren und Ihnen weiterhin den Zugriff auf SharePoint-Websites gestatten möchten, können Sie Azure AD PowerShell-Cmdlets verwenden, um den AllowGuestsToAccessGroups-Parameter für das Unternehmensobjekt zu deaktivieren, vorausgesetzt, die externe Freigabe ist für SharePoint-Websites aktiviert. .

## <a name="guest-access-vs-external-access"></a>Gastzugriff vs. externer Zugriff

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
