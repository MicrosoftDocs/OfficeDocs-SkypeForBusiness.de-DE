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
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280271"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des anonymen Benutzerzugriffs in Skype for Business Server

Anonyme Benutzer sind Benutzer, die nicht über ein Benutzerkonto in den Active Directory-Domänendiensten Ihrer Organisation oder in einer unterstützten Föderationsdomäne verfügen, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können. Durch das zulassen anonymer Teilnahme an Besprechungen können Sie anonyme Benutzer (also Benutzer, deren Identität nur über den Besprechungs-oder Konferenzschlüssel überprüft wird) aktivieren, um an Besprechungen teilzunehmen. Das Zulassen einer anonymen Teilnahme erfordert die Aktivierung für Ihre Organisation.

Wenn Sie den Zugriff von anonymen Benutzern später vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.

> [!NOTE]  
> Indem Sie den anonymen Benutzer Zugriff für Ihre Organisation aktivieren, geben Sie nur an, dass die Server, auf denen der Access Edge-Dienst ausgeführt wird, den Zugriff durch anonyme Benutzer unterstützen. Anonyme Benutzer können erst dann an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine konferenzrichtlinie konfiguriert und auf einen oder mehrere Benutzer oder Benutzergruppen anwenden. Die einzigen Benutzer, die anonyme Benutzer zu Besprechungen einladen können, sind diejenigen Benutzer, denen eine konferenzrichtlinie zugewiesen ist, die für die Unterstützung anonymer Benutzer konfiguriert ist. Details zum Konfigurieren von Konferenzrichtlinien zur Unterstützung der Einladung anonymer Benutzer finden Sie unter [Verwalten von Konferenzrichtlinien](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den anonymen Benutzer Zugriff für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Access-Edge-Konfiguration**.

4.  Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren.
    
      - Wenn Sie den anonymen Benutzer Zugriff für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** .

6.  Klicken Sie auf **Commit ausführen**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Zugriffs auf anonyme Benutzer mithilfe von Windows PowerShell-Cmdlets

Sie können den anonymen Benutzer Zugriff mithilfe von Windows PowerShell und dem Cmdlet " **Satz-csaccessedgeconfiguration nicht angeben** " verwalten. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. 

## <a name="to-enable-anonymous-user-access"></a>So aktivieren Sie den anonymen Benutzer Zugriff

  - Um den anonymen Benutzer Zugriff zu aktivieren, setzen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf true ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>So deaktivieren Sie den anonymen Benutzer Zugriff

  - Um den anonymen Benutzer Zugriff zu deaktivieren, setzen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf false ($false):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Siehe auch

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
