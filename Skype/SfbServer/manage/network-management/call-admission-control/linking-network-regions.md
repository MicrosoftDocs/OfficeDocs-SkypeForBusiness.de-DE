---
title: Verknüpfen von Netzwerkregionen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren. '
ms.openlocfilehash: 163f214b05ba0dca3bc7dd4ec722f148cafe724e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096681"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Verknüpfen von Netzwerkregionen in Skype for Business Server

Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren. Verwenden Sie die Abschnitte in diesem Artikel, um Informationen zu neuen Netzwerkbereichslinks anzeigen oder netwrok-Regionenlinks konfigurieren oder löschen. 

## <a name="view-network-region-link-information"></a>Anzeigen von Informationen zu Netzwerkregionsverbindungen 

Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen anzeigen. Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden. Mit der Skype for Business Server-Systemsteuerung können Sie eine vorhandene Verbindung zwischen zwei Netzwerkregionen anzeigen. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>So zeigen Sie eine Netzwerkregionsverbindung in der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über entsprechende Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region Link**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie anzeigen möchten.
    
    > [!NOTE]  
    > Es können in einem Arbeitsschritt nur Informationen zu einer Regionenverbindung angezeigt werden.

5.  Wählen Sie im Menü **Bearbeiten** die Option **Details anzeigen** aus.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerkregionsverbindungsinformationen mithilfe Windows PowerShell Cmdlets

Sie können Netzwerkregionenverbindungen mit Windows PowerShell und **dem Cmdlet Get-CsNetworkRegionLink** anzeigen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. 


### <a name="to-view-network-region-link-information"></a>So zeigen Sie die Informationen zu einer Netzwerkregionenverbindung an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerkregionsverbindungen den folgenden Befehl in die Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkRegionLink
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Für weitere Informationen, siehe [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Konfigurieren von Netzwerkregionsverbindungen 

Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren. Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden. Mit der Skype for Business Server-Systemsteuerung können Sie eine Verbindung zwischen zwei Netzwerkregionen definieren und die Bandbreiteneinschränkungen für Audio- und Videoverbindungen zwischen diesen Regionen festlegen.

### <a name="to-create-a-network-region-link"></a>So erstellen Sie eine Netzwerkregionenverbindung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über entsprechende Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region Link**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf **Neu**.

5.  Geben Sie im Abschnitt **Neue Regionenverbindung** im Feld **Name** einen Wert ein.
 
    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste Netzwerkregion **\# 1** eine der beiden zu verbindende Regionen aus.

7.  Wählen Sie in der Dropdownliste Netzwerkregion **\# 2** die andere zu verbindende Region aus. Diese Region muss sich von der Region unterscheiden, die für Netzwerkregion 1 ausgewählt \# wurde.

8.  (Optional) Wenn Sie Bandbreitenbeschränkungen für Audio- oder Videoanrufe zwischen diesen Regionen festlegen möchten, wählen Sie ein Bandbreitenrichtlinienprofil in der Dropdownliste **Bandbreitenrichtlinie** aus.

9.  Klicken Sie auf **Commit**.

### <a name="to-modify-a-network-region-link"></a>So ändern Sie eine Netzwerkregionenverbindung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über entsprechende Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region Link**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Im Abschnitt **Regionenverbindung bearbeiten** können Sie die verknüpften Regionen oder das Bandbreitenrichtlinienprofil für diese Region ändern.

7.  Klicken Sie auf **Commit**.


## <a name="delete-network-region-links"></a>Löschen von Netzwerkregionsverbindungen

Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren. Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden. Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine vorhandene Verbindung zwischen zwei Netzwerkregionen zu löschen. 

### <a name="to-delete-a-network-region-link"></a>So löschen Sie eine Netzwerkregionenverbindung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über entsprechende Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region Link**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie löschen möchten.
 
    > [!NOTE]  
    > Sie können mehrere Regionenverbindungen in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Netzwerkregionen aus. Wenn Sie alle Netzwerkregionen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.

5.  Wählen Sie im Menü **Bearbeiten** die Option **Löschen** aus.

6.  Klicken Sie auf **OK**.


## <a name="see-also"></a>Siehe auch

[New-CsNetworkRegionLink](/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)