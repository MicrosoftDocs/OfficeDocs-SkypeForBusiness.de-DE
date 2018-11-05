---
title: 'Lync Server 2013: Konfigurieren der Anrufsteuerung'
TOCTitle: Konfigurieren der Anrufsteuerung
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398870(v=OCS.15)
ms:contentKeyID: 49295442
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Bei der Anrufsteuerung (Call Admission Control, CAC) handelt es sich um eine Lösung, die basierend auf der verfügbaren Bandbreite bestimmt, ob eine Echtzeitsitzung hergestellt werden kann. Auf diese Weise lässt sich schlechte Audio/Videoübertragungsqualität für Benutzer in überlasteten Netzwerken verhindern. Die Anrufsteuerung steuert den Echtzeitdatenverkehr nur für Audio- und Videodaten und hat keinen Einfluss auf anderen Datenverkehr. Wenn der standardmäßige WAN-Pfad nicht über die erforderliche Bandbreite verfügt, leitet die Anrufsteuerung den Anruf möglicherweise über einen Internetpfad. Ausführliche Informationen finden Sie unter [Planen des Anrufsteuerungsdiensts in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.

In diesem Abschnitt werden Beispielverfahren bereitgestellt, um die Bereitstellung und Verwaltung der Anrufsteuerung in Ihrem Netzwerk zu veranschaulichen.


> [!IMPORTANT]
> Bevor Sie die Anrufsteuerung bereitstellen, müssen Sie alle erforderlichen Informationen für Ihre Unternehmensnetzwerktopologie sammeln, wie unter <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013</A> in der Planungsdokumentation beschrieben. Stellen Sie auch sicher, dass die Anrufsteuerungskomponenten installiert und aktiviert wurden. Eine Beschreibung der erforderlichen Schritte finden Sie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013</A> in der Bereitstellungsdokumentation.




> [!NOTE]
> Alle Beispiele für die Bereitstellung und Verwaltung der Anrufsteuerung in diesem Abschnitt werden unter Verwendung der Lync Server-Verwaltungsshell ausgeführt. Alternativ dazu können Sie auch den Abschnitt <STRONG>Netzwerkkonfiguration</STRONG> der Lync Server-Systemsteuerung verwenden, um die Anrufsteuerung zu verwalten.



## In diesem Abschnitt

  - [Konfigurieren von Netzwerkregionen für die Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Erstellen von Bandbreitenrichtlinienprofilen in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Zuordnen von Subnetzen zu Netzwerkstandorten für die Anrufsteuerung in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Erstellen von Netzwerkregionenverbindungen in Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Erstellen von regionenübergreifenden Netzwerkrouten in Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Erstellen von standortübergreifenden Netzwerkrichtlinien in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Aktivieren der Anrufsteuerung in Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Prüfliste für die Bereitstellung der Anrufsteuerung für Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

