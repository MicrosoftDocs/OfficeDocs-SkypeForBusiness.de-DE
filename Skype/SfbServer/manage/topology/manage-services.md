---
title: Verwalten von Diensten in Skype for Business Server
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
description: Erfahren Sie, wie Sie den Dienststatus anzeigen, Dienste starten und beenden und Sitzungen für Dienste verhindern.
ms.openlocfilehash: 6071526febcd3a4c1cb925ae3fb704eca6db575c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826315"
---
# <a name="manage-services-in-skype-for-business-server"></a>Verwalten von Diensten in Skype for Business Server

Mithilfe der Skype for Business Server-Systemsteuerung können Sie eine Liste aller Computer anzeigen, auf denen Skype for Business Server in Ihrer Topologie ausgeführt wird, den Status der Dienste anzeigen, Dienste starten oder beenden und Sitzungen für Dienste verhindern.

- [Anzeigen einer Liste der Computer, auf denen Skype for Business Server ausgeführt wird](#view-a-list-of-computers-running-skype-for-business-server)
- [Anzeigen des Status von Diensten, die auf einem Computer in Skype for Business ausgeführt werden](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Starten oder Beenden von Skype for Business-Diensten](#start-or-stop-skype-for-business-services)
- [Verhindern von Sitzungen für Dienste](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Anzeigen einer Liste der Computer, auf denen Skype for Business Server ausgeführt wird

Verwenden Sie die Skype for Business Server-Systemsteuerung, um eine Liste aller Computer, auf denen Skype for Business in Ihrer Topologie ausgeführt wird, und den Jeweiligen Dienststatus anzeigen zu können. Sie können die Liste nach Computer, Pool oder Standort sortieren. 

1. Melden Sie sich über ein Benutzerkonto, das einer der vordefinierten Administratorrollen für Skype for Business Server zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an. Weitere Informationen finden Sie unter [Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server.](../../plan-your-deployment/security/role-based-access-control-rbac.md)
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter "Installieren und Öffnen [von Verwaltungstools".](../../management-tools/install-and-open-administrative-tools.md)
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Gehen Sie auf der Seite "Status" nach Bedarf wie folgt vor:
    - Sortieren Sie die Liste, indem Sie auf die Spaltenüberschrift **Computer**, **Pool** oder **Standort** und anschließend auf den Aufwärts- oder Abwärtspfeil klicken.
    - Klicken Sie auf **Aktualisieren**, um die aktuelle Liste anzuzeigen.
    - Suchen Sie nach einem bestimmten Computer, indem Sie den Computernamen im Suchfeld eingeben.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Anzeigen des Status von Diensten, die auf einem Computer in Skype for Business ausgeführt werden

Verwenden Sie die Skype for Business Server-Systemsteuerung, um alle Dienste, die auf einem bestimmten Computer in Ihrer Skype for Business Server-Topologie ausgeführt werden, und den Status der einzelnen Dienste zu sehen.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter "Installieren und Öffnen [von Verwaltungstools".](../../management-tools/install-and-open-administrative-tools.md)
3. Klicken Sie auf der linken Navigationsleiste auf **Topologie**.
4. Sortieren oder durchsuchen Sie auf der Statusseite die Liste nach Bedarf, um den gewünschten Computer zu finden, und klicken Sie dann auf den Computernamen.
5. Gehen Sie wie folgt vor:
    - Klicken Sie auf Dienststatus erhalten, um den neuesten Status der auf dem Computer **ausgeführten Dienste zu sehen.**
    - Wenn Sie eine Liste der auf dem Computer ausgeführten Dienste und den  Status der einzelnen Dienste anzeigen möchten, klicken Sie auf "Eigenschaften" **und** dann auf "Schließen", um zur Liste zurückzukehren.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Anzeigen des Dienststatus mithilfe Windows PowerShell Cmdlets

Sie können den Dienststatus auch mit Windows PowerShell und dem Get-CsWindowsService anzeigen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. Weitere Informationen finden Sie unter [Skype for Business Server Management Shell](../management-shell.md).

**So zeigen Sie den Dienststatus an**

Geben Sie zum Anzeigen des Dienststatus auf einem Computer einen Befehl wie den folgenden in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Es werden etwa folgende Informationen zurückgegeben:

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

Weitere Informationen finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Starten oder Beenden von Skype for Business-Diensten

Verwenden Sie die Skype for Business Server-Systemsteuerung, um alle Skype for Business Server-Dienste zu starten oder zu beenden, die auf einem bestimmten Computer ausgeführt werden, oder um einen bestimmten Dienst zu starten oder zu beenden.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Starten oder Beenden aller Skype for Business Server-Dienste auf einem Computer

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. Sie können ermitteln, ob Ihnen die Rollen "CsServerAdministrator" oder "CsAdministrator RBAC" zugewiesen wurde, indem Sie einen Befehl wie den folgenden ausführen:

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter "Installieren und Öffnen [von Verwaltungstools".](../../management-tools/install-and-open-administrative-tools.md)
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder durchsuchen Sie die Liste auf der Seite Status, und ermitteln Sie so den Computer, auf dem die Dienste ausgeführt werden, die Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **Alle Dienste starten** bzw. auf **Alle Dienste beenden**.

### <a name="start-or-stop-a-specific-service"></a>Starten oder Beenden eines bestimmten Diensts

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter "Installieren und Öffnen [von Verwaltungstools".](../../management-tools/install-and-open-administrative-tools.md)
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder durchsuchen Sie die Liste auf der Seite Status, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **Dienst starten** bzw. auf **Dienst beenden**.
9. Klicken Sie auf **Schließen**.


## <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste

Verwenden Sie die Skype for Business-Systemsteuerung, um neue Sitzungen für alle Skype for Business Server-Dienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Dienst zu verhindern.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Verhindern neuer Sitzungen für alle Skype for Business Server-Dienste auf einem Computer

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter "Installieren und Öffnen [von Verwaltungstools".](../../management-tools/install-and-open-administrative-tools.md)
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Sortieren oder durchsuchen Sie auf der Seite Status die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Verhindern neuer Sitzungen für einen bestimmten Dienst

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Server-Systemsteuerung verwenden können, finden Sie unter "Installieren und Öffnen [von Verwaltungstools".](../../management-tools/install-and-open-administrative-tools.md)
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
4. Klicken Sie auf **Eigenschaften**.
5. Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.
6. Klicken Sie auf **Aktion**.
7. Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.
8. Klicken Sie auf **Schließen**.
