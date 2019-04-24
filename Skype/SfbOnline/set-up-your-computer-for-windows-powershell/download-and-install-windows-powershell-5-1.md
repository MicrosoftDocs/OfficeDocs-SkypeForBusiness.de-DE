---
title: Herunterladen und Installieren von Windows PowerShell 5.1
ms.reviewer: ''
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
description: Herunterladen Sie, installieren Sie, und klicken Sie dann verwenden Sie Windows PowerShell 5.1, um eine remote-PowerShell-Sitzung zu erstellen, die mit Skype für Business Online verbindet.
ms.openlocfilehash: 63f4924a30bfc910679f23a617cc5252ecc5b6aa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198068"
---
# <a name="download-and-install-windows-powershell-51"></a>Herunterladen und Installieren von Windows PowerShell 5.1

Wenn Sie Windows 10 Jahrestag Update oder Windows Server 2016 verwenden, sollten Sie bereits Windows PowerShell 5.1 verfügen. Das liegt daran, dass die Anwendung unter diesen Betriebssystemen vorinstalliert ist.
  
Um zu bestimmen, welche Version von Microsoft PowerShelll Sie verwenden, gehen Sie auf Ihrem Windows 7 oder Windows Server 2008 R2 oder Windows Server 2012-Computer:
  
1. Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör**, auf **Windows PowerShell** und dann auf **Windows PowerShell**.
    
2. Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
   ```
   Get-Host | Select-Object Version
   ```

3. Im Konsolenfenster sollten dann etwa die folgenden Informationen angezeigt werden:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Wenn die zurückgegebene Versionsnummer 5.1 ist, werden Sie Windows PowerShell 5.1 ausgeführt. Wenn die zurückgegebene Versionsnummer nicht 5.1 ist, müssen Sie Windows PowerShell 5.1 installieren. Sie können Windows Management Framework 5.1, einschließlich Windows PowerShell 5.1, aus dem [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616)herunterladen.
  
Nachdem Sie sichergestellt haben, dass Windows PowerShell 5.1 installiert ist, müssen Sie sicherstellen, dass für das Ausführen von Skripts remote PowerShell konfiguriert wurde. Starten Sie dazu PowerShell als Administrator. Unter Windows 7, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 gehen Sie wie folgt vor:
  
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
> Wenn Sie mit dem vorstehenden Befehl ausführen, erhalten Sie möglicherweise die folgenden Fehler angezeigt: > *Set-ExecutionPolicy: Zugriff auf den Registrierungsschlüssel "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' wird verweigert.* Diese Fehlermeldung tritt typischerweise auf, wenn Sie PowerShell nicht unter Administratoranmeldeinformationen ausgeführt werden. Schließen der PowerShell-Sitzung, und starten Sie eine neue Sitzung als Administrator.
 
Um zu überprüfen, ob die Ausführungsrichtlinie richtig konfiguriert ist, geben Sie Folgendes an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
  
```
Get-ExecutionPolicy
```

Wenn der folgende Wert zurückgegeben wird, ist alles richtig konfiguriert:
  
`RemoteSigned`

Wenn Sie Windows PowerShell 5.1 derzeit nicht ausgeführt werden, müssen Sie auch zum Herunterladen und Installieren von Windows Management Framework 5.1 aus dem Microsoft Download Center. Dies ist ein Installationspaket, die Windows PowerShell 5.1 und Windows-Remoteverwaltung (WinRM) 3.0 enthält. Dieses Installationspaket kann erforderlich sein, wenn Sie beispielsweise Windows 7 SP1 ausgeführt werden und noch nicht auf Windows PowerShell 5.1 aktualisiert haben. Wenn Sie Windows Server 2016 oder Windows 10 Jahrestag Update ausführen, sollten keine müssen Windows PowerShell 5.1 installieren werden. Windows PowerShell 5.1 ist auf diesen Betriebssystemen vorinstalliert.
  
Vor der Installation von Windows Management Framework 5.1:
  
- Vergewissern Sie sich, dass Sie die richtige Version des Installationspakets heruntergeladen haben. Wenn Sie die 64-Bit-Version von Windows 7 SP1 ausgeführt werden, laden Sie die Datei Win7AndW2K8R2-KB3191566-x64.ZIP. Wenn Sie die 32-Bit-Version von Windows 7 ausgeführt werden, laden Sie die Datei Win7-KB3191566-x86.ZIP.
    
- Wenn Sie auf Ihrem Computer Windows 7 ausführen, vergewissern Sie sich, dass Windows 7 Service Pack 1 installiert ist.

Wenn Sie nicht sicher sind, welche Version von Windows ausgeführt wird oder ob Windows 7 Service Pack 1 installiert ist, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**. Diese Informationen werden im Dialogfeld „System" angezeigt.
  
Führen Sie zum Installieren von Windows Management Framework 5.1 das Verfahren in [Installieren und Konfigurieren von WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)
  
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

  
 
