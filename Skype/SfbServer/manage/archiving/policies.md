---
title: Verwalten von Archivierungsrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzerrichtlinien für die Archivierung von Skype for Business Server verwalten.'
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278426"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Verwalten von Archivierungsrichtlinien in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie Benutzerrichtlinien für die Archivierung von Skype for Business Server verwalten.
  
Sie haben zunächst Archivierungsrichtlinien eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. Archivierungsrichtlinien bestimmen, ob Sie archivieren: 
  
- Interne Kommunikation
    
- Externe Kommunikation
    
Archivierungsrichtlinien können auf globaler, Website-oder Benutzerebene eingestellt werden.
  
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden. Ausführliche Informationen finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) und [Konfigurieren der Integration in Exchange Storage für Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Verwalten von Archivierungsrichtlinien über die Systemsteuerung

Sie können Archivierungsrichtlinien wie folgt mit der Systemsteuerung verwalten:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Archivierungsrichtlinie**.
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Verwalten von Archivierungsrichtlinien mit Windows PowerShell

Sie können die Archivierungsrichtlinien auch mithilfe der in der folgenden Tabelle aufgeführten Windows PowerShell-Cmdlets konfigurieren. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server-Verwaltungsshell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Gibt Informationen zu Archivierungsrichtlinien für Chatsitzungen zurück.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Weist Benutzern oder Gruppen von Benutzern Chat-Archivierungsrichtlinien für Sofortnachrichten (im) zu. Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.  <br/> |
|New-CsArchivingPolicy  <br/> |Erstellt neue Archivierungsrichtlinien für Chatsitzungen. Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Entfernt die angegebene Sofortnachrichten-Archivierungsrichtlinie, die bestimmt, ob Skype for Business Server automatisch alle Chatsitzungen speichert, die zwischen internen Benutzern und/oder allen Chatsitzungen zwischen internen Benutzern und Verbundpartnern stattfinden.  <br/> |
|Set-CsArchivingPolicy  <br/> |Ändert eine vorhandene Instant Messaging-Archivierungsrichtlinie (im). Eine Archivierungsrichtlinie bietet Ihnen die Möglichkeit, alle Chatsitzungen und Konferenzen zu archivieren, die zwischen internen Benutzern stattfinden. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartnern stattfinden.  <br/> |
   

