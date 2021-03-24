---
title: Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Zusammenfassung: Erfahren Sie, wie Sie Benutzern in Skype for Business Server eine Archivierungsrichtlinie zuweisen.'
ms.openlocfilehash: 1fce0dbd0cc7b0595dcf3cd91baeba9ed364e28a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095489"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Benutzern in Skype for Business Server eine Archivierungsrichtlinie zuweisen.
  
Wenn Sie eine oder mehrere Benutzerrichtlinien für die Archivierung für Benutzer erstellt haben, die in Skype for Business Server gespeichert sind, können Sie die Archivierungsunterstützung für bestimmte Benutzer implementieren, indem Sie die entsprechenden Richtlinien auf diese Benutzer oder Benutzergruppen anwenden. Wenn Sie beispielsweise eine Richtlinie zur Unterstützung der Archivierung der internen Kommunikation erstellen, können Sie sie auf mindestens einen Benutzer oder eine Benutzergruppe anwenden, um die Archivierung der Skype for Business Server-Kommunikation des Benutzers zu unterstützen.
  
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, steuern Exchange In-Place-Aufbewahrungsrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange gespeichert sind und deren Postfächer In-Place werden. Weitere Informationen finden Sie unter [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) und Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Anwenden einer Benutzerrichtlinie mithilfe der Systemsteuerung

So wenden Sie eine Benutzerrichtlinie mithilfe der Systemsteuerung an:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie dann nach dem Benutzerkonto, das Sie konfigurieren möchten. 
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen **Sie unter Lync Server-Benutzer** bearbeiten unter **Archivierungsrichtlinie** die Archivierungsbenutzerrichtlinie aus, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die **\<Automatic\>** Einstellungen übernehmen die Standardeinstellungen für die Serverinstallation. Diese Einstellungen werden automatisch vom Server angewendet.
  
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Anwenden einer Benutzerrichtlinie mithilfe von Windows PowerShell

Sie können eine Benutzerrichtlinie auch mithilfe des Windows PowerShell **Grant-CsArchivingPolicy** anwenden.
  
Mit dem folgenden Befehl wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" dem Benutzer "Ken Myer" zugewiesen.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Mit diesem Befehl wird die Benutzerarchivierungsrichtlinie "RedmondArchivingPolicy" allen Benutzern zugewiesen, deren Konten im Registrierungspool atl-cs-001.contoso.com. Ausführliche Informationen zum in diesem Befehl verwendeten Filter-Parameter finden Sie in der [Get-CsUser-Cmdletdokumentation.](/powershell/module/skype/get-csuser?view=skype-ps)
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Mit dem folgenden Befehl werden alle Benutzerarchivierungsrichtlinien entfernt, die Ken Myer zuvor zugewiesen waren. Nachdem die Benutzerrichtlinie entfernt wurde, wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, falls vorhanden, seiner lokalen Websiterichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor einer globalen Richtlinie.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Ausführliche Informationen finden Sie in der Dokumentation zum [Grant-CsArchivingPolicy-Cmdlet.](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)
