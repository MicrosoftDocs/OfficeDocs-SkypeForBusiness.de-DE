---
title: Verwalten von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server verwalten.'
ms.openlocfilehash: d835c4760ef3e77bc36f21e64cb80aeb618526ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289055"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Verwalten von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server verwalten.
  
In diesem Themenbereich wird die Verwaltung der Konferenzrichtlinien beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Mit den Konferenzrichtlinien können Sie eine breite Auswahl an Planungs- und Teilnahmeoptionen definieren, von der Verwendung von IP-Audio und -Video in einer Besprechung bis hin zur Höchstzahl der möglichen Teilnehmer. Sie können die Konferenzrichtlinien verwenden, um die Sicherheit, die Bandbreite und die rechtlichen Aspekte von Besprechungen zu verwalten.
  
Die Konferenzrichtlinie kann auf drei Ebenen definiert werden: auf globaler, auf Standort- und auf Benutzerebene. Die Einstellungen gelten für einen bestimmten Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine Richtlinie zuweisen, erhalten diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gelten die Standorteinstellungen. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale Richtlinie die Standardeinstellungen bereit.
  
Eine globale Richtlinie ist standardmäßig vorhanden, sodass Sie keine neue globale Richtlinie erstellen können. Sie können auch die vorhandene globale Richtlinie nicht löschen, aber Sie können die vorhandene globale Richtlinie so ändern, dass die Standardeinstellungen angepasst werden.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Verwalten von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung

So verwalten Sie Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Verwalten von Besprechungen mithilfe der Skype for Business Server-Verwaltungsshell die folgenden Cmdlets:
  
**Konferenzrichtlinieneinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Weist einzelnen Benutzern eine Konferenzrichtlinie zu.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Entfernt die angegebene Konferenzrichtlinie.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Ändert eine vorhandene Konferenzrichtlinie.  <br/> |
   

