---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer'
TOCTitle: Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182586(v=OCS.15)
ms:contentKeyID: 49295437
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Bei Remotebenutzern handelt es sich um Benutzer in Ihrer Organisation, die über eine dauerhafte Active Directory-Identität innerhalb der Organisation verfügen. Wenn sie nicht intern mit dem Organisationsnetzwerk verbunden sind, melden sich Remotebenutzer häufig außerhalb des Netzwerks über ein VPN (Virtuelles Privates Netzwerk) bei Lync Server an. Remotebenutzer umfassen Mitarbeiter, die zu Hause oder unterwegs arbeiten, sowie andere Remotemitarbeiter, z. B. vertrauenswürdige Lieferanten, denen Anmeldeinformationen für das Unternehmen zur Verfügung gestellt wurden. Wenn Sie den Zugriff durch Remotebenutzer aktivieren, stellen unterstützte Remotebenutzer über das Internet eine Verbindung her und müssen sich nicht über ein VPN anmelden, um unter Verwendung von Lync Server mit internen Benutzern zusammenzuarbeiten.

Zur Unterstützung des Remotebenutzerzugriffs muss der Zugriff durch Remotebenutzer aktiviert werden. Bei Aktivierung wird der Zugriff durch Remotebenutzer für die gesamte Organisation aktiviert. Wenn Sie den Zugriff durch Remotebenutzer zu einem späteren Zeitpunkt temporär oder dauerhaft unterbinden möchten, können Sie die Option für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Zugriff durch Remotebenutzer für Ihre Organisation zu aktivieren oder zu deaktivieren.


> [!NOTE]
> Durch die Aktivierung des Zugriffs durch Remotebenutzer wird lediglich angegeben, dass Ihre Server, auf denen der Zugriffs-Edgedienst ausgeführt wird, die Kommunikation mit Remotebenutzern unterstützen. Remotebenutzer können jedoch erst dann an Chats oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie außerdem mindestens eine Richtlinie zur Verwaltung der Verwendung des Remotebenutzerzugriffs konfigurieren. Lync Server-Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien, und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt. Ausführliche Informationen zur Konfiguration von Richtlinien für die Verwendung des Remotebenutzerzugriffs finden Sie unter <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013</A>.



## So aktivieren oder deaktivieren Sie den Zugriff durch Remotebenutzer für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** , und klicken Sie dann auf **Zugriffs-Edgekonfiguration** .

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global** , klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Details anzeigen** .

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren** , um den Zugriff durch Remotebenutzer für Ihre Organisation zuzulassen.
    
      - Deaktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren** , um den Zugriff durch Remotebenutzer für Ihre Organisation zu unterbinden.

6.  Klicken Sie auf **Commit** .

Sie müssen außerdem mindestens eine externe Zugriffsrichtlinie für die Unterstützung des Remotebenutzerzugriffs konfigurieren, damit Remotebenutzer sich an Ihren Servern mit Lync Server anmelden können. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in der Bereitstellungs- oder Betriebsdokumentation.

## Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer mithilfe der Windows PowerShell-Cmdlets

Der Remotebenutzerzugriff kann mithilfe der Windows PowerShell und dem Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie den Zugriff durch Remotebenutzer

  - Zum Aktivieren des Zugriffs durch Remotebenutzer legen Sie den Wert der **AllowOutsideUsers**-Eigenschaft auf "True" ( $True ) fest:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## So deaktivieren Sie den Zugriff durch Remotebenutzer

  - Zum Deaktivieren des Zugriffs durch Remotebenutzer legen Sie den Wert der **AllowOutsideUsers**-Eigenschaft auf "False" ( $False ) fest:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

