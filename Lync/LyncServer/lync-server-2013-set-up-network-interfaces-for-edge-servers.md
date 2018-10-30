---
title: 'Lync Server 2013: Einrichten von Netzwerkschnittstellen für Edgeserver'
TOCTitle: Einrichten von Netzwerkschnittstellen für Edgeserver
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412847(v=OCS.15)
ms:contentKeyID: 49295110
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten von Netzwerkschnittstellen für Edgeserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Bei jedem Edgeserver handelt es sich um einen mehrfach vernetzten Computer mit externen und internen Schnittstellen. Die DNS-Einstellungen (Domain Name System) des Netzwerkadapters richten sich danach, ob im Umkreisnetzwerk DNS-Server vorhanden sind. Wenn im Umkreisnetzwerk DNS-Server vorhanden sind, müssen diese über eine Zone mit mindestens einem DNS-A-Eintrag für den Server oder Pool für den nächsten Hop verfügen (hierbei handelt es sich entweder um einen Director oder einen festgelegten Front-End-Pool). Für externe Abfragen werden Namelookups über andere öffentliche DNS-Server durchgeführt. Wenn im Umkreisnetzwerk keine DNS-Server vorhanden sind, verwenden der oder die Edgeserver externe DNS-Server zur Durchführung von Namelookups im Internet, und jeder Edgeserver verwendet eine HOST-Datei, um die Namen der Server für den nächsten Hop in IP-Adressen aufzulösen.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Sicherheit Hinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aus Sicherheitsgründen wird empfohlen, dass die Edgeserver nicht auf einen DNS-Server zugreifen können, der sich im internen Netzwerk befindet.</td>
</tr>
</tbody>
</table>


## So konfigurieren Sie Schnittstellen mit DNS-Servern im Umkreisnetzwerk

1.  Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne und einen für die externe Schnittstelle.
    

    > [!IMPORTANT]
    > Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein.



2.  Konfigurieren Sie für die externe Schnittstelle drei statische IP-Adressen im externen Subnetz des Umkreisnetzwerks (auch als überwachtes Subnetz bezeichnet), und verweisen Sie das Standardgateway auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters, sodass diese auf ein DNS-Umkreisserverpaar verweisen.
    

    > [!NOTE]
    > Es ist möglich, für diese Schnittstelle nur eine einzige IP-Adresse zu verwenden, hierfür müssen Sie allerdings die Portzuweisungen in nicht standardmäßige Werte ändern. Dies wird beim Erstellen der Topologie im Topologie-Generator festgelegt.



3.  Konfigurieren Sie in der internen Schnittstelle eine statische IP-Adresse im internen Subnetz des Umkreisnetzwerks, und geben Sie kein Standardgateway an. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters, sodass diese mindestens auf einen DNS-Server, jedoch vorzugsweise auf ein DNS-Umkreisserverpaar verweisen.

4.  Erstellen Sie in der internen Schnittstelle dauerhafte statische Routen zu allen internen Netzwerken, in denen sich Clients, Lync Server 2013-Server und Exchange UM-Server befinden.

## Konfigurieren von Schnittstellen ohne DNS-Server im Umkreisnetzwerk

1.  Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne und einen für die externe Schnittstelle.
    

    > [!IMPORTANT]
    > Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein.



2.  Konfigurieren Sie in der externen Schnittstelle drei statische IP-Adressen im externen Subnetz des Umkreisnetzwerks. Sie konfigurieren zudem das Standardgateway auf der externen Schnittstelle. Definieren Sie beispielsweise den Internetrouter oder die externe Firewall als Standardgateway. Konfigurieren Sie die DNS-Einstellungen, sodass diese auf einen DNS-Server, jedoch vorzugsweise auf ein externes DNS-Serverpaar verweisen.
    

    > [!NOTE]
    > Es ist möglich, jedoch nicht empfehlenswert, für die externe Schnittstelle nur eine einzige IP-Adresse zu verwenden. Hierfür müssen Sie allerdings die Portzuweisungen in nicht standardmäßige Werte ändern und sich vom Standardport 443 wegbewegen, der gewöhnlich "firewallfreundlich" für die Clientkonfiguration ist. Sie bestimmen die IP-Adresseneinstellung und die Porteinstellungen, wenn Sie die Topologie im Topologie-Generator erstellen.



3.  Konfigurieren Sie in der internen Schnittstelle eine statische IP-Adresse im internen Subnetz des Umkreisnetzwerks, und geben Sie kein Standardgateway an. Lassen Sie die DNS-Einstellungen des Netzwerkadapters leer.

4.  Erstellen Sie für die interne Schnittstelle dauerhafte statische Routen zu allen internen Netzwerken, in denen sich Lync-Clients oder Server, die Lync Server 2013 ausführen, befinden.

5.  Fügen Sie einen Eintrag für den Server für den nächsten Hop oder eine virtuelle IP (VIP) in die HOST-Datei auf jedem Edgeserver ein (bei diesem Eintrag handelt es sich um einen Director, Standard Edition-Server oder Front-End-Pool, der im Topologie-Generator als Adresse für den nächsten Hop des Edgeservers konfiguriert wurde). Wenn Sie den DNS-Lastenausgleich verwenden, fügen Sie eine Zeile für jedes Mitglied im Pool für den nächsten Hop ein.

