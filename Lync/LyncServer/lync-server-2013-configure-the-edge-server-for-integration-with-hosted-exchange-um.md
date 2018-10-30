---
title: 'Lync Server 2013: Konfigurieren des Edgeservers für die Integration in gehostete Exchange UM-Dienste'
TOCTitle: Konfigurieren des Edgeservers für die Integration in gehostete Exchange UM-Dienste
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399075(v=OCS.15)
ms:contentKeyID: 49295818
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Edgeservers für die Integration in gehostete Exchange UM-Dienste

 

_**Letztes Änderungsdatum des Themas:** 2015-01-23_

Führen Sie auf dem Edgeserver die folgenden Konfigurationsaufgaben aus, um Ihren Lync Server 2013-Benutzern Voicemailfunktionen über einen gehosteten Exchange Unified Messaging (UM)-Dienst bereitzustellen:

  - Konfigurieren Sie den Edgeserver für einen Partnerverbund.

  - Replizieren Sie die Daten des zentralen Verwaltungsspeichers auf den Edgeserver, und überprüfen Sie die Replikation.

  - Erstellen Sie auf dem Edgeserver einen Hostinganbieter.

Ausführliche Informationen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zu den folgenden Cmdlets:

  - [Set-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAccessEdgeConfiguration)

  - [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)


> [!IMPORTANT]
> Vor dem Ausführen dieser Schritte müssen Sie einen externen DNS-SRV-Eintrag zum Hosten des Exchange-Diensts erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste</A>.



## So konfigurieren Sie den Edgeserver für einen Partnerverbund

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsAccessEdgeConfiguration" aus, um den Server für einen Partnerverbund zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **UseDnsSrvRouting** gibt an, dass Edgeserver beim Senden und Empfangen von Partnerverbundanforderungen auf DNS-SRV-Einträge zurückgreifen.
    
      - **AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft legt außerdem fest, ob interne Benutzer mit Benutzern in einem Szenario mit getrennten Domänen kommunizieren können.
    
      - **EnablePartnerDiscovery** gibt an, ob Lync Server DNS-Einträge zur Suche nach Partnerdomänen verwendet, die nicht in der Liste der zulässigen Active Directory-Domänen aufgeführt sind. Bei Festlegung auf "False" erkennt Lync Server 2013 nur Domänen als Partnerdomänen an, die in der Liste der zulässigen Domänen aufgeführt sind. Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich. In den meisten Bereitstellungen ist der Wert auf "False" gesetzt, um einen Partnerverbund mit allen Partnern zu vermeiden.

## So replizieren Sie Daten auf den Edgeserver und überprüfen die Replikation

  - Überprüfen Sie, ob die Replikation auf den Edgeserver vollständig durchgeführt wurde. Informationen zu diesem Verfahren finden Sie unter [Überprüfen der Konnektivität zwischen internen Servern und Edgeservern in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).

## So erstellen Sie auf dem Edgeserver einen Hostinganbieter

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das **New-CsHostingProvider**-Cmdlet aus, um den Hostinganbieter zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen, in diesem Beispiel **Fabrikam.com** . Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True** festgelegt ist.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.
        

        > [!NOTE]
        > Bevor Sie <CODE>EnableSharedAddressSpace</CODE> auf „True“ festlegen, versuchen Sie, den Partnerverbund-SRV-Eintrag intern aufzulösen. Wenn dieser Eintrag intern aufgelöst werden kann, müssen Sie die Einträge _sipfederationtls._tcp.&lt;domain&gt; und _sip._tls.&lt;domain&gt; im internen DNS erstellen. Diese Einträge müssen auf die externe IP-Adresse der Zugriffsschnittstelle des Edgeservers verweisen.

    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Lync Server 2013-Konten verwendet wird. Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an, in diesem Beispiel **proxyserver.fabrikam.com** . Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **IsLocal** gibt an, ob sich der vom Hostinganbieter verwendete Proxyserver in Ihrer Lync Server 2013-Topologie befindet.
    
      - **VerificationLevel** gibt die Überprüfungsstufe an, die für Nachrichten zulässig ist, die an den und vom gehosteten Anbieter gesendet werden. Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden. Wenn diese Stufe nicht angegeben ist, wird die Nachricht als nicht überprüfbar eingestuft und abgelehnt.

## Siehe auch

#### Aufgaben

[Exportieren der Lync Server 2013-Topologie und Kopieren auf externe Medien zur Edgeinstallation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  

#### Konzepte

[Überprüfen der Konnektivität zwischen internen Servern und Edgeservern in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  

#### Weitere Ressourcen

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

