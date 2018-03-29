---
title: Verwalten von Konferenzrichtlinien in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Zusammenfassung: Informationen Sie zum Verwalten von konferenzrichtlinien in Skype für Business Server 2015.'
ms.openlocfilehash: 48ae623a9571b848ccb70b377416343eccca0c1c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-policies-in-skype-for-business-server-2015"></a>Verwalten von Konferenzrichtlinien in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Verwalten von konferenzrichtlinien in Skype für Business Server 2015.
  
In diesem Themenbereich wird die Verwaltung der Konferenzrichtlinien beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype für Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) und [Bereitstellen von Konferenzen in Skype für Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Mit den Konferenzrichtlinien können Sie eine breite Auswahl an Planungs- und Teilnahmeoptionen definieren, von der Verwendung von IP-Audio und -Video in einer Besprechung bis hin zur Höchstzahl der möglichen Teilnehmer. Sie können die Konferenzrichtlinien verwenden, um die Sicherheit, die Bandbreite und die rechtlichen Aspekte von Besprechungen zu verwalten.
  
Die Konferenzrichtlinie kann auf drei Ebenen definiert werden: auf globaler, auf Standort- und auf Benutzerebene. Die Einstellungen gelten für einen bestimmten Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine Richtlinie zuweisen, erhalten diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gelten die Standorteinstellungen. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale Richtlinie die Standardeinstellungen bereit.
  
Standardmäßig ist eine globale Richtlinie vorhanden, daher können Sie eine neue globale Richtlinie erstellen. Die vorhandene globale Richtlinie auch kann nicht gelöscht werden, aber Sie können die vorhandene globale Richtlinie zum Anpassen Ihrer Standardeinstellungen ändern.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Verwalten von konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung

So verwalten Sie konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Verwalten von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie zum Verwalten von Besprechungen mithilfe von Skype für Business Server-Verwaltungsshell die folgenden Cmdlets:
  
**Konferenzrichtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.  <br/> |
|[GRANT-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Weist einzelnen Benutzern eine Konferenzrichtlinie zu.  <br/> |
|[Mit New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Entfernt die angegebene Konferenzrichtlinie.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Ändert eine vorhandene Konferenzrichtlinie.  <br/> |
   

