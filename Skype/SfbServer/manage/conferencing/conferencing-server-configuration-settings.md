---
title: Verwalten von Konfigurationseinstellungen für Konferenzserver in Skype for Business Server
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Zusammenfassung: Informationen zum Verwalten von Konfigurationseinstellungen für Konferenzserver in Skype for Business Server.'
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828285"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Verwalten von Konfigurationseinstellungen für Konferenzserver in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Konfigurationseinstellungen für Konferenzserver in Skype for Business Server verwalten.
  
In diesem Thema wird die Verwaltung von Konferenzkonfigurationseinstellungen beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter "Planen von Konferenzen [in Skype for Business Server"](../../plan-your-deployment/conferencing/conferencing.md) und "Bereitstellen von Konferenzen in Skype for Business [Server".](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
Konferenzkonfigurationseinstellungen bestimmen z. B. die maximal zulässige Größe für Besprechungsinhalte und Handzettel. maximale Bandbreite für den Konferenzdienst für anwendungsfreigaben; Speichergrenzwerte und Ablaufzeiträume; die URLs für die internen und externen Downloads des unterstützten Clients; zeigers to internal and external URLs where users can obtain conferencing help and resources; und die Ports, die für anwendungsfreigabe, Clientaudio, Dateiübertragungen und Mediendatenverkehr verwendet werden. Mit diesen Einstellungen können Sie die eigentlichen Server selbst verwalten. Diese Einstellungen können mithilfe der Skype for Business Server-Verwaltungsshell festgelegt werden.
  
Wenn Sie Skype for Business Server installieren, bietet ihnen das System eine einzelne Auflistung von Konferenzkonfigurationseinstellungen (die globale Auflistung). Wenn Sie benutzerdefinierte Einstellungen für einen Standort oder Dienst erstellen müssen, können Sie dies mit dem Cmdlet **New-CsConferencingConfiguration** tun. Beachten Sie, dass neue Einstellungen nur auf Standort- oder Dienstbereich angewendet werden können. Sie können keine neue globale Auflistung von Konferenzkonfigurationseinstellungen erstellen, aber Sie können die globale Auflistung mithilfe des Cmdlets **"Set-CsConferencingConfiguration"** ändern. Darüber hinaus kann kein Standort oder Dienst mehr als eine Auflistung von Einstellungen hosten. Wenn Sie versuchen, neue Einstellungen für den Standort "Redmond" zu erstellen, und der Standort "Redmond" bereits eine Auflistung von Konferenzkonfigurationseinstellungen hostet, kann der Befehl nicht ausgeführt werden.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenzkonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um die Konferenzkonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konferenzkonfigurationseinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den Konferenzkonfigurationseinstellungen für Ihre Organisation zurück.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Entfernt die angegebene Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Ändert eine vorhandene Auflistung von Konfigurationseinstellungen für Konferenzen.  <br/> |
   
Mit dem folgenden Befehl wird eine neue Auflistung von Konferenzkonfigurationseinstellungen für den Standort "Redmond" (site:Redmond) erstellt. In diesem Beispiel ist ein zusätzlicher Parameter enthalten (Organization), der verwendet wird, um den Wert der Eigenschaft "Organization" auf "Litwareinc" zu setzen: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Beachten Sie, dass pro Standort nur eine solche Auflistung vorhanden sein kann, daher würde dieser Befehl fehlschlagen, wenn der Standort "Redmond" bereits über eine Auflistung von Konferenzkonfigurationseinstellungen verfügt. 
  
Im nächsten Beispiel wird eine neue Auflistung von Konferenzkonfigurationseinstellungen definiert, die zunächst im Arbeitsspeicher gespeichert und zu einem späteren Zeitpunkt auf den Standort "Redmond" angewendet werden. 
  
Der erste Befehl verwendet das **Cmdlet "New-CsConferencingConfiguration",** um eine neue, im Arbeitsspeicher gespeicherte Auflistung von Einstellungen zu erstellen, die in der Variablensammlung $x. Der Parameter "InMemory" gibt an, dass die Auflistung im Arbeitsspeicher erstellt und nicht sofort auf den Standort "Redmond" angewendet werden soll.
  
Nachdem die Auflistung erstellt wurde, wird mit dem zweiten Befehl der Wert für die Eigenschaft "Organization" auf "Litwareinc" festgelegt. 
  
Schließlich verwendet der dritte Befehl das **Cmdlet "Set-CsConferencingConfiguration",** um die neuen Einstellungen tatsächlich auf den Standort "Redmond" anzuwenden:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Wenn Sie das Cmdlet **"Set-CsConferencingConfiguration"** nicht aufrufen, werden die neuen Einstellungen nie wirksam. Stattdessen werden sie ausgeblendet, sobald Sie ihre Windows PowerShell beenden oder die Variable $x.
  

