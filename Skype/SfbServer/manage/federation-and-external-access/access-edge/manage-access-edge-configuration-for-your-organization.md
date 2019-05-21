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
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen-oder Anbieter Zugriffs, den Remotebenutzerzugriff und den anonymen Benutzer Zugriff auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.
ms.openlocfilehash: b79560d2cb0e570ab2b4fcf061a5b91c6a74a8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280194"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation

Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen-oder Anbieter Zugriffs, den Remotebenutzerzugriff und den anonymen Benutzer Zugriff auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.

Zu diesen Optionen gehören die folgenden Zugriffsarten, die über die Seite " **Zugriffs-Edge-Konfiguration** " konfiguriert werden können:

  - **Aktivieren von Föderations-und öffentlichen Chat Verbindungen**   aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Partnerdomänen für Föderationen unterstützen möchten. Diese Einstellung gilt für SIP-Föderationen, die für globale, Website-oder benutzerbereiche auf der Seite " **externe Zugriffsrichtlinie** " konfiguriert sind. Damit die Verbund Einstellungen angewendet werden, müssen Sie die Verbundunterstützung auf beiden Seiten konfigurieren.
    
    Es gibt zwei Optionen, die optionale Einstellungen für die Erkennung von Verbundpartnern sind, und ob Archivierungs verzichte (Benachrichtigung an verbundene Kontakte, mit denen Sie kommunizieren, dass Ihre Bereitstellung die Archivierung aktiviert hat und dass die Kommunikation Details werden archiviert) werden an die Kontakte weitergeleitet:
    
      - **Aktivieren der Partnerdomänen Ermittlung**   durch Auswahl dieser Option wird die automatische Ermittlung von Domänen ermöglicht, mit denen Sie eine Föderation durchsetzen können. Skype for Business Server verwendet DNS-Einträge (Domain Name System), um zu ermitteln, welche Domänen nicht in der Liste der zulässigen Domänen aufgeführt sind, und die eingehenden Datenverkehr von ermittelten Partner Partnern automatisch auswerten und den Datenverkehr basierend auf Vertrauen einschränken oder blockieren. Ebene, Umfang des Datenverkehrs und Administratoreinstellungen. Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen aufnehmen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zulässig sein sollen, einschließlich der Beschränkung des Zugriffs auf bestimmte Server, auf denen der Access-Edgedienst in der Verbunddomäne ausgeführt wird. Ausführliche Informationen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Archivierungs Ausschluss an verbundene Partner**   senden wenn Sie diese Option aktivieren, können Sie eine Nachricht zur Archivierung des Disclaimers an verbundene Partner senden, die Ihnen mitteilt, dass Kommunikationsdetails aufgezeichnet werden. Wenn Sie die externe Kommunikation mit Verbundpartner Domänen archivieren, sollten Sie die Benachrichtigung über Archivierungs Verzicht aktivieren, um die Partner zu warnen, dass Ihre Nachrichten und Kommunikationsdetails von Ihrer Bereitstellung archiviert werden. Details zur Archivierung finden Sie unter [Aktivieren oder Deaktivieren des Sendens einer Archivierungs Klausel an den Verbundpartner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Aktivieren des Remotebenutzerzugriffs**   aktivieren Sie diese Option, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie Telecommuter und Benutzer, die unterwegs sind, eine Verbindung mit Skype for Business Server herstellen können. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](enable-or-disable-remote-user-access.md).

  - **Aktivieren von anonymen Benutzern für den Zugriff auf Konferenzen**   aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu Konferenzen einladen möchten, die Sie organisieren. Wenn Sie diese Einstellung aktivieren, können anonyme Benutzer nur für Konferenzen zugelassen werden.

> [!NOTE]  
> Neben der Unterstützung für den Zugriff durch externe Benutzer können Sie auch Richtlinien konfigurieren, um die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation zu steuern, bevor Benutzer Zugriff auf externe Benutzer erhalten. Details zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter [Verwalten der Richtlinien für den externen Zugriff für Ihre Organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Anzeigen von Informationen zur Access-Edge-Konfiguration mithilfe von Windows PowerShell-Cmdlets**

  - Informationen zur Access-Edge-Konfiguration können mithilfe von Windows PowerShell und dem Cmdlet **Get-csaccessedgeconfiguration nicht angeben** angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 
    
    Wenn Sie Informationen zu allen Einstellungen für die Zugriffs-Edge-Konfiguration anzeigen möchten, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
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

