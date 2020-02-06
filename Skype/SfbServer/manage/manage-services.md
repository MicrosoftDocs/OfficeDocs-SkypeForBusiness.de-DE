---
title: Verwalten von Diensten für Skype for Business Server
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: In diesem Artikel wird beschrieben, wie Sie Dienste verwalten, die in einer Skype for Business Server-Topologie ausgeführt werden.
ms.openlocfilehash: f730f095bdbf88af68afa0cd93568b1bf35ebdd9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817574"
---
# <a name="manage-services-for-skype-for-business-server"></a>Verwalten von Diensten für Skype for Business Server

In diesem Artikel wird beschrieben, wie Sie Dienste verwalten, die in einer Skype for Business Server-Topologie ausgeführt werden.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Anzeigen einer Liste mit Computern, auf denen Skype for Business Server ausgeführt wird
<a name="view_list"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine Liste aller Computer anzuzeigen, auf denen Skype for Business Server in Ihrer Topologie ausgeführt wird, und den jeweiligen Dienststatus anzuzeigen. Sie können die Liste nach Computer, Pool oder Website sortieren. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>So zeigen Sie eine Liste der Computer mit Skype for Business Server an

1. Melden Sie sich bei einem Benutzerkonto, das einer der vordefinierten Administratorrollen für Skype for Business Server zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an. Details zu den vordefinierten Administratorrollen, die in Skype for Business Server zur Verfügung stehen, finden Sie unter **Planen einer rollenbasierten Zugriffssteuerung**.   
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.   
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.   
4. Führen Sie auf der **Status** Seite nach Bedarf eine der folgenden Aktionen aus:
   - Sortieren Sie die Liste, indem Sie auf die Überschrift **Computer**, **Pool**oder **Website** Spalte und dann auf den nach oben oder den nach unten weisenden Pfeil klicken. 
   - Klicken Sie auf **Aktualisieren** , um die aktuelle Liste anzuzeigen.  
   - Suchen Sie nach einem bestimmten Computer, indem Sie den Computernamen in das Suchfeld eingeben.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Anzeigen des Status der Dienste, die auf einem Skype for Business-Server ausgeführt werden
<a name="view-status"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um alle Dienste anzuzeigen, die auf einem bestimmten Computer in Ihrer Skype for Business Server-Topologie ausgeführt werden, und den Status jedes Diensts anzuzeigen.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>So zeigen Sie den Status der auf einem Computer ausgeführten Dienste an

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie**. 
4. Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, an dem Sie interessiert sind, und klicken Sie dann auf den Computernamen.
5. Führen Sie einen der folgenden Schritte aus:
   - Wenn Sie den aktuellen Status der auf dem Computer ausgeführten Dienste anzeigen möchten, klicken Sie auf **Dienststatus abrufen**.
   - Wenn Sie eine Liste der auf dem Computer ausgeführten Dienste und den Status jedes Diensts anzeigen möchten, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf **Schließen** , um zur Liste zurückzukehren.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Anzeigen des Dienststatus mit Windows PowerShell-Cmdlets

Sie können den Dienststatus auch mithilfe von Windows PowerShell und dem Cmdlet **Get-CsWindowsService** anzeigen. Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-view-service-status"></a>So zeigen Sie den Dienststatus an

Wenn Sie den Dienststatus auf einem Computer anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell einen Befehl ähnlich dem folgenden ein, und drücken Sie dann die EINGABETASTE:
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
  
|**RoleName**|**Status**|
|:-----|:-----|
|W3SVC  <br/> |Ausgeführt  <br/> |
|{CentralManagement}  <br/> | Ausgeführt <br/> |
|{ClsAgent}  <br/> |Ausgeführt  <br/> |
|{Registrar, UserServer, EdgeServer}  <br/> |Ausgeführt  <br/> |
|ApplicationServer  <br/> |Ausgeführt  <br/> |
|{ConferencingServer}  <br/> |Ausgeführt  <br/> |
|{MediationServer}  <br/> |Ausgeführt  <br/> |
   
Ausführliche Informationen finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Anzeigen von Details zu einem Dienst
<a name="view_details"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um Details zu jedem Dienst anzuzeigen, der auf einem bestimmten Computer in Ihrer Topologie ausgeführt wird. Sie können den Status jedes Diensts und Details wie die zugehörigen Datenbanken, Ports und abhängigen Dienste anzeigen.
  
### <a name="to-view-details-for-a-service"></a>So zeigen Sie Details zu einem Dienst an

1. Melden Sie sich bei einem Benutzerkonto, das einer der vordefinierten Administratorrollen für Skype for Business Server zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an. Details zu den vordefinierten Administratorrollen, die in Skype for Business Server zur Verfügung stehen, finden Sie unter **Planen einer rollenbasierten Zugriffssteuerung**.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste, und klicken Sie dann auf den Computer, den Sie anzeigen möchten.
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie im Fenster **Computer Detail anzeigen** die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, den Sie anzeigen möchten.
7. Führen Sie bei Bedarf eine der folgenden Aktionen aus:
   - Wenn Sie den aktuellen Status dieses bestimmten Diensts anzeigen möchten, klicken Sie auf **Dienststatus abrufen**.
   - Wenn Sie die Details für diesen bestimmten Dienst anzeigen möchten, klicken Sie auf **Eigenschaften** , und klicken Sie dann auf **Schließen**.
   - Klicken Sie auf **Schließen**, um zur Liste aller Computer in Ihrer Topologie zurückzukehren.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Starten oder Beenden von Skype for Business Server-Diensten
<a name="StartStop"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um alle Skype for Business Server-Dienste zu starten oder zu beenden, die auf einem bestimmten Computer ausgeführt werden, oder um einen bestimmten Dienst zu starten oder zu beenden.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>So starten oder beenden Sie alle Skype for Business-Dienste auf einem Computer

1. Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. . Sie können feststellen, ob Ihnen die CsServerAdministrator-oder CsAdministrator-RBAC-Rolle zugewiesen wurde, indem Sie einen Befehl wie den folgenden ausführen:
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem die Dienste ausgeführt werden, die Sie starten oder beenden möchten, und klicken Sie darauf.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **alle Dienste starten** oder **alle Dienste beenden**.
    
### <a name="to-start-or-stop-a-specific-service"></a>So starten oder beenden Sie einen bestimmten Dienst

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten, und klicken Sie darauf.
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **Dienst starten** oder **Dienst beenden**.
9. Klicken Sie auf **Schließen**.
    
## <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste
<a name="prevent_session"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um neue Sitzungen für alle Skype for Business Server-Dienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Skype for Business Server-Dienst zu verhindern.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>So verhindern Sie neue Sitzungen für alle Skype for Business-Dienste auf einem Computer

1. Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten, und klicken Sie darauf.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **neue Sitzungen für alle Dienste verhindern**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>So verhindern Sie neue Sitzungen für einen bestimmten Dienst

1. Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten, und klicken Sie darauf. 
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **neue Sitzungen für Dienst verhindern**.
9. Klicken Sie auf **Schließen**.
    

