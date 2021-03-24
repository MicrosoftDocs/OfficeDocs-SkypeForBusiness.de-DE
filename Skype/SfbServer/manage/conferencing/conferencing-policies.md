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
description: 'Zusammenfassung: Informationen zum Verwalten von Konferenzrichtlinien in Skype for Business Server.'
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099101"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Verwalten von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server verwalten.
  
In diesem Thema wird das Verwalten von Konferenzrichtlinien beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Mit Konferenzrichtlinien können Sie eine Vielzahl von Terminplanungs- und Teilnahmeoptionen definieren, von der Frage, ob eine Besprechung IP-Audio und Video enthalten kann, bis hin zur maximalen Anzahl von Personen, die teilnehmen können. Sie können Konferenzrichtlinien verwenden, um Sicherheits-, Bandbreiten- und rechtliche Aspekte von Besprechungen zu verwalten.
  
Die Konferenzrichtlinie kann auf drei Ebenen definiert werden: auf globaler, auf Standort- und auf Benutzerebene. Die Einstellungen gelten für einen bestimmten Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine Richtlinie zuweisen, haben diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gelten die Standorteinstellungen. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale Richtlinie die Standardeinstellungen bereit.
  
Eine globale Richtlinie ist standardmäßig vorhanden. Sie können daher keine neue globale Richtlinie erstellen. Außerdem können Sie die vorhandene globale Richtlinie nicht löschen. Es ist jedoch möglich, die vorhandene globale Richtlinie Ihren Standardeinstellungen entsprechend anzupassen.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Verwalten von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf** Konferenzen und dann auf **Konferenzrichtlinie**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Besprechungen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konferenzrichtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Weist eine Konferenzrichtlinie auf Benutzerbereich zu.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Entfernt die angegebene Konferenzrichtlinie.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Ändert eine vorhandene Konferenzrichtlinie.  <br/> |
