---
title: Verwalten von Diensten in Skype for Business Server
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
description: Hier erfahren Sie, wie Sie den Dienststatus anzeigen, Dienste starten und beenden sowie Sitzungen für Dienste verhindern.
ms.openlocfilehash: 154c7b2d5ff858e22be4159ec1797ef6a6724445
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817116"
---
# <a name="manage-services-in-skype-for-business-server"></a>Verwalten von Diensten in Skype for Business Server

Sie können die Skype for Business Server-Systemsteuerung verwenden, um eine Liste aller Computer anzuzeigen, die Skype for Business Server in Ihrer Topologie ausführen, den Status der Dienste anzeigen, Dienste starten oder beenden sowie Sitzungen für Dienste verhindern.

- [Anzeigen einer Liste mit Computern, auf denen Skype for Business Server ausgeführt wird](#view-a-list-of-computers-running-skype-for-business-server)
- [Anzeigen des Status der auf einem Computer ausgeführten Dienste in Skype for Business](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Starten oder Beenden von Skype for Business-Diensten](#start-or-stop-skype-for-business-services)
- [Verhindern von Sitzungen für Dienste](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Anzeigen einer Liste mit Computern, auf denen Skype for Business Server ausgeführt wird

Verwenden Sie das Skype for Business Server Control Panel, um eine Liste aller Computer anzuzeigen, auf denen Skype for Business in Ihrer Topologie ausgeführt wird, und den jeweiligen Dienststatus anzuzeigen. Sie können die Liste nach Computer, Pool oder Website sortieren. 

1. Melden Sie sich bei einem Benutzerkonto, das einer der vordefinierten Administratorrollen für Skype for Business Server zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an. Weitere Informationen finden Sie unter [rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) für Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 
4. Führen Sie auf der Status Seite nach Bedarf eine der folgenden Aktionen aus:
    - Sortieren Sie die Liste, indem Sie auf die Überschrift **Computer**, **Pool**oder **Website** Spalte und dann auf den nach oben oder den nach unten weisenden Pfeil klicken.
    - Klicken Sie auf **Aktualisieren** , um die aktuelle Liste anzuzeigen.
    - Suchen Sie nach einem bestimmten Computer, indem Sie den Computernamen in das Suchfeld eingeben.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Anzeigen des Status der auf einem Computer ausgeführten Dienste in Skype for Business

Verwenden Sie die Skype for Business Server-Systemsteuerung, um alle Dienste anzuzeigen, die auf einem bestimmten Computer in Ihrer Skype for Business Server-Topologie ausgeführt werden, und den Status jedes Diensts anzuzeigen.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie**.
4. Sortieren oder Durchsuchen Sie auf der Status Seite die Liste nach Bedarf, um den Computer zu finden, an dem Sie interessiert sind, und klicken Sie dann auf den Computernamen.
5. Führen Sie eine der folgenden Aktionen aus:
    - Wenn Sie den aktuellen Status der auf dem Computer ausgeführten Dienste anzeigen möchten, klicken Sie auf **Dienststatus abrufen**.
    - Wenn Sie eine Liste der auf dem Computer ausgeführten Dienste und den Status jedes Diensts anzeigen möchten, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf **Schließen** , um zur Liste zurückzukehren.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Anzeigen des Dienststatus mithilfe von Windows PowerShell-Cmdlets

Sie können den Dienststatus auch mithilfe von Windows PowerShell und dem Cmdlet Get-CsWindowsService anzeigen. Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Weitere Informationen finden Sie unter [Skype for Business Server-Verwaltungsshell](../management-shell.md).

**So zeigen Sie den Dienststatus an**

Wenn Sie den Dienststatus auf einem Computer anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell einen Befehl ähnlich der folgenden ein, und drücken Sie dann die EINGABETASTE:

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

Ausführliche Informationen finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Starten oder Beenden von Skype for Business-Diensten

Verwenden Sie das Skype for Business Server Control Panel, um alle Skype for Business Server-Dienste zu starten oder zu beenden, die auf einem bestimmten Computer ausgeführt werden, oder um einen bestimmten Dienst zu starten oder zu beenden.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Starten oder Beenden aller Skype for Business Server-Dienste auf einem Computer

1. Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. . Sie können feststellen, ob Ihnen die CsServerAdministrator-oder CsAdministrator-RBAC-Rolle zugewiesen wurde, indem Sie einen Befehl wie den folgenden ausführen:

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 
4. Sortieren oder Durchsuchen Sie auf der Status Seite die Liste nach Bedarf, um den Computer zu finden, auf dem die Dienste ausgeführt werden, die Sie starten oder beenden möchten, und klicken Sie darauf.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **alle Dienste starten** oder **alle Dienste beenden**.

### <a name="start-or-stop-a-specific-service"></a>Starten oder Beenden eines bestimmten Diensts

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 
4. Sortieren oder Durchsuchen Sie auf der Status Seite die Liste nach Bedarf, um den Computer zu finden, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten, und klicken Sie darauf.
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **Dienst starten** oder **Dienst beenden**.
9. Klicken Sie auf **Schließen**.


## <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste

Verwenden Sie das Skype Control Panel für Unternehmen, um neue Sitzungen für alle Skype for Business Server-Dienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Dienst zu verhindern.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Verhindern neuer Sitzungen für alle Skype for Business Server-Dienste auf einem Computer

1. Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder Durchsuchen Sie auf der Status Seite die Liste nach Bedarf, um den Computer zu finden, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten, und klicken Sie darauf.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **neue Sitzungen für alle Dienste verhindern**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Verhindern neuer Sitzungen für einen bestimmten Dienst

1. Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 
4. Klicken Sie auf **Eigenschaften**.
5. Sortieren Sie die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.
6. Klicken Sie auf **Aktion**.
7. Klicken Sie auf **neue Sitzungen für Dienst verhindern**.
8. Klicken Sie auf **Schließen**.
