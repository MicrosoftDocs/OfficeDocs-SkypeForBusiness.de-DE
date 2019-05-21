---
title: Verknüpfen von netzwerkregionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren. '
ms.openlocfilehash: b9ffa45c8a0a09ba4a7f9f0ebf6402b87116f01f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279557"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Verknüpfen von Netzwerkregionen in Skype for Business Server

Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren. Verwenden Sie die Abschnitte in diesem Artikel, um die Verknüpfungsinformationen für den Molch Bereich anzuzeigen oder Brücker Regions Verknüpfungen zu konfigurieren oder zu löschen. 

## <a name="view-network-region-link-information"></a>Link Informationen zum Anzeigen von netzwerkregionen 

Sie können die Verknüpfungen zwischen zwei netzwerkregionen im Rahmen der Anrufsteuerung (Call Admission Control, CAC) anzeigen. Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden. Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen anzuzeigen. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>So zeigen Sie einen Link zur netzwerkregion in der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Link**.

4.  Klicken Sie auf der Seite **Regions Link** auf den Link Region, den Sie anzeigen möchten.
    
    > [!NOTE]  
    > Sie können nur Informationen zu einem Regions Link gleichzeitig anzeigen.

5.  Wählen Sie im Menü **Bearbeiten** die Option **Details anzeigen**aus.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Link Informationen zu netzwerkregionen mithilfe von Windows PowerShell-Cmdlets

Sie können Netzwerk Regions Verknüpfungen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsNetworkRegionLink** anzeigen. Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. 


### <a name="to-view-network-region-link-information"></a>So zeigen Sie netzwerkregion-Verknüpfungsinformationen an

  - Wenn Sie Informationen zu allen ihren netzwerkregion-Links anzeigen möchten, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkRegionLink
    
    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Ausführliche Informationen finden Sie unter [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Konfigurieren von Netzwerk Regions Verknüpfungen 

Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren. Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden. Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine Verknüpfung zwischen zwei netzwerkregionen zu definieren und die Bandbreiteneinschränkungen für Audio-und Videoverbindungen zwischen diesen Regionen festzulegen.

### <a name="to-create-a-network-region-link"></a>So erstellen Sie eine Netzwerk Regions Verknüpfung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Link**.

4.  Klicken Sie auf der Seite **Regions Link** auf **neu**.

5.  Geben Sie im Feld **neuer Bereich**einen Wert in das Feld **Name** ein.
 
    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **netzwerkregion \#1** einen der beiden zu verknüpfende Regionen aus.

7.  Wählen Sie in der Dropdownliste **netzwerkregion \#2** die andere Region aus, die verknüpft werden soll. Diese Region muss sich von der für netzwerkregion \#1 ausgewählten Region unterscheiden.

8.  Optional Wenn Sie Bandbreiteneinschränkungen für Audio-oder Videoanrufe zwischen diesen Regionen festlegen möchten, wählen Sie in der Dropdownliste **bandbreitenrichtlinie** ein Profil für Bandbreitenrichtlinien aus.

9.  Klicken Sie auf **Commit ausführen**.

### <a name="to-modify-a-network-region-link"></a>So ändern Sie eine Netzwerk Regions Verknüpfung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Link**.

4.  Klicken Sie auf der Seite **Regions Link** auf den zu ändernden Bereichs Link.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Im **Link "Region bearbeiten**" können Sie die verknüpften Regionen oder das bandbreitenrichtlinienprofil für diesen Link ändern.

7.  Klicken Sie auf **Commit ausführen**.


## <a name="delete-network-region-links"></a>Löschen von Netzwerk Regions Verknüpfungen

Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren. Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden. Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen zu löschen. 

### <a name="to-delete-a-network-region-link"></a>So löschen Sie eine Netzwerk Regions Verknüpfung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Link**.

4.  Klicken Sie auf der Seite **Regions Link** auf den zu löschenden Regions Link.
 
    > [!NOTE]  
    > Sie können mehrere Regions Verknüpfungen gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie bei gedrückter STRG-Taste mehrere Regions Links aus. Wenn Sie alle Regions Verknüpfungen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .

5.  Wählen Sie im Menü **Bearbeiten** die Option **Löschen**aus.

6.  Klicken Sie auf **OK**.


## <a name="see-also"></a>Siehe auch

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
