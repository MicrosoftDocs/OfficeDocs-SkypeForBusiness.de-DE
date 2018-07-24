---
title: Verwalten von konferenzrichtlinien in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Zusammenfassung: Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server verwalten.'
ms.openlocfilehash: d5fed0c6615747069d71015fca33144ca41dd64b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986657"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Verwalten von konferenzrichtlinien in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server verwalten.
  
In diesem Themenbereich wird die Verwaltung der Konferenzrichtlinien beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype für Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Konferenzen in Skype für Business Server bereitstellen](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Mit den Konferenzrichtlinien können Sie eine breite Auswahl an Planungs- und Teilnahmeoptionen definieren, von der Verwendung von IP-Audio und -Video in einer Besprechung bis hin zur Höchstzahl der möglichen Teilnehmer. Sie können die Konferenzrichtlinien verwenden, um die Sicherheit, die Bandbreite und die rechtlichen Aspekte von Besprechungen zu verwalten.
  
Die Konferenzrichtlinie kann auf drei Ebenen definiert werden: auf globaler, auf Standort- und auf Benutzerebene. Die Einstellungen gelten für einen bestimmten Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine Richtlinie zuweisen, erhalten diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gelten die Standorteinstellungen. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale Richtlinie die Standardeinstellungen bereit.
  
Eine globale Richtlinie ist standardmäßig vorhanden. Sie können daher keine neue globale Richtlinie erstellen. Außerdem können Sie die vorhandene globale Richtlinie nicht löschen. Es ist jedoch möglich, die vorhandene globale Richtlinie Ihren Standardeinstellungen entsprechend anzupassen.
  
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
   

