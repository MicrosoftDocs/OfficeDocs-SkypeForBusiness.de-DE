---
title: Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzern in Skype for Business Server eine Archivierungsrichtlinie zuweisen.'
ms.openlocfilehash: 5dbd1624813b187e8c0981aa1a84b6096b79e86a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992782"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie Benutzern in Skype for Business Server eine Archivierungsrichtlinie zuweisen.
  
Wenn Sie eine oder mehrere Benutzerrichtlinien für die Archivierung für Benutzer erstellt haben, die in Skype for Business Server verwaltet werden, können Sie Archivierungsunterstützung für bestimmte Benutzer implementieren, indem Sie die entsprechenden Richtlinien auf diese Benutzer oder Benutzergruppen anwenden. Wenn Sie beispielsweise eine Richtlinie erstellen, um die Archivierung interner Kommunikation zu unterstützen, können Sie diese auf mindestens einen Benutzer oder eine Benutzergruppe anwenden, um die Archivierung der Skype for Business Server-Kommunikation des Benutzers zu unterstützen.
  
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden. Ausführliche Informationen finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) und [Konfigurieren der Integration in Exchange Storage für Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Anwenden einer Benutzerrichtlinie mithilfe der Systemsteuerung

So wenden Sie eine Benutzerrichtlinie mithilfe der Systemsteuerung an:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten. 
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die ** \<automatischen\> ** Einstellungen gelten für die standardmäßigen Server Installationseinstellungen. Diese Einstellungen werden vom Server automatisch übernommen.
  
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Anwenden einer Benutzerrichtlinie mithilfe von Windows PowerShell

Sie können eine Benutzerrichtlinie auch mithilfe des Windows PowerShell-Cmdlets **Grant-CsArchivingPolicy** anwenden.
  
Mithilfe des folgenden Befehls wird die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ dem Benutzer Jonas Baar zugeordnet.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Der folgende Befehl weist die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ allen Benutzern zu, deren Konten sich auf dem Registrierungsstellenpool „atl-cs-001.contoso.com“ befinden. Details zu dem in diesem Befehl verwendeten Filter Parameter finden Sie in der Dokumentation zum Cmdlet " [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) ".
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Mithilfe des folgenden Befehls wird die Zuordnung aller benutzerbezogenen Archivierungsrichtlinien aufgehoben, die zuvor Jonas Baar zugeordnet wurden. Nach dem Aufheben der Zuordnung der benutzerbezogenen Richtlinie wird Jonas Baar automatisch mithilfe der globalen Richtlinie oder, sofern vorhanden, mithilfe seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Ausführliche Informationen finden Sie in der Dokumentation zu [Grant-CsArchivingPolicy-](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) Cmdlets.
  

