---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren der Suche von Verbundpartnern'
TOCTitle: Aktivieren oder Deaktivieren der Suche von Verbundpartnern
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182550(v=OCS.15)
ms:contentKeyID: 49294760
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Nachdem Sie Ihre Edgeserver bereitgestellt und den Partnerverbund für Ihre Organisation aktiviert haben, sollten Sie festlegen, ob die automatische Suche von Verbundpartnerdomänen unterstützt werden soll. Verwenden Sie das Verfahren in diesem Thema, um diese Konfiguration zu ändern.


> [!NOTE]
> Im folgenden Verfahren wird vorausgesetzt, dass Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Ausführliche Informationen zum Aktivieren des Partnerverbunds finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</A> in der Bereitstellungs- oder Betriebsdokumentation.



## So aktivieren oder deaktivieren Sie die automatische Suche von Partnerdomänen für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Zugriffs-Edgekonfiguration** .

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global** , klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Details anzeigen** .

5.  Aktivieren oder deaktivieren Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** unter **Kommunikation mit Partnerbenutzern aktivieren** das Kontrollkästchen **Suche von Partnerdomänen aktivieren** , um die automatische Suche von Partnerdomänen zu aktivieren bzw. zu deaktivieren.

6.  Klicken Sie auf **Commit** .

Sie müssen außerdem mindestens eine Richtlinie für den externen Zugriff von Benutzern des Partnerverbunds konfigurieren, damit Partnerbenutzer mit Benutzern in Ihrer Lync Server-Bereitstellung zusammenarbeiten können. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in der Bereitstellungs- oder Betriebsdokumentation. Ausführliche Informationen zur Steuerung des Zugriffs für bestimmte Partnerdomänen finden Sie unter [Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) und [Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in der Betriebsdokumentation.

## Aktivieren oder Deaktivieren von Verbundpartnern mithilfe von Windows PowerShell-Cmdlets

Die Ermittlung von Verbundpartnern kann mithilfe der Windows PowerShell und dem Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie die Ermittlung von Verbundpartnern

  - Legen Sie zur Aktivierung der Ermittlung von Verbundpartnern den Wert der Eigenschaft **EnablePartnerDiscovery** auf "True" ($True) fest. Beachten Sie, dass Sie DNS-SRV-Routing aktivieren müssen, um diesen Eigenschaftswert zu ändern.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

## So deaktivieren Sie die Ermittlung von Verbundpartnern

  - Legen Sie zur Deaktivierung der Ermittlung von Verbundpartnern den Wert der Eigenschaft **EnablePartnerDiscovery** auf "False" ($False) fest:
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

