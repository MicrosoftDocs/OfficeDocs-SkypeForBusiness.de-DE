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
ms.localizationpriority: medium
description: Nach der Bereitstellung eines oder mehrerer Edgeserver müssen Sie die Typen des externen Domänen- oder Anbieterzugriffs, des Remotebenutzerzugriffs und des anonymen Benutzerzugriffs auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.
ms.openlocfilehash: af03dbd058884d0a09b5cb68c5f43e030c84fb06
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634329"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Verwalten der Zugriffs-Edgekonfiguration für Ihre Organisation

Nach der Bereitstellung eines oder mehrerer Edgeserver müssen Sie die Typen des externen Domänen- oder Anbieterzugriffs, des Remotebenutzerzugriffs und des anonymen Benutzerzugriffs auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.

Zu diesen Optionen gehören die folgenden Zugriffsarten, die auf der Seite **Zugriffs-Edgekonfiguration** konfiguriert werden können:

  - **Aktivieren des Partnerverbunds und der Verbindung mit öffentlichen Chatdiensten**   Aktivieren Sie diese Option, wenn Sie den Benutzerzugriff auf Partnerdomänen unterstützen möchten. Diese Einstellung gilt für SIP-Partnerverbund, der für globale, Standort- oder Benutzerbereiche auf der Seite "Richtlinie für **den externen Zugriff"** konfiguriert ist. Damit die Partnerverbundeinstellungen gelten, müssen Sie die Partnerverbundunterstützung auf beiden Seiten konfigurieren.
    
    Es gibt zwei Optionen, bei denen es sich um optionale Einstellungen für die Erkennung von Verbundpartnern handelt und ob Archivierungshaftungsausschlüsse (Benachrichtigung an Verbundkontakte, mit denen Sie kommunizieren, dass die Archivierung für Ihre Bereitstellung aktiviert ist und die Kommunikationsdetails archiviert werden) an Kontakte gesendet werden:
    
      - **Aktivieren der Partnerdomänenermittlung**   Wenn Sie diese Option auswählen, wird die automatische Ermittlung von Domänen aktiviert, mit denen Sie einen Verbund erstellen können. Skype for Business Server dns-Einträge (Domain Name System) verwendet, um Domänen zu ermitteln, die nicht in der Liste der zulässigen Domänen aufgeführt sind, wobei eingehender Datenverkehr von ermittelten Verbundpartnern automatisch ausgewertet und dieser Datenverkehr basierend auf Vertrauensebene, Datenverkehrsmenge und Administratoreinstellungen eingeschränkt oder blockiert wird. Wenn Sie diese Option nicht auswählen, ist der Verbundbenutzerzugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste der zulässigen Domänen aufnehmen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zugelassen werden sollen, einschließlich der Einschränkung des Zugriffs auf bestimmte Server, auf denen der Zugriffs-Edgedienst in der Verbunddomäne ausgeführt wird. Ausführliche Informationen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)
    
      - **Archivierungshaftungsausschluss an Verbundpartner senden**   Wenn Sie diese Option auswählen, kann eine Archivierungshaftungsausschlussnachricht an Verbundpartner gesendet werden, die sie darüber informiert, dass Kommunikationsdetails aufgezeichnet werden. Wenn Sie die externe Kommunikation mit Verbundpartnerdomänen archivieren, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten und Kommunikationsdetails durch Ihre Bereitstellung in Kenntnis zu setzen. Ausführliche Informationen zur Archivierung finden Sie unter [Aktivieren oder Deaktivieren des Sendens eines Archivierungshaftungsausschlusses an Verbundpartner.](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - **Aktivieren des Remotebenutzerzugriffs**   Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, z. B. Telekommunikationspendler und Benutzer, die unterwegs sind, in der Lage sein sollen, eine Verbindung mit Skype for Business Server herzustellen. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs.](enable-or-disable-remote-user-access.md)

  - **Anonymen Benutzern den Zugriff auf Konferenzen ermöglichen**   Aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu Konferenzen einladen sollen, die sie organisieren. Wenn Sie diese Einstellung aktivieren, sind nur anonyme Benutzer für Konferenzen zugelassen.

> [!NOTE]  
> Zusätzlich zur Unterstützung des Zugriffs externer Benutzer können Sie auch Richtlinien konfigurieren, mit denen die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation gesteuert wird, bevor Benutzer den Zugriff für externe Benutzer verwenden können. Ausführliche Informationen zum Erstellen, Konfigurieren und Anwenden von Richtlinien für den externen Benutzerzugriff finden Sie unter Verwalten der [Richtlinie für den externen Zugriff für Ihre Organisation.](../external-access-policies/manage-external-access-policy-for-your-organization.md)

**Anzeigen von Zugriffs-Edgekonfigurationsinformationen mithilfe Windows PowerShell Cmdlets**

  - Zugriffs-Edgekonfigurationsinformationen können mithilfe von Windows PowerShell und dem Cmdlet **"Get-CsAccessEdgeConfiguration"** angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 
    
    Um Informationen zu allen Zugriffs-Edge-Konfigurationseinstellungen anzuzeigen, geben Sie den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
     `Get-CsAccessEdgeConfiguration`
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
    Identität : Global<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers: True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery: False<br/>
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

