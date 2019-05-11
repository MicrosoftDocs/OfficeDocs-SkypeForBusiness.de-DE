---
title: Verbinden von netzwerkregionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Sie können die Verbindungen zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) konfigurieren. '
ms.openlocfilehash: 30d4a020826b24c3615ce059809645481466efc3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888352"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Verknüpfen von Netzwerkregionen in Skype for Business Server

Sie können die Verbindungen zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) konfigurieren. Verwenden Sie in den Abschnitten in diesem Artikel, um Newtwork Informationen zu netzwerkregionenverbindungen anzeigen oder konfigurieren oder Löschen von Netwrok Region Verknüpfungen. 

## <a name="view-network-region-link-information"></a>Informationen zu netzwerkregionenverbindungen anzeigen 

Sie können zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) Links anzeigen. Regionen in einem Netzwerk sind über Netzwerkkonnektivität (WAN) physischen WAN verknüpft. Sie können die Skype Business Server-Systemsteuerung verwenden, um einer vorhandenen Verknüpfung zwischen zwei netzwerkregionen anzuzeigen. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>So zeigen Sie eine netzwerkregionenverbindung in Skype Business Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die regionenverbindung, die Sie anzeigen möchten.
    
    > [!NOTE]  
    > Sie können nur Informationen zu einer regionenverbindung zu einem Zeitpunkt anzeigen.

5.  Wählen Sie im Menü **Bearbeiten** die **Details anzeigen**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zu netzwerkregionenverbindungen mithilfe von Windows PowerShell-cmdlets

Sie können mithilfe von Windows PowerShell und das Cmdlet **Get-CsNetworkRegionLink** netzwerkregionenverbindungen anzeigen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung. 


### <a name="to-view-network-region-link-information"></a>Informationen zu netzwerkregionenverbindungen anzeigen

  - Um Informationen über alle netzwerkregionenverbindungen anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
        Get-CsNetworkRegionLink
    
    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Weitere Informationen hierzu finden Sie unter [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Konfigurieren von netzwerkregionenverbindungen 

Sie können die Verbindungen zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) konfigurieren. Regionen in einem Netzwerk sind über Netzwerkkonnektivität (WAN) physischen WAN verknüpft. Die Skype Business Server-Systemsteuerung können Sie eine Verbindung zwischen zwei netzwerkregionen definieren und die Netzwerkbandbreite ist eingeschränkt auf audio und video Verbindungen zwischen diesen Regionen festlegen.

### <a name="to-create-a-network-region-link"></a>Erstellen Sie eine netzwerkregionenverbindung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf **neu**.

5.  Geben Sie in **Neue Regionenverbindung**einen Wert in das Feld **Name** ein.
 
    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Skype für Business Server-Bereitstellung eindeutig sein.

6.  Aus der **netzwerkregion \#1** Dropdown-Listenfeld, wählen Sie eine der zwei Regionen aus, die verknüpft werden.

7.  Aus der **netzwerkregion \#2** Dropdown-Liste, wählen Sie die anderen Region verknüpft werden soll. Diese Region muss die Region für die netzwerkregion ausgewählt anders \#1.

8.  (Optional) Wenn Sie die Netzwerkbandbreite ist eingeschränkt auf Audio- oder Videoinhalten Anrufe zwischen diesen Regionen platzieren möchten, wählen Sie ein bandbreitenrichtlinienprofil aus der Dropdownliste **bandbreitenrichtlinie** aus.

9.  Klicken Sie auf **Commit ausführen**.

### <a name="to-modify-a-network-region-link"></a>So ändern Sie eine netzwerkregionenverbindung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die regionenverbindung, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Im **Abschnitt Regionenverbindung bearbeiten**können Sie ändern, der die verknüpften Regionen oder das bandbreitenrichtlinienprofil für diese Verknüpfung.

7.  Klicken Sie auf **Commit ausführen**.


## <a name="delete-network-region-links"></a>Löschen von netzwerkregionenverbindungen

Sie können die Verbindungen zwischen zwei netzwerkregionen im Rahmen der anrufsteuerung (CAC) konfigurieren. Regionen in einem Netzwerk sind über Netzwerkkonnektivität (WAN) physischen WAN verknüpft. Die Skype Business Server-Systemsteuerung können Sie um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen zu löschen. 

### <a name="to-delete-a-network-region-link"></a>So löschen Sie eine netzwerkregionenverbindung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die regionenverbindung, die Sie löschen möchten.
 
    > [!NOTE]  
    > Sie können mehrere regionenverbindung zu einem Zeitpunkt löschen. Zu diesem Zweck drücken Sie STRG, und wählen Sie mehrere regionenverbindungen, während Sie die STRG-Taste gedrückt halten. Oder, um alle regionenverbindungen auszuwählen, klicken Sie auf <STRONG>Alles markieren</STRONG> im Menü <STRONG>Bearbeiten</STRONG> .

5.  Wählen Sie im Menü **Bearbeiten** **Löschen**aus.

6.  Klicken Sie auf **OK**.


## <a name="see-also"></a>Siehe auch

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
