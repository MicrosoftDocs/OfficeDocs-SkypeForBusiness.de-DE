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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Sie können Windows PowerShell 5.1 herunterladen, installieren und dann verwenden, um eine Remote-PowerShell-Sitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt.
ms.openlocfilehash: 227023d5c86b99a66ecdbdabd3b2973d0383a534
ms.sourcegitcommit: ac922addbc1422b5c41273a2e03196efb2ed7770
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41831151"
---
# <a name="download-and-install-windows-powershell-51"></a>Herunterladen und Installieren von Windows PowerShell 5.1

Wenn Sie das Windows 10 Anniversary Update oder Windows Server 2016 verwenden, sollten Sie bereits über Windows PowerShell 5.1 verfügen. Das liegt daran, dass diese Anwendung mit diesen Betriebssystemen vorinstalliert wird.
  
Um zu ermitteln, welche Version von Microsoft PowerShell Sie verwenden, gehen Sie auf Ihrem Computer unter Windows 7 oder Windows Server 2008 R2 oder Windows Server 2012 wie folgt vor:
  
1. Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör**, auf **Windows PowerShell** und dann auf **Windows PowerShell**.
    
2. Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. Nun werden im Konsolenfenster Informationen wie die folgenden angezeigt:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Wenn die Versionsnummer 5.1 zurückgegeben wird, führen Sie Windows PowerShell 5.1 aus. Wenn anstelle von 5.1 eine andere Versionsnummer zurückgegeben wird, müssen Sie Windows PowerShell 5.1 installieren. Sie können Windows Management Framework 5.1 (einschließlich Windows PowerShell 5.1) aus dem [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616) herunterladen.
  
Wenn Sie sich vergewissert haben, dass Windows PowerShell 5.1 installiert ist, müssen Sie sicherstellen, dass PowerShell für die Ausführung von Remoteskripts konfiguriert ist. Starten Sie dazu PowerShell als Administrator. Unter Windows 7, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 gehen Sie wie folgt vor:
  
1. Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Klicken Sie dann im Dialogfeld **Benutzerkontensteuerung** auf **Ja**, um zu bestätigen, dass Sie PowerShell mit den Administratoranmeldeinformationen ausführen möchten.
    
Wenn Sie Windows 8 verwenden, gehen Sie stattdessen wie folgt vor:
  
1. Greifen Sie auf die Charmsleiste zu, klicken Sie auf **Suchen**, und klicken Sie dann mit der rechten Maustaste auf **Windows PowerShell**. Auf Windows 8-Computern (mit oder ohne Touchscreen) können Sie schnell auf die Charmsleiste zugreifen, indem Sie die WINDOWS-TASTE gedrückt halten und C drücken.
    
2. Klicken Sie auf der Symbolleiste unten auf dem Bildschirm auf **Als Administrator ausführen**.
    
3. Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**. Damit bestätigen Sie, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.
    
Wenn PowerShell ausgeführt wird, müssen Sie die Ausführungsrichtlinie ändern, um die Ausführung von Remoteskripts zuzulassen. Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Wenn Sie den vorstehenden Befehl ausführen, wird möglicherweise die folgende Fehlermeldung angezeigt:> *Set-ExecutionPolicy : Der Zugriff auf den Registrierungsschlüssel „HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShel“ wird verweigert.* Diese Fehlermeldung wird normalerweise ausgegeben, wenn Sie PowerShell nicht mit Administratorrechten ausführen. Schließen Sie die PowerShell-Sitzung, und starten Sie eine neue Sitzung als Administrator.
 
Um zu überprüfen, ob die Ausführungsrichtlinie richtig konfiguriert ist, geben Sie Folgendes an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
  
```PowerShell
Get-ExecutionPolicy
```

Wenn der folgende Wert zurückgegeben wird, wurde alles ordnungsgemäß konfiguriert:
  
`RemoteSigned`

Wenn Sie zurzeit nicht Windows PowerShell 5.1 ausführen, müssen Sie auch Windows Management Framework 5.1 aus dem Microsoft Download Center herunterladen. Dabei handelt es sich um ein Installationspaket, in dem Windows PowerShell 5.1 und Windows-Remoteverwaltung (WinRM) 3.0 enthalten sind. Das Installationspaket ist möglicherweise erforderlich, wenn Sie beispielsweise Windows 7 SP1 ausführen und noch nicht auf Windows PowerShell 5.1 aktualisiert haben. Wenn Sie Windows Server 2016 oder das Windows 10 Anniversary Update ausführen, sollte es nicht erforderlich sein, Windows PowerShell 5.1 zu installieren. Unter diesen Betriebssystemen ist Windows PowerShell 5.1 vorinstalliert.
  
Vor der Installation von Windows Management Framework 5.1:
  
- Vergewissern Sie sich, dass Sie die korrekte Version des Installationspakets heruntergeladen haben. Wenn Sie die 64-Bit-Version von Windows 7 SP1 verwenden, laden Sie die Datei "Win7AndW2K8R2-KB3191566-x64.ZIP" herunter. Für die 32-Bit-Version von Windows 7 laden Sie die Datei "Win7-KB3191566-x86.ZIP" herunter.
    
- Wenn auf Ihrem Computer Windows 7 ausgeführt wird, vergewissern Sie sich, dass Sie Windows 7 Service Pack 1 installiert haben.

Wenn Sie nicht sicher sind, welche Version von Windows ausgeführt wird oder ob Windows 7 Service Pack 1 installiert ist, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**. Diese Informationen werden im Dialogfeld „System" angezeigt.
  
Um Windows Management Framework 5.1 zu installieren, führen Sie die Schritte unter [Installieren und Konfigurieren von WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure) aus.
  
Überprüfen Sie nach dem Neustart des Computers, ob Windows PowerShell gestartet wird und ob die Anwendung mit Anmeldeinformationen ausgeführt werden kann. Gehen Sie dazu so vor:
  
1. Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Wenn das Dialogfeld „Benutzerkontensteuerung" angezeigt wird, klicken Sie auf **Ja**, um zu bestätigen, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.
    
Wenn die PowerShell-Konsole angezeigt wird, überprüfen Sie, ob der WinRM-Dienst ausgeführt wird und richtig konfiguriert ist. Um zu überprüfen, ob der Dienst ausgeführt wird, geben Sie den folgenden Befehl an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
  
```PowerShell
Get-Service winrm
```

Auf dem Bildschirm werden nun Informationen zum Dienst WinRM angezeigt:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Wenn der Dienststatus nicht „Running" (Wird ausgeführt) entspricht, starten Sie den WinRM-Dienst, indem Sie den folgenden Befehl eingeben und dann die EINGABETASTE drücken:
  
```PowerShell
Start-Service winrm
```

Nachdem der Dienst gestartet wurde, führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass WinRM mit der Standardauthentifizierung arbeitet:
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Auf dem Bildschirm werden nun Informationen wie die folgenden angezeigt:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Wenn die Standardauthentifizierung auf „true" festgelegt ist, können Sie PowerShell verwenden, um eine Verbindung mit Skype for Business Online herzustellen.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 
