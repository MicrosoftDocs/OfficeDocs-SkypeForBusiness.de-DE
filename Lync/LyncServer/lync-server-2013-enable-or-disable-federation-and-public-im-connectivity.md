---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten'
TOCTitle: Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182549(v=OCS.15)
ms:contentKeyID: 49294718
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-06-24_

Die Unterstützung für einen Partnerverbund ist erforderlich, um Benutzern mit einem Konto in einer vertrauenswürdigen Kunden- oder Partnerorganisation - Partnerdomänen und Benutzer eines unterstützten öffentlichen Sofortnachrichtenanbieters eingeschlossen - die Zusammenarbeit mit Benutzern in Ihrer Organisation zu ermöglichen. Der Partnerverbund ist auch erforderlich, um einen gehosteten Exchange-Dienstanbieter zu verwenden, um Voicemail für Enterprise-VoIP-Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, z. B. Microsoft Exchange Online. Wenn Sie eine Vertrauensstellung mit diesen externen Domänen eingerichtet haben, können Sie Benutzer in diesen Domänen für den Zugriff auf Ihre Bereitstellung und für die Teilnahme an der Lync Server-Kommunikation autorisieren. Diese Vertrauensstellung wird Partnerverbund genannt, und es besteht weder ein Zusammenhang mit noch eine Abhängigkeit von einer Active Directory-Vertrauensstellung.

Zur Unterstützung des Benutzerzugriffs auf Partnerdomänen müssen Sie den Partnerverbund aktivieren. Wenn Sie den Partnerverbund für Ihre Organisation aktivieren, müssen Sie auch angeben, ob die folgenden Optionen implementiert werden sollen:

  - **Suche von Partnerdomänen aktivieren**    Wenn Sie diese Option aktivieren, werden vom Lync Server DNS-Einträge (Domain Name System) verwendet, um Domänen zu suchen, die nicht in der Liste der zulässigen Domänen aufgeführt sind. Darüber hinaus wird der eingehende Datenverkehr von ermittelten Verbundpartnern automatisch ausgewertet und je nach Vertrauensebene, Umfang des Datenverkehrs und den Administratoreinstellungen eingeschränkt oder blockiert. Wenn Sie diese Option nicht aktivieren, wird der Partnerbenutzerzugriff nur für Benutzer in Domänen aktiviert, die Sie der Liste der zulässigen Domänen hinzugefügt haben. Unabhängig von der Aktivierung dieser Option können Sie festlegen, ob einzelne Domänen blockiert oder zugelassen werden, und Sie können den Zugriff auf bestimmte Server in der Partnerdomäne einschränken, auf denen der Zugriffs-Edgedienst ausgeführt wird. Ausführliche Informationen zum Steuern des Zugriffs durch Partnerdomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Senden Sie einen Archivierungshaftungsausschluss an Verbundpartner**    Dieser Haftungsausschluss wird an Verbundpartner gesendet, um sie darüber zu informieren, dass die Archivierung innerhalb der Bereitstellung ausgeführt wurde. Wenn Sie die Archivierung der externen Kommunikation mit Verbundpartnerdomänen unterstützen, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten in Kenntnis zu setzen.

Wenn Sie den Zugriff durch Benutzer von Partnerdomänen zu einem späteren Zeitpunkt temporär oder dauerhaft unterbinden möchten, können Sie den Partnerverbund für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Partnerbenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren und um die geeigneten Partnerverbundoptionen festzulegen, die für Ihre Organisation unterstützt werden sollen.


> [!NOTE]
> Durch die Aktivierung des Partnerverbunds für Ihre Organisation legen Sie lediglich fest, dass Ihre Server, auf denen der Zugriffs-Edgedienst ausgeführt wird, das Routing an Verbunddomänen unterstützen. Benutzer in Verbunddomänen können nicht an Sofortnachrichtensitzungen oder Konferenzen in Ihrer Organisation teilnehmen. Dies ist erst möglich, wenn Sie zusätzlich mindestens eine Richtlinie zur Unterstützung des Partnerbenutzerzugriffs konfigurieren. Benutzer öffentlicher Sofortnachrichten-Dienstanbieter können nicht an Sofortnachrichtensitzungen oder Konferenzen in Ihrer Organisation teilnehmen. Dies ist erst möglich, wenn Sie zusätzlich mindestens eine Richtlinie zur Unterstützung von Verbindungen mit öffentlichen Sofortnachrichtendiensten konfigurieren. Lync Server kann keine gehosteten Exchange-Dienst verwenden, um Mailboxansage, Outlook Voice Access (einschließlich Voicemail) oder Dienste für die automatische Telefonzentrale für Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden. Hierzu müssen Sie zuerst eine Richtlinie für eine gehostete Voicemail konfigurieren, die Routinginformationen bereitstellt. Ausführliche Informationen zum Konfigurieren von Richtlinien für die Kommunikation mit Benutzern von Partnerdomänen in anderen Organisationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013</A> in der Betriebsdokumentation. Wenn Sie außerdem die Kommunikation mit Benutzern von Sofortnachrichten-Dienstanbietern unterstützen möchten, müssen Sie entsprechende Richtlinien konfigurieren. Zusätzlich müssen Sie die Unterstützung für einzelne Dienstanbieter konfigurieren, die Sie unterstützen möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013</A> in der Betriebsdokumentation. Detaillierte Informationen zum Erstellen einer Richtlinie für gehostete Voicemail finden Sie unter <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von Richtlinien für gehostete Voicemail in Lync Server 2013</A> in der Bereitstellungsdokumentation.



## So aktivieren oder deaktivieren Sie den Partnerbenutzerzugriff für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge** .

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global** , klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Details anzeigen** .

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren** , um den Zugriff durch Remotebenutzer für Ihre Organisation zuzulassen.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** , um den Partnerbenutzerzugriff für Ihre Organisation zu deaktivieren.

6.  Führen Sie nach Aktivierung des Kontrollkästchens **Kommunikation mit Partnerbenutzern aktivieren** eine der folgenden Aktionen aus:
    
    1.  Aktivieren Sie das Kontrollkästchen **Suche von Partnerdomänen aktivieren** , um die automatische Suche von Partnerdomänen zu unterstützen.
    
    2.  Wenn Ihre Organisation die Archivierung der externen Kommunikation unterstützt, aktivieren Sie das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden** .

7.  Klicken Sie auf **Commit** .

Sie müssen außerdem mindestens eine Richtlinie für den externen Zugriff zur Unterstützung des Zugriffs durch Partnerbenutzer konfigurieren, damit Partnerbenutzer mit Benutzern in Ihrer Lync Server 2013-Bereitstellung zusammenarbeiten können. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in der Bereitstellungs- oder Betriebsdokumentation. Informationen zur Steuerung des Zugriffs für bestimmte Partnerdomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungs- oder Betriebsdokumentation.

## Aktivieren oder Deaktivieren des Partnerverbunds und der Verbindung mit öffentlichen Chatdiensten mithilfe von Windows PowerShell-Cmdlets

Partnerverbunde und Verbindungen mit öffentlichen Sofortnachrichtendiensten können ebenfalls mithilfe von Windows PowerShell und dem Cmdlet "Set-CsAccessEdgeConfiguration" verwaltet werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876). ausgeführt werden.

## So aktivieren Sie den Partnerverbund und die Verbindung mit öffentlichen Chatdiensten

  - Legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "True" ($True) fest, um den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten zu aktivieren:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## So deaktivieren Sie den Partnerverbund und die Verbindung mit öffentlichen Chatdiensten

  - Legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "False" ($False) fest, um den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten zu deaktivieren:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

