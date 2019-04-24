---
title: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 859b4e295a90fd44ce69efe4af7daa63ddc8812c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197863"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Aktivieren Sie oder deaktivieren Sie das Senden einer Archiving Disclaimer an Verbundpartner in Skype für Business Server

Der Zeitpunkt Edgeserver bereitgestellt und aktiviert den Verbund für Ihr Unternehmen, Sie sollten angegeben haben, ob automatisch des Archivierungshaftungsausschlusses an Verbundpartner senden. Wenn Sie externe Kommunikation archivieren, sollten Sie das Senden eines Archivierungshaftungsausschlusses aktivieren. Verwenden Sie das Verfahren in diesem Thema, um die Konfiguration zu ändern.

> [!NOTE]
> Das folgende Verfahren wird davon ausgegangen, dass Sie den Verbund für Ihre Organisation bereits aktiviert haben. Ausführliche Informationen zur Aktivierung des Verbunds finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>So aktivieren oder deaktivieren Sie das Senden eines Archivierungshaftungsausschlusses an Verbundpartner

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**, und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.

5.  **Konfiguration für Zugriffsedge bearbeiten**, unter der **Kommunikation mit Partnerbenutzern aktivieren**aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden** zum Aktivieren oder deaktivieren automatisch Senden der Archivierung Haftungsausschluss.

6.  Klicken Sie auf **Commit ausführen**.

Um Verbundbenutzer Zusammenarbeit mit Benutzern in Ihrer Skype für Business Server-Bereitstellung zu aktivieren, müssen Sie auch mindestens eine externe Zugriffsrichtlinie zur Unterstützung der partnerbenutzerzugriff konfiguriert haben. Ausführliche Informationen zum Steuern des Zugriffs für spezifische Partnerdomänen an finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe von Windows PowerShell-cmdlets

Die Verwendung von des Archivierungshaftungsausschlusses kann mithilfe von Windows PowerShell und das Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 

## <a name="to-enable-the-archiving-disclaimer"></a>Zum Aktivieren des Archivierungshaftungsausschlusses

  - Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „True“ ($True) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Zum Deaktivieren des Archivierungshaftungsausschlusses

  - Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „False“ ($False) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


