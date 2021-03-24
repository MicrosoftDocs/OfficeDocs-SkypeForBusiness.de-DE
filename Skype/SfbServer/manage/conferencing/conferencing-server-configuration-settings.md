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
ms.openlocfilehash: db44ad62acb99bab32b732ea0686784b14c3b2b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099091"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Verwalten von Konfigurationseinstellungen für Konferenzserver in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Die Konfigurationseinstellungen für Konferenzserver in Skype for Business Server verwalten.
  
In diesem Thema wird das Verwalten von Konfigurationseinstellungen für Konferenzen beschrieben. Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Konferenzkonfigurationseinstellungen bestimmen z. B. die maximal zulässige Größe für Besprechungsinhalte und Handzettel. maximale Bandbreite für den Anwendungsfreigabekonferenzdienst; Speichergrenzwerte und Ablaufzeiten; die URLs für die internen und externen Downloads des unterstützten Clients; Zeiger auf interne und externe URLs, in denen Benutzer Hilfe und Ressourcen für Konferenzen erhalten können; und die Ports, die für anwendungsfreigabe, Clientaudio, Dateiübertragungen und Mediendatenverkehr verwendet werden. Mit diesen Einstellungen können Sie die tatsächlichen Server selbst verwalten. Diese Einstellungen können mithilfe der Skype for Business Server-Verwaltungsshell festgelegt werden.
  
Wenn Sie Skype for Business Server installieren, bietet Ihnen das System eine einzige Auflistung von Konferenzkonfigurationseinstellungen (die globale Auflistung). Wenn Sie benutzerdefinierte Einstellungen für einen Standort oder Dienst erstellen müssen, können Sie dies mit dem Cmdlet **New-CsConferencingConfiguration** tun. Beachten Sie, dass neue Einstellungen nur auf Standort- oder Dienstbereich angewendet werden können. Sie können keine neue globale Auflistung von Konferenzkonfigurationseinstellungen erstellen, aber Sie können die globale Auflistung mithilfe des **Cmdlets Set-CsConferencingConfiguration** ändern. Darüber hinaus kann keine Website oder kein Dienst mehr als eine Sammlung von Einstellungen hosten. Wenn Sie versuchen, neue Einstellungen für den Standort Redmond zu erstellen, und der Standort "Redmond" bereits eine Auflistung von Konferenzkonfigurationseinstellungen hostet, wird der Befehl fehlschlagen.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Verwalten von Konferenzkonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie die folgenden Cmdlets, um Konfigurationseinstellungen für Konferenzen mithilfe der Skype for Business Server-Verwaltungsshell zu verwalten:
  
**Konfigurationseinstellungen für Konferenzen**

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Gibt Informationen zu den Konfigurationseinstellungen für Konferenzen für Ihre Organisation zurück.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Erstellt eine neue Auflistung von Konfigurationseinstellungen für Konferenzen.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Entfernt die angegebene Auflistung von Konferenzkonfigurationseinstellungen.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Ändert eine vorhandene Auflistung von Konfigurationseinstellungen für Konferenzen.  <br/> |
   
Mit dem folgenden Befehl wird eine neue Auflistung von Konferenzkonfigurationseinstellungen für den Standort "Redmond" (site:Redmond) erstellt. In diesem Beispiel ist ein zusätzlicher Parameter (Organization) enthalten, der zum Festlegen des Werts der Organization-Eigenschaft auf Litwareinc verwendet wird: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Beachten Sie, dass pro Standort nur eine solche Auflistung vorhanden sein kann, sodass dieser Befehl fehlschlagen würde, wenn der Standort "Redmond" bereits über eine Auflistung von Konfigurationseinstellungen für Konferenzen verfügt. 
  
Im nächsten Beispiel wird eine neue Auflistung von Konfigurationseinstellungen für Konferenzen definiert, die zunächst im Arbeitsspeicher gespeichert und dann zu einem späteren Zeitpunkt auf den Standort "Redmond" angewendet werden. 
  
Der erste Befehl verwendet das **Cmdlet New-CsConferencingConfiguration,** um eine neue, im Arbeitsspeicher gespeicherte Auflistung von Einstellungen zu erstellen, die in der Variablen $x. Der Parameter InMemory gibt an, dass die Auflistung im Arbeitsspeicher erstellt werden soll, anstatt sofort auf den Standort "Redmond" angewendet zu werden.
  
Nachdem die Auflistung erstellt wurde, wird mit dem zweiten Befehl der Wert für die Eigenschaft "Organization" auf "Litwareinc" festgelegt. 
  
Schließlich verwendet der dritte Befehl das **Cmdlet Set-CsConferencingConfiguration,** um die neuen Einstellungen tatsächlich auf den Standort "Redmond" anzuwenden:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Wenn Sie das **Cmdlet Set-CsConferencingConfiguration** nicht aufrufen, werden die neuen Einstellungen nie wirksam. Stattdessen werden sie ausgeblendet, sobald Sie ihre Windows PowerShell beenden oder die Variable $x.
