---
title: Herunterladen und Installieren von Windows PowerShell 5,1
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Sie können Windows PowerShell 5,1 herunterladen, installieren und verwenden, um eine Remote-PowerShell-Sitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt.
ms.openlocfilehash: 5afca0ef1fd5d7437c3974de1424a664c99ab1a1
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701555"
---
# <a name="download-and-install-windows-powershell-51"></a>Herunterladen und Installieren von Windows PowerShell 5,1

Wenn Sie Windows 10 Anniversary Update oder Windows Server 2016 verwenden, sollten Sie Windows PowerShell 5,1 bereits verwenden. Das liegt daran, dass die Anwendung unter diesen Betriebssystemen vorinstalliert ist.
  
Wenn Sie ermitteln möchten, welche Version von Microsoft PowerShell Sie verwenden, führen Sie die folgenden Schritte auf Ihrem Windows 7-oder Windows Server 2008 R2-oder Windows Server 2012-Computer aus:
  
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

    Wenn die zurückgegebene Versionsnummer 5,1 ist, führen Sie Windows PowerShell 5,1 aus. Wenn die zurückgegebene Versionsnummer nicht 5,1 ist, müssen Sie Windows PowerShell 5,1 installieren. Sie können das Windows Management Framework 5,1, einschließlich Windows PowerShell 5,1, aus dem [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616)herunterladen.
  
Nachdem Sie überprüft haben, dass Windows PowerShell 5,1 installiert ist, müssen Sie sicherstellen, dass PowerShell für die Ausführung von Remoteskripts konfiguriert wurde. Starten Sie dazu PowerShell als Administrator. Unter Windows 7, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 gehen Sie wie folgt vor:
  
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
> Wenn Sie den vorhergehenden Befehl ausführen, wird möglicherweise die folgende Fehlermeldung angezeigt: #a0 *Satz-ExecutionPolicy: Zugriff\\auf\\die\\Registrierungs\\-\\key'HKEY_LOCAL_MACHINE-Software Microsoft PowerShell 1 ShellIds\\Micrsoft. PowerShell ' wurde verweigert.* Diese Fehlermeldung tritt in der Regel auf, wenn Sie PowerShell nicht unter Administratoranmeldeinformationen ausführen. Schließen Sie Ihre PowerShell-Sitzung, und starten Sie eine neue Sitzung als Administrator.
 
Um zu überprüfen, ob die Ausführungsrichtlinie richtig konfiguriert ist, geben Sie Folgendes an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
  
```
Get-ExecutionPolicy
```

Wenn der folgende Wert zurückgegeben wird, ist alles richtig konfiguriert:
  
`RemoteSigned`

Wenn Sie derzeit nicht mit Windows PowerShell 5,1 arbeiten, müssen Sie auch Windows Management Framework 5,1 aus dem Microsoft Download Center herunterladen und installieren. Hierbei handelt es sich um ein Installationspaket, das Windows PowerShell 5,1 und Windows Remote Management (WinRM) 3,0 umfasst. Dieses Installationspaket ist möglicherweise erforderlich, wenn Sie beispielsweise Windows 7 SP1 ausführen und noch nicht auf Windows PowerShell 5,1 aktualisiert wurden. Wenn Sie Windows Server 2016 oder Windows 10 Anniversary Update ausführen, sollten Sie Windows PowerShell 5,1 nicht installieren müssen. Windows PowerShell 5,1 ist auf diesen Betriebssystemen vorinstalliert.
  
Vor der Installation von Windows Management Framework 5,1:
  
- Vergewissern Sie sich, dass Sie die richtige Version des Installationspakets heruntergeladen haben. Wenn Sie die 64-Bit-Version von Windows 7 SP1 ausführen, laden Sie die Datei Win7AndW2K8R2-KB3191566-x64. zip herunter. Wenn Sie die 32-Bit-Version von Windows 7 ausführen, laden Sie die Datei Win7-KB3191566-x86. zip herunter.
    
- Wenn Sie auf Ihrem Computer Windows 7 ausführen, vergewissern Sie sich, dass Windows 7 Service Pack 1 installiert ist.

Wenn Sie nicht sicher sind, welche Version von Windows ausgeführt wird oder ob Windows 7 Service Pack 1 installiert ist, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**. Diese Informationen werden im Dialogfeld „System" angezeigt.
  
Zum Installieren von Windows Management Framework 5,1 führen Sie das Verfahren unter [Installieren und Konfigurieren von WMF 5,1](https://docs.microsoft.com/powershell/wmf/setup/install-configure)aus.
  
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

Wenn die Standardauthentifizierung auf "true" festgelegt wurde, können Sie PowerShell verwenden, um eine Verbindung mit Skype for Business Online herzustellen.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 
