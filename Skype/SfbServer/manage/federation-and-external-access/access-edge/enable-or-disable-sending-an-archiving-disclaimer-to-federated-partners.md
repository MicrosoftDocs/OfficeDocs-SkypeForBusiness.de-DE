---
title: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280215"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren des Sendens einer Archivierungs Klausel an verbundene Partner in Skype for Business Server

Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angegeben haben, ob die Archivierungs Verzicht automatisch an Verbundpartner gesendet werden soll. Wenn Sie die externe Kommunikation archivieren, sollten Sie das Senden eines Archivierungs Verzichts aktivieren. Verwenden Sie das in diesem Thema beschriebene Verfahren, um diese Konfiguration zu ändern.

> [!NOTE]
> Im folgenden Verfahren wird davon ausgegangen, dass Sie die Föderation für Ihre Organisation bereits aktiviert haben. Details zum Aktivieren von Föderationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>So aktivieren oder deaktivieren Sie das Senden einer Archivierungs Klausel an verbundene Partner

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Access-Edge-Konfiguration**.

4.  Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.

5.  Aktivieren oder deaktivieren Sie in " **Access-Edge-Konfiguration bearbeiten**" unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Archivierungs Ausschluss an verbundene Partner senden** , um das automatische Senden der Archivierung zu aktivieren oder zu deaktivieren. Haftungsausschluss.

6.  Klicken Sie auf **Commit ausführen**.

Damit Föderationsbenutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Verbundbenutzer Zugriff zu unterstützen. Details zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Archivierungs Verzichts mithilfe von Windows PowerShell-Cmdlets

Die Verwendung des Haftungsausschlusses für die Archivierung kann mithilfe von Windows PowerShell und dem Cmdlet "Satz-csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

## <a name="to-enable-the-archiving-disclaimer"></a>So aktivieren Sie den Archivierungs Ausschluss

  - Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „True“ ($True) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>So deaktivieren Sie den Haftungsausschluss für Archivierung

  - Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „False“ ($False) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


