---
title: 'Lync Server 2013: Konfigurieren der lokalen Lync Server-Integration in Exchange Online'
TOCTitle: Konfigurieren der lokalen Lync Server 2013-Integration in Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh533880(v=OCS.15)
ms:contentKeyID: 49294801
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der lokalen Lync Server 2013-Integration in Exchange Online

 

_**Letztes Änderungsdatum des Themas:** 2014-07-02_

Kunden, die lokale Lync Server 2013-Bereitstellungen verwenden, können die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online im Modus der hybriden Bereitstellung konfigurieren. Zu den Interoperabilitätsfeatures gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle. Zur Aktivierung dieser Integration müssen Sie den Edgeserver in der lokalen Lync Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:

  - Konfigurieren eines freigegebenen SIP-Adressraums

  - Konfigurieren eines Hostinganbieters auf dem Edgeserver

  - Überprüfen der Replikation des aktualisierten zentraler Verwaltungsspeichers

## Konfigurieren eines freigegebenen SIP-Adressraums

Zur Integration der lokalen Lync Server 2013-Bereitstellung in Exchange Online müssen Sie einen freigegebenen SIP-Adressraum konfigurieren. Derselbe Adressraum der SIP-Domäne wird sowohl von Lync Server als auch vom Exchange Online-Dienst unterstützt.

Konfigurieren Sie mit der Lync Server-Verwaltungsshell den Edgeserver für den Parnterverbund, indem Sie das **Set-CSAccessEdgeConfiguration**-Cmdlet mit den im folgenden Beispiel angezeigten Parametern ausführen:

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - Der **AllowFederatedUsers**-Parameter gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft legt außerdem fest, ob interne Benutzer mit Benutzern in einem Szenario mit freigegebenen SIP-Adressraum mit Lync Server und Exchange Online kommunizieren können.

Ausführliche Informationen zur Verwendung der Lync Server-Verwaltungsshell finden Sie unter [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

## Konfigurieren eines Hostinganbieters auf dem Edgeserver

Konfigurieren Sie mit der Lync Server-Verwaltungsshell einen Hostinganbieter auf dem Edgeserver, indem Sie das **New-CsHostingProvider**-Cmdlet mit den Parametern aus dem folgenden Beispiel ausführen:

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification


> [!NOTE]
> Sollten Sie Office 365 über 21Vianet in China nutzen, ersetzen Sie den Wert für den Parameter <STRONG>ProxyFqdn</STRONG> in diesem Beispiel ("exap.um.outlook.com") durch FQDN den Dienst, der in China von 21Vianet bereitgestellt wird: "exap.um.partner.outlook.cn".



  - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen (beispielsweise "Exchange Online"). Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.

  - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf TRUE festgelegt werden.

  - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf TRUE festgelegt werden.

  - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder Lync Server verwendet wird. Dieser Parameter muss auf FALSE festgelegt werden.

  - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Für Exchange Online ist der FQDN "exap.um.outlook.com".

  - **IsLocal** gibt an, ob sich der vom Hostinganbieter verwendete Proxyserver in Ihrer Lync Server-Topologie befindet. Dieser Parameter muss auf FALSE festgelegt werden.

  - **VerificationLevel** gibt die Überprüfungsstufe an, die für Nachrichten zulässig ist, die an den und vom gehosteten Anbieter gesendet werden. Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden. Wenn diese Stufe nicht angegeben ist, wird die Nachricht als nicht überprüfbar eingestuft und abgelehnt.

## Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Die Änderungen, die Sie mit den Cmdlets aus den vorherigen Abschnitten vorgenommen haben, werden automatisch für den Edgeserver übernommen, und die Replikation dauert im Allgemeinen weniger als eine Minute. Mit den folgenden Cmdlets können Sie den Replikationsstatus überprüfen und dann bestätigen, dass die Änderungen für den Edgeserver übernommen wurden.

Führen Sie das folgende Cmdlet aus, um die Replikationsaktualisierungen auf einem Server in der Lync Server-Bereitstellung zu überprüfen:

    Get-CsManagementStoreReplicationStatus

Führen Sie auf dem Edgeserver das folgende Cmdlet aus, um zu bestätigen, dass die Änderungen übernommen wurden:

    Get-CsHostingProvider -LocalStore

## Siehe auch

#### Weitere Ressourcen

[Bereitstellen von Voicemail für Benutzer von Lync Server 2013 für gehostete Exchange Unified Messaging-Dienste](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Integration in gehostete Exchange Unified Messaging-Dienste in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)

