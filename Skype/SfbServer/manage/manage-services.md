---
title: Verwalten von Diensten für Skype for Business Server
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: In diesem Artikel wird beschrieben, wie Sie Dienste verwalten, die in einer Skype for Business Server-Topologie ausgeführt werden.
ms.openlocfilehash: 05bf37248e710424b7540fe0dbcc10338bd1f4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816595"
---
# <a name="manage-services-for-skype-for-business-server"></a>Verwalten von Diensten für Skype for Business Server

In diesem Artikel wird beschrieben, wie Sie Dienste verwalten, die in einer Skype for Business Server-Topologie ausgeführt werden.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Anzeigen einer Liste der Computer, auf denen Skype for Business Server ausgeführt wird
<a name="view_list"> </a>

Mithilfe der Skype for Business Server-Systemsteuerung können Sie eine Liste aller Computer anzeigen, auf denen Skype for Business Server in Ihrer Topologie ausgeführt wird, und den Jeweiligen Dienststatus anzeigen. Sie können die Liste nach Computer, Pool oder Standort sortieren. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>So zeigen Sie eine Liste der Computer an, auf denen Skype for Business Server ausgeführt wird

1. Melden Sie sich über ein Benutzerkonto, das einer der vordefinierten Administratorrollen für Skype for Business Server zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an. Details zu den vordefinierten Administratorrollen, die in Skype for Business Server verfügbar sind, finden Sie unter **Planning for Role-Based Access Control**.   
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.   
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.   
4. Führen Sie auf der Seite **Status** nach Bedarf die folgenden Schritte aus:
   - Sortieren Sie die Liste, indem Sie auf die Spaltenüberschrift **Computer**, **Pool** oder **Standort** und anschließend auf den Aufwärts- oder Abwärtspfeil klicken. 
   - Klicken Sie auf **Aktualisieren**, um die aktuelle Liste anzuzeigen.  
   - Suchen Sie nach einem bestimmten Computer, indem Sie den Computernamen im Suchfeld eingeben.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Anzeigen des Status von Diensten, die auf einem Skype for Business-Server ausgeführt werden
<a name="view-status"> </a>

Mithilfe der Skype for Business Server-Systemsteuerung können Sie alle Dienste anzeigen, die auf einem bestimmten Computer in Ihrer Skype for Business Server-Topologie ausgeführt werden, und den Status der einzelnen Dienste anzeigen.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>So zeigen Sie den Status von Diensten an, die auf einem Computer ausgeführt werden

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie auf der linken Navigationsleiste auf **Topologie**. 
4. Sortieren oder **durchsuchen** Sie auf der Statusseite die Liste nach Bedarf, um den gewünschten Computer zu finden, und klicken Sie dann auf den Computernamen.
5. Führen Sie einen der folgenden Schritte aus:
   - Klicken Sie auf Dienststatus erhalten, um den neuesten Status der auf dem Computer **ausgeführten Dienste zu sehen.**
   - Wenn Sie eine Liste der auf dem Computer ausgeführten Dienste und den  Status der einzelnen Dienste anzeigen möchten, klicken Sie auf "Eigenschaften" **und** dann auf "Schließen", um zur Liste zurückzukehren.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Anzeigen des Dienststatus mit Windows -Powershell-Cmdlets

Sie können den Dienststatus auch mithilfe Windows PowerShell **Cmdlets "Get-CsWindowsService"** anzeigen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. Details zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.
  
### <a name="to-view-service-status"></a>So zeigen Sie den Dienststatus an

Geben Sie zum Anzeigen des Dienststatus auf einem Computer einen Befehl wie den folgenden in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Es werden etwa folgende Informationen zurückgegeben:
  
|**RoleName**|**Status**|
|:-----|:-----|
|{W3SVC}  <br/> |Wird ausgeführt  <br/> |
|{CentralManagement}  <br/> | Wird ausgeführt <br/> |
|{ClsAgent}  <br/> |Wird ausgeführt  <br/> |
|{Registrar, UserServer, EdgeServer}  <br/> |Wird ausgeführt  <br/> |
|{ApplicationServer}  <br/> |Wird ausgeführt  <br/> |
|{ConferencingServer}  <br/> |Wird ausgeführt  <br/> |
|{MediationServer}  <br/> |Wird ausgeführt  <br/> |
   
Weitere Informationen finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Anzeigen von Details zu einem Dienst
<a name="view_details"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um Details zu jedem Dienst anzuzeigen, der auf einem bestimmten Computer in Ihrer Topologie ausgeführt wird. Sie können den Status der einzelnen Dienste und Details anzeigen, z. B. die zugehörigen Datenbanken, Ports und abhängigen Dienste.
  
### <a name="to-view-details-for-a-service"></a>So zeigen Sie Details für einen Dienst an

1. Melden Sie sich über ein Benutzerkonto, das einer der vordefinierten Administratorrollen für Skype for Business Server zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an. Details zu den vordefinierten Administratorrollen, die in Skype for Business Server verfügbar sind, finden Sie unter **Planning for Role-Based Access Control**.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder **durchsuchen Sie auf** der Seite "Status" die Liste, und klicken Sie dann auf den Computer, den Sie anzeigen möchten.
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie **im Fenster "Computerdetails** anzeigen" die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, den Sie anzeigen möchten.
7. Gehen Sie nach Bedarf wie folgt vor:
   - Klicken Sie auf Dienststatus erhalten, um den neuesten Status dieses **bestimmten Diensts zu sehen.**
   - Um die Details für diesen bestimmten Dienst anzuzeigen, klicken Sie **auf "Eigenschaften"** und dann auf **"Schließen".**
   - Klicken Sie auf "Schließen", um zur Liste aller Computer in Ihrer Topologie **zurückzukehren.**
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Starten oder Beenden von Skype for Business Server-Diensten
<a name="StartStop"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um alle Skype for Business Server-Dienste zu starten oder zu beenden, die auf einem bestimmten Computer ausgeführt werden, oder um einen bestimmten Dienst zu starten oder zu beenden.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>So starten oder beenden Sie alle Skype for Business-Dienste auf einem Computer

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. Sie können ermitteln, ob Ihnen die Rollen "CsServerAdministrator" oder "CsAdministrator RBAC" zugewiesen wurde, indem Sie einen Befehl wie den folgenden ausführen:
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, und ermitteln Sie so den Computer, auf dem die Dienste ausgeführt werden, die Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **Alle Dienste starten** bzw. auf **Alle Dienste beenden**.
    
### <a name="to-start-or-stop-a-specific-service"></a>So starten oder beenden Sie einen bestimmten Dienst

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **Dienst starten** bzw. auf **Dienst beenden**.
9. Klicken Sie auf **Schließen**.
    
## <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste
<a name="prevent_session"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um neue Sitzungen für alle Skype for Business Server-Dienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Skype for Business Server-Dienst zu verhindern.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>So verhindern Sie neue Sitzungen für alle Skype for Business-Dienste auf einem Computer

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder durchsuchen Sie auf der Seite **Status** die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>So verhindern Sie neue Sitzungen für einen bestimmten Dienst

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer. 
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.
9. Klicken Sie auf **Schließen**.
    

