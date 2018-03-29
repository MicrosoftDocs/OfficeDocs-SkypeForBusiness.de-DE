---
title: Verwalten der Besprechungskonfigurationseinstellung in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Zusammenfassung: Informationen zum Verwalten von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.'
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Verwalten der Besprechungskonfigurationseinstellung in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen zum Verwalten von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.
  
In diesem Themenbereich wird die Verwaltung der Einstellungen der Besprechungskonfiguration beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype für Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) und [Bereitstellen von Konferenzen in Skype für Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Besprechungskonfigurationseinstellungen bestimmen den Typ des Besprechungen, die Benutzer, müssen Sie zusätzlich zu steuern erstellen können wie (oder sogar ob) anonyme Benutzer und Benutzer von einwahlkonferenzen können an diesen Besprechungen teilnehmen. Beachten Sie, dass diese Einstellungen nur geplante Besprechungen wirken sich auf. Sie wirken sich nicht auf Ad-hoc-Besprechungen durch Klicken auf die Option Jetzt besprechen in Skype für Unternehmen erstellt.
  
Die Konfigurationseinstellungen für Besprechungen definieren Folgendes:
  
- Werden Benutzer, die sich über das Telefonfestnetz (PSTN, Public Switched Telephone Network) einwählen, in den Wartebereich umgeleitet?
    
- Welche Benutzer können als Referenten fungieren?
    
- Wird der Konferenztyp standardmäßig zugeordnet?
    
- Werden anonyme Benutzer (ohne Authentifizierung) standardmäßig zugelassen?
    
Sie können die Merkmale von Besprechungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell definieren. 
  
Sie können angeben, Besprechung Einstellungen auf globaler Ebene (standardmäßig erstellt), site-Ebene oder -pool-Ebene. Standardmäßig werden die Besprechungen über die globalen Einstellungen definiert. Wenn Sie Einstellungen auf der Poolebene erstellen, gelten diese für alle Besprechungen, die von dem jeweiligen Pool gehostet werden. Wenn Sie keine Einstellungen auf der Poolebene erstellen, gelten die auf der Standortebene definierten Einstellungen (sofern vorhanden). Sind keine Einstellungen auf der Standortebene definiert, werden die globalen Einstellungen auf sämtliche Besprechungen angewendet.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Verwalten von Einstellungen für die Besprechung mithilfe von Skype Business Server-Systemsteuerung

So verwalten Sie besprechungseinstellungen mithilfe von Skype Business Server-Systemsteuerung
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Verwalten von Einstellungen für die Besprechung mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie zum Verwalten von Besprechungen mithilfe von Skype für Business Server-Verwaltungsshell die folgenden Cmdlets:
  
**Besprechungskonfigurationseinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen zurück.  <br/> |
|[Mit New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konfigurationseinstellungen für Besprechungen auf Standort- oder Dienstebene.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Löscht eine vorhandene Auflistung von Konfigurationseinstellungen für Besprechungen.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Passt die derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen an.  <br/> |
   

