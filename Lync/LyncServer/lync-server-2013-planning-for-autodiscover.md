---
title: Planen der AutoErmittlung in Lync Server 2013
TOCTitle: Planen der AutoErmittlung in Lync Server 2013
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945628(v=OCS.15)
ms:contentKeyID: 52056335
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen der AutoErmittlung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-16_

Die AutoErmittlung wurde für Lync Server mit dem kumulativen Update für Lync Server 2010: November 2011 eingeführt. Der Hauptzweck dieser Erstimplementierung der AutoErmittlung bestand in der Bereitstellung einer Methode für Lync Mobile zum Identifizieren des Mobilitätsdiensts (Mcx). Der AutoErmittlungsdienst in Lync Server 2013 ist mittlerweile ein Dienst, der von allen Clients zum Identifizieren von Server- und Benutzerdiensten verwendet wird. Der AutoErmittlungsdienst von Microsoft Lync Server 2013 wird auf Directors und Front-End-Server ausgeführt.


> [!TIP]
> Weitere technische Informationen zur AutoErmittlung und der Kommunikation an Clients finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Grundlegendes zur AutoErmittlung</A>.<BR>Bei der Mobilität handelt es sich noch um ein eigenständiges Szenario und die Mobilitätsdienste erfordern individuelle Planung. Zusätzliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in Lync Server&nbsp;2013</A>.



Als die AutoErmittlung in Lync Server 2010 eingeführt wurde, mussten Kompromisse geschlossen werden, um einen Dienst zu implementieren, der u. U. Zertifikatänderungen an vorhandenen Serverbereitstellungen erfordert. Die AutoErmittlung konnte über Port TCP 443 für HTTPS oder über Port TCP 80 für HTTP verwendet werden. Bei der Verwendung von HTTPS mussten Zertifikate auf Reverseproxys, Directors und Front-End-Serverm erneut ausgestellt werden, um die erforderlichen DNS-Einträge `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` zu speichern. Bei der Verwendung von HTTP konnte das erneute Ausstellen von Zertifikaten umgangen werden, indem DNS-CNAME (oder Alias)-Einträge verwendet wurden, um vorhandene Namen auf den Zertifikaten beizubehalten. Bei der Verwendung von HTTP war die erste Kommunikation jedoch unverschlüsselt.

Das Lync Server 2013 die AutoErmittlung für alle Clients verwendet, sieht das Hauptszenario die ausschließliche Verwendung von HTTPS sowie die Erstellung von Zertifikaten mit "lyncdiscover.\<domain\>" als Teil der Konfiguration von Reverseproxys, Directors und Front-End-Servern vor. Wenn Sie die AutoErmittlung in eine Bereitstellung von Lync Server 2010 implementieren, sollten Sie HTTP verwenden, um das erneute Ausstellen von Zertifikaten zu umgehen. Anleitungen für beide Szenarien werden in den folgenden Abschnitten bereitgestellt.


> [!IMPORTANT]
> Die Liste der alternativen Antragstellernamen auf Zertifikaten, die von der Veröffentlichungsregel für externe Webdienste verwendet wird, muss den Eintrag <EM>lyncdiscover.&lt;sipdomain&gt;</EM> für jede SIP-Domäne innerhalb Ihrer Organisation enthalten. Ausführliche Informationen zu den erforderlichen Einträgen alternativer Antragstellernamen für Directors, Front-End-Server und Reverseproxys finden Sie unter <A href="lync-server-2013-certificate-summary-autodiscover.md">Zertifikatübersicht – AutoErmittlung</A>.



## In diesem Abschnitt

  - [Zertifikatübersicht – AutoErmittlung](lync-server-2013-certificate-summary-autodiscover.md)

  - [Portübersicht – AutoErmittlung in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [DNS-Zusammenfassung – AutoErmittlung in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Hybriddomäne oder geteilte Domäne – AutoErmittlung](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

