---
title: Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem eine oder mehrere Edgeserver bereitstellen, müssen Sie die Typen von externen Domäne oder Anbieter zugreifen, Zugriff durch Remotebenutzer und Zugriff anonymer Benutzer auf Konferenzen über die Edge-Server, die für Ihre Organisation unterstützt werden aktivieren.
ms.openlocfilehash: ab6f1ac28b375e5fddf9b99226770d92d8236bac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920689"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation

Nachdem eine oder mehrere Edgeserver bereitstellen, müssen Sie die Typen von externen Domäne oder Anbieter zugreifen, Zugriff durch Remotebenutzer und Zugriff anonymer Benutzer auf Konferenzen über die Edge-Server, die für Ihre Organisation unterstützt werden aktivieren.

Zu diesen Optionen gehören die folgenden Zugriffsarten, die über die Seite **Konfiguration für Zugriffsedge** konfiguriert werden können:

  - **Aktivieren Sie den Verbund und Verbindung mit öffentlichen Sofortnachrichtendiensten**   aktivieren Sie diese Option, wenn Sie Benutzerzugriff auf verbundpartnerdomänen unterstützen möchten. Diese Einstellung gilt für SIP den Verbund konfiguriert für globale, Standort- oder Benutzer Bereiche auf der Seite **Richtlinie für den externen Zugriff** . Bei verbundeinstellungen anwenden müssen Sie die verbundunterstützung auf beiden Seiten konfigurieren.
    
    Zwei Optionen vorhanden, die optionale Einstellungen für sind wie Verbundpartnern erkannt werden, und ob Haftungsausschlüsse Archivierung (Benachrichtigung den Verbundkontakten angezeigt, dass Sie mit die Bereitstellung kommunizieren muss Archivierung aktiviert und die Kommunikation Details archiviert werden) an Kontakte gesendet:
    
      - **Aktivieren Sie Partner Domäne Discovery**   Wenn diese Option aktiviert die automatische Ermittlung von Domänen, die Sie einen Verbund mit konfigurieren können. Skype für Business Server verwendet Domain Name System (DNS) Datensätze versuchen, nicht in der Liste zugelassener Domänen aufgeführte Domänen erkennen automatisch Auswerten von eingehenden Datenverkehr von Verbundpartnern ermittelten und eingeschränkt oder blockieren, die basierend auf der Vertrauenswürdigkeit Datenverkehr die Ebene, Umfang des Datenverkehrs und administratoreinstellungen. Wenn Sie diese Option nicht auswählen, wird partnerbenutzerzugriff für Benutzer in den Domänen nur aktiviert, die Sie in der Liste der zugelassenen Domänen hinzufügen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass diese Person Domänen blockiert oder zulässig, einschließlich Einschränken des Zugriffs auf bestimmten Servern in der Partnerdomäne Zugriffs-edgedienst ausgeführt. Weitere Informationen hierzu finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Archivierungshaftungsausschlusses an Verbundpartner senden**   durch Auswählen dieser Option ermöglicht das Senden einer Archivierung Haftungsausschluss-Nachricht an Verbundpartner, die sie darüber informiert, dass Communications Details aufgezeichnet werden. Wenn Sie mit verbundpartnerdomänen externe Kommunikation archivieren, sollten Sie den Archivierungshaftungsausschluss für Partner zu warnen, wenn ihre Nachrichten und Kommunikation Details von Ihrer Bereitstellung archiviert werden aktivieren. Ausführliche Informationen zum Archivierung finden Sie unter [Aktivieren oder Deaktivieren einer Archiving Disclaimer an Verbundpartner senden](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Aktivieren des Zugriffs durch Remotebenutzer**   aktivieren Sie diese Option aus, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die außerhalb der Firewall, wie Telearbeiter und Benutzer, die viel unterwegs sind Skype für Business Server herstellen können, sind. Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](enable-or-disable-remote-user-access.md).

  - **Aktivieren Sie anonyme Benutzern Konferenzen Zugriff auf**   aktivieren Sie diese Option aus, wenn Sie interne Benutzern an externe anonyme Benutzer zu Konferenzen einladen, die sie organisieren möchten. Durch Aktivieren dieser Einstellung kann anonyme Benutzer nur für Konferenzen.

> [!NOTE]  
> Neben der Aktivierung Zugriff durch externe Benutzer unterstützen, auch konfigurieren Sie Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Ihrer Organisation der Verwendung bevor keinerlei Zugriff durch externe Benutzer für Benutzer verfügbar ist. Ausführliche Informationen zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff externer Benutzer finden Sie unter [Manage externe Zugriffsrichtlinie für Ihre Organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Anzeigen von Zugriffs-Edgeservers-Konfigurationsinformationen mithilfe von Windows PowerShell-cmdlets**

  - Zugreifen auf Edge-Konfigurationsinformationen kann mithilfe von Windows PowerShell und das Cmdlet " **Get-CsAccessEdgeConfiguration** " angezeigt werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 
    
    Anzeigen von Informationen zu allen Access Edge-Konfigurationseinstellungen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
     `Get-CsAccessEdgeConfiguration`
    
    Es werden etwa folgende Informationen zurückgegeben:
    
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

