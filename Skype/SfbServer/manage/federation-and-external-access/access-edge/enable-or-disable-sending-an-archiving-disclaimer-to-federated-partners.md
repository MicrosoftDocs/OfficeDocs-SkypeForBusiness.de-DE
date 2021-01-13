---
title: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
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
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817355"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des Sendens eines Archivierungsausschlusses an Verbundpartner in Skype for Business Server

Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver bereitgestellt und den Partnerverbund für Ihre Organisation aktiviert haben, sollten Sie angegeben haben, ob der Archivierungsausschluss automatisch an Verbundpartner gesendet werden soll. Wenn Sie die externe Kommunikation archivieren, sollten Sie das Senden eines Archivierungsausschlusses aktivieren. Verwenden Sie das Verfahren in diesem Thema, um diese Konfiguration zu ändern.

> [!NOTE]
> Im folgenden Verfahren wird vorausgesetzt, dass Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Weitere Informationen zum Aktivieren des Verbunds finden Sie unter ["Aktivieren oder Deaktivieren des Remotebenutzerzugriffs".](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>So aktivieren oder deaktivieren Sie das Senden eines Archivierungsausschlusses an Verbundpartner

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie **auf der Registerkarte "Konfiguration von Zugriffs-Edge"** **auf "Global",** dann auf **"Bearbeiten"** und dann auf **"Details anzeigen".**

5.  Aktivieren oder deaktivieren Sie in "Zugriffs-Edgekonfiguration bearbeiten"  unter "Kommunikation mit Partnerbenutzern aktivieren" das Kontrollkästchen "Archivierungsausschluss an Verbundpartner senden", um das automatische Senden des Archivierungsausschlusses zu aktivieren oder zu deaktivieren. 

6.  Klicken Sie auf **Commit ausführen**.

Damit Verbundbenutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Zugriff durch Partnerbenutzer zu unterstützen. Weitere Informationen zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter ["Konfigurieren der Unterstützung für zulässige externe Domänen".](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Archivierungsausschlusses mithilfe Windows PowerShell Cmdlets

Die Verwendung des Archivierungsausschlusses kann mithilfe von Windows PowerShell und dem Set-CsAccessEdgeConfiguration verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>So aktivieren Sie den Archivierungsausschluss

  - Um den Archivierungsausschluss zu aktivieren, legen Sie den Wert der **Eigenschaft "EnableArchivingDisclaimer"** auf "True" ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>So deaktivieren Sie den Archivierungsausschluss

  - Um den Archivierungsausschluss zu deaktivieren, legen Sie den Wert der **Eigenschaft "EnableArchivingDisclaimer"** auf "False" ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


