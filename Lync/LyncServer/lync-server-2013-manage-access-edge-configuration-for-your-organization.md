---
title: 'Lync Server 2013: Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation'
TOCTitle: Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ552443(v=OCS.15)
ms:contentKeyID: 49292979
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Diese Dokumentation ist vorläufig und kann geändert werden. Leere Themen sind als Platzhalter enthalten.

Nach dem Bereitstellen eines oder mehrerer Edgeserver müssen Sie angeben, welche Arten von externem Domänenzugriff oder Anbieterzugriff, Remotebenutzerzugriff und anonymem Benutzerzugriff auf Konferenzen über die Edgeserver aktiviert und für Ihre Organisation unterstützt werden sollen.

Zu diesen Optionen gehören die folgenden Zugriffsarten, die auf der Seite **Zugriffs-Edgekonfiguration** konfiguriert werden können:

  - **Partnerverbund und Verbindung mit öffentlichen Chatdiensten aktivieren**    Aktivieren Sie diese Option, wenn Sie den Benutzerzugriff auf Verbundpartnerdomänen unterstützen möchten. Diese Einstellung gilt gleichermaßen für SIP- und XMPP-Partnerverbunde, die auf der Seite **Externe Zugriffsrichtlinie** für die Bereiche "Global", "Standort" oder "Benutzer" konfiguriert sind. Damit die Partnerverbundeinstellungen gelten, müssen Sie die Partnerverbundunterstützung auf beiden Seiten konfigurieren.
    
    Es sind zwei Optionen vorhanden, bei denen es sich um optionale Einstellungen zur Erkennung von Verbundpartnern handelt. Damit wird auch festgelegt, ob Archivierungshaftungsausschlüsse (Benachrichtigung an Verbundkontakte, mit denen Sie kommunizieren, dass für Ihre Bereitstellung die Archivierung aktiviert ist und dass Kommunikationsdetails archiviert werden) an Kontakte gesendet werden.
    
      - **Partnerdomänenerkennung aktivieren**    Wenn Sie diese Option auswählen, werden Domänen, mit denen Sie einen Partnerverbund einrichten können, automatisch erkannt. Lync Server 2013 verwendet DNS-Einträge (Domain Name System), um Domänen zu suchen, die nicht in der Liste der zulässigen Domänen aufgeführt sind. Darüber hinaus wird der eingehende Datenverkehr von ermittelten Verbundpartnern automatisch ausgewertet und je nach Vertrauensebene, Umfang des Datenverkehrs und den Administratoreinstellungen eingeschränkt oder blockiert. Wenn Sie diese Option nicht aktivieren, wird der Partnerbenutzerzugriff nur für Benutzer in Domänen aktiviert, die Sie der Liste der zulässigen Domänen hinzugefügt haben. Unabhängig von der Aktivierung dieser Option können Sie festlegen, ob einzelne Domänen blockiert oder zugelassen werden, und Sie können den Zugriff auf bestimmte Server in der Partnerdomäne einschränken, auf denen der Zugriffs-Edgedienst ausgeführt wird. Ausführliche Informationen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Archivierungshaftungsausschluss an Verbundpartner senden**    Wenn Sie diese Option auswählen, wird das Senden einer Archivierungshaftungsausschluss-Nachricht an Verbundpartner ermöglicht, um sie darüber zu informieren, dass die Kommunikation aufgezeichnet wird. Wenn Sie die externe Kommunikation mit Verbundpartnerdomänen archivieren, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten und Kommunikationsdetails durch Ihre Bereitstellung in Kenntnis zu setzen. Ausführliche Informationen zur Archivierung finden Sie unter [Definieren der Anforderungen Ihrer Organisation für die Archivierung in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Zugriff durch Remotebenutzer aktivieren**    Aktivieren Sie diese Option, um zu ermöglichen, dass außerhalb der Firewall befindliche Benutzer Ihrer Organisation, z. B. Telearbeiter und Außendienstmitarbeiter, eine Verbindung mit Lync Server herstellen können. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Anonyme Benutzer dürfen auf Konferenzen zugreifen**    Aktivieren Sie diese Option, wenn Sie internen Benutzern das Einladen externer anonymer Benutzer zu selbst organisierten Konferenzen ermöglichen möchten. Wenn Sie diese Einstellung aktivieren, sind nur anonyme Benutzer für Konferenzen zugelassen. Ausführliche Informationen zur Konfiguration von Konferenzen, zu den Optionen, mit denen die Möglichkeiten für Benutzer von Konferenzen festgelegt werden, und zur Einbindung anonymer Benutzer finden Sie unter [Erstellen oder Ändern der Konferenzeinstellungen für einen Standort oder eine Benutzergruppe](https://technet.microsoft.com/de-de/library/gg429715\(v=ocs.15\)) und [Referenz zu den Konferenzrichtlinieneinstellungen](lync-server-2013-conferencing-policy-settings-reference.md).


> [!NOTE]
> Zusätzlich zur Unterstützung des Zugriffs externer Benutzer können Sie auch Richtlinien konfigurieren, mit denen die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation gesteuert wird, bevor Benutzer den Zugriff für externe Benutzer verwenden können. Ausführliche Informationen zum Erstellen, Konfigurieren und Anwenden von Richtlinien für den externen Benutzerzugriff finden Sie unter <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation in Lync Server 2013</A>.



**Anzeigen von Informationen zur Zugriffs-Edgekonfiguration durch Verwendung von Windows PowerShell-Cmdlets**

  - Sie können Informationen zur Zugriffs-Edgekonfiguration anzeigen, indem Sie die Windows PowerShell und das Cmdlet **Get-CsAccessEdgeConfiguration** verwenden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung der Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Geben Sie zum Anzeigen von Informationen zu allen Einstellungen der Zugriffs-Edgekonfiguration den folgenden Befehl in die Lync Server-Verwaltungsshell ein und drücken Sie die EINGABETASTE:
    
        Get-CsAccessEdgeConfiguration
    
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

## In diesem Abschnitt

  - [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer in Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

