---
title: Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In diesem Thema werden Bereitstellungsverfahren für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop erläutert.
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805935"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server
 
In diesem Thema werden Bereitstellungsverfahren für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop erläutert. Planungsüberlegungen finden [Sie unter "Planen von Skype for Business in VDI-Umgebungen".](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
  
In einigen Organisationen, in denen Sicherheits- und Complianceprobleme besonders sensibel sind, wird eine Virtuelle Desktopinfrastrukturumgebung (Virtual Desktop Infrastructure, VDI) verwendet. Ihre Benutzer befinden sich auf lokalen Windows-Computern und verwenden Clients auf einem virtuellen Desktop. Die Verwendung von Skype for Business für eine verbindung wie diese erfordert zusätzliche VDI-Plug-In-Software.
  
Für die VDI-Plug-In-Komponente stehen zwei Lösungen zur Verfügung: eine von Microsoft und eine von Citrix angebotene. Microsoft empfiehlt die Verwendung der neuen HDX RealTime Optimization Pack-Lösung in neuen Bereitstellungen, unterstützt aber weiterhin das ursprüngliche Lync VDI-Plug-In für den Rest seines Lebenszyklus. 
  
Dieses Thema enthält Details zur Bereitstellung des Microsoft Lync VDI-Plug-Ins, das nur unter Windows 7 und Windows 8 oder Windows Server 2008 unterstützt wird und nur Lync 2013- oder Skype for Business-Clients unterstützt. Es gibt keine Pläne, dieses Plug-In zu aktualisieren, aber [das Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) für Skype for Business wird bei Bedarf aktualisiert.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Vorbereiten der Umgebung für das Lync VDI-Plug-In
<a name="Prepare_vdi"> </a>

1. Stellen Sie in Skype for Business Server sicher, dass "EnableMediaRedirection" für alle Benutzer des Lync VDI-Plug-Ins auf "TRUE" festgelegt ist. Weitere Informationen finden Sie in den Hilfethemen für das [Cmdlet "New-CsClientPolicy"](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) und das Cmdlet ["Set-CsClientPolicy".](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)
    
2. Installieren Sie auf dem Rechenzentrumsserver den Skype for Business-Client auf allen virtuellen Desktops.
    
3. Installieren Sie auf den lokalen Computern das Lync VDI-Plug-In.
    
    Benutzer sollten jetzt ein Gerät wie ein Headset oder eine Webcam mit ihrem lokalen Computer verbinden.
    
## <a name="configure-remote-desktop-connection-settings"></a>Konfigurieren von Einstellungen für die Remotedesktopverbindung
<a name="Prepare_vdi"> </a>

Führen Sie die folgenden Schritte auf dem lokalen Computer aus, um die Remotedesktopverbindung für das Lync VDI-Plug-In vorzubereiten:
  
1. Wenn auf dem lokalen Computer ein Windows 8, überspringen Sie diesen Schritt. Wenn auf dem lokalen Computer Windows 7 mit SP1 ausgeführt wird, installieren Sie Windows 8 version des [Remotedesktopdienste-Clients.](https://go.microsoft.com/fwlink/p/?LinkId=268032)
    
2. Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.
    
3. Klicken Sie auf **Optionen**.
    
4. Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und führen Sie die folgenden Aktionen aus:
    
   - Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.
    
   - Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.
    
   - Klicken Sie auf **OK**.
    
5. Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.
    
6. Klicken Sie auf **die Registerkarte "Allgemein".** Geben **Sie** im Computer den Namen des virtuellen Desktops ein, und klicken Sie dann auf **"Verbinden".** 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Anmelden und Verwenden von Skype for Business auf dem virtuellen Desktop
<a name="SfB_signin"> </a>

Nachdem das Lync VDI-Plug-In aktiviert wurde, folgt der Benutzer diesen Schritten bei der Anmeldung bei Skype for Business auf dem virtuellen Desktop.
  
1. Der Benutzer gibt seine Anmeldeinformationen in den Skype for Business-Client ein, der auf dem virtuellen Desktop ausgeführt wird.
    
2. Nachdem Skype for Business das Lync VDI-Plug-In erkannt hat, fordert Skype for Business den Benutzer auf, die Anmeldeinformationen erneut ein- und ein- oder aus dem Fenster zu machen. Es wird empfohlen, in diesem Dialogfeld das Kontrollkästchen **Kennwort speichern** zu aktivieren, damit der Benutzer seine Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben muss.
    
3. Skype for Business beginnt mit der Kopplung mit dem Lync VDI-Plug-In. Während dies geschieht, zeigt der Client zwei Symbole in der Skype for Business-Statusleiste an. Das Symbol unten links zeigt an, dass keine Audiogeräte verfügbar sind, und das blinkende Symbol in der unteren rechten Seite zeigt an, dass die Kopplung von VDI ausgeführt wird: a. Nach der erfolgreichen Kopplung von VDI ändern sich die Symbole, um das Audiogerät anzugeben, das für Anrufe verwendet wird, und den Erfolg der VDI-Kopplung: b. Der Benutzer kann jetzt seine Anwesenheit auf Skype for Business-kompatiblen Geräten sehen, die mit dem lokalen Computer verbunden sind, und Anrufe wie gewohnt ein- und beantworten.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Problembehandlung für das Lync VDI-Plug-In
<a name="tshoot_VDI"> </a>

Lesen Sie die folgenden Abschnitte, wenn nach der Installation des Lync VDI-Plug-Ins Probleme auftreten.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Probleme beim Installieren des Lync VDI-Plug-Ins

Wenn beim Installieren des Lync VDI-Plug-Ins Probleme auftreten, überprüfen Sie Folgendes:
  
- Stellen Sie sicher, dass im Ordner, den Sie in den Systemvariablen "TEMP" und "TMP" angegeben haben, ausreichend Speicherplatz vorhanden ist
    
- Stellen Sie sicher, dass der Schreibschutz deaktiviert ist. Anweisungen finden Sie in der Dokumentation ihres Geräteherstellers.
    
### <a name="troubleshooting-issues-with-pairing"></a>Behebung von Problemen bei der Paarung

Wenn die Lync VDI-Plug-In-Kopplung fehlschlägt, wird das Kopplungssymbol unten rechts als rotes "X" angezeigt, wie im Folgenden dargestellt: 
  
Im Folgenden finden Sie mögliche Ursachen für Fehler und die Aktionen, die Sie zur Problemlösung ergreifen können. 
  
- **Der Benutzer hat bei der Anmeldung falsche Anmeldeinformationen eingegeben.**
    
    Der Benutzer sollte sich von Skype for Business abmelden und sich erneut mit den richtigen Anmeldeinformationen anmelden. Das Paarungsdialogfeld wird erneut angezeigt und gibt an, ob die Paarung erfolgreich war.
    
- **Eine andere Instanz des Remotedesktop-Clients wird bereits ausgeführt**
    
    Wenn sie die Remotedesktopverbindung in Windows verwenden, sollten Benutzer wie folgt vor:
    
1. Starten Sie den Task-Manager: Drücken Sie **Alt+Strg+Entf**, und klicken Sie dann auf **Task-Manager starten**.
    
2. Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.
    
3. Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**. 
    
4. Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen. 
    
- **Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**
    
    Überprüfen Sie nach der Installation des #A0 auf dem lokalen Computer, ob diese Dateien unter "C:\Programme\Microsoft Office\Office15" (oder den entsprechenden Laufwerkbuchstaben) vorhanden sind:
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Der Skype for Business-Client wird auf dem lokalen Computer ausgeführt.**
    
    Um das Lync VDI-Plug-In zu verwenden, darf ein Skype for Business-Client nicht auf dem lokalen Computer ausgeführt werden, andernfalls wird die Kopplung fehlschlagen. Als bewährte Methode sollte der Benutzer keinen Skype for Business-Client auf dem lokalen Computer installieren.
    
## <a name="see-also"></a>Siehe auch
<a name="tshoot_VDI"> </a>

[Planen von Skype for Business in VDI-Umgebungen](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
