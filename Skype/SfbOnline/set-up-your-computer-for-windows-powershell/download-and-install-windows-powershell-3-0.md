---
title: Herunterladen und Installieren von Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: 8470a095e516179d1d328f47c1fe10d5a9e00aa6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23862885"
---
# <a name="download-and-install-windows-powershell-30"></a>Herunterladen und Installieren von Windows PowerShell 3.0

Wenn Sie Windows 8.1, Windows 8, Windows Server 2012 R2 oder Windows Server 2012 verwenden, sollten Sie bereits über Windows PowerShell 3.0 verfügen. Das liegt daran, dass die Anwendung unter diesen Betriebssystemen vorinstalliert ist. 
  
Wenn Sie Windows 7 oder Windows Server 2008 R2 ausführen, führen Sie möglicherweise auch Windows PowerShell 3.0 aus. Es kann jedoch auch sein, dass Sie stattdessen Version 2.0 ausführen - die Version, die ursprünglich mit diesen Betriebssystemen ausgeliefert wurde. Um zu ermitteln, welche Version von Microsoft PowerShell Sie verwenden, gehen Sie auf Ihrem Computer unter Windows 7 oder Windows Server 2008 R2 wie folgt vor:
  
1. Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör**, auf **Windows PowerShell** und dann auf **Windows PowerShell**.
    
2. Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
   ```
   Get-Host | Select-Object Version
   ```

3. Im Konsolenfenster sollten dann etwa die folgenden Informationen angezeigt werden:
    
    <pre>
    Version <BR>
    ------- <BR>
    3.0
    </pre>

    Wenn die Versionsnummer 3.0 zurückgegeben wird, führen Sie Windows PowerShell 3.0 aus. Wenn anstelle von 3.0 eine andere Versionsnummer zurückgegeben wird, müssen Sie Windows PowerShell 3.0 installieren. Sie können Windows Management Framework 3.0 (einschließlich Windows PowerShell 3.0) aus dem [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595) herunterladen.
  
Wenn Sie sich vergewissert haben, dass Windows PowerShell 3.0 installiert ist, müssen Sie sicherstellen, dass PowerShell für die Ausführung von Remoteskripts konfiguriert ist. Starten Sie dazu PowerShell als Administrator. Unter Windows 7, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 gehen Sie wie folgt vor:
  
1. Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**. Damit bestätigen Sie, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.
    
Unter Windows 8 gehen Sie stattdessen so vor:
  
1. Greifen Sie auf die Charmsleiste zu, klicken Sie auf **Suchen**, und klicken Sie dann mit der rechten Maustaste auf **Windows PowerShell**. Auf Windows 8-Computern (mit oder ohne Touchscreen) können Sie schnell auf die Charmsleiste zugreifen, indem Sie die WINDOWS-TASTE gedrückt halten und C drücken.
    
2. Klicken Sie auf der Symbolleiste unten auf dem Bildschirm auf **Als Administrator ausführen**.
    
3. Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**. Damit bestätigen Sie, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.
    
Wenn PowerShell ausgeführt wird, müssen Sie die Ausführungsrichtlinie ändern, um die Ausführung von Remoteskripts zuzulassen. Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Wenn Sie mit dem vorstehenden Befehl ausführen, erhalten Sie die folgende Fehlermeldung angezeigt: > *Set-ExecutionPolicy: Zugriff auf den Registrierungsschlüssel "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' wird verweigert.* Diese Fehlermeldung tritt typischerweise auf, wenn Sie PowerShell nicht unter Administratoranmeldeinformationen ausgeführt werden. Schließen der PowerShell-Sitzung, und starten Sie eine neue Sitzung als Administrator.
 
Um zu überprüfen, ob die Ausführungsrichtlinie richtig konfiguriert ist, geben Sie Folgendes an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
  
```
Get-ExecutionPolicy
```

Wenn der folgende Wert zurückgegeben wird, ist alles richtig konfiguriert:
  
`RemoteSigned`

Wenn Sie zurzeit nicht Windows PowerShell 3.0 ausführen, müssen Sie auch Windows Management Framework 3.0 aus dem Microsoft Download Center herunterladen. Dabei handelt es sich um ein Installationspaket, in dem Windows PowerShell 3.0 und Windows-Remoteverwaltung (WinRM) 3.0 enthalten sind. Das Installationspaket ist möglicherweise erforderlich, wenn Sie Windows 7 ausführen und noch nicht auf Windows PowerShell 3.0 aktualisiert haben. Wenn Sie Windows Server 2012, Windows Server 2012 R2, Windows 8 oder Windows 8.1 ausführen, sollte die Installation von Windows PowerShell 3.0 nicht notwendig sein. Unter diesen Betriebssystemen ist Windows PowerShell 3.0 vorinstalliert.
  
Vor der Installation von Windows Management Framework 3.0:
  
- Vergewissern Sie sich, dass Sie die richtige Version des Installationspakets heruntergeladen haben. Wenn Sie die 64-Bit-Version von Windows 7 ausführen, laden Sie die Datei „Windows6.1-KB2506143-x64.msu" herunter. Wenn Sie die 32-Bit-Version von Windows 7 ausführen, laden Sie die Datei „Windows6.1-KB2506143-x86.msu" herunter.
    
- Wenn Sie auf Ihrem Computer Windows 7 ausführen, vergewissern Sie sich, dass Windows 7 Service Pack 1 installiert ist.
    
Wenn Sie nicht sicher sind, welche Version von Windows ausgeführt wird oder ob Windows 7 Service Pack 1 installiert ist, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**. Diese Informationen werden im Dialogfeld „System" angezeigt.
  
Um Windows Management Framework 3.0 zu installieren, gehen Sie wie folgt vor:
  
1. Doppelklicken Sie auf die MSU-Installationsdatei ( **Windows6.1-KB2506143-x64.msu** oder **Windows6.1-KB2506143-x86.msu**).
    
2. Klicken Sie im Assistenten zum Herunterladen und Installieren von Updates auf der Seite **Lesen Sie die Lizenzbedingungen (1 von 1)** auf **Ich stimme zu**.
    
3. Nach Abschluss der Installation klicken Sie auf **Jetzt neu starten**, um den Computer neu zu starten.
    
Überprüfen Sie nach dem Neustart des Computers, ob Windows PowerShell gestartet wird und ob die Anwendung mit Anmeldeinformationen ausgeführt werden kann. Gehen Sie dazu so vor:
  
1. Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Wenn das Dialogfeld „Benutzerkontensteuerung" angezeigt wird, klicken Sie auf **Ja**, um zu bestätigen, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.
    
Wenn die PowerShell-Konsole angezeigt wird, überprüfen Sie, ob der WinRM-Dienst ausgeführt wird und richtig konfiguriert ist. Um zu überprüfen, ob der Dienst ausgeführt wird, geben Sie den folgenden Befehl an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
  
```
Get-Service winrm
```

Auf dem Bildschirm werden dann Informationen zum WinRM-Dienst angezeigt:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Wenn der Dienststatus nicht „Running" (Wird ausgeführt) entspricht, starten Sie den WinRM-Dienst, indem Sie den folgenden Befehl eingeben und dann die EINGABETASTE drücken:
  
```
Start-Service winrm
```

Nachdem der Dienst gestartet wurde, führen Sie den folgenden Befehl aus, um sicherzustellen, dass WinRM Standardauthentifizierung verwendet:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Auf dem Bildschirm werden etwa die folgenden Informationen angezeigt:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Wenn die Standardauthentifizierung festgelegt wurde auf "true", und klicken Sie dann Sie PowerShell verwenden, um eine Verbindung mit Skype für Business Online bereit sind.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 