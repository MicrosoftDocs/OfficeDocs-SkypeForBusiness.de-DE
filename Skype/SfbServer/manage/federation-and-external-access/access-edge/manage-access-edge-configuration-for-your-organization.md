---
title: Verwalten der Zugriffs-Edgekonfiguration für Ihre Organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
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
description: Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen- oder Anbieterzugriffs, des Remotebenutzerzugriffs und des anonymen Benutzerzugriffs auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817335"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Verwalten der Zugriffs-Edgekonfiguration für Ihre Organisation

Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen- oder Anbieterzugriffs, des Remotebenutzerzugriffs und des anonymen Benutzerzugriffs auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.

Zu diesen Optionen gehören die folgenden Zugriffsarten, die auf der Seite **Zugriffs-Edgekonfiguration** konfiguriert werden können:

  - **Aktivieren von Verbund- und Verbindungen mit öffentlichen Verbindungen**   Aktivieren Sie diese Option, wenn Sie den Benutzerzugriff auf Verbundpartnerdomänen unterstützen möchten. Diese Einstellung gilt für SIP-Verbund, der auf der Seite "Richtlinie für den externen Zugriff" für globale, Standort- oder **Benutzerbereiche konfiguriert** ist. Damit die Partnerverbundeinstellungen gelten, müssen Sie die Partnerverbundunterstützung auf beiden Seiten konfigurieren.
    
    Es gibt zwei Optionen, bei der es sich um optionale Einstellungen für die Art und Weise handelt, wie Verbundpartner ermittelt werden, und ob Archivierungsausschlüsse (Benachrichtigung an Verbundkontakte, mit deren Kommunikation Sie kommunizieren, dass die Archivierung in Ihrer Bereitstellung aktiviert ist und die Kommunikationsdetails archiviert werden) an Kontakte gesendet werden:
    
      - **Aktivieren der Partnerdomänenermittlung**   Wenn Sie diese Option auswählen, wird die automatische Ermittlung von Domänen aktiviert, mit der Sie einen Verbund erstellen können. Skype for Business Server verwendet DNS(Domain Name System)-Einträge, um zu versuchen, Domänen zu ermitteln, die nicht in der Liste der zulässigen Domänen aufgeführt sind, den eingehenden Datenverkehr von ermittelten Verbundpartnern automatisch auszuwerten und diesen Datenverkehr basierend auf Vertrauensebene, Datenverkehrsmenge und Administratoreinstellungen zu begrenzen oder zu blockieren. Wenn Sie diese Option nicht auswählen, ist der Partnerbenutzerzugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste der zulässigen Domänen aufgenommen haben. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zugelassen werden sollen, einschließlich der Einschränkung des Zugriffs auf bestimmte Server, auf denen der Zugriffs-Edgedienst in der Verbunddomäne ausgeführt wird. Weitere Informationen finden Sie unter ["Konfigurieren der Unterstützung für zulässige externe Domänen".](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)
    
      - **Senden eines Archivierungsausschlusses an Verbundpartner**   Wenn Sie diese Option auswählen, können Sie eine Archivierungsausschlussnachricht an Verbundpartner senden, die sie zur Aufzeichnung von Kommunikationsdetails informieren. Wenn Sie die externe Kommunikation mit Verbundpartnerdomänen archivieren, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten und Kommunikationsdetails durch Ihre Bereitstellung in Kenntnis zu setzen. Weitere Informationen zur Archivierung finden Sie unter "Aktivieren oder Deaktivieren des Sendens eines [Archivierungsausschlusses an Den Verbundpartner".](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - **Aktivieren des Zugriffs durch Remotebenutzer**   Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, z. B. Telekommunikationsanbieter und Unterwegsbenutzer, eine Verbindung mit Skype for Business Server herstellen können sollen. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer.](enable-or-disable-remote-user-access.md)

  - **Anonymen Benutzern den Zugriff auf Konferenzen ermöglichen**   Aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu von ihnen organisierten Konferenzen einladen sollen. Wenn Sie diese Einstellung aktivieren, sind nur anonyme Benutzer für Konferenzen zugelassen.

> [!NOTE]  
> Zusätzlich zur Unterstützung des Zugriffs externer Benutzer können Sie auch Richtlinien konfigurieren, mit denen die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation gesteuert wird, bevor Benutzer den Zugriff für externe Benutzer verwenden können. Weitere Informationen zum Erstellen, Konfigurieren und Anwenden von Richtlinien für den externen Benutzerzugriff finden Sie unter "Verwalten der Richtlinie für den externen Zugriff [für Ihre Organisation".](../external-access-policies/manage-external-access-policy-for-your-organization.md)

**Anzeigen von Konfigurationsinformationen für Zugriffs-Edge mit Windows PowerShell Cmdlets**

  - Konfigurationsinformationen zum Zugriffsedge können mithilfe von Windows PowerShell und dem **Cmdlet "Get-CsAccessEdgeConfiguration"** angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. 
    
    Geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Konfigurationseinstellungen für Den Zugriffs-Edgeserver anzeigen zu können:
    
     `Get-CsAccessEdgeConfiguration`
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

