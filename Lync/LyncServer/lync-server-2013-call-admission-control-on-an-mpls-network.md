---
title: 'Lync Server 2013: Anrufsteuerung in einem MPLS-Netzwerk'
TOCTitle: Anrufsteuerung in einem MPLS-Netzwerk
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398168(v=OCS.15)
ms:contentKeyID: 49293147
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anrufsteuerung in einem MPLS-Netzwerk mit Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

In einem MPLS-Netzwerk (Multiprotocol Label Switching) sind alle Standorte vollständig miteinander vernetzt, d. h. alle Standorte sind direkt mit dem MPLS-Backbone des Internetdienstanbieters verbunden, und jedem Standort wird Bandbreite für eine WAN-Verbindung mit der MPLS-Cloud zur Verfügung gestellt. Es ist kein Netzwerkhub oder zentraler Standort zur Steuerung des IP-Routings vorhanden. Die folgende Abbildung zeigt ein einfaches Beispiel für ein auf der MPLS-Technologie basierendes Netzwerk.

**Beispiel eines MPLS-Netzwerks**

![Anrufsteuerung mit MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "Anrufsteuerung mit MPLS")

Zur Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) in einem MPLS-Netzwerk erstellen Sie eine Netzwerkregion für die MPLS-Cloud und Netzwerkstandorte für jeden MPLS-Zweigstellenstandort. Die folgende Abbildung zeigt, wie Netzwerkregion und Netzwerkstandorte konfiguriert sein sollten, um das MPLS-Beispielnetzwerk aus der oben stehenden Abbildung darzustellen. Die Bandbreitenbeschränkungen insgesamt sowie die Bandbreitenbeschränkung pro Sitzung basieren auf der Kapazität der WAN-Verbindung zwischen jedem Netzwerkstandort und der Netzwerkregion, welche die MPLS-Cloud darstellt.

**Netzwerkregion und Netzwerkstandorte für ein MPLS-Netzwerk**

![Anrufsteuerung mit MPLS (Diagramm)](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Anrufsteuerung mit MPLS (Diagramm)")

