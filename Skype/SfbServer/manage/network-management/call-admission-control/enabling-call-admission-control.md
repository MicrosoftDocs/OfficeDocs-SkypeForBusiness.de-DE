---
title: Aktivieren der Anrufsteuerung
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
description: " Nachdem Sie das CAC-Netzwerk (Call Admission Control) konfiguriert haben, müssen Sie CAC aktivieren, um die Bandbreiteneinschränkungen zu erzwingen."
ms.openlocfilehash: 4f9f3f09f943b417ec589f26dc5c6505d30831f9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817534"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Aktivieren der Anrufsteuerung in Skype for Business Server

Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nachdem Sie das CAC-Netzwerk konfiguriert haben, müssen Sie CAC aktivieren, um die Bandbreiteneinschränkungen zu erzwingen. Dazu können Sie die Skype for Business Server-Systemsteuerung verwenden.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>So aktivieren Sie CAC über das Skype Control Panel für Unternehmen-Server

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration.
   
    > [!NOTE]  
    > Für die Bereitstellung von Skype for Business Server kann nur ein Netzwerk konfiguriert werden, sodass in der Liste nie mehr als eine Netzwerkkonfiguration vorhanden ist. Sie können die globale Konfiguration nicht umbenennen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Aktivieren Sie auf der Seite **globale Einstellungen bearbeiten** das Kontrollkästchen **Anruf Zulassungs Steuerung aktivieren** , und klicken Sie dann auf **Commit**.

Wenn Sie auf **Commit**klicken, führen Sie einen Test der Konfiguration aus. Das Dialogfeld **globale Einstellungen bearbeiten** wird geschlossen, und Sie kehren zur **globalen** Seite zurück. Sie erhalten eine Warnung, wenn in Ihrer Netzwerkkonfiguration Fehler oder Inkonsistenzen festgestellt werden, die verhindern, dass Sie ordnungsgemäß funktionieren (Wenn beispielsweise alle Regionen über eine interregions Route nicht mit allen anderen Regionen verbunden sind).

Wenn Sie Änderungen an Ihrer Netzwerkkonfiguration vornehmen, können Sie die Überprüfungs Prüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit**klicken. Sie müssen CAC nicht zuerst deaktivieren: lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**. Sie können dies jederzeit tun, ohne Konfigurationsänderungen vorzunehmen.

## <a name="see-also"></a>Siehe auch

[Planen der Anrufsteuerung](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Bereitstellen der Anrufsteuerung](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Satz-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
