---
title: Aktivieren der Anrufsteuerung
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
description: " Nachdem Sie das Anrufsteuerungsnetzwerk konfiguriert haben, müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816505"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Aktivieren der Anrufsteuerung in Skype for Business Server

Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nach der Konfiguration des Anrufsteuerungsnetzwerks müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen. Dazu können Sie die Skype for Business Server-Systemsteuerung verwenden.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>So aktivieren Sie die Anrufsteuerung über die Skype for Business Server-Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Global".**

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**.
   
    > [!NOTE]  
    > Für jede Skype for Business Server-Bereitstellung kann nur ein Netzwerk konfiguriert werden, sodass in der Liste nie mehr als eine Netzwerkkonfiguration enthalten sein wird. Die globale Konfiguration kann nicht umbenannt werden.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**, und klicken Sie auf **Commit**.

Beim Klicken auf **Commit** wird die Konfiguration getestet. Das Dialogfeld **Globale Einstellungen bearbeiten** wird geschlossen, und die Seite **Global** wird erneut angezeigt. Wenn in Ihrer Netzwerkkonfiguration Fehler oder Inkonsistenzen ermittelt werden, die eine ordnungsgemäße Funktionsweise verhindern, wird eine Warnung angezeigt (wenn die einzelnen Regionen beispielsweise nicht über eine regionenübergreifende Route miteinander verbunden sind).

Nach dem Ändern Ihrer Netzwerkkonfiguration können Sie die Überprüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit** klicken. Es ist nicht erforderlich, die Anrufsteuerung zunächst zu deaktivieren: Lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**. Dieser Vorgang kann zu einem beliebigen Zeitpunkt ausgeführt werden, ohne Konfigurationsänderungen vorzunehmen.

## <a name="see-also"></a>Siehe auch

[Planen der Anrufsteuerung](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Bereitstellen der Anrufsteuerung](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
