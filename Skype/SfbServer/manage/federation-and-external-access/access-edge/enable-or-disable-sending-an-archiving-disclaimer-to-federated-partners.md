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
description: Aktivieren oder deaktivieren Sie das Senden eines Archivierungshaftungsausschlusses an Verbundpartner in Skype for Business Server.
ms.openlocfilehash: a44643d5a46d796e253a0fe444a45bdf610bd572
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235080"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des Sendens eines Archivierungshaftungsausschlusses an Verbundpartner in Skype for Business Server

Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver bereitgestellt und den Partnerverbund für Ihre Organisation aktiviert haben, sollten Sie angegeben haben, ob der Archivierungshaftungsausschluss automatisch an Verbundpartner gesendet werden soll. Wenn Sie externe Kommunikation archivieren, sollten Sie das Senden eines Archivierungshaftungsausschlusses aktivieren. Verwenden Sie das Verfahren in diesem Thema, um diese Konfiguration zu ändern.

> [!NOTE]
> Im folgenden Verfahren wird vorausgesetzt, dass Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Ausführliche Informationen zum Aktivieren des Partnerverbunds finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs.](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>So aktivieren oder deaktivieren Sie das Senden eines Archivierungshaftungsausschlusses an Verbundpartner

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Registerkarte **"Zugriffs-Edgekonfiguration"** auf **"Global",** klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".**

5.  Aktivieren oder deaktivieren Sie unter **"Kommunikation mit Verbundbenutzern aktivieren"** unter "Bearbeiten der **Zugriffs-Edgekonfiguration"** das Kontrollkästchen **"Archivierungshaftungsausschluss an Verbundpartner** senden", um das automatische Senden des Archivierungshaftungsausschlusses zu aktivieren oder zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Damit Verbundbenutzer mit Benutzern in Ihrer Skype for Business Server Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Zugriff durch Verbundbenutzer zu unterstützen. Ausführliche Informationen zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter Konfigurieren der [Unterstützung für zulässige externe Domänen.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe Windows PowerShell Cmdlets

Die Verwendung des Archivierungshaftungsausschlusses kann mithilfe von Windows PowerShell und dem cmdlet Set-CsAccessEdgeConfiguration verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

## <a name="to-enable-the-archiving-disclaimer"></a>So aktivieren Sie den Archivierungshaftungsausschluss

  - Um den Archivierungshaftungsausschluss zu aktivieren, legen Sie den Wert der **Eigenschaft "EnableArchivingDisclaimer"** auf "True" ($True) fest:<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>So deaktivieren Sie den Archivierungshaftungsausschluss

  - Um den Archivierungshaftungsausschluss zu deaktivieren, legen Sie den Wert der **Eigenschaft "EnableArchivingDisclaimer"** auf "False" ($False) fest:<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

