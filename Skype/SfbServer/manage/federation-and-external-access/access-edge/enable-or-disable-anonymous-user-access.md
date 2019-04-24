---
title: Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a68790f870a6c62b513caab559580695763cd4df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199948"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Aktivieren Sie oder deaktivieren Sie den anonymen Benutzerzugriff in Skype für Business Server

Anonyme Benutzer sind Benutzer, die ein Benutzerkonto in Ihrer Organisation Active Directory Domain Services oder in einer unterstützten verbunddomäne nicht haben, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können. Durch anonyme Teilnahme an Besprechungen zulassen aktivieren Sie anonyme Benutzern (d. h., Benutzer, deren Identität wird über die Besprechung oder Konferenz-Taste nur überprüft) an Besprechungen teilnehmen. Zulassen der anonymen Teilnahme erfordert es für Ihre Organisation zu aktivieren.

Wenn Sie später vorübergehend oder endgültig Zugriff durch anonyme Benutzer zu verhindern möchten, können Sie es für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt zum Aktivieren oder Deaktivieren des anonymen Zugriffs für Ihre Organisation.

> [!NOTE]  
> Durch Aktivieren des anonymen Zugriffs für Ihre Organisation werden Sie nur angeben, dass Servern mit Zugriffs-edgediensts Zugriff durch anonyme Benutzer zu unterstützen. Anonyme Benutzer können nicht an alle Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine konferenzrichtlinie konfigurieren und einen oder mehrere Benutzer oder Benutzergruppen zuweisen. Nur Benutzer, die anonyme Benutzer zu Besprechungen einladen können sind Benutzer, die eine konferenzrichtlinie zugeordnet sind, die Unterstützung für anonyme Benutzer konfiguriert ist. Ausführliche Informationen zum Konfigurieren von konferenzrichtlinien zur Unterstützung der anonyme Benutzer einladen finden Sie unter [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>So aktivieren oder Deaktivieren des anonymen Zugriffs für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**und klicken Sie dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in der **Konfiguration für Zugriffsedge bearbeiten**eine der folgenden Aktionen aus:
    
      - Um Anonymer Benutzerzugriff für Ihre Organisation zu aktivieren, aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** .
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um Anonymer Benutzerzugriff für Ihre Organisation zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Zugriff anonymer Benutzer mithilfe von Windows PowerShell-cmdlets

Sie können mithilfe von Windows PowerShell und das **Set-CsAccessEdgeConfiguration** -Cmdlet Zugriff anonymer Benutzer verwalten. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. 

## <a name="to-enable-anonymous-user-access"></a>So aktivieren Sie den anonymen Benutzerzugriff

  - Zum Aktivieren des Benutzerzugriffs für anonyme legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf "true" ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>So deaktivieren Sie den anonymen Benutzerzugriff

  - Um Zugriff anonymer Benutzer deaktivieren möchten, legen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf "false" ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Siehe auch

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
