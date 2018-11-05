---
title: 'Lync Server 2013: Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers – Aufgaben am zentralen Standort'
TOCTitle: Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers – Aufgaben am zentralen Standort
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398189(v=OCS.15)
ms:contentKeyID: 49293193
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am zentralen Standort

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Führen Sie die Aufgaben in diesem Abschnitt am zentralen Standort aus. Wenn Sie einen Survivable Branch-Server bereitstellen, überspringen Sie die erste Aufgabe.


> [!IMPORTANT]
> Stellen Sie vor dem Ausführen der Aufgaben in diesem Abschnitt sicher, dass die folgenden Bedingungen erfüllt sind: 
> <UL>
> <LI>
> <P>Lync Server muss am zentralen Standort eingerichtet sein.</P>
> <LI>
> <P>Am Zweigstellenstandort wurde der Gruppe "RTCUniversalSBATechnicians" ein Installationstechniker hinzugefügt.</P></LI></UL>Zusätzlich wird die Ausführung der folgenden Aufgaben empfohlen: 
> <UL>
> <LI>
> <P>Bereitstellen eines DHCP-Servers an jedem Zweigstellenstandort, um Clients das Anfordern von IP-Adressen zu ermöglichen.</P>
> <LI>
> <P>Als Alternative zum Bereitstellen eines DHCP-Servers an jedem Zweigstellenstandort können Sie Lync Server DHCP auf der Survivable Branch-Anwendung oder dem Survivable Branch-Server aktivieren, indem Sie das Lync Server-Verwaltungsshell-Cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG> ausführen. Ausführliche Informationen finden Sie im Abschnitt zu den Hardware- und Softwareanforderungen unter <A href="lync-server-2013-branch-site-resiliency-requirements.md">Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013</A> in der Planungsdokumentation.</P></LI></UL>



## In diesem Abschnitt

  - [Hinzufügen einer Survivable Branch Appliance zu Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Hinzufügen von Zweigstellenstandorten zur Topologie in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

