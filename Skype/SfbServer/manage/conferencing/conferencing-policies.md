---
title: Verwalten von Konferenzrichtlinien in Skype for Business Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server verwalten.'
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835275"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Verwalten von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server verwalten.
  
In diesem Thema wird die Verwaltung von Konferenzrichtlinien beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter "Planen von Konferenzen [in Skype for Business Server"](../../plan-your-deployment/conferencing/conferencing.md) und "Bereitstellen von Konferenzen in Skype for Business [Server".](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
Mit Konferenzrichtlinien können Sie eine Vielzahl von Planungs- und Teilnahmeoptionen definieren, von der Festlegung, ob eine Besprechung ip-Audio- und -Videodaten enthalten kann, bis hin zur maximalen Anzahl von Personen, die teilnehmen können. Sie können Konferenzrichtlinien verwenden, um Sicherheits-, Bandbreiten- und rechtliche Aspekte von Besprechungen zu verwalten.
  
Die Konferenzrichtlinie kann auf drei Ebenen definiert werden: auf globaler, auf Standort- und auf Benutzerebene. Die Einstellungen gelten für einen bestimmten Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine Richtlinie zuweisen, haben diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gelten die Standorteinstellungen. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale Richtlinie die Standardeinstellungen bereit.
  
Eine globale Richtlinie ist standardmäßig vorhanden. Sie können daher keine neue globale Richtlinie erstellen. Außerdem können Sie die vorhandene globale Richtlinie nicht löschen. Es ist jedoch möglich, die vorhandene globale Richtlinie Ihren Standardeinstellungen entsprechend anzupassen.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Verwalten von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf "Konferenz" und dann auf **"Konferenzrichtlinie".**
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Besprechungen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konferenzrichtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Weist eine Konferenzrichtlinie auf Benutzerbereich zu.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Entfernt die angegebene Konferenzrichtlinie.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Ändert eine vorhandene Konferenzrichtlinie.  <br/> |
   

