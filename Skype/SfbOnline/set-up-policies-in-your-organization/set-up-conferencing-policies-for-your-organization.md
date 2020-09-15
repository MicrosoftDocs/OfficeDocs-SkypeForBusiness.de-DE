---
title: Einrichten von Konferenzrichtlinien für Ihre Organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
- Setup
description: 'Konferenzen sind ein wichtiger Bestandteil von Skype for Business Online: In Konferenzen können Gruppen von Benutzern gemeinsam online Folien und Videos anzeigen, Anwendungen freigeben, Dateien austauschen und anderweitig kommunizieren und zusammenarbeiten.'
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814754"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Einrichten von Konferenzrichtlinien für Ihre Organisation

Konferenzen sind ein wichtiger Bestandteil von Skype for Business Online: In Konferenzen können Gruppen von Benutzern gemeinsam online Folien und Videos anzeigen, Anwendungen freigeben, Dateien austauschen und anderweitig kommunizieren und zusammenarbeiten.
  
Wichtig ist dabei, dass Sie die Kontrolle über Konferenzen und Konferenzeinstellungen behalten. In manchen Fällen liegen möglicherweise Sicherheitsbedenken vor: Standardmäßig können alle, das heißt auch nicht authentifizierte Benutzer, an Besprechungen teilnehmen und die in diesen Besprechungen verteilten Folien oder Handzettel speichern. Darüber hinaus sind manchmal auch rechtliche Bedenken möglich. So können beispielsweise die Besprechungsteilnehmer standardmäßig Anmerkungen zu freigegebenen Inhalten hinzufügen. Diese Anmerkungen werden jedoch nicht gespeichert, wenn die Besprechung archiviert wird. Wenn Ihre Organisation Aufzeichnungen der gesamten elektronischen Kommunikation aufbewahren muss, sollten Sie Anmerkungen deaktivieren. 
  
In Skype for Business Online werden Konferenzen mithilfe von Konferenzrichtlinien verwaltet. Konferenzrichtlinien bestimmen die Merkmale und Funktionen, die in einer Konferenz verwendet werden können. Dazu gehört die Frage, ob die Konferenz IP-Audio und -Video für die maximal mögliche Teilnehmeranzahl in einer Besprechung enthalten kann. Konferenzrichtlinien können auf globaler Ebene oder auf Benutzerebene konfiguriert werden. Dadurch können Administratoren sehr flexibel entscheiden, welche Funktionen welchen Benutzern zur Verfügung gestellt werden sollen.
  
Richtlinieneinstellungen können Sie bei der Erstellung einer Richtlinie konfigurieren. Alternativ können Sie das **Set-CsConferencingPolicy** -Cmdlet verwenden, um die Einstellungen einer vorhandenen Richtlinie zu ändern.
  
## <a name="set-your-conferencing-policies"></a>Festlegen Ihrer Konferenzrichtlinien

> [!NOTE]
> Für alle Konferenzrichtlinieneinstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**. 
  
### <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
    1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
        
    2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
        
    3. Wenn Sie nicht über Version 3,0 oder höher verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
        
    4. Außerdem müssen Sie das Windows PowerShell-Modul für Teams installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt.
    
    Wenn Sie weitere Informationen benötigen, lesen Sie [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
    1. Vom **Start Menu** > **Windows PowerShell**.
        
    2. Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Ihrem Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:
        
     > [!NOTE]
     > Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
     >
     > Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Blockieren von Dateiübertragung und Desktopfreigabe in Besprechungen

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   Weitere Informationen finden Sie unter dem Cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   Weitere Informationen finden Sie im Cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx)-Cmdlet die Einstellungen auf die Benutzer anwenden.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Blockieren der Aufzeichnung von Konferenzen und Verhindern von anonymen Besprechungsteilnehmern

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus: 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   Weitere Informationen finden Sie unter dem Cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .
    
- Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   Weitere Informationen finden Sie im Cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das Cmdlet " [festlegen-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) " verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und verwenden Sie dann das Cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) , um die Einstellungen auf die Benutzer anzuwenden.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Blockieren der Aufzeichnung von Besprechungen durch anonyme Teilnehmer und der Speicherung von Besprechungsinhalten durch externe Benutzer

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   Weitere Informationen finden Sie unter dem Cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

Weitere Informationen finden Sie im Cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx)-Cmdlet die Einstellungen auf die Benutzer anwenden.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Microsoft 365 oder Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

  
 
