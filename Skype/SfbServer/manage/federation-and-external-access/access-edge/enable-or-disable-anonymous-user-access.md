---
title: Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: cc0d779e2728fd2a82547b52bda57c05c7a983a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006000"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des Zugriffs anonymer Benutzer in Skype for Business Server

Anonyme Benutzer sind Benutzer, die nicht über ein Benutzerkonto in der Active Directory-Domänendienste Ihrer Organisation oder in einer unterstützten Verbunddomäne verfügen, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können. Durch das Zulassen der anonymen Teilnahme an Besprechungen aktivieren Sie anonyme Benutzer (also Benutzer, deren Identität nur über den Besprechungs-oder Konferenzschlüssel überprüft wird), um an Besprechungen teilzunehmen. Das Zulassen der anonymen Teilnahme erfordert die Aktivierung für Ihre Organisation.

Wenn Sie den Zugriff durch anonyme Benutzer später vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.

> [!NOTE]  
> Indem Sie den anonymen Benutzer Zugriff für Ihre Organisation aktivieren, geben Sie nur an, dass Ihre Server mit dem Zugriffs-Edgedienst den Zugriff durch anonyme Benutzer unterstützen. Anonyme Benutzer können nur dann an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine konferenzrichtlinie konfiguriert haben und diese auf einen oder mehrere Benutzer oder Benutzergruppen anwenden. Die einzigen Benutzer, die anonyme Benutzer zu Besprechungen einladen können, sind die Benutzer, denen eine konferenzrichtlinie zugewiesen ist, die für die Unterstützung anonymer Benutzer konfiguriert ist. Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien zur Unterstützung der Einladung anonymer Benutzer finden Sie unter [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den anonymen Benutzer Zugriff für Ihre Organisation

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer mithilfe von Windows PowerShell-Cmdlets

Sie können den anonymen Benutzer Zugriff mit Windows PowerShell und dem Cmdlet " **csaccessedgeconfiguration nicht angeben** " verwalten. Sie können dieses Cmdlet entweder über die Skype for Business Server Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. 

## <a name="to-enable-anonymous-user-access"></a>So aktivieren Sie den anonymen Benutzer Zugriff

  - Zum Aktivieren des Zugriffs durch anonyme Benutzer legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf true ($true) fest:
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>So deaktivieren Sie den anonymen Benutzer Zugriff

  - Wenn Sie den anonymen Benutzer Zugriff deaktivieren möchten, legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf false ($false) fest:
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Siehe auch

[Gruppe-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
