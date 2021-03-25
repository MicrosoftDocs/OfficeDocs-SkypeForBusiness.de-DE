---
title: Verwalten von Besprechungskonfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Zusammenfassung: Informationen zum Verwalten von Besprechungskonfigurationseinstellungen in Skype for Business Server.'
ms.openlocfilehash: 1e6ef11992a547456d2a971c2f8de6f3097b166e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119434"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Verwalten von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server verwalten.
  
In diesem Thema wird das Verwalten von Besprechungskonfigurationseinstellungen beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Besprechungskonfigurationseinstellungen bestimmen die Art von Besprechungen, die Benutzer erstellen können, und steuern nicht nur, wie (oder auch wenn) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Beachten Sie, dass diese Einstellungen nur geplante Besprechungen betreffen. sie wirken sich nicht auf Ad-hoc-Besprechungen aus, die durch Klicken auf die Option Jetzt treffen in Skype for Business erstellt werden.
  
Besprechungskonfigurationseinstellungen definieren Folgendes:
  
- Ob Benutzer, die sich aus dem Telefonfestnetz einwählen, zum Wartebereich weitergeleitet werden
    
- Wer als Referent agieren darf
    
- Ob der Konferenztyp standardmäßig zugewiesen wird
    
- Ob anonyme (nicht authentifizierte) Benutzer standardmäßig zugelassen werden
    
Sie können Die Merkmale von Besprechungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell definieren. 
  
Sie können Besprechungseinstellungen auf globaler (standardmäßig erstellter), Standort- oder Poolebene angeben. Standardmäßig definieren die globalen Einstellungen die Besprechungserfahrung. Wenn Sie Einstellungen auf Poolebene erstellen, gelten diese Einstellungen für alle Besprechungen, die von diesem Pool gehostet werden. Wenn Sie keine Einstellungen auf Poolebene erstellen, gelten Einstellungen auf Standortebene, sofern vorhanden. Wenn Sie keine Einstellungen auf Websiteebene definieren, gelten die globalen Einstellungen für alle Besprechungen.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Verwalten von Besprechungseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Besprechungseinstellungen mithilfe der Skype for Business Server-Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf** Konferenzen und dann auf **Besprechungskonfiguration**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Verwalten von Besprechungseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Besprechungen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konfigurationseinstellungen für Besprechungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den Besprechungskonfigurationseinstellungen zurück, die derzeit in Ihrer Organisation verwendet werden.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Besprechungskonfigurationseinstellungen auf Standort- oder Dienstbereich.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Löscht eine vorhandene Auflistung von Besprechungskonfigurationseinstellungen.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Ändert die derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen.  <br/> |
