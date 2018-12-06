---
title: 'Lync Server 2013: Routing zwischen Trunks'
TOCTitle: Routing zwischen Trunks
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205272(v=OCS.15)
ms:contentKeyID: 49295508
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routing zwischen Trunks in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Lync Server 2013 kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) verbinden, damit Anrufe von einer Nebenstellenanlage (Private Branch Exchange, PBX) an das PSTN-Gateway sowie eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. Entsprechend kann Lync Server 2013 zwei oder mehr IP-Nebenstellensysteme (IP-PBX-Systeme) miteinander verbinden, damit Anrufe zwischen Nebenstellentelefonen in den verschiedenen IP-Nebenstellensystemen getätigt und angenommen werden können.

Dieses Feature für das Intertrunk-Routing kann mithilfe des Lync Server-Verwaltungsshell-Cmdlets **Set-CsTrunkConfiguration** und dem neuen PstnUsages -Parameter konfiguriert werden. Mit diesem Parameter werden die zu verwendenden PSTN-Verwendungseinträge angegeben. Ein Trunk bestimmt mithilfe dieser PSTN-Verwendung eine Route und leitet alle eingehenden Anrufe entsprechend weiter.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

Das folgende Diagramm veranschaulicht, wie Lync Server 2013 eine Verbindung zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage herstellt.

**Intertrunk-Routing zwischen Gateway und IP-Nebenstellenanlage**

![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)")

Das folgende Diagramm veranschaulicht, wie Lync Server 2013 eine Verbindung zwischen zwei IP-Nebenstellensystemen herstellt.

**Intertrunk-Routing zwischen zwei IP-Nebenstellenanlagen**

![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)")

