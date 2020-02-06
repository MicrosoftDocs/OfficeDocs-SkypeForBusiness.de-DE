---
title: Verwalten von netzwerkregionen
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
description: Netzwerkregion * sind die Netzwerkhubs oder Backbones, die bei der Konfiguration der Anrufsteuerung, E9-1-1 und medienumgehung verwendet werden.
ms.openlocfilehash: c08232e455edb4388a052c2859b35e6c137b890a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817484"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Verwalten von Netzwerkregionen in Skype for Business Server

*Netzwerkregionen* sind die Netzwerkhubs oder Backbones, die in der Konfiguration der Anruf Zulassungs Steuerung, E9-1-1 und medienumgehung verwendet werden. Gehen Sie wie folgt vor, um netzwerkregionen anzuzeigen, zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits netzwerkregionen für ein Sprachfeature erstellt haben, müssen Sie keine neuen netzwerkregionen erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben netzwerkregionen verwendet. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben. 

Verwenden Sie die in diesem Artikel beschriebenen Verfahren, um Netzwerk Regionsinformationen anzuzeigen oder netzwerkregionen zu erstellen, zu ändern oder zu löschen. 

## <a name="view-network-region-information"></a>Anzeigen von Netzwerk Regionsinformationen 


Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg. Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird. Sie können die Skype for Business Server-Systemsteuerung verwenden, um netzwerkregionen anzuzeigen. Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind. Verwenden Sie dieses Thema, um vorhandene netzwerkregionen anzuzeigen. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>So zeigen Sie Informationen zu einem Netzwerkbereich mit der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf den Bereich, den Sie anzeigen möchten.
  
    > [!NOTE]  
    > Sie können nur jeweils einen Bereich anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerk Regionsinformationen mithilfe von Windows PowerShell-Cmdlets

Sie können Netzwerk Regionsinformationen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsNetworkRegion** anzeigen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. 

### <a name="to-view-network-region-information"></a>So zeigen Sie Netzwerkbereichs Informationen an

  - Wenn Sie Informationen zu allen ihren netzwerkregionen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkRegion
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .


## <a name="create-or-modify-network-regions"></a>Erstellen oder Ändern von netzwerkregionen 

Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg. Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird. Sie können die Skype for Business Server-Systemsteuerung verwenden, um netzwerkregionen zu konfigurieren. Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind. In der Skype for Business Server-Systemsteuerung können Sie einen Netzwerkbereich erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um netzwerkregionen zu erstellen und zu ändern. 

### <a name="to-create-a-network-region"></a>So erstellen Sie einen Netzwerkbereich

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf **neu**.

5.  Geben Sie auf der Seite **neuer Bereich** einen Wert in das Feld **Name** ein. Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Central Site** die zentrale Website für diesen Netzwerkbereich aus.

7.  Das Kontrollkästchen **audioalternativen Pfad aktivieren** ist standardmäßig aktiviert. Dieses Feld bestimmt, ob Audioanrufe durch einen alternativen Pfad weitergeleitet werden, wenn im primären Pfad keine ausreichende Bandbreite vorhanden ist. Deaktivieren Sie dieses Kontrollkästchen nur, wenn Sie die Verschiebung zum Internet deaktivieren müssen. Wenn es sich bei ihren anrufen um Internet Anrufe handelt, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

8.  Das Kontrollkästchen **Video alternativen Pfad aktivieren** ist standardmäßig aktiviert. Dieses Feld bestimmt, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn im primären Pfad keine ausreichende Bandbreite vorhanden ist. Deaktivieren Sie dieses Kontrollkästchen nur, wenn Sie die Verschiebung zum Internet deaktivieren müssen. Wenn es sich bei ihren anrufen um Internet Anrufe handelt, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

9.  Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu dieser Region bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.

10. Klicken Sie auf **Commit ausführen**.

Die Tabelle **zugeordnete Websites** wird nicht zum Erstellen eines Netzwerkbereichs verwendet. Sie ordnen eine Website einem Bereich zu, wenn Sie die Website erstellen oder ändern. Ausführliche Informationen finden Sie unter [Verwalten der Anrufsteuerung für Websites](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>So ändern Sie einen Netzwerkbereich

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf den Bereich, den Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite " **Bereich bearbeiten** " können Sie die Einstellungen für die Aktivierung und Deaktivierung von Audio-und Video Alternativen Pfaden ändern und die Beschreibung ändern (Einzelheiten finden Sie im Abschnitt "So erstellen Sie einen Netzwerkbereich" weiter oben in diesem Thema.

7.  Klicken Sie auf **Commit ausführen**.

Auf dieser Seite können Sie die **zugehörigen Websites** nicht ändern. Die Liste der zugehörigen Websites wird als Referenz bereitgestellt, damit Sie wissen, welche Websites beeinträchtigt werden, wenn Sie die Regionseinstellungen ändern.


## <a name="delete-existing-network-regions"></a>Löschen vorhandener netzwerkregionen 

Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg. Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird. Sie können die Skype for Business Server-Systemsteuerung verwenden, um netzwerkregionen zu konfigurieren. Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind. In der Skype for Business Server-Systemsteuerung können Sie einen Netzwerkbereich erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um vorhandene netzwerkregionen zu löschen. 

### <a name="to-delete-a-network-region"></a>So löschen Sie einen Netzwerkbereich

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf den Bereich, den Sie löschen möchten.
  
    > [!NOTE]  
    > Sie können mehr als einen Bereich gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Bereiche aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Bereiche auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.


    > [!WARNING]  
    > Eine netzwerkregion kann nicht entfernt werden, wenn Sie einer Netzwerk Website zugeordnet ist. Wenn Sie versuchen, einen Bereich zu entfernen, der einer Website zugeordnet ist, wird eine Fehlermeldung angezeigt. Wenn Sie feststellen möchten, ob ein Bereich Websites zugeordnet ist, wählen Sie den Bereich aus, und klicken Sie dann im Menü **Bearbeiten** auf **Details anzeigen** .


## <a name="see-also"></a>Siehe auch

[Verwalten von Routen im Netzwerkbereich](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
