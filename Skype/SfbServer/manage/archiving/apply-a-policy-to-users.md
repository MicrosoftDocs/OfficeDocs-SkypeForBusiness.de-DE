---
title: Anwenden einer Richtlinie auf Benutzer in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Archivierungsrichtlinie für Benutzer in Skype für Business Server 2015 zuweisen.'
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a>Anwenden einer Richtlinie auf Benutzer in Skype for Business Server 2015

**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Archivierungsrichtlinie für Benutzer in Skype für Business Server 2015 zuweisen.
  
Wenn Sie eine erstellt haben oder weitere Benutzerrichtlinien für die Archivierung für Benutzer, die unter Skype für Business Server 2015 verwaltet, können Sie die archivierungsunterstützung für bestimmte Benutzer durch Anwenden geeigneten Richtlinien auf die Benutzer oder Benutzergruppen implementieren. Wenn Sie eine Richtlinie zur Unterstützung der Archivierung der internen Kommunikation erstellen, können Sie es beispielsweise auf mindestens einen Benutzer oder eine Benutzergruppe zur Unterstützung der Archivierung von Skype für Business Server 2015 Kommunikation der Benutzer anwenden.
  
> [!NOTE]
> Wenn Sie Microsoft Exchange-Integration für die Bereitstellung, Exchange In-Place Hold Policies Steuerelement aktiviert, ob Archivierung aktiviert ist, für die Benutzer, die sich auf Exchange befinden und haben ihren Postfächern zu Compliance-Archiv platzieren. Weitere Informationen hierzu finden Sie unter [Planen für die Archivierung in Skype für Business Server 2015](../../plan-your-deployment/archiving/archiving.md) und [Integration mit Exchange-Speicher für Skype für Business Server 2015 konfigurieren](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Anwenden einer Benutzerrichtlinie mithilfe der Systemsteuerung

So wenden Sie eine Benutzerrichtlinie mithilfe der Systemsteuerung an:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten. 
    
4. Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Benutzerrichtlinie, die Sie anwenden möchten.
    
    > [!NOTE]
    > Die ** \<automatische\> ** Einstellungen gelten die Standardeinstellungen für Server-Installation. Diese Einstellungen werden automatisch vom Server angewendet.
  
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Anwenden einer Benutzerrichtlinie mithilfe von Windows PowerShell

Sie können auch eine Benutzerrichtlinie anzuwenden, mit dem Windows PowerShell **Grant-CsArchivingPolicy** -Cmdlet.
  
Mithilfe des folgenden Befehls wird die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ dem Benutzer Jonas Baar zugeordnet.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Dieser Befehl weist die benutzerbasierte Archivierungsrichtlinie "redmondarchivingpolicy" für alle Benutzer, die haben Konten, die sich in der Registrierung Pool Atl-Cs-001.contoso.com. Ausführliche Informationen zu den Parameter "Filter", die in dieser Befehl verwendet finden Sie unter der [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) -Cmdlet-Dokumentation.
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

Mithilfe des folgenden Befehls wird die Zuordnung aller benutzerbezogenen Archivierungsrichtlinien aufgehoben, die zuvor Jonas Baar zugeordnet wurden. Nach dem Aufheben der Zuordnung der benutzerbezogenen Richtlinie wird Jonas Baar automatisch mithilfe der globalen Richtlinie oder, sofern vorhanden, mithilfe seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Weitere Informationen hierzu finden Sie unter [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) -Cmdlet-Dokumentation.
  

