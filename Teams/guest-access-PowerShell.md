---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: Verwenden Sie PowerShell, um den Gastzugriff auf Teams in Microsoft Teams zuzulassen oder zu blockieren.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: fd9844d0a72932cb28dca97d8bb8c1c05d0ddfe5
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
================================================

Zusätzlich zur Verwendung des Office 365 Admin Center und des Azure Active Directory-Portals können Sie Windows PowerShell verwenden, um den Gastzugriff zu steuern. Mit PowerShell können Sie folgende Aktionen durchführen:
  
  
   

- Zulassen und Blockieren von Gastzugriff auf alle Teams in Office 365-Gruppen
    
  
- Zulassen, dass Gäste zu allen Teams und Office 365-Gruppen hinzugefügt werden können
    
  
- Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe
    
  
Weitere Einzelheiten finden Sie unter [Verwenden von PowerShell zum Steuern von Gastzugriff](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).
  
    
    
Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden. Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam). Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können. Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).
  
 
Wenn Sie Gäste in Teams blockieren möchten und den Gästen dennoch den Zugriff auf SharePoint-Websites ermöglichen möchten, können Sie mithilfe von PowerShell-Cmdlets für Azure Active Directory den Parameter „AllowGuestAccessToGroups“ für das Objekt „Company“ deaktivieren. Dabei wird angenommen, dass externe Freigaben für SharePoint-Websites aktiviert sind.   