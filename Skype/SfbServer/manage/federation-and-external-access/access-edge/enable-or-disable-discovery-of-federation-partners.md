---
title: Aktivieren oder Deaktivieren der Suche von Verbundpartnern
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angeben, ob die automatische Ermittlung von Verbundpartner Domänen unterstützt werden soll.
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280257"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in Skype for Business Server

Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angeben, ob die automatische Ermittlung von Verbundpartner Domänen unterstützt werden soll. Verwenden Sie das in diesem Thema beschriebene Verfahren, um diese Konfiguration zu ändern.

> [!NOTE]  
> Im folgenden Verfahren wird davon ausgegangen, dass Sie die Föderation für Ihre Organisation bereits aktiviert haben. Details zum Aktivieren von Föderationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>So aktivieren oder deaktivieren Sie die automatische Ermittlung von Verbunddomänen für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Access-Edge-Konfiguration**.

4.  Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Aktivieren oder deaktivieren Sie in der **Konfiguration der Access-Edge-Konfiguration**unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Ermittlung der Partnerdomäne aktivieren** , um die automatische Ermittlung von Partnerdomänen zu aktivieren oder zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Damit Föderationsbenutzer mit Benutzern in Ihrer Skype for Business Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Verbundbenutzer Zugriff zu unterstützen. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](enable-or-disable-federation-and-public-im-connectivity.md). Details zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter [Verwalten von SIP-Verbunddomänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md) und [Verwalten von SIP-Verbund Anbietern](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern mithilfe von Windows PowerShell-Cmdlets

Die Ermittlung von Verbundpartnern kann mithilfe von Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 


## <a name="to-enable-discovery-of-federation-partners"></a>So aktivieren Sie die Suche nach Verbundpartnern

  - Um die Suche nach Verbundpartnern zu aktivieren, setzen Sie den Wert der **EnablePartnerDiscovery** -Eigenschaft auf true ($true). Beachten Sie, dass Sie das DNS-SRV-Routing aktivieren müssen, um diesen Eigenschaftswert zu ändern.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>So deaktivieren Sie die Ermittlung von Verbundpartnern

  - Um die Ermittlung von Verbundpartnern zu deaktivieren, setzen Sie den Wert der **EnablePartnerDiscovery** -Eigenschaft auf false ($false):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

