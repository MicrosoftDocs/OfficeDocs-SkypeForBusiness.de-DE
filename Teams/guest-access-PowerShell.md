---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Verwenden Sie PowerShell, um den Gastzugriff auf Teams in Microsoft Teams zuzulassen oder zu blockieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0efb3a8054008d179b9d2e7e674b3482fe62a32c
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865090"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
================================================

Windows PowerShell können Sie zusätzlich zur Verwendung der Microsoft-365-Verwaltungskonsole und Azure Active Directory-Portal, um Gastzugriff zu steuern. Mit PowerShell können Sie folgende Aktionen durchführen:
  
- Zulassen und Blockieren von Gastzugriff auf alle Teams in Office 365-Gruppen
    
- Zulassen, dass Gäste zu allen Teams und Office 365-Gruppen hinzugefügt werden können
      
- Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe
    
Weitere Informationen hierzu finden Sie im Abschnitt "Verwenden von PowerShell zur Steuerung des Zugriffs Gast" auf der Registerkarte Verwalten von [Gast Access in Office 365-Gruppen](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden. Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam). Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können. Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).
  
Wenn Sie möchten Gäste in Teams blockieren und trotzdem auf SharePoint-Websites zugreifen zu können, können Azure Active Directory-Powershell-Cmdlets Sie zum Deaktivieren des AllowGuestsToAccessGroups-Parameters für das Unternehmen-Objekt unter der Voraussetzung, dass externe Freigabe für eingeschaltet ist SharePoint-Websites.   

## <a name="guest-access-vs-external-access"></a>Gastzugriff im Vergleich zum externen Zugriff

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
