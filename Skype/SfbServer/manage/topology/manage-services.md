---
title: Verwalten von Diensten in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informationen Sie zum Anzeigen des Dienststatus, starten und Beenden von Diensten und verhindern von Sitzungen für Dienste.
ms.openlocfilehash: 78d8b2a16204585a0ff403867617ff709666c4f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911966"
---
# <a name="manage-services-in-skype-for-business-server"></a>Verwalten von Diensten in Skype für Business Server

Sie können die Skype Business Server-Systemsteuerung zum Anzeigen einer Liste aller Computer, auf dem Skype für Business Server in der Topologie ausgeführt werden, Anzeigen des Status der Dienste, starten oder Beenden von Diensten und verhindern von Sitzungen für Dienste verwenden.

- [Anzeigen einer Liste von Computern mit Skype für Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Anzeigen des Status der Dienste, die auf einem Computer in Skype für Unternehmen ausgeführt werden.](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Starten oder Beenden von Skype für Unternehmensdienste](#start-or-stop-skype-for-business-services)
- [Verhindern von Sitzungen für Dienste](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Anzeigen einer Liste von Computern mit Skype für Business Server

Verwenden Sie die Skype Business Server-Systemsteuerung, um eine Liste aller Computer anzuzeigen, die in Ihrer Topologie Skype für Unternehmen ausgeführt werden und den Status der einzelnen. Sie können die Liste nach Computer, Pool oder Website zu sortieren. 

1. Melden Sie sich bei einem Benutzerkonto, das eine der vordefinierten Administratorrollen für Skype für Business Server zugeordnet ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. Weitere Informationen finden Sie unter [Role-based Access Control (RBAC) Skype für Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 
4. Führen Sie auf der Seite Status eine der folgenden Bedarf:
    - Sortieren Sie die Liste, indem Sie auf die **Computer**, **Pool**oder **Standort** Spaltenüberschrift, und klicken Sie dann auf den Pfeil nach oben oder den Pfeil nach unten.
    - Klicken Sie auf **Aktualisieren** , um die aktuelle Liste anzuzeigen.
    - Suchen Sie nach einem bestimmten Computer durch den Namen des Computers im Suchfeld eingeben.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Anzeigen des Status der Dienste, die auf einem Computer in Skype für Unternehmen ausgeführt werden.

Verwenden Sie die Skype Business Server-Systemsteuerung, um alle Dienste anzuzeigen, die auf einem bestimmten Computer in Ihrer Skype für Business Server-Topologie ausgeführt werden und den Status der einzelnen Dienste.

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie**.
4. Sortieren Sie auf der Seite Status oder Durchsuchen Sie die Liste, je nach Bedarf auf den Computer zu suchen, dem Sie, interessiert sind, und klicken Sie dann auf den Namen des Computers.
5. Führen Sie eine der folgenden Aktionen aus:
    - Um den aktuellen Status der Dienste auf dem Computer anzuzeigen, klicken Sie auf **Dienststatus abrufen**.
    - Um herauszufinden, eine Liste bestimmter Dienste, die den Status der einzelnen Dienste auf dem Computer ausgeführt wird, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf **Schließen** um zur Liste zurückzukehren.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Anzeigen des Dienststatus mithilfe von Windows PowerShell-Cmdlets

Sie können auch Dienststatus mithilfe von Windows PowerShell und das Cmdlet Get-CsWindowsService anzeigen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung. Weitere Informationen finden Sie unter [Skype für Business Server-Verwaltungsshell](../management-shell.md).

**Zum Anzeigen des Dienststatus**

Anzeigen des Dienststatus auf einem Computer, geben Sie einen Befehl ähnlich dem folgenden in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:

```
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

Weitere Informationen hierzu finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Starten oder Beenden von Skype für Unternehmensdienste

Mithilfe der Skype Business Server-Systemsteuerung zum Starten oder Beenden alle Skype für Business Server-Dienste auf einem bestimmten Computer ausgeführt oder einen bestimmten Dienst gestartet oder beendet.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Starten Sie oder beenden Sie alle Skype für Business Server-Dienste auf einem computer

1. Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist . Sie können bestimmen, ob Sie die CsServerAdministrator oder CsAdministrator RBAC-Rolle zugewiesen wurden durch einen Befehl ähnlich dem folgenden ausführen:

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 
4. Sie möchten starten oder beenden, und klicken Sie dann auf, auf der Seite Status, sortieren oder Durchsuchen der Liste nach Bedarf zum Computer, auf der die Dienste ausgeführt wird.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **Start, alle Dienste** oder **Beenden Sie alle Dienste**.

### <a name="start-or-stop-a-specific-service"></a>Starten Sie oder beenden Sie einen bestimmten Dienst

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 
4. Sie möchten starten oder beenden, und klicken Sie dann auf, auf der Seite Status, sortieren oder Durchsuchen der Liste nach Bedarf an den Computer zu suchen, der der Dienst ausgeführt wird.
5. Klicken Sie auf **Eigenschaften**.
6. Sortieren Sie die Liste der Dienste, bei Bedarf, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.
7. Klicken Sie auf **Aktion**.
8. Klicken Sie auf **Dienst starten** oder **Beenden**.
9. Klicken Sie auf **Schließen**.


## <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste

Verwenden Sie die Skype für die Business-Systemsteuerung, um zu verhindern, dass neue Sitzungen für alle Skype für Business Server-Dienste auf einem bestimmten Computer ausgeführt oder um neue Sitzungen für einen bestimmten Dienst zu verhindern.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Verhindern, dass neue Sitzungen für alle Skype für Business Server-Dienste auf einem computer

1. Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Status**.
4. Erforderlich, auf der Seite Status sortieren oder Durchsuchen der Liste als zum Computer mit der die Dienste zu verhindern, dass neue Sitzungen, und klicken Sie dann auf es werden soll.
5. Klicken Sie auf **Aktion**.
6. Klicken Sie auf **neue Sitzungen für alle Dienste verhindern**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Verhindern, dass neue Sitzungen für einen bestimmten Dienst

1. Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype Business Server-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 
4. Klicken Sie auf **Eigenschaften**.
5. Sortieren Sie die Liste der Dienste, bei Bedarf, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.
6. Klicken Sie auf **Aktion**.
7. Klicken Sie auf **neue Sitzungen für Dienst verhindern**.
8. Klicken Sie auf **Schließen**.
