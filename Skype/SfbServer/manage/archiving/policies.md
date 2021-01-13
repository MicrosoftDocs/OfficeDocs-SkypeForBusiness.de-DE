---
title: Verwalten von Archivierungsrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Zusammenfassung: Erfahren Sie, wie Sie Benutzerrichtlinien für die Archivierung für Skype for Business Server verwalten.'
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828546"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Verwalten von Archivierungsrichtlinien in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Benutzerrichtlinien für die Archivierung für Skype for Business Server verwalten.
  
Sie richten Archivierungsrichtlinien zunächst ein, wenn Sie die Archivierung bereitstellen, sie können jedoch Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. Archivierungsrichtlinien bestimmen, ob Dies archiviert werden soll: 
  
- Interne Kommunikation
    
- Externe Kommunikation
    
Archivierungsrichtlinien können auf globaler, Standort- oder Benutzerebene festgelegt werden.
  
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, steuern Die Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange gespeichert sind und deren Postfächer im In-Place werden. Weitere Informationen finden Sie unter [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Verwalten von Archivierungsrichtlinien mithilfe der Systemsteuerung

Sie können Archivierungsrichtlinien mithilfe der Systemsteuerung wie folgt verwalten:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **"Archivierungsrichtlinie"**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Verwalten von Archivierungsrichtlinien mithilfe Windows PowerShell

Sie können Archivierungsrichtlinien auch mithilfe der Windows PowerShell in der folgenden Tabelle aufgeführten Cmdlets konfigurieren. Einzelheiten zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Gibt Informationen zu den Archivierungsrichtlinien für Chatsitzungen in Ihrer Organisation zurück.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Weist Benutzern oder Benutzergruppen Archivierungsrichtlinien für Chatsitzungen zu. Diese Richtlinien bieten Ihnen die Möglichkeit, alle Nachrichtensitzungen zu archivieren, die zwischen internen Benutzern stattfinden, und/oder alle Im-Im-Sitzungen zu archivieren, die zwischen internen Benutzern und externen Partnern stattfinden.  <br/> |
|New-CsArchivingPolicy  <br/> |Erstellt neue Archivierungsrichtlinien für Chatsitzungen. Diese Richtlinien bieten Ihnen die Möglichkeit, alle Nachrichtensitzungen zu archivieren, die zwischen internen Benutzern stattfinden, und/oder alle Im-Im-Sitzungen zu archivieren, die zwischen internen Benutzern und externen Partnern stattfinden.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Entfernt die angegebene Archivierungsrichtlinie für Chatnachrichten, die bestimmt, ob Skype for Business Server automatisch alle Chatnachrichtensitzungen zwischen internen Benutzern und/oder alle Chatnachrichtensitzungen zwischen internen Benutzern und Verbundpartnern speichern wird.  <br/> |
|Set-CsArchivingPolicy  <br/> |Ändert eine vorhandene Archivierungsrichtlinie für Chatnachrichten. Mit einer Archivierungsrichtlinie können Sie alle #A0 und -Konferenzen archivieren, die zwischen internen Benutzern stattfinden. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartnern stattfinden.  <br/> |
   

