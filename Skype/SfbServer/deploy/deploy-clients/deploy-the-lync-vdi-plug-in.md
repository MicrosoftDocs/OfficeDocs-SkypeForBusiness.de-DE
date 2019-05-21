---
title: Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In diesem Thema werden Bereitstellungsverfahren für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remote Desktop erläutert.
ms.openlocfilehash: a3955ac3634dbf52b47b70482772e7302876bf1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288754"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server
 
In diesem Thema werden Bereitstellungsverfahren für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remote Desktop erläutert. Planungsüberlegungen sind [für Skype for Business in VDI-Umgebungen vorgesehen](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
Eine VDI-Umgebung (Virtual Desktop Infrastructure) wird in einigen Organisationen verwendet, in denen Sicherheits- und Complianceprobleme besonders sensibel sind. Die Benutzer arbeiten mit lokalen Windows-Computern und verwenden Clients auf einem virtuellen Desktop. Die Verwendung von Skype for Business für eine solche Verbindung erfordert eine zusätzliche VDI-Plug-in-Software.
  
Für die VDI-Plug-in-Komponente stehen zwei Lösungen zur Verfügung – eine von Microsoft und eine von Citrix angebotene. Microsoft empfiehlt die Verwendung der neuen HDX-Realtime Optimization Pack-Lösung in neuen Bereitstellungen, unterstützt aber weiterhin das ursprüngliche lync-VDI-Plug-in für den Rest des Lebenszyklus. 
  
Dieses Thema enthält Details zur Bereitstellung des Microsoft lync VDI-Plug-ins, das nur unter Windows 7 und Windows 8 oder Windows Server 2008 unterstützt wird, und unterstützt nur lync 2013-oder Skype for Business-Clients. Es gibt keine Pläne, dieses Plugin zu aktualisieren, aber das [Citrix HDX Realtime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) für Skype for Business wird bei Bedarf aktualisiert.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Vorbereiten Ihrer Umgebung für das Lync VDI-Plug-In
<a name="Prepare_vdi"> </a>

1. Stellen Sie in Skype for Business Server sicher, dass EnableMediaRedirection für alle Benutzer von lync VDI-Plug-Ins auf true festgelegt ist. Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) und dem Cmdlet " [Satz-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) ".
    
2. Installieren Sie auf dem Rechenzentrumsserver den Skype for Business-Client auf allen virtuellen Desktops.
    
3. Installieren Sie auf den lokalen Computern das lync VDI-Plug-in.
    
    Die Benutzer sollten jetzt ein Gerät wie etwa ein Headset oder eine Webcam mit ihrem lokalen Computer verbinden.
    
## <a name="configure-remote-desktop-connection-settings"></a>Konfigurieren von Einstellungen der Remotedesktopverbindung
<a name="Prepare_vdi"> </a>

Führen Sie die folgenden Schritte auf dem lokalen Computer aus, um die Remote Desktop Verbindung für das lync VDI-Plug-in vorzubereiten:
  
1. Wenn auf dem lokalen Computer Windows 8 ausgeführt wird, überspringen Sie diesen Schritt. Wenn auf dem lokalen Computer Windows 7 mit SP1 ausgeführt wird, installieren Sie die neueste Version von Windows 8 des [Remote Desktop Dienste-Clients](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
2. Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.
    
3. Klicken Sie auf **Optionen**.
    
4. Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und gehen Sie wie folgt vor:
    
   - Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.
    
   - Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.
    
   - Klicken Sie anschließend auf **OK**.
    
5. Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.
    
6. Klicken Sie auf die Registerkarte **Allgemein**. Geben Sie im Feld **Computer** den Namen des virtuellen Desktops ein, und klicken Sie dann auf **Verbinden**.  
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Anmelden und Verwenden von Skype for Business auf dem virtuellen Desktop
<a name="SfB_signin"> </a>

Nachdem das lync-VDI-Plug-in aktiviert wurde, führt der Benutzer die folgenden Schritte aus, wenn er sich bei Skype for Business auf dem virtuellen Desktop anmeldet.
  
1. Der Benutzer gibt seine Anmeldeinformationen in den Skype for Business-Client ein, der auf dem virtuellen Desktop ausgeführt wird.
    
2. Nachdem Skype for Business das lync VDI-Plug-in erkannt hat, fordert Skype for Business den Benutzer auf, die Anmeldeinformationen erneut einzugeben. In diesem Dialogfeld sollten die Benutzer das Kontrollkästchen **Kennwort speichern** aktivieren, damit sie die Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben müssen.
    
3. Skype for Business beginnt mit der Kopplung mit dem lync VDI-Plug-in. In diesem Fall zeigt der Client zwei Symbole in der Statusleiste von Skype for Business an. Das Symbol in der unteren linken Ecke zeigt an, dass keine Audiogeräte verfügbar sind, und das blinkende Symbol in der unteren rechten Ecke zeigt an, dass die VDI-Kopplung in Bearbeitung ist: a. Nachdem die VDI-Kopplung erfolgreich war, ändern sich die Symbole, um das Audiogerät anzugeben, das für Anrufe verwendet wird, und den Erfolg der VDI-Kopplung: b. Der Benutzer kann nun seine Anwesenheit auf Skype for Business-kompatiblen Geräten sehen, die mit dem lokalen Computer verbunden sind, und Anrufe wie gewohnt tätigen und annehmen.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Problembehandlung für das Lync VDI-Plug-In
<a name="tshoot_VDI"> </a>

Lesen Sie die folgenden Abschnitte, wenn nach der Installation des Lync VDI-Plug-Ins Probleme auftreten.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Probleme beim Installieren des Lync VDI-Plug-Ins 

Wenn Probleme mit der Installation des lync VDI-Plug-ins auftreten, überprüfen Sie Folgendes:
  
- Stellen Sie sicher, dass in dem Ordner, den Sie in den Systemvariablen „TEMP“ und „TMP“ angegeben haben, ausreichend Speicherplatz vorhanden ist.
    
- Stellen Sie sicher, dass der Schreibschutz deaktiviert ist. Anweisungen hierzu finden Sie in der Dokumentation Ihres Geräteherstellers.
    
### <a name="troubleshooting-issues-with-pairing"></a>Problembehandlung für die Kopplung

Wenn die Kopplung von lync VDI-Plug-ins fehlschlägt, wird das Kopplungs Symbol in der unteren rechten Ecke als rotes "X" angezeigt: 
  
Nachfolgend finden Sie mögliche Gründe für Fehler und Maßnahmen, mit denen Sie das Problem korrigieren können.  
  
- **Die Benutzer haben bei der Anmeldung falsche Anmeldeinformationen eingegeben.**
    
    Der Benutzer sollte sich bei Skype for Business abmelden und sich mit den korrekten Anmeldeinformationen erneut anmelden. Das Kopplungsdialogfeld wird erneut angezeigt und gibt an, ob die Kopplung erfolgreich war.
    
- **Eine andere Instanz des Remotedesktopclients wird bereits ausgeführt.**
    
    Wenn Sie in Windows die Remote Desktop Verbindung verwenden, sollten die Benutzer die folgenden Schritte ausführen:
    
1. Starten Sie den Task-Manager: Drücken Sie **ALT+STRG+ENTF**, und klicken Sie dann auf **Task-Manager starten**.
    
2. Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.
    
3. Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**.  
    
4. Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen.  
    
- **Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**
    
    Vergewissern Sie sich nach der Installation des Plug-Ins auf dem lokalen Computer, dass die folgenden Dateien in „C:\Programme\Microsoft Office\Office15“ (ändern Sie gegebenenfalls den Laufwerkbuchstaben) vorhanden sind:
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Der Skype for Business-Client wird auf dem lokalen Computer ausgeführt.**
    
    Wenn Sie das lync VDI-Plug-in verwenden möchten, muss ein Skype for Business-Client nicht auf dem lokalen Computer ausgeführt werden, da andernfalls die Kopplung fehlschlägt. Als bewährte Methode sollte der Benutzer keinen Skype for Business-Client auf dem lokalen Computer installieren.
    
## <a name="see-also"></a>Siehe auch
<a name="tshoot_VDI"> </a>

[Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
