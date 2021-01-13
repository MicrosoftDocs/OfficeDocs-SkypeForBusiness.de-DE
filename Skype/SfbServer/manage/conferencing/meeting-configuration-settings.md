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
description: 'Zusammenfassung: Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server verwalten.'
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828085"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Verwalten von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server verwalten.
  
In diesem Thema wird die Verwaltung von Besprechungskonfigurationseinstellungen beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter "Planen von Konferenzen [in Skype for Business Server"](../../plan-your-deployment/conferencing/conferencing.md) und "Bereitstellen von Konferenzen in Skype for Business [Server".](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
Besprechungskonfigurationseinstellungen bestimmen die Art von Besprechungen, die Benutzer erstellen können, und steuern zusätzlich, wie (oder auch ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. sie wirken sich nicht auf Ad-hoc-Besprechungen aus, die durch Klicken auf die Option "Sofortbesprechungen" in Skype for Business erstellt werden.
  
Die Besprechungskonfigurationseinstellungen definieren Folgendes:
  
- Ob Benutzer, die sich aus dem Telefonfestnetz einwählen, zum Wartebereich weitergeleitet werden
    
- Wer als Referent agieren darf
    
- Ob der Konferenztyp standardmäßig zugewiesen wird
    
- Ob anonyme (nicht authentifizierte) Benutzer standardmäßig zugelassen werden
    
Sie können Die Merkmale von Besprechungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell definieren. 
  
Sie können Besprechungseinstellungen auf globaler (standardmäßiger), Standort- oder Poolebene angeben. Standardmäßig definieren die globalen Einstellungen die Besprechungserfahrung. Wenn Sie Einstellungen auf Poolebene erstellen, gelten diese Einstellungen für alle Besprechungen, die von diesem Pool gehostet werden. Wenn Sie keine Einstellungen auf Poolebene erstellen, gelten die Einstellungen auf Standortebene, sofern vorhanden. Wenn Sie keine Einstellungen auf Standortebene definieren, gelten die globalen Einstellungen für alle Besprechungen.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Verwalten von Besprechungseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Besprechungseinstellungen mithilfe der Skype for Business Server-Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf "Konferenzen"** und dann auf **"Besprechungskonfiguration".**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Verwalten von Besprechungseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Besprechungen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konfigurationseinstellungen für Besprechungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen zurück.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Besprechungskonfigurationseinstellungen auf Standort- oder Dienstseite.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Löscht eine vorhandene Auflistung von Besprechungskonfigurationseinstellungen.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Ändert die derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen.  <br/> |
   

