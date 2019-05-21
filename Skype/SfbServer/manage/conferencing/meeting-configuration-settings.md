---
title: Verwalten von Besprechungs Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Besprechungen in Skype for Business Server verwalten.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283739"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Verwalten von Besprechungs Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Besprechungen in Skype for Business Server verwalten.
  
In diesem Themenbereich wird die Verwaltung der Einstellungen der Besprechungskonfiguration beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Die Konfigurationseinstellungen für Besprechungen diktieren die Art der Besprechungen, die Benutzer erstellen können, und Steuern, wie (oder sogar ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. Sie wirken sich nicht auf Ad-hoc-Besprechungen aus, die durch Klicken auf die Option "jetzt besprechen" in Skype for Business erstellt wurden.
  
Die Konfigurationseinstellungen für Besprechungen definieren Folgendes:
  
- Werden Benutzer, die sich über das Telefonfestnetz (PSTN, Public Switched Telephone Network) einwählen, in den Wartebereich umgeleitet?
    
- Welche Benutzer können als Referenten fungieren?
    
- Wird der Konferenztyp standardmäßig zugeordnet?
    
- Werden anonyme Benutzer (ohne Authentifizierung) standardmäßig zugelassen?
    
Sie können die Merkmale von Besprechungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell definieren. 
  
Sie können Besprechungseinstellungen auf globaler Ebene (standardmäßig erstellt), Websiteebene oder Poolebene angeben. Standardmäßig werden die Besprechungen über die globalen Einstellungen definiert. Wenn Sie Einstellungen auf der Poolebene erstellen, gelten diese für alle Besprechungen, die von dem jeweiligen Pool gehostet werden. Wenn Sie keine Einstellungen auf der Poolebene erstellen, gelten die auf der Standortebene definierten Einstellungen (sofern vorhanden). Sind keine Einstellungen auf der Standortebene definiert, werden die globalen Einstellungen auf sämtliche Besprechungen angewendet.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Verwalten von Besprechungseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Besprechungseinstellungen mithilfe der Skype for Business Server-Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Verwalten von Besprechungseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Verwalten von Besprechungen mithilfe der Skype for Business Server-Verwaltungsshell die folgenden Cmdlets:
  
**Konfigurationseinstellungen für Besprechungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen zurück.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konfigurationseinstellungen für Besprechungen auf Standort- oder Dienstebene.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Löscht eine vorhandene Auflistung von Konfigurationseinstellungen für Besprechungen.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Passt die derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen an.  <br/> |
   

