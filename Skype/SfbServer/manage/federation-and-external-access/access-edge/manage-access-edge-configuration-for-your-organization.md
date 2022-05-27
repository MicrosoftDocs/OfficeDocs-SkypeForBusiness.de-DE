---
title: Verwalten der Zugriffs-Edgekonfiguration für Ihre Organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Nach der Bereitstellung eines oder mehrerer Edgeserver müssen Sie die Typen des externen Domänen- oder Anbieterzugriffs, des Remotebenutzerzugriffs und des anonymen Benutzerzugriffs auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674597"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Verwalten der Zugriffs-Edgekonfiguration für Ihre Organisation

Nach der Bereitstellung eines oder mehrerer Edgeserver müssen Sie die Typen des externen Domänen- oder Anbieterzugriffs, des Remotebenutzerzugriffs und des anonymen Benutzerzugriffs auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.

Zu diesen Optionen gehören die folgenden Zugriffsarten, die auf der Seite **Zugriffs-Edgekonfiguration** konfiguriert werden können:

  - **Aktivieren der Verbund- und öffentlichen Chatkonnektivität**   Aktivieren Sie diese Option, wenn Sie den Benutzerzugriff auf Partnerverbunddomänen unterstützen möchten. Diese Einstellung gilt für SIP-Partnerverbund, der für globale, Standort- oder Benutzerbereiche auf der Seite **"Richtlinie für den externen Zugriff"** konfiguriert ist. Damit die Partnerverbundeinstellungen gelten, müssen Sie die Partnerverbundunterstützung auf beiden Seiten konfigurieren.
    
    Es gibt zwei Optionen, bei denen es sich um optionale Einstellungen für die Ermittlung von Verbundpartnern handelt und ob Archivierungshaftungsausschlüsse (Benachrichtigung an Verbundkontakte, mit denen Sie kommunizieren, dass die Archivierung für Ihre Bereitstellung aktiviert ist und die Kommunikationsdetails archiviert werden) an Kontakte gesendet werden:
    
      - **Aktivieren der Partnerdomänenermittlung**   Wenn Sie diese Option auswählen, wird die automatische Ermittlung von Domänen aktiviert, mit denen Sie eine Verbindung bilden können. Skype for Business Server verwendet DNS-Einträge (Domain Name System), um zu versuchen, Domänen zu ermitteln, die nicht in der Liste der zulässigen Domänen aufgeführt sind, wobei eingehender Datenverkehr von ermittelten Verbundpartnern automatisch ausgewertet und der Datenverkehr basierend auf der Vertrauensstufe, dem Umfang des Datenverkehrs und den Administratoreinstellungen eingeschränkt oder blockiert wird. Wenn Sie diese Option nicht auswählen, ist der Partnerbenutzerzugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste der zulässigen Domänen einschließen. Unabhängig davon, ob Sie diese Option auswählen oder nicht, können Sie angeben, dass einzelne Domänen blockiert oder zugelassen werden sollen, einschließlich der Einschränkung des Zugriffs auf bestimmte Server, auf denen der Access Edge-Dienst in der Verbunddomäne ausgeführt wird. Ausführliche Informationen finden [Sie unter Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Archivierungshaftungsausschluss an Verbundpartner senden**   Wenn Sie diese Option auswählen, wird das Senden einer Archivierungshaftungsnachricht an Partnerverbundpartner ermöglicht, die ihnen mitteilen, dass Kommunikationsdetails aufgezeichnet werden. Wenn Sie die externe Kommunikation mit Verbundpartnerdomänen archivieren, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten und Kommunikationsdetails durch Ihre Bereitstellung in Kenntnis zu setzen. Ausführliche Informationen zur Archivierung finden Sie unter [Aktivieren oder Deaktivieren des Sendens eines Archivierungshaftungsausschlusses an partnerverbundene Partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Aktivieren des Remotebenutzerzugriffs**   Aktivieren Sie diese Option, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, z. B. Telekommunikationsmutierer und Benutzer, die unterwegs sind, eine Verbindung mit Skype for Business Server herstellen können. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](enable-or-disable-remote-user-access.md).

  - **Anonymen Benutzern den Zugriff auf Konferenzen ermöglichen**   Aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu Konferenzen einladen möchten, die sie organisieren. Wenn Sie diese Einstellung aktivieren, sind nur anonyme Benutzer für Konferenzen zugelassen.

> [!NOTE]  
> Zusätzlich zur Unterstützung des Zugriffs externer Benutzer können Sie auch Richtlinien konfigurieren, mit denen die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation gesteuert wird, bevor Benutzer den Zugriff für externe Benutzer verwenden können. Ausführliche Informationen zum Erstellen, Konfigurieren und Anwenden von Richtlinien für den Externen Benutzerzugriff finden [Sie unter Verwalten der Richtlinie für den externen Zugriff für Ihre Organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Anzeigen von Access Edge-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets**

  - Access Edge-Konfigurationsinformationen können mithilfe von Windows PowerShell und dem Cmdlet **"Get-CsAccessEdgeConfiguration**" angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 
    
    Um Informationen zu allen Ihren Access Edge-Konfigurationseinstellungen anzuzeigen, geben Sie den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
     `Get-CsAccessEdgeConfiguration`
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
    Identität : Global<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers : True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery : False<br/>
    EnableArchivingDisclaimer : False<br/>
    EnableUserReplicator : True<br/>
    KeepCrlsUpToDateForPeers : True<br/>
    MarkSourceVerifiableOnOutgoingMessages : True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate : 20<br/>
    EnableDiscoveredPartnerContactsLimit : True<br/>
    MaxContactsPerDiscoveredPartner : 1000<br/>
    DiscoveredPartnerReportPeriodMinutes : 60<br/>
    MaxAcceptedCertificatesStored : 1000<br/>
    MaxRejectedCertificatesStored : 500<br/>
    CertificatesDeletedPercentage : 20<br/>
    RoutingMethod : UseDnsSrvRouting<br/>

