---
title: Aktivieren der anrufsteuerung
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Nachdem Sie das Anruf Admission Control (, CAC) Netzwerk konfigurieren, müssen Sie zum Erzwingen der Netzwerkbandbreite ist eingeschränkt CAC aktivieren."
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228407"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Aktivieren der Anrufsteuerung in Skype for Business Server

Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nachdem Sie das CAC Netzwerk konfiguriert haben, müssen Sie CAC zum Erzwingen der Netzwerkbandbreite ist eingeschränkt aktivieren. Sie können die Skype Business Server-Systemsteuerung dazu verwenden.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Zum Aktivieren der Anrufsteuerung aus der Skype Business Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global** .
   
    > [!NOTE]  
    > Nur ein Netzwerk kann für alle Skype für Business Server-Bereitstellung konfiguriert werden, sodass es nie mehr als eine Netzwerkkonfiguration in der Liste werden. Die globale Konfiguration kann nicht umbenannt werden.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Kontrollkästchen Sie auf der Seite **Globale Einstellungen bearbeiten** das **anrufsteuerung aktivieren** , und klicken Sie dann auf **Commit**.

Wenn Sie auf **Commit ausführen**klicken, führen Sie einen Test der Konfiguration. Das **Globale Einstellungen bearbeiten** -Dialogfeld wird geschlossen, Sie auf der Seite **Global** zurückgeben. Sie erhalten eine Warnung, wenn alle Fehler oder Inkonsistenzen in der Netzwerkkonfiguration, die verhindern, dass wird ordnungsgemäß ermittelt werden (z. B., wenn jeder Region nicht mit allen anderen Regionen über eine regionenübergreifende Route verbunden ist).

Wenn Sie Änderungen an der Netzwerkkonfiguration vornehmen, können Sie die Überprüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit**. Sie müssen nicht zuerst deaktivieren, CAC: lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**. Sie hierzu können Sie jederzeit ohne konfigurationsänderungen vorzunehmen.

## <a name="see-also"></a>Siehe auch

[Planen der Anrufsteuerung](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Bereitstellen der Anrufsteuerung](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
