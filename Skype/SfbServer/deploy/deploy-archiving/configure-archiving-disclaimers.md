---
title: Konfigurieren der Archivierung Haftungsausschlüsse für externe Benutzer in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Konfigurieren eines Archivierungshaftungsausschlusses für Skype für Business Server.'
ms.openlocfilehash: 7cc1c5c770a20c9ccd4d1473eeca4147042fde95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894155"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Konfigurieren der Archivierung Haftungsausschlüsse für externe Benutzer in Skype für Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie ein Archivierungshaftungsausschlusses für Skype für Business Server konfigurieren.
  
Wenn Ihre Organisation mit externen Partnern kommuniziert, müssen Sie die Partner darüber informieren, dass diese Kommunikationen archiviert werden. Wenn Sie einen Edge-Server bereitstellen und Föderation für Ihre Organisation zu aktivieren, werden Sie gefragt, ob Sie automatisch ein Archivierungshaftungsausschlusses an externe Partner senden möchten. 
  
Wenn Sie diese Konfiguration ändern müssen, können Sie die Skype für Business Server-Systemsteuerung oder Windows PowerShell **Set-CsAccessEdgeConfiguration** -Cmdlet verwenden. Cmdlets für kann entweder von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.
  
Um externe Benutzer für die Zusammenarbeit mit Benutzern in Ihrer Skype für Business Server-Bereitstellung zu aktivieren, müssen Sie auch mindestens eine externe Zugriffsrichtlinie zur Unterstützung der Zugriff durch externe Benutzer konfigurieren. Weitere Informationen hierzu finden Sie unter Verwalten von XMPP-Verbundpartner für Ihre Organisation. Ausführliche Informationen zur Steuerung des Zugriffs für bestimmte Partnerdomänen finden Sie unter „Control Access by Individual Federated Domains“.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe der Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.
    
4. Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.
    
5. Aktivieren oder deaktivieren Sie im Abschnitt **Zugriffs-Edgekonfiguration bearbeiten** unter **Partnerverbund und Verbindung mit öffentlichen Chatdiensten aktivieren** das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden**, um das automatische Versenden eines Archivierungshaftungsausschlusses zu aktivieren bzw. zu deaktivieren.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe von Windows PowerShell

Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „True“ ($True) fest:
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „False“ ($False) fest:
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


