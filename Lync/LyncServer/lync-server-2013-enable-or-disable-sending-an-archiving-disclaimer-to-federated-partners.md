---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner'
TOCTitle: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182584(v=OCS.15)
ms:contentKeyID: 49295387
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Nachdem Sie Ihre Edgeserver bereitgestellt und den Partnerverbund für Ihre Organisation aktiviert haben, sollten Sie festlegen, ob automatisch ein Archivierungshaftungsausschluss an Verbundpartner gesendet werden soll. Wenn Sie die externe Kommunikation archivieren, sollten Sie das Versenden eines Archivierungshaftungsausschlusses aktivieren. Verwenden Sie das Verfahren in diesem Thema, um diese Konfiguration zu ändern.


> [!NOTE]
> Im folgenden Verfahren wird vorausgesetzt, dass Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Ausführliche Informationen zum Aktivieren des Partnerverbunds finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</A> in der Bereitstellungs- oder Betriebsdokumentation.



## So aktivieren oder deaktivieren Sie das Senden eines Archivierungshaftungsausschlusses an Verbundpartner

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Zugriffs-Edgekonfiguration** .

4.  Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global** , klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Details einblenden** .

5.  Aktivieren oder deaktivieren Sie im Abschnitt **Zugriffs-Edgekonfiguration bearbeiten** unter **Kommunikation mit Partnerbenutzern aktivieren** das Kontrollkästchen **Archivierungshaftungssausschluss an Verbundpartner senden** , um das automatische Versenden eines Archivierungshaftungsausschlusses zu aktivieren bzw. zu deaktivieren.

6.  Klicken Sie auf **Commit** .

Sie müssen außerdem mindestens eine Richtlinie für den externen Zugriff konfigurieren, damit Partnerbenutzer mit Benutzern in Ihrer Lync Server 2013-Bereitstellung zusammenarbeiten können. Ausführliche Informationen finden Sie unter [Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in der Bereitstellungs- oder Betriebsdokumentation. Ausführliche Informationen zur Steuerung des Zugriffs für bestimmte Partnerdomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungs- oder Betriebsdokumentation.

## Aktivieren oder Deaktivieren des Archivierungshaftungsausschlusses mithilfe der Windows PowerShell-Cmdlets

Die Verwendung des Archivierungshaftungsausschlusses kann mit Windows PowerShell und dem Set-CsAccessEdgeConfiguration -Cmdlet verwaltet werden. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie den Archivierungshaftungsausschluss

  - Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der **EnableArchivingDisclaimer**-Eigenschaft auf "True" ( $True ) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## So deaktivieren Sie den Archivierungshaftungsausschluss

  - Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der **EnableArchivingDisclaimer**-Eigenschaft auf "False" ( $False ) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

