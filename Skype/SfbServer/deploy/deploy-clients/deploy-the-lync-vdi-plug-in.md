---
title: Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In diesem Thema werden Bereitstellungsverfahren für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop erläutert.
---

# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Bereitstellen des Lync VDI-Plug-Ins mit Skype for Business Server
 
In diesem Thema werden Bereitstellungsverfahren für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop erläutert. Planungsüberlegungen sind im [Plan für Skype for Business in VDI-Umgebungen.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
  
Eine Virtual Desktop Infrastructure (VDI)-Umgebung wird in einigen Organisationen verwendet, in denen Sicherheits- und Complianceprobleme besonders sensibel sind. Ihre Benutzer befinden sich auf lokalen Windows Computern und verwenden Clients auf einem virtuellen Desktop. Die Verwendung von Skype for Business auf einer solchen Verbindung erfordert zusätzliche VDI-Plug-In-Software.
  
Für die VDI-Plug-In-Komponente stehen zwei Lösungen zur Verfügung– eine von Microsoft und eine von Citrix. Microsoft empfiehlt die Verwendung der neuen HDX RealTime Optimization Pack-Lösung in neuen Bereitstellungen, unterstützt aber weiterhin das ursprüngliche Lync VDI-Plug-In für den restlichen Lebenszyklus. 
  
Dieses Thema enthält Ausführliche Informationen zur Bereitstellung des Microsoft Lync VDI-Plug-Ins, das nur auf Windows 7 und Windows 8 oder Windows Server 2008 unterstützt wird und nur Lync 2013- oder Skype for Business-Clients unterstützt. Es gibt keine Pläne, dieses Plug-In zu aktualisieren, aber das [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) für Skype for Business wird bei Bedarf aktualisiert.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Vorbereiten der Umgebung für das Lync VDI-Plug-In
<a name="Prepare_vdi"> </a>

1. Stellen Sie in Skype for Business Server sicher, dass EnableMediaRedirection für alle Lync VDI-Plug-In-Benutzer auf TRUE festgelegt ist. Ausführliche Informationen finden Sie in den Hilfethemen für das Cmdlet ["New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) " und das Cmdlet ["Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) ".
    
2. Installieren Sie auf dem Rechenzentrumsserver den Skype for Business-Client auf allen virtuellen Desktops.
    
3. Installieren Sie auf den lokalen Computern das Lync VDI-Plug-In.
    
    Benutzer sollten nun ein Gerät wie ein Headset oder eine Webcam mit ihrem lokalen Computer verbinden.
    
## <a name="configure-remote-desktop-connection-settings"></a>Konfigurieren der Einstellungen für die Remotedesktopverbindung
<a name="Prepare_vdi"> </a>

Führen Sie die folgenden Schritte auf dem lokalen Computer aus, um die Remotedesktopverbindung für das Lync VDI-Plug-In vorzubereiten:
  
1. Wenn auf dem lokalen Computer Windows 8 ausgeführt wird, überspringen Sie diesen Schritt. Wenn auf dem lokalen Computer Windows 7 mit SP1 ausgeführt wird, installieren Sie die neueste Windows 8-Version des [Remotedesktopdienste-Clients](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients).
    
2. Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.
    
3. Klicken Sie auf **Optionen**.
    
4. Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und führen Sie die folgenden Aktionen aus:
    
   - Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.
    
   - Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.
    
   - Klicken Sie auf **OK**.
    
5. Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.
    
6. Klicken Sie auf die Registerkarte "**Allgemein**". Geben Sie in **Computer** den Namen des virtuellen Desktops ein, und klicken Sie dann auf **Verbinden**. 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Anmelden und Verwenden von Skype for Business auf dem virtuellen Desktop
<a name="SfB_signin"> </a>

Nachdem das Lync VDI-Plug-In aktiviert wurde, führt der Benutzer diese Schritte bei der Anmeldung bei Skype for Business auf dem virtuellen Desktop aus.
  
1. Der Benutzer gibt seine Anmeldeinformationen in den Skype for Business Client ein, der auf dem virtuellen Desktop ausgeführt wird.
    
2. Nachdem Skype for Business das Lync VDI-Plug-In erkannt hat, fordert Skype for Business den Benutzer auf, die Anmeldeinformationen erneut einzugeben. Es wird empfohlen, in diesem Dialogfeld das Kontrollkästchen **Kennwort speichern** zu aktivieren, damit der Benutzer seine Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben muss.
    
3. Skype for Business beginnt mit der Kopplung mit dem Lync VDI-Plug-In. In diesem Fall zeigt der Client zwei Symbole in der Skype for Business Statusleiste an. Das Symbol unten links zeigt an, dass keine Audiogeräte verfügbar sind, und das blinkende Symbol unten rechts zeigt an, dass die VDI-Kopplung ausgeführt wird: a. Nachdem die VDI-Kopplung erfolgreich war, ändern sich die Symbole, um das Audiogerät anzugeben, das für Anrufe verwendet wird, und den Erfolg der VDI-Kopplung: b. Der Benutzer kann seine Anwesenheit jetzt auf Skype for Business kompatiblen Geräten sehen, die mit dem lokalen Computer verbunden sind, und Anrufe wie gewohnt tätigen und beantworten.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Problembehandlung für das Lync VDI-Plug-In
<a name="tshoot_VDI"> </a>

Lesen Sie die folgenden Abschnitte, wenn nach der Installation des Lync VDI-Plug-Ins Probleme auftreten.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Probleme bei der Installation des Lync VDI-Plug-Ins

Wenn Probleme bei der Installation des Lync VDI-Plug-Ins auftreten, überprüfen Sie Folgendes:
  
- Stellen Sie sicher, dass im Ordner, den Sie in den Systemvariablen "TEMP" und "TMP" angegeben haben, ausreichend Speicherplatz vorhanden ist
    
- Stellen Sie sicher, dass der Schreibschutz deaktiviert ist. Anweisungen finden Sie in der Dokumentation ihres Geräteherstellers.
    
### <a name="troubleshooting-issues-with-pairing"></a>Behebung von Problemen bei der Paarung

Wenn die Kopplung des Lync VDI-Plug-Ins fehlschlägt, wird das Kopplungssymbol unten rechts wie dargestellt als rotes "X" angezeigt: 
  
Nachfolgend finden Sie die möglichen Gründe für Fehler und die Aktionen, die Sie zur Behebung des Problems ausführen können. 
  
- **Der Benutzer hat bei der Anmeldung falsche Anmeldeinformationen eingegeben.**
    
    Der Benutzer sollte sich von Skype for Business abmelden und sich erneut mit den richtigen Anmeldeinformationen anmelden. Das Paarungsdialogfeld wird erneut angezeigt und gibt an, ob die Paarung erfolgreich war.
    
- **Eine andere Instanz des Remotedesktop-Clients wird bereits ausgeführt**
    
    Wenn sie die Remotedesktopverbindung in Windows verwenden, sollten benutzer die folgenden Aktionen ausführen:
    
1. Starten Sie den Task-Manager: Drücken Sie **Alt+Strg+Entf**, und klicken Sie dann auf **Task-Manager starten**.
    
2. Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.
    
3. Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**. 
    
4. Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen. 
    
- **Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**
    
    Überprüfen Sie nach der Installation des Plug-Ins auf dem lokalen Computer, ob diese Dateien unter "C:\Programme\Microsoft Office\Office15" (oder dem entsprechenden Laufwerkbuchstaben) vorhanden sind:
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Der Skype for Business Client wird auf dem lokalen Computer ausgeführt.**
    
    Um das Lync VDI-Plug-In zu verwenden, darf ein Skype for Business Client nicht auf dem lokalen Computer ausgeführt werden, andernfalls schlägt die Kopplung fehl. Als bewährte Methode sollte der Benutzer keinen Skype for Business Client auf dem lokalen Computer installieren.
    
## <a name="see-also"></a>Siehe auch
<a name="tshoot_VDI"> </a>

[Planen der Skype for Business in VDI-Umgebungen](../../plan-your-deployment/clients-and-devices/vdi-environments.md)