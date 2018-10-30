---
title: Konfigurieren der Unterstützung für die AutoErmittlung
TOCTitle: Konfigurieren der Unterstützung für die AutoErmittlung
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945622(v=OCS.15)
ms:contentKeyID: 52056328
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Unterstützung für die AutoErmittlung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Der Lync Server-Webdienst **AutoErmittlungsdienst** war zuerst mit dem kumulativen Lync Server 2010-Update: November 2011 verfügbar. Dieses Update erfolgte gleichzeitig mit der Erstveröffentlichung von Lync Mobile-Clients. Mit dem AutoErmittlungsdienst wurden die als "Mcx-Dienst" bekannten Mobilitätsdienste verfügbar gemacht.

Der AutoErmittlungsdienst fungiert als zentraler Ort für alle Clients zum Abfragen von Informationen zu verfügbaren Diensten und Features sowie zum Kontaktieren der Dienste – entweder über einen vollqualifizierten Domänennamen oder den Verweis auf eine Web-URL. Die AutoErmittlung stellt eine Reihe von Features bereit, und jeder Client stellt Anforderungen basierend auf den Features, die er verwenden kann. Ein Lync 2013-Desktopclient verwendet die AutoErmittlung z. B. zum Bestimmen der externen Webdienste, verwendet jedoch nicht die Mobilitätsdienste (Mcx). Zum ordnungsgemäßen Definieren und Aktivieren Ihrer Clients für die Verwendung der verfügbaren Features sollten die Szenarien definiert werden, die es einem Client ermöglichen, AutoErmittlungseinträge effektiv zu identifizieren und zu nutzen. Für die Verwendung der AutoErmittlung erfordert Ihre Bereitstellung, dass ein Reverseproxy die Lync Server-Webdienste veröffentlicht, das DNS-Einträge für das Auflösen von DNS-Abfragen für den Lync Server-AutoErmittlungsdienst und die Lync Server-Webdienste konfiguriert sind, sowie dass Zertifikatdienste ordnungsgemäß für Ihr bestimmtes Szenario konfiguriert sind.


> [!TIP]
> Technische Details zu den Funktionen der Elemente in den AutoErmittlungs-Anfragen/Antworten finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Grundlegendes zur AutoErmittlung</A>.



In den folgenden Informationen und Tabellen wird szenarioabhängig angegeben, welche Konfigurationen Sie ggf. implementieren müssen, um die vollständige und effektive Verwendung des AutoErmittlungsdiensts bereitzustellen. Die Informationen in den folgenden Themen beziehen sich auf Microsoft Lync Server 2013. Anweisungen zur Planung der Mobilität für Lync Server 2010 finden Sie unter <http://go.microsoft.com/fwlink/?linkid=275113>. Informationen zur Bereitstellung der Mobilität für Lync Server 2010 finden Sie unter <http://go.microsoft.com/fwlink/?linkid=275114>

## In diesem Abschnitt

  - [Konfigurieren von DNS für die AutoErmittlung](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Konfigurieren von Zertifikaten für die AutoErmittlung](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Konfigurieren eines Reverseproxys für die AutoErmittlung](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Konfigurieren der AutoErmittlung für Hybridbereitstellungen](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

