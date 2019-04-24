---
title: Verwalten von Diensten für Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: In diesem Artikel wird beschrieben, wie zum Verwalten von Diensten in einer Skype für Business Server-Topologie ausgeführt.
ms.openlocfilehash: 4f5e1c4d91d5412470edebf3ed8d320101153da1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225328"
---
# <a name="manage-services-for-skype-for-business-server"></a>Verwalten von Diensten für Skype für Business Server

In diesem Artikel wird beschrieben, wie zum Verwalten von Diensten in einer Skype für Business Server-Topologie ausgeführt.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Anzeigen einer Liste von Computern mit Skype für Business Server
<a name="view_list"> </a>

Sie können Skype Business Server-Systemsteuerung verwenden, um eine Liste aller Computer anzuzeigen, die Skype für Business Server in der Topologie ausgeführt werden und den Status der einzelnen. Sie können die Liste nach Computer, Pool oder Website zu sortieren. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Zum Anzeigen einer Liste von Skype-Computern für Business Server

1. Melden Sie sich bei einem Benutzerkonto, das eine der vordefinierten Administratorrollen für Skype für Business Server zugeordnet ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. Ausführliche Informationen zu den vordefinierten Administratorrollen in Skype für Business Server verfügbar sind finden Sie unter **Planning for Role-Based Access Control**.   
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.   
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Status**.   
4. Führen Sie einen der Bedarf die folgenden Schritte aus, auf der Seite **Status** :
   - Sortieren Sie die Liste, indem Sie auf die **Computer**, **Pool**oder **Standort** Spaltenüberschrift, und klicken Sie dann auf den Pfeil nach oben oder den Pfeil nach unten. 
   - Klicken Sie auf **Aktualisieren** , um die aktuelle Liste anzuzeigen.  
   - Suchen Sie nach einem bestimmten Computer durch den Namen des Computers im Suchfeld eingeben.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Anzeigen des Status der Dienste auf einen Skype für Business server
<a name="view-status"> </a>

Sie können Skype Business Server-Systemsteuerung verwenden, um alle Dienste anzuzeigen, die auf einem bestimmten Computer in Ihrer Skype für Business Server-Topologie ausgeführt werden und den Status der einzelnen Dienste.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Anzeigen des Status von Diensten auf einem Computer ausgeführt

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie**. 
4. Sortieren Sie auf der Seite **Status** oder Durchsuchen Sie die Liste, je nach Bedarf auf den Computer zu suchen, dem Sie, interessiert sind, und klicken Sie dann auf den Namen des Computers.
5. Führen Sie einen der folgenden Schritte aus:
   - Um den aktuellen Status der Dienste auf dem Computer anzuzeigen, klicken Sie auf **Dienststatus abrufen**.
   - Um herauszufinden, eine Liste bestimmter Dienste, die den Status der einzelnen Dienste auf dem Computer ausgeführt wird, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf **Schließen** um zur Liste zurückzukehren.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Anzeigen des Dienststatus mit Windows Powershell-cmdlets

Sie können auch Dienststatus mithilfe von Windows PowerShell und das Cmdlet **Get-CsWindowsService** anzeigen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.
  
### <a name="to-view-service-status"></a>Zum Anzeigen des Dienststatus

Zum Anzeigen des Dienststatus auf einem Computer Geben Sie einen Befehl ähnlich dem folgenden in der Skype für Business Server-Verwaltungsshell, und drücken Sie dann die EINGABETASTE:
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
  
|**RoleName**|**Status**|
|:-----|:-----|
|{W3SVC}  <br/> |Ausgeführte  <br/> |
|{CentralManagement}  <br/> | Ausgeführte <br/> |
|{ClsAgent}  <br/> |Ausgeführte  <br/> |
|{Registrierung UserServer, EdgeServer}  <br/> |Ausgeführte  <br/> |
|{ApplicationServer}  <br/> |Ausgeführte  <br/> |
|{ConferencingServer}  <br/> |Ausgeführte  <br/> |
|{MediationServer}  <br/> |Ausgeführte  <br/> |
   
Weitere Informationen hierzu finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Anzeigen von Details zu einem Dienst
<a name="view_details"> </a>

Skype für Business Server-Systemsteuerung können Sie Details zu einzelnen Dienste anzeigen, die auf einem bestimmten Computer in Ihrer Topologie ausgeführt wird. Sie können den Status der einzelnen Service und Details wie etwa die zugehörigen Datenbanken sowie die Ports und die abhängigen Dienste anzeigen.
  
### <a name="to-view-details-for-a-service"></a>So zeigen Sie Details zu einem Dienst an

1. Melden Sie sich bei einem Benutzerkonto, das eine der vordefinierten Administratorrollen für Skype für Business Server zugeordnet ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. Ausführliche Informationen zu den vordefinierten Administratorrollen in Skype für Business Server verfügbar sind finden Sie unter **Planning for Role-Based Access Control**.
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Status**.
4. Auf der Seite **Status** sortieren oder Durchsuchen Sie die Liste, und klicken Sie dann auf dem Computer, die Sie anzeigen möchten.
5. Klicken Sie auf **Eigenschaften**.
6. Klicken Sie im Fenster **Anzeigen von Computerdetails** sortieren Sie die Liste der Dienste, bei Bedarf, und klicken Sie auf den Dienst, den Sie anzeigen möchten.
7. Eine der Bedarf die folgenden Aktionen aus:
   - Um den aktuellen Status von diesem Dienst anzuzeigen, klicken Sie auf **Dienststatus abrufen**.
   - Um die Details zu diesem Dienst anzuzeigen, klicken Sie auf **Eigenschaften** , und klicken Sie dann auf **Schließen**.
   - Klicken Sie auf **Schließen**, um zur Liste aller Computer in Ihrer Topologie zurückzukehren.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Starten oder Beenden von Skype für Business Server-Dienste
<a name="StartStop"> </a>

Skype für Business Server-Systemsteuerung können so starten oder Beenden alle Skype für Business Server-Dienste auf einem bestimmten Computer ausgeführt oder auf einen bestimmten Dienst gestartet oder beendet.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>So starten oder Beenden alle Skype für BusinessServices auf einem computer

1. Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist . Sie können bestimmen, ob Sie die CsServerAdministrator oder CsAdministrator RBAC-Rolle zugewiesen wurden durch einen Befehl ähnlich dem folgenden ausführen:
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Status**.
4. Sie möchten starten oder beenden, und klicken Sie dann auf, auf der **Statusseite** , sortieren oder Durchsuchen der Liste nach Bedarf zum Computer, auf der die Dienste ausgeführt wird.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **Start, alle Dienste** oder **Beenden Sie alle Dienste**.
    
### <a name="to-start-or-stop-a-specific-service"></a>So starten oder Beenden einen bestimmten Dienst

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Status**.
4. Sie möchten starten oder beenden, und klicken Sie dann auf, auf der Seite **Status** , sortieren oder Durchsuchen der Liste nach Bedarf an den Computer zu suchen, der der Dienst ausgeführt wird.
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie die Liste der Dienste, bei Bedarf, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **Dienst starten** oder **Beenden**.
9. Klicken Sie auf **Schließen**.
    
## <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste
<a name="prevent_session"> </a>

Sie können Skype Business Server-Systemsteuerung, neue Sitzungen für alle Skype für Business Server-Dienste auf einem bestimmten Computer ausgeführt zu verhindern oder um neue Sitzungen für einen bestimmten Skype für Business Server-Dienst zu verhindern.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Um zu verhindern, dass neue Sitzungen für alle Skype für Business Services auf einem computer

1. Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Status**.
4. Erforderlich, auf der Seite **Status** sortieren oder Durchsuchen der Liste als zum Computer mit der die Dienste zu verhindern, dass neue Sitzungen, und klicken Sie dann auf es werden soll.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **neue Sitzungen für alle Dienste verhindern**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>So verhindern Sie neue Sitzungen für einen bestimmten Dienst

1. Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Status**.
4. Sie möchten starten oder beenden, und klicken Sie dann auf, auf der Seite **Status** , sortieren oder Durchsuchen der Liste nach Bedarf an den Computer zu suchen, der der Dienst ausgeführt wird. 
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie die Liste der Dienste, bei Bedarf, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **neue Sitzungen für Dienst verhindern**.
9. Klicken Sie auf **Schließen**.
    

