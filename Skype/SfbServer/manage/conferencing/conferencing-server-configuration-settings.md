---
title: Verwalten von Konferenzserver-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Konferenzserver in Skype for Business Server verwalten.'
ms.openlocfilehash: c43734a2d79bf07023486eb163fff7bbef56e73f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818636"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Verwalten von Konferenzserver-Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Konferenzserver in Skype for Business Server verwalten.
  
In diesem Themenbereich wird die Verwaltung der Einstellungen der Konferenzkonfiguration beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Die Konfigurationseinstellungen für Konferenzen legen fest, wie groß die maximal zulässige Größe für Besprechungsinhalte und Handzettel sind. maximale Bandbreite für den Anwendungsfreigabe-Konferenzdienst; Speichergrenzwerte und Ablaufzeiten; die URLs für die internen und externen Downloads des unterstützten Clients; Zeiger auf interne und externe URLs, in denen Benutzer Konferenz Hilfen und-Ressourcen erhalten können; und die Ports, die für Anwendungsfreigabe, Client-Audio, Dateiübertragungen und Mediendatenverkehr verwendet werden. Diese Einstellungen ermöglichen es Ihnen, die eigentlichen Server selbst zu verwalten. Diese Einstellungen können mithilfe der Skype for Business Server-Verwaltungsshell eingestellt werden.
  
Wenn Sie Skype for Business Server installieren, stellt Ihnen das System eine einzige Sammlung von Konferenz Konfigurationseinstellungen (der globalen Sammlung) zur Verfügung. Wenn Sie benutzerdefinierte Einstellungen für eine Website oder einen Dienst erstellen müssen, können Sie dies mit dem Cmdlet **New-CsConferencingConfiguration** . Beachten Sie, dass neue Einstellungen nur auf dem Website-oder Dienstbereich angewendet werden können. Es ist nicht möglich, eine neue globale Sammlung von Konferenz Konfigurationseinstellungen zu erstellen, Sie können jedoch die globale Sammlung mithilfe des Cmdlets " **Satz-CsConferencingConfiguration** " ändern. Darüber hinaus kann keine Website oder ein Dienst mehr als eine Sammlung von Einstellungen hosten. Wenn Sie versuchen, neue Einstellungen für die Website "Redmond" zu erstellen, und die Redmond-Website bereits eine Sammlung von Konferenz Konfigurationseinstellungen hostet, schlägt Ihr Befehl fehl.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenz Konfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Konferenz Konfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konferenzkonfigurationseinstellungen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Konferenzkonfigurationseinstellungen zurück.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Entfernt die angegebene Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Ändert eine vorhandene Auflistung von Konfigurationseinstellungen für Konferenzen.  <br/> |
   
Mit dem folgenden Befehl wird eine neue Auflistung an Konferenzkonfigurationseinstellungen für den Standort „Redmond“ (site:Redmond) erstellt. In diesem Beispiel wird ein zusätzlicher Parameter (Organization) verwendet, mit dem der Wert der Eigenschaft „Organization“ auf „Litwareinc“ festgelegt wird. 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Beachten Sie, dass Sie pro Standort nur eine solche Auflistung erstellen können, sodass bei diesem Befehl ein Fehler auftritt, wenn der Standort „Redmond“ bereits über eine Auflistung von Konfigurationseinstellungen für Konferenzen verfügt. 
  
Das nächste Beispiel definiert eine neue Auflistung von Konferenzkonfigurationseinstellungen, die zunächst im Speicher gespeichert und dann zu einem späteren Zeitpunkt auf den Standort „Redmond“ angewendet werden. 
  
Der erste Befehl verwendet das Cmdlet **New-CsConferencingConfiguration**, um eine neue Auflistung von in der Variablen „$x“ gespeicherten Einstellungen im Arbeitsspeicher zu erstellen. Mit dem Parameter „InMemory“ wird festgelegt, ob die Auflistung im Arbeitsspeicher erstellt werden soll, anstatt sie sofort auf den Standort „Redmond“ anzuwenden.
  
Nachdem die Auflistung erstellt wurde, wird mit dem zweiten Befehl der Wert für die Eigenschaft "Organization" auf "Litwareinc" festgelegt. 
  
Der dritte Befehl verwendet schließlich das Cmdlet **Set-CsConferencingConfiguration**, um die neuen Einstellungen auf den Standort „Redmond“ tatsächlich anzuwenden.
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Wenn Sie das Cmdlet **Set-CsConferencingConfiguration** nicht aufrufen, werden die neuen Richtlinien nie übernommen. Stattdessen gehen sie verloren, sobald Sie die Windows PowerShell-Sitzung beenden oder die Variable „$x“ löschen.
  

