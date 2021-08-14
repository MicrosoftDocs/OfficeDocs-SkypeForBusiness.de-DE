---
title: Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: So aktivieren und deaktivieren Sie anonymen Benutzerzugriff in Skype for Business Server.
ms.openlocfilehash: 4f7fb11e7b168922a4027e75703c164638dd1f2d
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234390"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer in Skype for Business Server

Anonyme Benutzer sind Benutzer, die kein Benutzerkonto in den Active Directory-Domänendiensten Ihrer Organisation oder in einer unterstützten Verbunddomäne haben, aber zur Remoteteilnahme an einer lokalen Konferenz eingeladen werden können. Indem Sie die anonyme Teilnahme an Besprechungen zulassen, können anonyme Benutzer (d. h. Benutzer, deren Identität nur über den Besprechungs- oder Konferenzschlüssel überprüft wird) an Besprechungen teilnehmen. Um anonyme Teilnahme zuzulassen, muss sie für Ihre Organisation aktiviert werden.

Wenn Sie später den Zugriff durch anonyme Benutzer vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um anonymen Benutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.

> [!NOTE]  
> Indem Sie anonymen Benutzerzugriff für Ihre Organisation aktivieren, geben Sie nur an, dass Ihre Server, auf denen der Zugriffs-Edgedienst ausgeführt wird, den Zugriff durch anonyme Benutzer unterstützen. Anonyme Benutzer können erst an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Konferenzrichtlinie konfigurieren und sie auf einen oder mehrere Benutzer oder Benutzergruppen anwenden. Die einzigen Benutzer, die anonyme Benutzer zu Besprechungen einladen können, sind die Benutzer, denen eine Konferenzrichtlinie zugewiesen ist, die für die Unterstützung anonymer Benutzer konfiguriert ist. Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien zur Unterstützung der Einladung anonymer Benutzer finden Sie unter [Verwalten von Konferenzrichtlinien.](../../conferencing/conferencing-policies.md)

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie anonymen Benutzerzugriff für Ihre Organisation

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie zum Aktivieren des anonymen Benutzerzugriffs für Ihre Organisation das Kontrollkästchen **"Kommunikation mit anonymen Benutzern aktivieren".**
    
      - Deaktivieren Sie das Kontrollkästchen **"Kommunikation mit anonymen Benutzern aktivieren",** um den anonymen Benutzerzugriff für Ihre Organisation zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des anonymen Benutzerzugriffs mithilfe Windows PowerShell Cmdlets

Sie können den anonymen Benutzerzugriff mithilfe von Windows PowerShell und dem Cmdlet **"Set-CsAccessEdgeConfiguration"** verwalten. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. 

## <a name="to-enable-anonymous-user-access"></a>So aktivieren Sie anonymen Benutzerzugriff

  - Um anonymen Benutzerzugriff zu aktivieren, legen Sie den Wert der **AllowAnonymousUsers-Eigenschaft** auf "True" ($True) fest:<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>So deaktivieren Sie anonymen Benutzerzugriff

  - Um den anonymen Benutzerzugriff zu deaktivieren, legen Sie den Wert der **AllowAnonymousUsers-Eigenschaft** auf False ($False) fest:<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Siehe auch

[Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy)  
