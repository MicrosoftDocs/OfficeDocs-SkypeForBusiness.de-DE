---
title: Verwalten von Server konferenzkonfigurationseinstellungen in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Zusammenfassung: Erfahren Sie, wie Server konferenzkonfigurationseinstellungen in Skype für Business Server verwalten.'
ms.openlocfilehash: ede34c37e957340f0aa01ac511378d2f4bb3a80e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009894"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Verwalten von Server konferenzkonfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Server konferenzkonfigurationseinstellungen in Skype für Business Server verwalten.
  
In diesem Themenbereich wird die Verwaltung der Einstellungen der Konferenzkonfiguration beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype für Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Konferenzen in Skype für Business Server bereitstellen](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Konferenzkonfigurationseinstellungen bestimmen anderem als die maximal zulässige Größe für Besprechungsinhalte und Ausdrucke. maximal Bandbreite für die Anwendung Anwendungsfreigabe-Konferenzdienst Speichergrenzwerte und Zeitlimits; die URLs für die interne und externe heruntergeladen unterstützten Clients. Zeiger auf die internen und externen URLs, in dem Benutzer Konferenzen Ressourcen erhalten Sie Hilfe und können; und die verwendeten Ports für die Anwendungsfreigabe, Client-Audio, dateiübertragungen und Mediendatenverkehr. Mit diesen Einstellungen können Sie die aktuellen Server selbst verwalten. Diese Einstellungen können mithilfe von Skype für Business Server-Verwaltungsshell festgelegt werden.
  
Wenn Sie Skype für Business Server installieren, enthält das System eine einzelne Auflistung von Konferenzen Konfigurationseinstellungen (die globale Auflistung). Wenn Sie benutzerdefinierte Einstellungen für einen Standort oder Dienst erstellen müssen, können Sie mit dem Cmdlet **New-CsConferencingConfiguration** tun. Beachten Sie, dass die neue Einstellungen nur auf Standortebene Standort oder Dienst angewendet werden können. Sie können keine neue globale Auflistung von Konferenzen Konfigurationseinstellungen erstellen, aber Sie können die globale Auflistung mithilfe des Cmdlets **Set-CsConferencingConfiguration** ändern. Darüber hinaus kann keine Standort oder Dienst mehr als eine Auflistung von Einstellungen hosten. Wenn Sie versuchen zum Erstellen neuer Einstellungen für die Redmond-Website und die Redmond Website bereits enthält eine Auflistung von konferenzkonfigurationseinstellungen und dann den gewünschten Befehl schlägt fehl.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Verwalten der konferenzkonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie zum Verwalten von konferenzkonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell die folgenden Cmdlets:
  
**Konferenzkonfigurationseinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Konferenzkonfigurationseinstellungen zurück.  <br/> |
|[Mit New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Entfernt die angegebene Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Ändert eine vorhandene Auflistung von Konfigurationseinstellungen für Konferenzen.  <br/> |
   
Mit dem folgenden Befehl wird eine neue Auflistung an Konferenzkonfigurationseinstellungen für den Standort „Redmond“ (site:Redmond) erstellt. In diesem Beispiel wird ein zusätzlicher Parameter (Organization) verwendet, mit dem der Wert der Eigenschaft „Organization“ auf „Litwareinc“ festgelegt wird. 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Beachten Sie, dass Sie pro Standort nur eine solche Auflistung erstellen können, sodass bei diesem Befehl ein Fehler auftritt, wenn der Standort „Redmond“ bereits über eine Auflistung von Konfigurationseinstellungen für Konferenzen verfügt. 
  
Das nächste Beispiel definiert eine neue Auflistung von Konferenzkonfigurationseinstellungen, die zunächst im Speicher gespeichert und dann zu einem späteren Zeitpunkt auf den Standort „Redmond“ angewendet werden. 
  
Der erste Befehl verwendet das Cmdlet **New-CsConferencingConfiguration**, um eine neue Auflistung von in der Variablen „$x“ gespeicherten Einstellungen im Arbeitsspeicher zu erstellen. Mit dem Parameter „InMemory“ wird festgelegt, ob die Auflistung im Arbeitsspeicher erstellt werden soll, anstatt sie sofort auf den Standort „Redmond“ anzuwenden.
  
Nachdem die Auflistung erstellt wurde, wird mit dem zweiten Befehl der Wert für die Eigenschaft "Organization" auf "Litwareinc" festgelegt. 
  
Der dritte Befehl verwendet schließlich das Cmdlet **Set-CsConferencingConfiguration**, um die neuen Einstellungen auf den Standort „Redmond“ tatsächlich anzuwenden.
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Wenn Sie das Cmdlet **Set-CsConferencingConfiguration** nicht aufrufen, werden die neuen Richtlinien nie übernommen. Stattdessen gehen sie verloren, sobald Sie die Windows PowerShell-Sitzung beenden oder die Variable „$x“ löschen.
  

