---
title: Aktivieren oder Deaktivieren der Suche von Verbundpartnern
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Der Zeitpunkt Edgeserver bereitgestellt und aktiviert den Verbund für Ihr Unternehmen, Sie sollten haben angegeben, ob die automatische Ermittlung aus verbundpartnerdomänen unterstützen.
ms.openlocfilehash: de61d8180a8f4e8f8be13abaab3d8911d2c6e22c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199941"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Aktivieren Sie oder deaktivieren Sie der Ermittlung von Verbundpartnern in Skype für Business Server

Der Zeitpunkt Edgeserver bereitgestellt und aktiviert den Verbund für Ihr Unternehmen, Sie sollten haben angegeben, ob die automatische Ermittlung aus verbundpartnerdomänen unterstützen. Verwenden Sie das Verfahren in diesem Thema, um die Konfiguration zu ändern.

> [!NOTE]  
> Das folgende Verfahren wird davon ausgegangen, dass Sie den Verbund für Ihre Organisation bereits aktiviert haben. Ausführliche Informationen zur Aktivierung des Verbunds finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>So aktivieren oder Deaktivieren der automatischen Suche von Partnerdomänen für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**, und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Details anzeigen**.

5.  Klicken Sie in **Konfiguration für Zugriffsedge bearbeiten**, unter der **Kommunikation mit Partnerbenutzern aktivieren**aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Partner Domäne Discovery aktivieren** , zum Aktivieren oder Deaktivieren der automatischen Suche von Partnerdomänen.

6.  Klicken Sie auf **Commit ausführen**.

Um Verbundbenutzer Zusammenarbeit mit Benutzern in Ihrer Skype für Business Server-Bereitstellung zu aktivieren, müssen Sie auch mindestens eine externe Zugriffsrichtlinie zur Unterstützung der partnerbenutzerzugriff konfiguriert haben. Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](enable-or-disable-federation-and-public-im-connectivity.md). Ausführliche Informationen zum Steuern des Zugriffs für spezifische Partnerdomänen an finden Sie unter [Verwalten von SIP-verbunddomänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md) und [Verwalten von SIP-partnerverbundanbieter](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern mithilfe von Windows PowerShell-cmdlets

Ermittlung von Verbundpartnern kann mithilfe von Windows PowerShell und das Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 


## <a name="to-enable-discovery-of-federation-partners"></a>So aktivieren Sie die Suche von Verbundpartnern

  - Legen Sie den Wert der Eigenschaft **EnablePartnerDiscovery** auf "true" ($True), um die Suche von Verbundpartnern zu ermöglichen. Beachten Sie, dass DNS-SRV-routing, um den Eigenschaftswert ändern aktiviert werden müssen.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>So deaktivieren Sie die Suche von Verbundpartnern

  - Um die Suche von Verbundpartnern zu deaktivieren, legen Sie den Wert der Eigenschaft **EnablePartnerDiscovery** auf "false" ($False):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

